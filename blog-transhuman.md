---
layout: base
title: Transhuman
permalink: /blog/transhuman/
category: Transhuman
---

<div class="blog-header">
  <h1>{{ page.title }}</h1>
  <p class="blog-description">Latest thoughts, ideas, and updates</p>
</div>

<div class="post-grid">
  {% assign filtered_posts = site.posts | where_exp: "post", "post.categories contains page.category" %}
  {% for post in filtered_posts %}
    <a href="{{ post.url | relative_url }}" class="post-card">
      <div class="post-image" {% if post.image %}style="background-image: url('{{ post.image | relative_url }}')"{% endif %}>
        {% unless post.image %}
          <div class="placeholder-image">
            <span>{{ post.title | truncate: 1, "" }}</span>
          </div>
        {% endunless %}
        <div class="post-overlay">
          <h2>{{ post.title }}</h2>
          <time datetime="{{ post.date | date_to_xmlschema }}">
            {{ post.date | date: "%B %-d, %Y" }}
          </time>
        </div>
      </div>
    </a>
  {% endfor %}
</div>

<style>
/* Extend the width of the content area for the home layout */
.page-content .wrapper {
    max-width: 100%; /* Adjust this value as needed */
    width: 100%; /* Adjust this value as needed */
}

.post-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1.5rem;
  padding: 0 1rem;
  max-width: 1200px;
  margin: 0 auto;
}

.post-card {
  text-decoration: none;
  color: inherit;
  transition: transform 0.2s;
  display: block;
}

.post-card:hover {
  transform: translateY(-5px);
}

.post-image {
  aspect-ratio: 3/2;
  background: #f8f9fa;
  border-radius: 12px;
  overflow: hidden;
  position: relative;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
}

.placeholder-image {
  width: 100%;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #e9ecef;
  font-size: 2rem;
  font-weight: bold;
  color: #adb5bd;
  text-transform: uppercase;
}

.post-overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  padding: 1.5rem;
  background: linear-gradient(to top, rgba(0,0,0,0.8), rgba(0,0,0,0));
  color: white;
}

.post-overlay h2 {
  font-size: 1.25rem;
  margin: 0 0 0.5rem 0;
  line-height: 1.3;
}

.post-overlay time {
  font-size: 0.875rem;
  opacity: 0.8;
}

@media (max-width: 768px) {
  .post-grid {
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 1rem;
  }
  
  .post-overlay {
    padding: 1rem;
  }
  
  .post-overlay h2 {
    font-size: 1.1rem;
  }
}

.blog-header {
  text-align: center;
  padding: 4rem 1rem;
  background-color: #f8f9fa;
  margin-bottom: 2rem;
}

.blog-description {
  color: #6c757d;
  font-size: 1.25rem;
  margin-top: 1rem;
}

</style>