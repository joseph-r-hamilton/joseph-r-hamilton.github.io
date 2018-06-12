---
title: Investigation: Docker
description: Web presentation on Docker
date: 2018-02-05
layout: slide
theme: serif
transition: cube
center: false
---


<style>
.reveal h1 h2 h3{
text-align: center;
}
.reveal p{
text-align: left;
}
.reveal .leftol{
display: block;
}
</style>


<section>
<h1 class="fragment fade-down">Docker</h1>
<img class="fragment fade-in" alt="chart" width="80%" src="/assets/img/slides/Docker/docker.png">
</section>
<section>
<h1><small>Agenda</small></h1>
<ul>
<li class="fragment">History
<ul>
<li>Virtualization</li>
<li>Containers</li>
<li>Docker</li>
</ul>
</li>
<li class="fragment">Use Case (and concerns)</li>
<li class="fragment">Architecture</li>
<li class="fragment">Demos</li>
</ul>
</section>
<section>
<h1><small>Ancient History</small></h1>
<ul>
<li class="fragment">Long, long ago there was <bold>chroot</bold>.</li>
<li class="fragment">Not quite so long ago there was dual-boot...<br/>and multi-boot.</li>
<li class="fragment">Eventually, we had virtualization.</li>
<li class="fragment">But, full blown virtual machines can be space hogs.</li>
</ul>
</section>
<section>
<h1><small>Virtual Machines</small></h1>
<img alt="chart" width="50%" src="/assets/img/slides/Docker/vm.png">
</section>
<section>
<h1><small>Evolution to Containers</small></h1>
<ul>
<li class="fragment">But if on one host we have many co-located VMs, it seems really wasteful to have so many copies of that guest OS.</li>
<li class="fragment">Furthermore, if the guest OS is the same as the host OS, why do we need ANY copy?  Isn't most of it the same?</li>
<li class="fragment">Different OS's started to address this in slightly different ways.</li>
</ul>
</section>
<section>
<h1><small>Containers</small></h1>
<ul>
<li class="fragment">FreeBSD created "jails".</li>
<li class="fragment">Solaris (and variants) gave us "zones".  And "ZFS" deduplication addressed the storage issue.</li>
<li class="fragment">Linux created "containers" (a couple kinds actually).</li>
<li class="fragment">All of these are like VM solutions but where the host and guest are the same thing.</li>
</ul>
</section>
<section>
<h3>Recap</h3>
<img alt="chart" width="100%" src="/assets/img/slides/Docker/brief_history.jpg"/>
</section>
<section>
<h1><small>Union File System</small></h1>
<ul>
<li class="fragment">Several Linux Container solution(s) took advantage of another innovation:<br/>Union File System.</li>
<li class="fragment">The idea here is to have a read-only file system "underneath" a writable file system".</li>
<li class="fragment">Any file operation that "reads" looks at the top layer first.</li>
<li class="fragment">Writes only occur at the top layer.</li>
<li class="fragment">You can have several read-only layers stacked.</li>
</ul>
</section>
<section>
<h1><small>on to Docker</small></h1>
<ul>
<li class="fragment">Docker grew out of LXC and UFS</li>
<li class="fragment">Docker provided a layered system architecture based on UFS</li>
<li class="fragment">Docker became very popular because it introduced a repository system for containers like GitHub</li>
<li class="fragment">Docker containers differ from Virtual Machines and general containers in that (for the most part) a Docker container is just one app.</li>
</ul>
</section>
<section>
<h1><small>Docker grows to<br/>non-Linux</small></h1>
<ul>
<li class="fragment">A host OS can run a guest container if it has the core of the guest OS builtin.</li>
<li class="fragment">Solaris did this supporting CentOS (Linux) in its Zones.</li>
<li class="fragment">Now, both Windows and MaxOS support Docker.</li>
</ul>
</section>
<section>
<h1><small>Why use Docker</small></h1>
<ul>
<li class="fragment">Speed of Implementation.  The Docker Ecosystem may already have the app you need, preconfigured and ready to deploy almost immediately.</li>
<li class="fragment">Ease of extending.  You can take a container, build upon it and create your own template for future containers.</li>
<li class="fragment">Segmentation of Concerns.  An update or removal of one app doesn't force you to endure "Dependency Hell".</li>
</ul>
</section>
<section>
<h1><small>When to avoid Docker</small></h1>
<ul>
<li class="fragment">Security.</li>
<li class="fragment">GUI (eg. X11)</li>
</ul>
</section>
<section>
<h1><small>Docker Architecture</small></h1>
<ul>
<li class="fragment">Images</li>
<li class="fragment">Containers</li>
</ul>
</section>

<section>
<section>
<h2>Docker Demo</h2>
<h4>(on Local Machine)</h4>
<iframe width="100%" height="450" src="http://localhost:4200"></iframe>
</section>
<section>
<h2>Demo Steps</h2>
<ul>
<li>Install: pacman -S docker</li>
<li>Start daemon: systemctl start docker</li>
<li>Fetch, install and run server (all in one step)</li>
<li>Run client</li>
</ul>
</section>
<section>
<h4>Search Docker Hub</h4>
<ul>
<li>Go to  <a href="https://hub.docker.com" data-preview-link>https://hub.docker.com</a></li>
<li>for  <a href="https://hub.docker.com/r/_/postgres/" data-preview-link>Postgresql (server)</a></li>
</ul>
</section>
</section>
<section>
<h2>Additional Topics</h2>
<ul>
<li>Virtual Networking</li>
<li>Using images to "snapshot" a container.</li>
<li>Ferry</li>
<li>Docker within Docker</li>
</ul>
</section>

