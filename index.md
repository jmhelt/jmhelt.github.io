---
layout: index
title: Home
---
Hello! I'm a second-year PhD student in Computer Science at [Princeton University](https://www.cs.princeton.edu/) advised by Professor [Wyatt Lloyd](https://www.cs.princeton.edu/~wlloyd/). My interests are in distributed systems and networking, and my current research focuses on distributed databases.

Before attending Princeton, I completed a master's at [Carnegie Mellon University](https://www.cs.cmu.edu/), where I was fortunate to be co-advised by Professors [Srini Seshan](https://www.cs.cmu.edu/~srini/) and [Vyas Sekar](https://users.ece.cmu.edu/~vsekar/). I also spent a few years in industry, and before that, I earned my BA from [Amherst College](https://www.amherst.edu/), where I was a member of the [Amherst Men's Swim Team](http://athletics.amherst.edu/sports/mswimdive/index).

## News
{% assign news = site.data.news %}

{% for event in news %}
**{{ event.date }}.** {{ event.text }}  {% endfor %}

## Publications
{%- assign publications = site.data.publications -%}
{%- assign papers_dir = "/assets/papers/" -%}
{%- assign slides_dir = "/assets/slides/" -%}

{% for pub in publications %}
* **{{ pub.title }}**  
{{ pub.authors }}  
{% if pub.status %}*{{ pub.status }}*  {%- endif -%}
{% if pub.venue %}{{ pub.venue_prefix }} [{{ pub.venue }}]({{ pub.venue_link }}), {{ pub.year }}  {% endif %}
{% if pub.paper %}[[paper]]({{ papers_dir | prepend: site.baseurl | append: pub.paper }}){% endif %}
{% if pub.slides %}[[slides]]({{ slides_dir | prepend: site.baseurl | append: pub.slides }}){% endif %}
{% endfor %}

## Teaching
{%- assign positions = site.data.teaching -%}

{% for position in positions %}
* {{ position.title }} for [{{ position.course }}]({{ position.link }}){% if position.professor %} by {{ position.professor }}{% endif %}. {{ position.school }}, {{ position.semesters }}.
{%- endfor -%}
