---
title: 文章
subtitle: 收錄短文、段落、Paro片段與隨筆
---

<div class="card small">
  雙子欠草債就寫一篇
</div>

{% assign sorted_articles = site.articles | sort: 'date' | reverse %}
{% for a in sorted_articles %}
<div class="card">
  <div class="small">{{ a.date | date: "%Y-%m-%d" }}{% if a.series %} · {{ a.series }}{% endif %}</div>
  <div style="font-weight:700; font-size:18px; margin-top:4px;">
    <a href="{{ a.url | relative_url }}">{{ a.title }}</a>
  </div>
  {% if a.excerpt %}
    <div class="small" style="margin-top:8px;">{{ a.excerpt | strip_html | truncate: 140 }}</div>
  {% endif %}
</div>
{% endfor %}
