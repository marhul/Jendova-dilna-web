---
layout: page
title: Galerie
permalink: /galerie/
ext-css:
  - //cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.4/css/lightbox.min.css
ext-js:
  - //cdnjs.cloudflare.com/ajax/libs/jquery/3.7.1/jquery.min.js
  - //cdnjs.cloudflare.com/ajax/libs/lightbox2/2.11.4/js/lightbox.min.js
---

<style>
.gallery-container {
  display: flex;
  flex-wrap: wrap;
  margin: -10px;
}
.gallery-item {
  width: 50%; /* 2 columns */
  padding: 10px;
  box-sizing: border-box;
}
.gallery-item img {
  width: 100%;
  height: 250px; /* Fixed height for consistency */
  object-fit: cover; /* Crop to fit */
  display: block;
  border-radius: 5px;
  transition: transform 0.2s;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
.gallery-item img:hover {
  transform: scale(1.02);
  box-shadow: 0 5px 15px rgba(0,0,0,0.2);
}
@media (max-width: 600px) {
  .gallery-item {
    width: 100%; /* 1 column on mobile */
  }
}
</style>

<div class="gallery-container">
  {% assign image_files = site.static_files | where_exp: "item", "item.path contains 'img/photos'" %}
  {% for file in image_files %}
    {% assign ext = file.extname | downcase %}
    {% if ext == '.jpg' or ext == '.jpeg' or ext == '.png' or ext == '.gif' %}
      <div class="gallery-item">
        <a href="{{ file.path | relative_url }}" data-lightbox="gallery" data-title="{{ file.basename }}">
          <img src="{{ file.path | relative_url }}" alt="{{ file.basename }}">
        </a>
      </div>
    {% endif %}
  {% endfor %}
</div>

<p style="text-align: center; margin-top: 20px; color: #666;">
  <em>Kliknutím na obrázek jej zvětšíte.</em>
</p>
