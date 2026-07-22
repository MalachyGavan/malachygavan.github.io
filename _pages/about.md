---
layout: about
title: About
permalink: /
subtitle: # name, affiliations and photo are rendered together in the page body (see the .intro block)

selected_papers: false # includes a list of papers marked as "selected={true}"
social: false # CV/email icons removed — they're redundant with the nav and the Find Me section

announcements:
  enabled: false # News is rendered manually in the page body (so the address/map can sit below it)
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

<div class="intro">
  <div class="intro-text">
    <h1 class="intro-name"><span style="font-weight: 700;">Malachy</span> <span style="font-weight: 500;">James Gavan</span></h1>
    <p class="affiliations">
      Lecturer (Assistant Professor), <a href="https://www.liverpool.ac.uk/management/">University of Liverpool</a><br />
      Junior Associate Editor, <a href="https://www.sciencedirect.com/journal/journal-of-mathematical-economics">Journal of Mathematical Economics</a><br />
      PhD in Economics, <a href="https://www.upf.edu/">Universitat Pompeu Fabra</a>
    </p>
  </div>
  <div class="intro-photo">
    <picture>
      <source
        type="image/webp"
        srcset="/assets/img/prof_pic-480.webp 480w, /assets/img/prof_pic-800.webp 800w"
        sizes="(max-width: 576px) 200px, 162px" />
      <img src="/assets/img/prof_pic.jpg" alt="Malachy James Gavan" width="1191" height="1321" />
    </picture>
  </div>
</div>

<style>
  /* Hide the theme's default name/subtitle header — we render our own below */
  .post-header { display: none; }
  .intro {
    display: flex;
    gap: 1.6rem;
    align-items: flex-start;
    margin: 0 0 1.5rem;
  }
  .intro-text { flex: 1 1 auto; min-width: 0; }
  .intro-name { font-size: 2.5rem; line-height: 1.15; margin: 0 0 0.7rem; }
  .affiliations { font-size: 1.05rem; line-height: 1.7; margin: 0; }
  /* Narrower reading measure for the prose (more editorial, easier to read) */
  .bio { max-width: 42rem; }
  .bio p { margin-bottom: 1rem; }
  .intro-photo {
    flex: 0 0 auto;
    height: 10.25rem; /* a touch larger so it reads as part of the hero, not appended */
    aspect-ratio: 1091 / 970;
    border-radius: 6px;
    overflow: hidden;
    box-shadow: 0 1px 6px rgba(0, 0, 0, 0.18);
  }
  .intro-photo picture {
    display: block;
    width: 100%;
    height: 100%;
  }
  .intro-photo img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }
  @media (max-width: 576px) {
    .intro { flex-direction: column; align-items: flex-start; }
    .intro-photo { height: auto; width: 224px; aspect-ratio: auto; }
    .intro-photo img { height: auto; }
  }
</style>

<div class="bio" markdown="1">

I am an economic theorist with research interests in mechanism design and negotiation. In mechanism design, I study how institutions can be designed to deliver good outcomes even when behaviour is unpredictable. In negotiation, I examine how real-world features of bargaining can lead to inefficiencies. These strands also connect to my secondary interest in international trade, where institutional design and negotiation play a central role in shaping trade agreements.

