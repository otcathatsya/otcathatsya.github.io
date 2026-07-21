---
layout: default
title: Book Notes
description: Personal book reviews and reading notes by Catherine Mia Schofmann.
permalink: /books/
---

# Book Notes

I mostly review books to force myself to critically engage with them. And because I like writing kneejerk reactions to silly reviews I disagree with.

<div class="review-list">
{% assign reviews = site.reviews | where_exp: "review", "review.published != false" | sort: "date" | reverse %}
{% for review in reviews %}
  <article class="review-list-item">
    <p class="review-list-date">{{ review.date | date: "%d %b %Y" }}</p>
    <h2><a href="{{ review.url | relative_url }}">{{ review.title }}</a></h2>
    {% if review.book_author %}<p class="review-list-author">{{ review.book_author }}</p>{% endif %}
    {% if review.summary %}<p>{{ review.summary }}</p>{% endif %}
  </article>
{% else %}
  <p>No book notes yet.</p>
{% endfor %}
</div>
