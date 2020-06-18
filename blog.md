## Blog

{% for post in site.posts %}
<h3><a href="{{ post.url }}" alt="{{ post.title }}">{{ post.title }}</a></h3>
<blockquote><p>{{ post.excerpt }}</p></blockquote>
<a href="{{ post.url }}" alt="{{ post.title }}">Read more</a>

{% endfor %}
