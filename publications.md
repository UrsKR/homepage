---
layout: page
title: Writing and Talks
permalink: /publications/
---

I write and speak on matters organizational. Also, I love translating books that more people should read.
Most publications are connected to my core interest in strategy implementation, but matters have shifted over time. Here is a list.

Would you like me to speak at your conference or user group? I would love to contribute. 

### Books
Books I have written or contributed to.

{% for book in site.data.publications.books %}
_{{ book.author }}_  
**{{ book.title }}**  
{{ book.publisher }}, {{ book.year }}  
ISBN: {{ book.isbn }}  
{{ book.summary }}  
[Publisher's website]({{ book.link }})

{% endfor %}
  
### Articles & Papers
Articles published in journals, magazines, and online publications.

{% for article in site.data.publications.articles %}
_{{ article.author }}_  
**{{ article.title }}**  
{{ article.publication }}, {{ article.year }}. {% if article.issue %} Issue {{article.issue }} {% endif %}  
{{ article.abstract }}  
[Read the article]({{ article.link }})

{% endfor %}

### Talks
Conference talks I held publicly. Most were given multiple times, this list has only the first showing. 

{% for talk in site.data.publications.talks %}
**{{ talk.title }}**  
_{{ talk.event }}_ – _{{ talk.location }}_ – _{{ talk.date }}_  
{{ talk.description }}  ([Slides]({{ talk.slides }}){% if talk.video %} | [Video]({{talk.video }}){% endif %})
  
{% endfor %}

### Interviews, Podcasts etc.
Listen! Watch!  

{% for show in site.data.publications.shows %}
**{{ show.title }}**  
_{{ show.series }} with {{ show.host }}_ – _{{ show.date }}_  
{{ show.description }} ({% if show.link %}[Link]({{ show.link }}){% endif %}{% if show.link and show.video %} | {% endif %}{% if show.video %}[Video]({{show.video }}){% endif %})
  
{% endfor %}