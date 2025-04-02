---
layout: page
title: Writing and Talks
permalink: /publications/
---

I write and speak on matters organizational and love translating books that more people should read.
Most publications are connected to my core interest in strategy implementation, but matters have shifted over time.  
Here is a list.

### Books
Books I have written or contributed to:  
{% for book in site.data.publications.books %}
#### {{ book.title }}

* **Author:** {{ book.author }}
* **Publisher:** {{ book.publisher }}
* **Year:** {{ book.year }}
* **ISBN:** {{ book.isbn }}
* **Summary:** {{ book.summary }}
* **More info:** <{{ book.link }}>

---
{% endfor %}
  
### Articles & Papers
Articles published in journals, magazines, and online publications:

{% for article in site.data.publications.articles %}
#### {{ article.title }}

* **Author:** {{ article.author }}
* **Publication:** {{ article.publication }}
* **Year:** {{ article.year }}
* **Volume/Issue:** {{ article.volume_issue }}
* **Abstract:** {{ article.abstract }}   
* [Link to Article]({{ article.link }})

---
{% endfor %}

### Talks
Talks held publicly:  

{% for talk in site.data.publications.talks %}
**{{ talk.title }}**  
_{{ talk.event }}_ – _{{ talk.location }}_ – _{{ talk.date }}_  
{{ talk.description }}  ([Slides/Video]({{ talk.link }}))
  
{% endfor %}