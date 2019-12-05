---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: post
title: Api Calls
permalink: /calls/
---
{{ site.data.api.circuitos.first.first }}

Parámetros:

{% for resource in site.data.api.circuitos %}

  <ol>
  {% for parametro in resource.last.parameters %}
    <li>{{ parametro.name  }} ( {{ parametro.description }} ) </li>
  {% endfor %}
  </ol>

  <ol>
  {% for request in resource.last.requests %}
    <li>{{ request.request_method }} ( {{ request.request_path }} ) </li>
  {% endfor %}
  </ol>

{% endfor %}

<hr>
{% for example in site.data.api.index.resources.first.examples %}
 <ul>
   <li> {{ example.description }} </li>
   {{ example.method }}
   {{ example.route }}
 </ul>
{% endfor %}


