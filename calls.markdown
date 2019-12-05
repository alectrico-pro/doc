---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: post
title: Api Calls
permalink: /calls/
---
{{ site.data.api.circuitos.first.first }}

{% for resource in site.data.api.circuitos %}

  Parámetros:
  <ol>
  {% for parametro in resource.last.parameters %}
    <li>{{ parametro.name  }} ( {{ parametro.description }} ) </li>
  {% endfor %}
  </ol>

  Ejemplo:
  <ol>
  {% for request in resource.last.requests %}
    request   
    {{ request.request_method }} ( {{ request.request_path }} ) 
    <br>
    <br>
    body
    <br>
      {{ request.request_body }}
    <br>
    <br>
    headers
    <br>
      {{ request.request_headers }}
    <br>
    <br>
    query_parameters
    <br>
    {{ request.query_parameters }}
    <br>
    <br>
    request_content_type
    <br>
    {{ request.request_content_type }}
    <br>
    <br>
    response_status
    <br>
    {{ request.response_status }}
    <br>
    <br>
    response_status_text
    <br>
    {{ request.response_status_text }}
    <br>
    <br>
    Respuesta
    <br>
    {{ request.response_body }}    
    <br>
    <br>
    Headers de la Respuesta
    <br>
    {{ request.response_headers }}
    <ul>
    {% for header in request.response_headers %}
     <li>
      {{ header }}
     </li>
    {% endfor %}
    </ul>
    <br>
    Tipo de respuesta
    <br>
    {{ request.response_content_type }}
    <br>
    Curl
    <br>
    {{ request.curl }}
  {% endfor %}
  </ol>

{% endfor %}

<hr>
Indice de Llamadas Api

{% for example in site.data.api.index.resources.first.examples %}
 <ul>
   <li> {{ example.description }} </li>
   {{ example.method }}
   {{ example.route }}
 </ul>
{% endfor %}


