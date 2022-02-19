---
layout: page
title: The Organizers
permalink: /organizers/
poster_img: /assets/images/blank-square.jpg
poster_alt: TODO! A description of the poster image
challenge_organizers: [
    {
        portrait: /assets/images/people/steven.jpg,
        portrait_alt: "Steven has long brown hair draping over his shoulder, a full brown beard, and light skin. He is wearing sunglasses, an olive green billed cap, and a black rain jacket. His teeth are showing as he smiles and leans against a tree, with a forest in the background.",
        name: Steven Bedrick,
        bio: "is an Associate Professor at Oregon Health and Science University. His research focuses on biomedical applications for speech and language technologies, with a particular emphasis on language disorders and disabilities."
    },
    {
        portrait: /assets/images/people/gerasimos.jpg,
        portrait_alt: "Gerasimos has short brown hair, a short brown beard with a few white patches, and light skin. He is wearing a blue and white collared shirt with a broad plaid pattern. He is smiling with his mouth closed in front of a plain sky-blue wall.",
        name: Gerasimos Fergadiotis,
        bio: "is a Professor at Portland State University. His research focuses on developing psychometric applications to quantify clinically relevant aspects of language processing in stroke patients."
    },
    {
        portrait: /assets/images/people/robert.jpg,
        portrait_alt: "Robert has a brown beard, light skin, and his hair is covered with a bright red beanie. He wears glasses and an orange/blue/white zippered coat. He is wide-eyed and has his hand to his ear, listening to the many barnacles on the large rock right behind him.",
        name: Robert Gale,
        bio: "is a Research Engineer at Oregon Health and Science University, researching and implementing systems to recognize and analyze speech & language in a clinical context."
    },
    {
        portrait: /assets/images/people/mikala.jpg,
        portrait_alt: "Mikala has light brown hair draped over her shoulder and light skin. She is wearing a dark gray blazer with a white shirt underneath. She smiles with her teeth showing, standing near a balcony railing and a variety of potted plants. Large city buildings cover most of the background, with a bit of blue sky in the middle.",   
        name: Mikala Fleegle,
        bio: "is a Research Speech-Language Pathologist at Portland State University. Her research interests are in using computer technologies for more precise assessment of aphasia and apraxia of speech."
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
