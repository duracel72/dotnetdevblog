---
title: "Willkommen im Blog"
excerpt: "Technik, Tipps und tiefes Wissen aus dem .NET-Kosmos"
---

<nav style="text-align: center; font-weight: bold; margin-bottom: 2rem;">
  <a href="/">Start</a> |
  <a href="/about/">Über mich</a> |
  <a href="/kontakt/">Kontakt</a>
</nav>


# Willkommen auf meinem Blog

Dies ist mein Blog rund um .NET, mit Tipps, Beispielen und Erfahrungen aus der Praxis.

---

{% for post in site.posts %}
  - [{{ post.title }}]({{ post.url }}) – {{ post.date | date: "%d.%m.%Y" }}
{% endfor %}

<hr>
<footer style="text-align: center; font-size: 0.9em; color: #666; margin-top: 2rem;">
  <p>
    © {{ "now" | date: "%Y" }} Michael Schneider · 
    <a href="https://schneider-michael.de/home/Impressum">Impressum</a> · 
    <a href="/kontakt/">Kontakt</a>
  </p>
</footer>