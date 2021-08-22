---
title: The Artists of Impressionism
permalink: /artists
layout: default
---
<div class="row">
{{ items_grouped }}
{% assign items_grouped = site.artists | group_by: 'artist' %}
  {% for group in items_grouped %}
    <div class="col-md-4 mb-3">
      <div class="card h-100" >
        <a href="{{site.url}}{{site.baseurl}}/artists/{{ group.name }}" class="stretched-link">
          <img class="card-img-top " src="{{ group.items[0].preview}}" alt="Thumbnail" width="300" height="300"/>
        </a>
        <div class="card-body">
          <h3 class="lead mt-2">
            <a href="{{site.url}}{{site.baseurl}}/artists/{{ group.name }}" class="stretched-link">Explore the works of {{group.items[0].artist_name}}</a>
          </h3>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
