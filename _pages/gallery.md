---
title: "Gallery"
permalink: /gallery/
---

# Research Gallery

## Fieldwork（野外考察）

{% assign photos = site.static_files | where_exp: "file", "file.path contains '/images/gallery/field/'" | sort: "path" %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    <a href="{{ photo.path | relative_url }}" target="_blank">
      <img src="{{ photo.path | relative_url }}" alt="Fieldwork photograph">
    </a>
  {% endif %}
{% endfor %}
</div>


## Laboratory & Research（实验与科研）

{% assign photos = site.static_files | where_exp: "file", "file.path contains '/images/gallery/lab/'" | sort: "path" %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    <a href="{{ photo.path | relative_url }}" target="_blank">
      <img src="{{ photo.path | relative_url }}" alt="Laboratory photograph">
    </a>
  {% endif %}
{% endfor %}
</div>


## Academic Activities（学术活动）

{% assign photos = site.static_files | where_exp: "file", "file.path contains '/images/gallery/academic/'" | sort: "path" %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    <a href="{{ photo.path | relative_url }}" target="_blank">
      <img src="{{ photo.path | relative_url }}" alt="Academic activity photograph">
    </a>
  {% endif %}
{% endfor %}
</div>


## Group Activities（团队活动）

{% assign photos = site.static_files | where_exp: "file", "file.path contains '/images/gallery/group/'" | sort: "path" %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    <a href="{{ photo.path | relative_url }}" target="_blank">
      <img src="{{ photo.path | relative_url }}" alt="Group activity photograph">
    </a>
  {% endif %}
{% endfor %}
</div>


<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 15px;
  margin: 20px 0 35px 0;
}

.gallery-grid img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  border-radius: 5px;
  transition: transform 0.2s ease;
}

.gallery-grid img:hover {
  transform: scale(1.03);
}

@media (max-width: 768px) {
  .gallery-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}
</style>
