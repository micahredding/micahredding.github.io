---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: base
---

<!-- Hero Section -->
<section class="hero">
  <div class="hero-content">
    <h1>Faith in our Future</h1>
    <p>Reconcile Faith & Science • Find Meaning & Purpose • Build a Better World</p>
    <p><a href="http://eepurl.com/harg5r" class="cta-button">Get the TEDx talk</a></p>
  <p class="hero-logos">
    <img src="https://res.cloudinary.com/micahredding/e_grayscale/w_160/c_scale/o_25/TEDx_logo1_dmhodp"><img src="https://res.cloudinary.com/micahredding/e_grayscale/w_200/c_scale/o_20/wired"><img src="https://res.cloudinary.com/micahredding/e_grayscale/w_160/c_scale/o_20/bbc"><img src="https://res.cloudinary.com/micahredding/e_grayscale/w_200/c_scale/o_25/motherboard-logo">
  </p>
  </div>
</section>



<div class="post-grid">
  {% for post in site.posts | limit: 21 %}
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

/* Hero Section Styles */
.hero {
  background-size: cover;
  background-position: center;
  padding: 80px 0px;
  text-align: center;
  color: #000;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
}

.hero-logos img {
  max-width:180px;
}

.hero h1 {
  font-size: 5em;
  margin-top: 0;
  margin-bottom: 0;
}

.hero p {
  font-size: 1.2em;
  margin-bottom: 30px;
}

/* Blog section styles */
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
</style>