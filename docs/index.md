---
title: Welcome
layout: page
---

<div style="margin: 0 3rem 3rem 3rem; font-style: italic">
<h3>Post-event update:</h3> 

<p>
Thank you to everyone who helped and participated in the challenge! Our summary and the 
challenger papers can be found beginning on page 41 of the 
<a href="http://www.lrec-conf.org/proceedings/lrec2022/workshops/RaPID4/2022.rapid4-1.0.pdf">RaPID proceedings</a>.
</p>

<p>
For those who are interested in
exploring the data we described at RaPID/LREC, please first obtain access to <a href="https://aphasia.talkbank.org/">AphasiaBank</a>, 
then use those credentials to retrieve <a href="https://github.com/PSST-Challenge/psstdata">psstdata</a>.
</p>
</div>

The PSST Challenge focuses on a technically-challenging and clinically important task&mdash;high-accuracy automatic phoneme recognition of disordered speech, in a diagnostic context&mdash;which has applications  in many different areas relating to speech and language disorders.

<a href="https://docs.google.com/forms/d/e/1FAIpQLScwAC3j7NQ2giyFSjrNen6NhmSbnHqdxS915ftZDBRi2SHQtQ/viewform" target="_blank">Fill out this form</a> to get access to the data. Papers must be submitted in <a href="https://www.softconf.com/lrec2022/RaPID-4/" target="_blank">softconf</a> by {{site.submission_deadline}}, formatted according to the <a href="https://lrec2022.lrec-conf.org/en/submission2022/authors-kit/" target="_blank">author's kit</a>. Please refer to <a href="https://spraakbanken.gu.se/en/rapid-2022/submission-details" target="_blank">RaPID submission details</a> for more information.

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

