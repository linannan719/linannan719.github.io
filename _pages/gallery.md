---
title: "Gallery"
permalink: /gallery/
---

## Fieldwork

{% assign gallery = site.static_files | where_exp: "file", "file.path contains '/images/gallery/'" %}

<div class="gallery">
  {% for image in gallery %}
    {% if image.extname == ".jpg" or image.extname == ".jpeg" or image.extname == ".png" %}
      <a href="{{ image.path | relative_url }}" target="_blank">
        <img src="{{ image.path | relative_url }}" alt="Research photograph">
      </a>
    {% endif %}
  {% endfor %}
</div>

<style>
.gallery {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 15px;
  margin-top: 20px;
}

.gallery img {
  width: 100%;
  height: 220px;
  object-fit: cover;
  border-radius: 5px;
  transition: transform 0.2s ease;
}

.gallery img:hover {
  transform: scale(1.03);
}

@media (max-width: 768px) {
  .gallery {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
