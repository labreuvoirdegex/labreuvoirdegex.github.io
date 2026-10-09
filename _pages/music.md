---
layout: indexcategory
title: Live Music
subtitle: some concerts organised at our place
permalink: /music
include_collection: music
header_img: "./assets/pics/music/music3_IMG_8009_small.jpeg"
show_breadcrumb   : true
---

<main class="container-lg pb-3 flex-fill">
  <div class="row pt-2 mt-3">
    <section class="col-md-8 offset-md-2">
    {% include_cached components/indexcards.html cacheddocs=paginator.posts  cachedlimit=site.paginate %}
    </section>
  </div>
</main>
{%- assign max_per_page = site.paginator_maxnum | 
                         default: 3 | at_least: 2 | 
                         at_most : paginator.total_pages -%}


{% for post in site.tags.musique %}
 <h4><a href="{{ post.url }}">{{ post.title }}</a></h4>
 <p> {{ post.content}}</p> <span>{{ post.date | date_to_string }}</span>
{% endfor %}