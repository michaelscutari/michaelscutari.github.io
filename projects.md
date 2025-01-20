---
layout: default
title: "Projects"
css_class: "projects-page"
---

# Featured Projects
---
<!-- Featured Projects (highest priority) -->
<div class="featured-gallery">
  {% assign sorted_by_priority = site.projects | sort: 'priority' | reverse %}
  {% assign top_three = sorted_by_priority | slice: 0,3 %}

  {% for project in top_three %}
    <a
      class="project-item"
      data-category="{{ project.category }}"
      href="{{ project.url }}"
    >
      <img src="{{ project.header_image | relative_url }}" alt="{{ project.title }}">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </a>
  {% endfor %}
</div>



<!-- All Projects (sorted newest to oldest by date) -->
# All Projects
---

<!-- Filter Buttons -->
<div class="project-filters">
  <button onclick="filterAllProjects('all')">All</button>
  <button onclick="filterAllProjects('professional')">Professional</button>
  <button onclick="filterAllProjects('personal')">Personal</button>
</div>
<!-- All Projects (sorted newest to oldest by date) -->
<div class="all-gallery">
  {% assign sorted_by_date = site.projects | sort: 'date' | reverse %}
  {% for project in sorted_by_date %}
    <a
      class="project-item"
      data-category="{{ project.category }}"
      href="{{ project.url }}"
    >
      <img src="{{ project.header_image | relative_url }}" alt="{{ project.title }}">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </a>
  {% endfor %}
</div>

<script>
  /**
   * Filters items in the all-gallery only
   */
  function filterAllProjects(category) {
    // Only select items within the .all-gallery
    const items = document.querySelectorAll('.all-gallery .project-item');

    items.forEach(item => {
      if (category === 'all') {
        item.style.display = 'block';
      } else {
        const cat = item.getAttribute('data-category');
        item.style.display = (cat === category) ? 'block' : 'none';
      }
    });
  }
</script>
