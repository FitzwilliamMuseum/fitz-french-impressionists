---
title: Works by Cézanne
layout: default
artist: cézanne
permalink: /artists/cézanne
---
<div class="container mb-3">
  <div class="row">
{% assign artist  = site.artists | where:"artist", page.artist %}
{% assign rows = site.artists.size | divided_by: 2.0 | ceil %}

{% for i in (1..rows) %}
{% assign offset = forloop.index0 | times: 2 %}
    {% for art in artist limit:2 offset:offset %}
    <div class="col-md-4 mb-3">
      <div class="card h-100" >
        <a href="{{site.baseurl}}{{ art.permalink }}" class="stretched-link">
          <img class="card-img-top" src="{{art.preview}}" alt="Card image cap" width="300" height="300"/>
        </a>
        <div class="card-body">
          <h3 class="lead mt-2">
            <a href="{{site.baseurl}}{{ art.permalink }}" class="stretched-link">{{art.title}}</a>
          </h3>
        </div>
      </div>
    </div>
    {% endfor %}
  {% endfor %}
  </div>
</div>
