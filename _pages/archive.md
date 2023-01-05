---
layout: page
permalink: /archive/
---

[Reverie](https://github.com/amitmerchant1990/reverie) is a Jekyll theme which is simple and opinionated. It's actually a fork of [jekyll-now](https://github.com/barryclark/jekyll-now) with some additional features and personal touches which I've implemented to suit my needs for [my blog](https://www.amitmerchant.com).

This is a plug-and-play Jekyll theme which you can use on GitHub Pages without even setting up a local environment.

## Features

- Command-line free fork-first workflow, using GitHub.com to create, customize and post to your blog
- Fully responsive and mobile optimized base theme
- Sass/Coffeescript support using Jekyll 2.0
- Free hosting on your GitHub Pages user site
- All the SEO goodies comes in-built
- Markdown blogging
- Syntax highlighting using Pygments
    - [Dracula syntax theme](https://draculatheme.com/) included
- Disqus commenting
- Google Analytics integration
- Fuzzy search across blog posts
- Pagination of posts works out-of-the-box.
- Categorize posts out-of-the box
- RSS Feed
- In-built sitemap

Learn more about it [here](https://github.com/amitmerchant1990/reverie) on how to get started.

<div id="archives">
  <section id="archive">
     <h3>Most Recent Posts</h3>
      {%for post in site.posts %}
      {% unless post.next %}
      <ul class="this">
          {% else %}
          {% capture month %}{{ post.date | date: '%B %Y' }}{% endcapture %}
          {% capture nmonth %}{{ post.next.date | date: '%B %Y' }}{% endcapture %}
          {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
          {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
          {% if year != nyear %}
      </ul>
      <h2 style="text-align:left;">{{ post.date | date: '%Y' }}</h2>
      <ul class="past">
          {% endif %}
          {% if month != nmonth %}
          <h3 style="text-align:left;">{{ post.date | date: '%B %Y' }}</h3>
          {% endif %}
          {% endunless %}
          <p><b><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></b> - {% if post.date and post.date != "" %}{{ post.date | date: "%e %B %Y" }}{%endif%}</p>
          {% endfor %}
      </ul>
    <h3>Oldest Posts</h3>
  </section>
</div>
