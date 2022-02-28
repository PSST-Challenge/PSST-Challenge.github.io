---
title: Welcome
layout: page
---

The PSST Challenge focuses on a technically-challenging and clinically important task&mdash;high-accuracy automatic phoneme recognition of disordered speech, in a diagnostic context&mdash;which has applications  in many different areas relating to speech and language disorders.

<div>
{%- if site.pages -%}
      <nav id="home-nav">
      {%- for page in site.pages -%}
        {%- unless page.disable -%}
            {%- if page.poster_img and page.poster_alt -%}
              <div id="home-nav-{{page.title | slugify}}" class="home-nav-poster">
                <a href="{{ page.url | relative_url }}" class="image-link">
                  <img src="{{page.poster_img}}" alt="{{page.poster_alt}}" title="{{page.poster_title}}"/>
                </a>
                <a class="button" href="{{ page.url | relative_url }}">{{page.title}}</a>
              </div>
            {%- endif -%}
        {%- endunless -%} 
    {%- endfor -%}
</nav>
{%- endif -%}

</div>

<div style="margin-top: 6rem; font-style: italic; font-size: 11px; color: #666">
<strong>Icon Credits:</strong>
<a href="https://thenounproject.com/icon/announcement-1704541/">Announcement</a> by Mello from Noun Project.
<a href="https://thenounproject.com/icon/line-graph-4002182/">Line Graph</a> by Tom Fricker from Noun Project.
<a href="https://thenounproject.com/icon/submit-3354574/">Submit</a> by Fajar Hasyim.
<a href="https://thenounproject.com/icon/flight-1968650/">Flight</a> by Paisley from Noun Project.
</div>

