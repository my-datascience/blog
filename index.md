---
title: About this blog
---
<h1>Welcome</h1>

This is my personal datascience portfolio blog. I write this with these purposes in mind:

1. To show my potential employers some of my knowledge and skills (though this blog is incomplete for this purpose).
2. For me to have sort of a library of topics that I might want to get back to later. (It happenes to me from time to time that I need to use a concept that I know I learned and once understood, but it was a long time ago and I don't ember all the details.)
3. To refresh my skills and knowledge and to kick start my datascience thinking again (see more in the upcoming article *About me*).
4. To fulfill my long-term dream of writing a datascience blog.


I'm not fully documenting my whole datascience journey here. At least not now. I'm only including topics that I'm struggling with (and I learn them by writing about them) or I think are worth having here due to other reasons.

Also, I'm not focusing on the beauty of the blog. Creating websites is not something I'm good at or even interested in. That is why I want a simple blog that allows me to focus on the content.


<h1>Articles</h1>
<ul>
  {% assign grouped = site.articles | group_by_exp:"item", "item.path | split: '/' | slice: 1, 1" %}
  {% for group in grouped %}
    <li>
      {{ group.name }}
      <ul>
        {% for article in group.items %}
          <li><a href="{{ article.url | relative_url }}">{{ article.title }}</a></li>
        {% endfor %}
      </ul>
    </li>
  {% endfor %}
</ul>