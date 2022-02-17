---
title: Welcome
layout: default
---

The PSST Challenge focuses on a technically-challenging and clinically important task&mdash;high-accuracy automatic phoneme recognition of disordered speech, in a diagnostic context&mdash;which has applications  in many different areas relating to speech and language disorders.

<div>
{%- if site.pages -%}
      <nav id="home-nav">
      {%- for page in site.pages -%}
        {%- if page.poster_img and page.poster_alt -%}
          <div id="home-nav-{{page.title | slugify}}" class="home-nav-poster">
            <a href="{{ page.url | relative_url }}" class="image-link">
              <img src="{{page.poster_img}}" alt="{{page.poster_alt}}" />
            </a>
            <a class="button" href="{{ page.url | relative_url }}">{{page.title}}</a>
          </div>
    
        {%- endif -%}
    {%- endfor -%}
</nav>
{%- endif -%}
</div>