I am currently a Lecturer (Assistant Professor) in Economics at the [University of Liverpool Management School](https://www.liverpool.ac.uk/management/). I received my Ph.D. from [Universitat Pompeu Fabra](https://www.upf.edu/) (UPF) and the [Barcelona School of Economics](https://bse.eu/) (BSE) under the supervision of Antonio Penta.

See my [research](/publications/), download my [CV](/cv/), or contact me by [email](mailto:malachy.gavan@liverpool.ac.uk).

</div>

## News

{% include news.liquid %}

## Contact

<div class="contact-wrap">
  <div class="contact-address">
    <p><strong>Office 405, Mulberry Court</strong><br />
    University of Liverpool<br />
    Liverpool, L69 7ZY</p>
    <p><a href="mailto:malachy.gavan@liverpool.ac.uk">malachy.gavan@liverpool.ac.uk</a></p>
  </div>
  <iframe
    class="contact-map"
    src="https://www.openstreetmap.org/export/embed.html?bbox=-3.02%2C53.38%2C-2.91%2C53.43&amp;layer=mapnik&amp;marker=53.4056%2C-2.9660"
    title="Map showing the University of Liverpool"
    loading="lazy"
  ></iframe>
</div>

<style>
  .contact-wrap {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    align-items: flex-start;
    margin-top: 1rem;
  }
  .contact-address {
    flex: 1 1 200px;
  }
  .contact-map {
    flex: 2 1 340px;
    width: 100%;
    height: 280px;
    border: 1px solid var(--global-divider-color);
    border-radius: 8px;
  }
</style>

## On the Map

Where I have studied and worked, and where I have presented or visited:

<div class="visits-map" id="visits-map">
  <div class="visits-viewport">
    <div class="visits-inner">
      <img src="/assets/img/maps/world_light.webp" alt="World map with pins marking places I have studied, worked, or given talks" draggable="false" />
      {% for v in site.data.visits %}
        {%- assign left = v.lon | plus: 180 | times: 100 | divided_by: 360.0 -%}
        {%- assign top = 90 | minus: v.lat | times: 100 | divided_by: 180.0 -%}
        <span class="visit-pin" style="left: {{ left }}%; top: {{ top }}%;" data-label="{{ v.place }} ({{ v.year }})" title="{{ v.place }} ({{ v.year }})"></span>
      {% endfor %}
      {% for v in site.data.homes %}
        {%- assign left = v.lon | plus: 180 | times: 100 | divided_by: 360.0 -%}
        {%- assign top = 90 | minus: v.lat | times: 100 | divided_by: 180.0 -%}
        <span class="visit-pin home" style="left: {{ left }}%; top: {{ top }}%;" data-label="{{ v.place }} ({{ v.year }})" title="{{ v.place }} ({{ v.year }})"></span>
      {% endfor %}
    </div>
  </div>
  <div class="visits-controls">
    <button type="button" class="vz" data-act="in" aria-label="Zoom in">+</button>
    <button type="button" class="vz" data-act="out" aria-label="Zoom out">&#8722;</button>
    <button type="button" class="vz" data-act="reset" aria-label="Reset view">&#8635;</button>
  </div>
</div>
<p class="visits-caption">
  <span class="legend-dot" style="background: #e0416a;"></span> seminars, talks &amp; visits
  &nbsp;&nbsp;<span class="legend-dot" style="background: #2b6cb0;"></span> education &amp; work
  &nbsp;·&nbsp; scroll or drag to zoom &amp; pan
</p>

<style>
  .visits-map {
    position: relative;
    width: 100%;
    max-width: 720px;
    margin: 1rem auto 0;
    border: 1px solid var(--global-divider-color);
    border-radius: 8px;
    overflow: hidden;
  }
  .visits-viewport {
    overflow: hidden;
    cursor: grab;
    touch-action: none;
  }
  .visits-viewport.grabbing {
    cursor: grabbing;
  }
  .visits-inner {
    position: relative;
    width: 100%;
    transform-origin: 0 0;
  }
  .visits-inner img {
    display: block;
    width: 100%;
    height: auto;
    user-select: none;
    -webkit-user-drag: none;
  }
  .visit-pin {
    position: absolute;
    width: 12px;
    height: 12px;
    border-radius: 50%;
    background: #e0416a;
    border: 2px solid #fff;
    box-shadow: 0 0 2px rgba(0, 0, 0, 0.55);
    cursor: pointer;
    transform: translate(-50%, -50%) scale(calc(1 / var(--z, 1)));
  }
  .visit-pin:hover {
    transform: translate(-50%, -50%) scale(calc(1.45 / var(--z, 1)));
    z-index: 10;
  }
  .visit-pin::after {
    content: attr(data-label);
    position: absolute;
    left: 50%;
    bottom: calc(100% + 5px);
    transform: translateX(-50%);
    background: rgba(20, 20, 20, 0.92);
    color: #fff;
    font-size: 11px;
    line-height: 1.3;
    padding: 4px 8px;
    border-radius: 5px;
    white-space: normal;
    width: max-content;
    max-width: 190px;
    text-align: center;
    opacity: 0;
    pointer-events: none;
    transition: opacity 0.12s;
  }
  .visit-pin:hover::after {
    opacity: 1;
  }
  .visit-pin.home {
    background: #2b6cb0;
  }
  .visits-caption {
    text-align: center;
    font-size: 0.82rem;
    margin-top: 0.7rem;
    color: var(--global-text-color);
    letter-spacing: 0.01em;
  }
  .legend-dot {
    display: inline-block;
    width: 11px;
    height: 11px;
    border-radius: 50%;
    box-shadow: 0 0 0 1px rgba(0, 0, 0, 0.15);
    vertical-align: middle;
    margin-right: 5px;
  }
  .visits-controls {
    position: absolute;
    top: 8px;
    right: 8px;
    display: flex;
    flex-direction: column;
    gap: 4px;
    z-index: 20;
  }
  .visits-controls .vz {
    width: 30px;
    height: 30px;
    padding: 0;
    border: 1px solid var(--global-divider-color);
    background: rgba(255, 255, 255, 0.92);
    border-radius: 5px;
    cursor: pointer;
    font-size: 18px;
    line-height: 1;
    color: #333;
  }
  .visits-controls .vz:hover {
    background: #fff;
  }
</style>

<script>
  (function () {
    var map = document.getElementById("visits-map");
    if (!map) return;
    var vp = map.querySelector(".visits-viewport");
    var inner = map.querySelector(".visits-inner");
    var z = 1, tx = 0, ty = 0, maxZ = 8;
    function apply() {
      inner.style.transform = "translate(" + tx + "px," + ty + "px) scale(" + z + ")";
      inner.style.setProperty("--z", z);
    }
    function clampPan() {
      var w = vp.clientWidth, h = vp.clientHeight;
      var minTx = w - w * z, minTy = h - h * z;
      tx = Math.min(0, Math.max(minTx, tx));
      ty = Math.min(0, Math.max(minTy, ty));
    }
    function zoomAt(cx, cy, factor) {
      var nz = Math.min(maxZ, Math.max(1, z * factor));
      if (nz === z) return;
      tx = cx - (cx - tx) * (nz / z);
      ty = cy - (cy - ty) * (nz / z);
      z = nz;
      clampPan();
      apply();
    }
    vp.addEventListener("wheel", function (e) {
      e.preventDefault();
      var r = vp.getBoundingClientRect();
      zoomAt(e.clientX - r.left, e.clientY - r.top, e.deltaY < 0 ? 1.2 : 1 / 1.2);
    }, { passive: false });
    var dragging = false, sx, sy, stx, sty;
    function down(x, y) { dragging = true; sx = x; sy = y; stx = tx; sty = ty; vp.classList.add("grabbing"); }
    function move(x, y) { if (!dragging) return; tx = stx + (x - sx); ty = sty + (y - sy); clampPan(); apply(); }
    function up() { dragging = false; vp.classList.remove("grabbing"); }
    vp.addEventListener("mousedown", function (e) { e.preventDefault(); down(e.clientX, e.clientY); });
    window.addEventListener("mousemove", function (e) { move(e.clientX, e.clientY); });
    window.addEventListener("mouseup", up);
    var lastDist = null;
    function dist(t) { var dx = t[0].clientX - t[1].clientX, dy = t[0].clientY - t[1].clientY; return Math.sqrt(dx * dx + dy * dy); }
    vp.addEventListener("touchstart", function (e) {
      if (e.touches.length === 1) down(e.touches[0].clientX, e.touches[0].clientY);
      else if (e.touches.length === 2) lastDist = dist(e.touches);
    }, { passive: true });
    vp.addEventListener("touchmove", function (e) {
      if (e.touches.length === 1) move(e.touches[0].clientX, e.touches[0].clientY);
      else if (e.touches.length === 2) {
        e.preventDefault();
        var d = dist(e.touches), r = vp.getBoundingClientRect();
        if (lastDist) {
          var mx = (e.touches[0].clientX + e.touches[1].clientX) / 2 - r.left;
          var my = (e.touches[0].clientY + e.touches[1].clientY) / 2 - r.top;
          zoomAt(mx, my, d / lastDist);
        }
        lastDist = d;
      }
    }, { passive: false });
    vp.addEventListener("touchend", function (e) { if (e.touches.length === 0) { up(); lastDist = null; } });
    map.querySelectorAll(".vz").forEach(function (b) {
      b.addEventListener("click", function () {
        var act = b.getAttribute("data-act"), w = vp.clientWidth, h = vp.clientHeight;
        if (act === "in") zoomAt(w / 2, h / 2, 1.5);
        else if (act === "out") zoomAt(w / 2, h / 2, 1 / 1.5);
        else { z = 1; tx = 0; ty = 0; apply(); }
      });
    });
    apply();
  })();
</script>
