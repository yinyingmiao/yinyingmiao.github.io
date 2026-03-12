---
layout: default
title: Publications
---

<section class="pubs">
    {% if site.data.projects %}
    {% assign items = site.data.projects | sort: "year" | reverse %}
    {% for item in items %}
        <p>{{ item.title }} ({{ item.year }})</p>
    {% endfor %}
    {% else %}
    <p>No projects found.</p>
    {% endif %}s

  {% for year in pubs_by_year %}
    <div class="pub-year">
      <h2>{{ year.name }}</h2>

      {% for pub in year.items %}
        <div class="pub-item">
          <div class="pub-main">
            <p class="pub-title">{{ pub.title }}</p>
            <p class="pub-authors">{{ pub.authors }}</p>
            <p class="pub-venue">{{ pub.venue }}</p>
          </div>

          <div class="pub-links">
            {% if pub.pdf %}<a href="{{ pub.pdf }}">PDF</a>{% endif %}
            {% if pub.project %}<a href="{{ pub.project }}">Project</a>{% endif %}
            {% if pub.doi %}<a href="{{ pub.doi }}">DOI</a>{% endif %}
          </div>
        </div>
      {% endfor %}
    </div>
  {% endfor %}
</section>
