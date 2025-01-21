---
layout: default
title: "Projects"
permalink: /projects/
css_class: "projects-page"
---

# Featured Projects

---
<!-- Featured Projects (highest priority) -->
<div class="featured-gallery">
  {% assign sorted_by_priority = site.projects | sort: 'priority' | reverse %}
  {% assign top_three = sorted_by_priority | slice: 0,3 %}

  {% for project in top_three %}
    <!-- Grab status, default to "" if none -->
    {% assign s = project.status | default: "" %}

    {% if s contains "under_construction" %}
      <!-- Non-clickable featured item -->
      <div class="project-item" data-category="{{ project.category }}">
        <div class="under-construction-banner">
          🚧 Under Construction 🚧
        </div>
        {% if s contains "new" %}
          <div class="corner-ribbon">New</div>
        {% endif %}

        {% if project.header_image %}
          <img src="{{ project.header_image | relative_url }}" alt="{{ project.title }}">
        {% endif %}
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
      </div>
    {% else %}
      <!-- Clickable featured item -->
      <a class="project-item"
         data-category="{{ project.category }}"
         href="{{ project.url }}">
        {% if s contains "new" %}
          <div class="corner-ribbon">New!</div>
        {% endif %}
        {% if project.header_image %}
          <img src="{{ project.header_image | relative_url }}" alt="{{ project.title }}">
        {% endif %}
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
      </a>
    {% endif %}
  {% endfor %}
</div>

# All Projects

---
<!-- Filter Buttons -->
<div class="project-filters">
  <button data-filter="all" onclick="filterAllProjects('all')">All</button>
  <button data-filter="professional" onclick="filterAllProjects('professional')">Professional</button>
  <button data-filter="personal" onclick="filterAllProjects('personal')">Personal</button>
</div>

<!-- All Projects (sorted newest to oldest by date) -->
<div class="all-gallery">
  {% assign sorted_by_date = site.projects | sort: 'date' | reverse %}
  {% for project in sorted_by_date %}
    {% assign s = project.status | default: "" %}

    {% if s contains "under_construction" %}
      <!-- Non-clickable item -->
      <div class="project-item" data-category="{{ project.category }}">
        <div class="under-construction-banner">
          🚧 Under Construction 🚧
        </div>
        {% if s contains "new" %}
          <div class="corner-ribbon">New!</div>
        {% endif %}
        {% if project.header_image %}
          <img src="{{ project.header_image | relative_url }}" alt="{{ project.title }}">
        {% endif %}
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
      </div>
    {% else %}
      <!-- Clickable item -->
      <a class="project-item"
         data-category="{{ project.category }}"
         href="{{ project.url }}">
        {% if s contains "new" %}
          <div class="corner-ribbon">New!</div>
        {% endif %}
        {% if project.header_image %}
          <img src="{{ project.header_image | relative_url }}" alt="{{ project.title }}">
        {% endif %}
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
      </a>
    {% endif %}
  {% endfor %}
</div>

<script>
  function filterAllProjects(category) {
    // Only select items within the all-gallery
    const items = document.querySelectorAll('.all-gallery .project-item');
    items.forEach(item => {
      if (category === 'all') {
        item.style.display = 'block';
      } else {
        const cat = item.getAttribute('data-category');
        item.style.display = (cat === category) ? 'block' : 'none';
      }
    });

    // Highlight the correct button
    const buttons = document.querySelectorAll('.project-filters button');
    buttons.forEach(btn => {
      btn.classList.remove('active');
      if (btn.dataset.filter === category) {
        btn.classList.add('active');
      }
    });
  }

  // Optional: auto-show "All" on page load
  document.addEventListener('DOMContentLoaded', () => {
    filterAllProjects('all');
  });
</script>
