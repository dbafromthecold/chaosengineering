# Chaos Engineering

---

## Andrew Pruski

<img src="images/apruski.jpg" style="float: right"/>

### Field Solutions Architect
#### Microsoft Data Platform MVP 
#### Docker Captain
#### VMware vExpert

<!-- .slide: style="text-align: left;"> -->
<i class="fa-brands fa-bluesky"></i><a href="https://bsky.app/profile/dbafromthecold.com">  @dbafromthecold.com</a><br>
<i class="fas fa-envelope"></i>  dbafromthecold@gmail.com<br>
<i class="fab fa-wordpress"></i>  www.dbafromthecold.com<br>
<i class="fab fa-github"></i><a href="https://github.com/dbafromthecold">  github.com/dbafromthecold</a>

---

### Session Aim
<!-- .slide: style="text-align: left;"> -->
An overview of Chaos Engineering and how it can be applied

<p align="center">
<img src="images/chaos.gif"/>
</p>

---

# Chaos Engineering?

---

### What is Chaos Engineering?
<!-- .slide: style="text-align: left;"> -->
"Chaos Engineering is the discipline of experimenting on a system in order to build confidence in the system's capability to withstand turbulent conditions in production"<br>
<font size="6"><a href="principlesofchaos.org">principlesofchaos.org</a></font>

---

### What Chaos Engineering is not!
<!-- .slide: style="text-align: left;"> -->
<ul>
<li class="fragment">Breaking things in production!</li>
<li class="fragment">Staging or Production?</li>
<ul>

---

# Chaos Engineering Implementations

---

### Netflix - Chaos Monkey
<!-- .slide: style="text-align: left;"> -->
<img src="images/chaosmonkey.png" style="float: right"/>

"Chaos Monkey is responsible for randomly terminating instances in production to ensure that engineers implement their services to be resilient to instance failures"<br>
<font size="6"><a href="netflix.github.io/chaosmonkey/">netflix.github.io/chaosmonkey</a></font>

---

### Other Implementations
<!-- .slide: style="text-align: left;"> -->
<i class="fab fa-slack"></i><b> Slack - Disasterpiece Theatre</b>

<span style="display: inline-block; width: 2ch;">&#9;</span><font size="6">- Planned failure exercises</font><br>
<span style="display: inline-block; width: 2ch;">&#9;</span><font size="6">- Group of engineers working together</font><br>
<span style="display: inline-block; width: 2ch;">&#9;</span><font size="6">- Run in development then production to build confidence</font>

<i class="fab fa-google"></i><b> Google - DiRT</b>

<span style="display: inline-block; width: 2ch;">&#9;</span><font size="6">- Disaster recovery testing</font><br>
<span style="display: inline-block; width: 2ch;">&#9;</span><font size="6">- "Hope is not a strategy" - SRE Team motto</font><br>
<span style="display: inline-block; width: 2ch;">&#9;</span><font size="6">- Automated and manual tests</font><br>
<span style="display: inline-block; width: 2ch;">&#9;</span><font size="6">- Controlled Chaos</font>

---

# Getting Started

---

### Environment Analysis

<!-- .slide: style="text-align: left;"> -->
<ul>
<li class="fragment">Infrastructure</li>
    <ul>
        <li class="fragment">Cloud, private data centre?</li>
    </ul>
<li class="fragment">Applications</li>
    <ul>
        <li class="fragment">What's hitting our SQL instances?</li>
    </ul>
<li class="fragment">Monitoring</li>
    <ul>
        <li class="fragment">How are we going to analyse the results of our experiments?</li>
    </ul>
<li class="fragment">Social</li>
    <ul>
        <li class="fragment">How do people react to systems going down?</li>
    </ul>
</ul>

---

### Past Incident Analysis
<!-- .slide: style="text-align: left;"> -->
How has the system failed previously?<br>
What technologies/strategies are now in place?<br>
What was learnt from those previous failures?<br>

---

