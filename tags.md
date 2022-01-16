---
---
# Categories &amp; Technologies

<section class="tag-list">
{% assign tags = site.tags | sort %}
{% for tag in tags %}
  {% if tag[1].size >= 1 %}
    {% assign id = tag[0] | replace: ' ', '-' %}
    {% if id != "evergreen" %}
      <a href="#{{ id }}"><h2 id="{{ id }}">{{ tag[0] }}</h2></a>
      {% assign posts = tag[1] | sort | reverse %}
      {% for post in posts %}
        {% unless post.hidden %}
          {% include featured.html post=post size="small" %}
        {% endunless %}
      {% endfor %}
    {% endif %}
    <!-- <hr /> -->
  {% endif %}
{% endfor %}
</section>
