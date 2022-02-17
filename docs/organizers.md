---
layout: page
title: The Organizers
permalink: /organizers/
poster_img: /assets/images/blank-square.jpg
poster_alt: TODO! A description of the poster image
challenge_organizers: [
    {
        portrait: /assets/images/blank-square.jpg,
        portrait_alt: A blank square,
        name: Steven Bedrick,
        bio: "is an Associate Professor at Oregon Health and Science University. His Research focuses on biomedical applications for speech and language technologies, with a particular emphasis on language disorders and disabilities."
    },
    {
        portrait: /assets/images/blank-square.jpg,
        portrait_alt: A blank square,
        name: Gerasimos Fergadiotis,
        bio: "is a Professor at Portland State University. His research focuses on developing psychometric applications to quantify clinically relevant aspects of language processing in stroke patients."
    },
    {
        portrait: /assets/images/blank-square.jpg,
        portrait_alt: A blank square,
        name: Robert Gale,
        bio: "is a Research Engineer at Oregon Health and Science University, researching and implementing systems to recognize and analyze speech & language in a clinical context."
    },
    {
        portrait: /assets/images/blank-square.jpg,
        portrait_alt: A blank square,
        name: Mikala Fleegle,
        bio: "has not submitted a bio."
    },
]
---


## Allow us to introduce ourselves

The PSST Challenge is a collaboration between Oregon Health and Science University (OHSU) and Portland State
University (PSU). Our proposed activities will be supported via a grant from the National Institute on Deafness
and Other Communication Disorders NIH (R01-DC015999-04S1), the purpose of which is to promote the use of clinical
datasets of aphasic speech by the mainstream machine learning community, and which includes travel support for
participating students.


<div id="the-psst-people">
{%- for person in page.challenge_organizers -%}
    <div class="person">
        <div class="portrait"><img src="{{person.portrait}}" alt="{{person.portrait_alt}}" /></div>
        <p><strong>{{person.name}}</strong> {{person.bio}}</p>
    </div>
{%- endfor -%}
</div>

### Special Thanks

Raye Watts designed our logo and web site.
