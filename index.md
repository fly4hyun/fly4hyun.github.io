---
layout: resume
---

# {{ site.name }}
{{ site.title }}

Email: [{{ site.email }}](mailto:{{ site.email }})  
{% if site.phone %}Phone: {{ site.phone }}{% endif %}  
{% if site.website %}Web: [{{ site.website }}]({{ site.website }}){% endif %}

---

## About Me
{{ site.about_content }}

---

{% for section in site.content %}
### {{ section.title }}

{% if section.layout == "list" %}
{% for item in section.content %}
**{{ item.title }}**  
{% if item.sub_title %} *{{ item.sub_title }}*{% endif %}  
{% if item.caption %} <span style="font-size:0.9em;color:gray;">{{ item.caption }}</span> {% endif %}  
{% if item.quote %}> {{ item.quote }}{% endif %}

{{ item.description | markdownify }}

---

{% endfor %}
{% elsif section.layout == "text" %}
{{ section.content | markdownify }}
{% endif %}
{% endfor %}
