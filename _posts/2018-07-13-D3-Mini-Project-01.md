---
layout: post
title: "D3 Mini-Project: Convex Hull"
date: 2018-07-13
categories: DataViz
tags: [Javascript]
---

Take a look at a recent mini-project I have been playing with.

A number of things recently converged to prompt me to create a mini project to sharpen some skills.

I used D3 during the Data Science bootcamp.  I was the first to take advantage of it.  But during a
recent technical interview, someone asked me how to do a particular thing in Javascript.  My answer
was truthful, yet likely unsatisfactory.  I simply stated I wouldn't have done that part in Javascript,
but in Python and then feed that into Javascript.  That could be as straightforward as creating an
appropriate Flask-based REST API.  Later upon researching this idea, I'm actually more confident on
this point.  It's not just that I only know to do it that way.  It may be important to do it that way
for security purposes.

But that got me thinking that I really do need to become a polyglot and know how to do a variety of
things in different ways using different languages.  Around the same time, I came aross an SQL challenge
on the CodeSignal (formerly CodeFight) site.  The challenge expected you to use a hard-coded specific
function to calculate the area of a [convex hull](https://www.geeksforgeeks.org/convex-hull-set-2-graham-scan/).
During the bootcamp David suggested to us that one way to learn something is to code it by yourself
from scratch.  For some reason I had just recently reviewed the idea or concept that SQL was elevated
to become an imperative language despite starting out strictly as a declarative language.  Furthermore,
not only did SQL have standard functions for this, so too does the Python stack (in scipy).  I wanted
to see how best to do this using numpy and pandas without scipy.

After getting Convex Hull working in procedural SQL and python, I decided to create a visualization to
demonstrate or show the methodology of the Graham algortihm to determine the Convex Hull given a series
of points.

This is somewhat of a work-in-progress.  I want to circle back here and polish things up a bit and then
show the way area is calculated after the convex hull has been determined.  But here it is...

NOTE: I've not yet included buttons or a mechanism to restart or pause the demo.  If you didn't catch
it just refresh the page while you have the chart on screen.

<iframe class="fragment fade-in" style="float:center" width="800" height="800" src="/assets/html/mini_001/c_002.html"></iframe>

SQL code follows.  Keep in mind the "proper" way to do this involves a standard function and takes about three or four
lines.  But here's what I used for the CodeSignal submission (which uses MySQL and calls the habitatArea procedure.

```sql

CREATE FUNCTION orientation() RETURNS INT NOT DETERMINISTIC
BEGIN
    -- treats the pS table as a stack
    DECLARE a_x FLOAT; DECLARE a_y FLOAT;
    DECLARE b_x FLOAT; DECLARE b_y FLOAT;
    DECLARE c_x FLOAT; DECLARE c_y FLOAT;
    DECLARE o FLOAT;
    SELECT p.x, p.y INTO c_x, c_y
        FROM pS p ORDER BY p.rn DESC LIMIT 1;
    SELECT p.x, p.y INTO b_x, b_y
        FROM pS p ORDER BY p.rn DESC LIMIT 1 OFFSET 1;
    SELECT p.x, p.y INTO a_x, a_y
        FROM pS p ORDER BY p.rn DESC LIMIT 1 OFFSET 2;
    SET o = (b_y - a_y)*(c_x - b_x) - (c_y - b_y)*(b_x - a_x); 
    RETURN(CASE
        WHEN o < 0 THEN -1 
        WHEN o > 0 THEN  1 
        ELSE 0
    END);
END;


CREATE PROCEDURE habitatArea()
BEGIN

    -- Select bottommost, leftmost place
    DROP TABLE IF EXISTS p0;
    CREATE TEMPORARY TABLE p0 AS (
        SELECT * FROM places
        ORDER BY y,x
        LIMIT 1
    );
    
    -- Select and order remaining places by angle (going CCW)
    DROP TABLE IF EXISTS pR;
    SET @row_number = 0;
    CREATE TEMPORARY TABLE pR AS (
        SELECT p.x, p.y,
               -- Calculate slope as proxy for angle
               acos((p.x - o.x)/
                   sqrt((p.y - o.y)*(p.y - o.y) +
                   (p.x - o.x)*(p.x - o.x))
               ) angle,
               -- Need distance later on...
               sqrt((p.y - o.y)*(p.y - o.y) +
               (p.x - o.x)*(p.x - o.x)) dist
        FROM (
            SELECT *, (@row_number:=@row_number+1) rn
            FROM places
            ORDER BY y,x
        ) p
        CROSS JOIN p0 o
        WHERE p.rn > 1
        ORDER BY angle, dist
    );
    
    -- Choose furthest point along any given angle
    DROP TABLE IF EXISTS pR2;
    CREATE TEMPORARY TABLE pR2 AS (SELECT * FROM pR);
    DROP TABLE IF EXISTS pC;
    SET @row_number = 0;
    CREATE TEMPORARY TABLE pC AS (
        SELECT o.x, o.y,
            (@row_number:=@row_number+1) rn
        FROM (
            SELECT pR.*
            FROM pR, (
                SELECT angle, MAX(dist) dist
                FROM pR2
                GROUP BY angle
            ) g
            WHERE g.angle = pR.angle and g.dist = pR.dist
        ) o
        ORDER BY angle
    );
    
    -- Iterate over candidates to determine perimeter...
    DROP TABLE IF EXISTS pS;
    CREATE TEMPORARY TABLE pS AS (
        SELECT x, y, 0 rn
        FROM p0
    );
    -- TODO: Length check on pC
    INSERT INTO pS
        SELECT * FROM pC ORDER BY rn LIMIT 2;
    DELETE FROM pC ORDER BY rn LIMIT 2;
    WHILE (EXISTS (SELECT 1 FROM pC)) DO
        -- Add a new point on the stack
        INSERT INTO pS
            SELECT * FROM pC ORDER BY rn LIMIT 1;
        DELETE FROM pC ORDER BY rn LIMIT 1;
        -- Clean the stack
        WHILE (orientation() <> -1) DO
            SET @row_number:=(
                    SELECT rn
                    FROM pS ORDER BY rn DESC LIMIT 1 OFFSET 1
                ); 
            DELETE FROM pS WHERE rn = @row_number;
        END WHILE;
    END WHILE;
    ALTER TABLE pS ADD i INT;
    SET @points:=-1;
    UPDATE pS
    SET i=@points:=@points+1;
    SET @points:=@points+1;
    
    -- Calculate the area from the perimeter stored in pS
    DROP TABLE IF EXISTS pS2;
    CREATE TEMPORARY TABLE pS2 AS (SELECT * FROM pS);
    DROP TABLE IF EXISTS pS3;
    CREATE TEMPORARY TABLE pS3 AS (SELECT * FROM pS);
    DROP TABLE IF EXISTS pA;
    CREATE TEMPORARY TABLE pA AS (
        SELECT pS.x, down.y dy, up.y uy, pS.i
        FROM pS
        JOIN pS2 down
        -- hack 'cause SQL mod returns negative numbers
        ON mod(@points+mod(pS.i-1,@points),@points) = down.i
        JOIN pS3 up
        ON mod(pS.i+1,@points) = up.i
        ORDER BY i
    );
    SET @area = (SELECT (SUM(x * (uy - dy))/2.0) area FROM pA);
    IF MOD(@area,1) THEN
        SELECT TRIM(TRAILING '0' FROM @area) area;
    ELSE
        SELECT ROUND(@area) area;
    END IF;
    
END


```