<svg viewBox="-100 0 820 560" width="760" height="560" xmlns="http://www.w3.org/2000/svg" role="img" aria-label="Likelihood vs Impact risk matrix">
  <!-- background -->
  <rect x="-100" y="0" width="920" height="560" fill="#0e4650"/>

  <!-- title -->
  <text x="380" y="70" text-anchor="middle"
        font-family="Inter, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif"
        font-size="48" font-weight="800" letter-spacing="2"
        fill="#ffffff">Likelihood-Impact Map</text>

  <!-- matrix frame -->
  <g transform="translate(110,130)">
    <!-- outer border -->
    <rect x="0" y="0" width="540" height="400" fill="none" stroke="#e5e7eb" stroke-width="2"/>

    <!-- grid (dashed) -->
    <g stroke="#e5e7eb" stroke-dasharray="4 6" opacity="0.7">
      <!-- verticals -->
      <path d="M0 0 V400"/>
      <path d="M108 0 V400"/>
      <path d="M216 0 V400"/>
      <path d="M324 0 V400"/>
      <path d="M432 0 V400"/>
      <path d="M540 0 V400"/>
      <!-- horizontals -->
      <path d="M0 0 H540"/>
      <path d="M0 100 H540"/>
      <path d="M0 200 H540"/>
      <path d="M0 300 H540"/>
      <path d="M0 400 H540"/>
    </g>

    <!-- cells -->
    <!-- Row 1 (top) -->
    <rect x="0"   y="0"   width="108" height="100" fill="#fff176"/>
    <rect x="108" y="0"   width="108" height="100" fill="#fff176"/>
    <rect x="216" y="0"   width="108" height="100" fill="#fff176"/>
    <rect x="324" y="0"   width="108" height="100" fill="#e53935"/>
    <rect x="432" y="0"   width="108" height="100" fill="#e53935"/>
    <!-- Row 2 -->
    <rect x="0"   y="100" width="108" height="100" fill="#fff176"/>
    <rect x="108" y="100" width="108" height="100" fill="#fff176"/>
    <rect x="216" y="100" width="108" height="100" fill="#fff176"/>
    <rect x="324" y="100" width="108" height="100" fill="#fff176"/>
    <rect x="432" y="100" width="108" height="100" fill="#e53935"/>
    <!-- Row 3 -->
    <rect x="0"   y="200" width="108" height="100" fill="#00c853"/>
    <rect x="108" y="200" width="108" height="100" fill="#fff176"/>
    <rect x="216" y="200" width="108" height="100" fill="#fff176"/>
    <rect x="324" y="200" width="108" height="100" fill="#fff176"/>
    <rect x="432" y="200" width="108" height="100" fill="#fff176"/>
    <!-- Row 4 (bottom) -->
    <rect x="0"   y="300" width="108" height="100" fill="#00c853"/>
    <rect x="108" y="300" width="108" height="100" fill="#00c853"/>
    <rect x="216" y="300" width="108" height="100" fill="#fff176"/>
    <rect x="324" y="300" width="108" height="100" fill="#fff176"/>
    <rect x="432" y="300" width="108" height="100" fill="#fff176"/>
  </g>

  <!-- axis labels -->
  <text x="380" y="530" text-anchor="middle"
        font-family="Inter, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif"
        font-size="22" fill="#eadfcb">Impact</text>

  <text x="-70" y="330"
        transform="rotate(-90,-70,330)"
        text-anchor="middle"
        font-family="Inter, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif"
        font-size="22" fill="#eadfcb">Likelihood</text>
</svg>

---

### Potential scenarios to test!
<!-- .slide: style="text-align: left;"> -->

TBD

---

### Defining an experiment
<!-- .slide: style="text-align: left;"> -->
Which failure has the highest likelihood?<br>
Which failure has the highest impact?<br>
What will you gain from testing that failure?<br>
Is there anything else that can be tested?

---

## Example implementation

---

# SQL Server running on Kubernetes

---

### What is Kubernetes?
<!-- .slide: style="text-align: left;"> -->
"Kubernetes is a portable, extensible open-source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation. It has a large, rapidly growing ecosystem. Kubernetes services, support, and tools are widely available"<br>
<font size="6"><a href="kubernetes.io">kubernetes.io</a></font>

---

### KubeInvaders

<img src="images/KubeInvaders_75.png" style="float: center"/>

---

# Demo

---

## Resources
<!-- .slide: style="text-align: left;"> -->
TBD
