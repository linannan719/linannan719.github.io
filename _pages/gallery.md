---
title: "Gallery"
permalink: /gallery/
---

## Fieldwork（野外考察）

{% assign photos = site.static_files | where_exp: "file", "file.path contains 'gallery/field/'" | sort: "path" %}
{% assign count = 0 %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    {% assign count = count | plus: 1 %}
    <a href="{{ photo.path | relative_url }}" target="_blank" rel="noopener" class="gallery-item {% if count > 6 %}hidden-photo{% endif %}">
      <img src="{{ photo.path | relative_url }}" alt="Fieldwork photograph">
    </a>
  {% endif %}
{% endfor %}
</div>

{% if count > 6 %}
<button class="show-more">Show More</button>
{% endif %}


## Laboratory & Research（实验与科研）

{% assign photos = site.static_files | where_exp: "file", "file.path contains 'gallery/lab/'" | sort: "path" %}
{% assign count = 0 %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    {% assign count = count | plus: 1 %}
    <a href="{{ photo.path | relative_url }}" target="_blank" rel="noopener" class="gallery-item {% if count > 6 %}hidden-photo{% endif %}">
      <img src="{{ photo.path | relative_url }}" alt="Laboratory photograph">
    </a>
  {% endif %}
{% endfor %}
</div>

{% if count > 6 %}
<button class="show-more">Show More</button>
{% endif %}


## Academic Activities（学术活动）

{% assign photos = site.static_files | where_exp: "file", "file.path contains 'gallery/academic/'" | sort: "path" %}
{% assign count = 0 %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    {% assign count = count | plus: 1 %}
    <a href="{{ photo.path | relative_url }}" target="_blank" rel="noopener" class="gallery-item {% if count > 6 %}hidden-photo{% endif %}">
      <img src="{{ photo.path | relative_url }}" alt="Academic activity photograph">
    </a>
  {% endif %}
{% endfor %}
</div>

{% if count > 6 %}
<button class="show-more">Show More</button>
{% endif %}


## Group Activities（团队活动）

{% assign photos = site.static_files | where_exp: "file", "file.path contains 'gallery/group/'" | sort: "path" %}
{% assign count = 0 %}

<div class="gallery-grid">
{% for photo in photos %}
  {% assign ext = photo.extname | downcase %}
  {% if ext == ".jpg" or ext == ".jpeg" or ext == ".png" or ext == ".webp" %}
    {% assign count = count | plus: 1 %}
    <a href="{{ photo.path | relative_url }}" target="_blank" rel="noopener" class="gallery-item {% if count > 6 %}hidden-photo{% endif %}">
      <img src="{{ photo.path | relative_url }}" alt="Group activity photograph">
    </a>
  {% endif %}
{% endfor %}
</div>

{% if count > 6 %}
<button class="show-more">Show More</button>
{% endif %}


<style>
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 15px;
  margin: 20px 0 15px 0;
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

.hidden-photo {
  display: none !important;
}

.show-more {
  display: block;
  margin: 10px 0 35px 0;
  padding: 8px 22px;
  background: #f2f2f2;
  border: 1px solid #ccc;
  border-radius: 5px;
  cursor: pointer;
  font-size: 14px;
}

.show-more:hover {
  background: #e5e5e5;
}

@media (max-width: 768px) {
  .gallery-grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }

  .gallery-grid img {
    height: 180px;
  }
}
</style>

<script>
document.addEventListener("DOMContentLoaded", function() {
  document.querySelectorAll(".show-more").forEach(function(button) {
    button.addEventListener("click", function() {
      const gallery = button.previousElementSibling;

      gallery.querySelectorAll(".hidden-photo").forEach(function(photo) {
        photo.classList.remove("hidden-photo");
      });

      button.style.display = "none";
    });
  });
});
</script>
