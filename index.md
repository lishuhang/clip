---
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: page
title: 首页
---

免责声明：

1. 所有摘录的文段均来自互联网，摘录时都会给出相应的文章名称、作者、发布日期、网址等信息。

2. 摘录行为不代表航通社对被摘录的文段赞成、反对或持有任何观点倾向，也不代表航通社对其中文章的真实性做背书，文章原作者拥有对文段的最终解释权。

3. 只有每段书摘的【标题】是航通社根据文意概括后自拟的。如果文章作者认为标题与文意不符或有其他问题，可以与航通社联系修改。

4. 书摘的“日期”是指文章首发日期，而不是航通社看到或者摘录文章的日期，因此今后可能会添加日期为几年前的文章。

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <div id="#{{ category_name | slugize }}"></div>
    <p></p>
    
    <h3 class="category-head" style="color:#999;">{{ category_name }}</h3>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <article class="archive-item">
    {% assign date_format = site.cayman-blog.date_format | default: "%Y-%m-%d" %}
      <h4>{{ post.date | date: date_format }}&nbsp;•&nbsp;<a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
</div>