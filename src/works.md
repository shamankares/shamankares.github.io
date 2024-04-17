---
layout: default
title: Works
permalink: /works
---

<style type="text/css" media="screen">
.mid-dot::after {
  content: " \00b7 ";
}

.work-category {
  margin: 28px 0;
}

.works {
  margin: 10px 0;
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(min(12rem, 100%), 1fr));
  column-gap: 8px;
  row-gap: 8px;
}

.work-item {
  padding: 20px;
  display: flex;
  justify-content: space-between;
}

.work-content > p {
  text-align: left;
}

.work-links {
  margin-top: 20px;
  text-align: center;

  .mid-dot:last-child::after {
    content: none;
  }
}

.subtitle {
  text-align: left;
  text-decoration: underline;
  font-size: 1.25em;
}

article {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: justify;

  @media (max-width: 540px) {
      margin: 8px 0;    
  }
}
</style>

{% for workCat in site.data.works %}
<div class="work-category">
  <h2 class="subtitle">{{ workCat.category }}</h2>
  <div class="works">
    {% for work in workCat.works %}
    <article class="work-item subbox">
      <div class="work-content">
        <h3>{{ work.name }}</h3>
        <p>{{ work.description }}</p>
      </div>
      <div class="work-links">
        {% for link in work.links %}
        <a href="{{ link.url }}">{{ link.text }}</a><span class="mid-dot"></span>
        {% endfor %}
      </div>
    </article>
    {% endfor %}
  </div>
</div>
{% endfor %}
