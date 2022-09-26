---
# Mr. Green Jekyll Theme - v1.1.0 (https://github.com/MrGreensWorkshop/MrGreen-JekyllTheme)
# Copyright (c) 2022 Mr. Green's Workshop https://www.MrGreensWorkshop.com
# Licensed under MIT

layout: default
# About page
---
{%- include multi_lng/get-lng-by-url.liquid -%}
{%- assign lng = get_lng -%}
<div class="multipurpose-container about-container">
  <div class="row about-main">
    <div class="col-md-3 about-img">
      <img src="{{ page.img }}" alt="">
    </div>
    <div class="col-md-9 about-header">
      <h1 translate="no">{{ site.data.owner[lng].brand }}</h1>
      <div class="meta-container">
        {%- assign about_title = site.data.owner[lng].about.sub_title | replace: site.data.conf.main.sample_replace, site.data.lang[lng].constants.sample -%}
        {%- if site.data.owner[lng].about.sub_title %}
          <p class="sub-title">
            {%- if site.data.conf.others.about.sub_title_icon %}<i class="{{ 'fa-fw ' }}{{ site.data.conf.others.about.sub_title_icon }}" aria-hidden="true"></i>{% endif -%}
            &nbsp;{{ about_title }}
          </p>
        {% endif -%}
        {%- assign tmp_obj =  site.data.owner[lng].contacts | where_exp: "item", "item.email != nil" | first -%}
        {%- assign email = tmp_obj['email'] -%}
        {%- if site.data.conf.others.about.show_email and email %}
          {%- assign _email = email | split: '@' %}
          <p class="email">
            <a href="javascript:void(0);" onclick="setAddress('{{ _email[0] }}', '{{ _email[1] }}');">
              {%- if site.data.conf.others.about.email_icon %}<i class="{{ 'fa-fw ' }}{{ site.data.conf.others.about.email_icon }}"></i>{% endif -%}
              &nbsp;{{ site.data.lang[lng].about.email_title }}
            </a>
          </p>
        {% endif -%}
        {%- if site.data.conf.others.about.show_contacts and site.data.owner[lng].contacts.size > 0 %}
          {% include default/nav/contact-links.html -%}
        {% endif -%}
      </div>
    </div>
  </div>
  <div class="row about-divider">
    <hr>
  </div>
  <div class="row">
    <div class="col-md-12">
      <div class="about-msg markdown-style">
        {{ content }}
      </div>
    </div>
  </div>
</div>

  <div class="row">
    <div class="col-md-12">
<mini-profile>
  <header>
    <iframe src="https://scapes.punkscape.xyz/?simple&autoplay&autoscale=false&chapter-switch=false&sound-control=false#8386" frameborder="0" tabindex="-1"></iframe>
    <img src="https://pbs.twimg.com/profile_images/1506309513745469440/d-srpQ3S_400x400.jpg" alt="Cryptogenik">
  </header>

  <section>
    <h1>Cryptogenik.eth</h1>
    <p>If you build it - they will come</p>

    <ul>
      <li>
        <a href="#">Mail</a>
      </li>
      <li>
        <a href="https://twitter.com/Cryptogenik" target="_blank">Twitter</a>
      </li>
      <li>
        <a href="https://github.com/" target="_blank">Github</a>
      </li>
    </ul>
  </section>
</mini-profile>
      </div></div>
<style>

:root {
  --box-padding: 1.5rem;

  /* Colors */
  --black: black;
  --dark-bg: rgb(14 11 18);
  --primary: #ae44d5;
  --action: rgb(58 50 86 / 40%);
  --action-active: rgb(58 50 86 / 80%);

  /* Borders */
  --border-radius: 0.5rem;
  --border: 3px solid rgb(20 15 25);
  --border-dark: 3px solid var(--dark-bg);
}


mini-profile {
  background-color: var(--dark-bg);
  color: white;
  max-width: 40.5rem;
  overflow: hidden;
}

mini-profile header {
  background-color: var(--black);
  position: relative;
  display: flex;
  justify-content: center;
  border-bottom: var(--border);
}

mini-profile iframe {
  width: 40.5rem;
  height: calc(40.5rem / 3);
}

mini-profile img:nth-child(2) {
  border-radius: 50%;
  border: var(--border-dark);
  max-width: 30vw;

  position: absolute;
  bottom: -2rem;
  left: var(--box-padding);
}

mini-profile section {
  padding: 2.25rem var(--box-padding) var(--box-padding);
}

mini-profile h1 {
  color: var(--primary);
  font-size: 1.4rem;
  text-transform: uppercase;
  font-style: italic;
  font-weight: 700;
}

mini-profile p {
  opacity: 0.8;
/*   font-size: 0.8rem; */
}

mini-profile ul {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin: 1rem 0 0;
  list-style: none;
}

mini-profile a:hover,
mini-profile a:focus,
mini-profile a:active {
  background-color: var(--action-active);
}

mini-profile a {
  display: block;
  padding: 0.5rem 1rem;
  background-color: var(--action);
  border-radius: var(--border-radius);
  transition: background .4s;
  text-transform: uppercase;
  font-style: italic;
  font-weight: bold;
  font-size: 0.8rem;
/*   background-color: var(--action-active); */
  text-decoration: none;
  color:white;
}

@media (min-width: 40.5rem) {
  :has(mini-profile) {
    display: flex;
/*     align-items: center; */
/*     background-color: var(--black); */
    align-content: center;
    justify-content: left;
  }

  mini-profile {
    background-color: var(--dark-bg);
    margin: 2rem auto 4rem;
    border: var(--border);
    border-radius: var(--border-radius);
/*     box-shadow: 0 0.25rem 3rem 2rem rgb(95 45 145 / 9%); */
/*     animation: gradient 5s infinite alternate; */
  }

  mini-profile img:nth-child(2) {
    max-width: 10rem;
  }
}

@keyframes gradient {
  0% {
    box-shadow: 0 0.25rem 3rem 2rem rgb(95 45 145 / 9%);
  }
  50% {
/*     box-shadow: -0.5rem -0.5rem 3rem 2rem rgb(100 45 130 / 19%); */
    box-shadow: -5px 4px 5px 3rem #00000039,0 0 5px #26bdff,0 0 5px .3rem #1ab3f6,0 0 10px .3rem #6b4eff,0 0 20px .5rem #cd5c5c;
  }
  100% {
/*     box-shadow: 1rem 1.45rem 5rem 3.9rem rgb(95 45 170 / 13%); */
    box-shadow: -5px 4px 5px #00000039,0 0 5px #26bdff,0 0 5px #1ab3f6,0 0 10px #6b4eff,0 0 20px #cd5c5c;
  }
}


</style>
