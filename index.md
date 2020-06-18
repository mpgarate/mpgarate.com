---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: Michael Garate
---

## Blog

<ul>
  {% for post in site.posts limit:3 %}
    <li>
      <a href="{{ post.url }}" alt="{{ post.title }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

## Open Source
### Optimizing fastText vector exports
Etsy uses [fastText](https://github.com/facebookresearch/fastText/) to generate word vectors for a variety of ML applications. [This optimization](https://github.com/facebookresearch/fastText/pull/843) allows fastText to serialize floating point values using multiple cores, which reduced the runtime of many Etsy workloads from hours to minutes.
