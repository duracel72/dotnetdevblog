---
layout: home
title: "Willkommen im Blog"
excerpt: "Technik, Tipps und tiefes Wissen aus dem .NET-Kosmos"
---

# Willkommen auf meinem Blog

Dies ist mein Blog rund um .NET, mit Tipps, Beispielen und Erfahrungen aus der Praxis.

---

{% for post in site.posts %}
  - [{{ post.title }}]({{ post.url }}) – {{ post.date | date: "%d.%m.%Y" }}
{% endfor %}