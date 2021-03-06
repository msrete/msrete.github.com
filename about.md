---
layout: page
permalink: /about/index.html
title: Simon Jang
tags: [Simon, Jang, 민석, 장민석]
imagefeature: fourseasons.jpg
chart: true
---
<figure>

</figure>

{% assign total_words = 0 %}
{% assign total_readtime = 0 %}
{% assign featuredcount = 0 %}
{% assign statuscount = 0 %}

{% for post in site.posts %}
    {% assign post_words = post.content | strip_html | number_of_words %}
    {% assign readtime = post_words | append: '.0' | divided_by:200 %}
    {% assign total_words = total_words | plus: post_words %}
    {% assign total_readtime = total_readtime | plus: readtime %}
    {% if post.featured %}
    {% assign featuredcount = featuredcount | plus: 1 %}
    {% endif %}
{% endfor %}



내 이름은 **장민석** , **Simon Jang**. 이곳은 나의 첫 개인블로그다. 이 블로그는 현재 {{ site.posts | size }} 개의 게시글이 {{ site.categories | size }} 개의 카테고리안에 {{ total_words }} 개의 단어로 이루어져 있으며, 평균 구독시간 ({{ site.wpm }} WPM) 약 <span class="time">{{ total_readtime }}</span> 분 정도 걸린다. {% if featuredcount != 0 %} 현재 <a href="{{ site.url }}/featured">{{ featuredcount }} 중요게시글</a>이 있고, Git과 Jekyll을 활용하고자 한다면 꼭 확인해보길 바란다. {% endif %} 가장 최근 게시글인 {% for post in site.posts limit:1 %}{% if post.description %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}">"{{ post.title }}"</a>{% else %}<a href="{{ site.url }}{{ post.url }}" title="{{ post.description }}" title="Read more about {{ post.title }}">"{{ post.title }}"</a>{% endif %}{% endfor %} 은 {% for post in site.posts limit:1 %}{% assign modifiedtime = post.modified | date: "%Y%m%d" %}{% assign posttime = post.date | date: "%Y%m%d" %}<time datetime="{{ post.date | date_to_xmlschema }}" class="post-time">{{ post.date | date: "%d %b %Y" }}</time>{% if post.modified %}{% if modifiedtime != posttime %} and last modified on <time datetime="{{ post.modified | date: "%Y-%m-%d" }}" itemprop="dateModified">{{ post.modified | date: "%d %b %Y" }}</time>{% endif %}{% endif %}{% endfor %}에 작성되었다. 마지막 커밋시각은 {{ site.time | date: "%A, %d %b %Y" }} at {{ site.time | date: "%I:%M %p" }} [UTC](http://en.wikipedia.org/wiki/Coordinated_Universal_Time "Temps Universel Coordonné")이다.

현재 [**한국기술교육대학교**](http://www.koreatech.ac.kr/) 에서 [컴퓨터공학](http://cse.kut.ac.kr/)을 전공하고 있다. 졸업작품으로 NF를 이용한 관광관리 시스템을 제작했으며, 사용한 알고리즘을 정보통신학회에서 **상황인식 기반의 관광소셜 네트워크 서비스 응용** 이라는 논문으로 발표했으며, 우수논문상을 수여받았다.

<figure>
	<img src="{{ site.url }}/images/paper.jpg" alt="Tour Social Network Service System Using Context Awareness">
	<figcaption>Tour Social Network Service System Using Context Awareness</figcaption>
</figure>

또한 알고리즘에 대해 **NFC를 이용한 낙서관리 시스템 및 이를 이용한 낙서관리 서비스 제공방법** 이라는 특허를 출원한 상태이다.

<figure>
	<img src="{{ site.url }}/images/patent.jpg" alt="The Request">
	<figcaption>The Request</figcaption>
</figure>

