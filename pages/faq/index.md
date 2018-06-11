---
layout: course
title: FAQ's
title_long: Frequently Asked Questions
permalink: faq/
---

> **tip**
>  
> FAQ's is a collection in Jekyll. They are registred as a collection in the `_config.yml` file. A **faq** doesn't have a physical output. FAQ's will be listed in this page. FAQ's can be added in the `_faqs` folder under the root of the Jekyll application. Each faq is a separate file under this folder with an unique filename (but the name doesn't matter for the user interface).
{:.alert.alert-tip} 

{% assign faqs = site.faqs %}
{% for faq in faqs %}
<article class="faq">
    <h2 class="faq__title" id="{{ faq.question | slugify }}">{{ faq.question }}</h2>
    <div class="faq__body">{{ faq.content }}</div>
</article>
{% endfor %}