---
permalink: /
title: "Hi! I'm Charlotte"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
I'm a belgo-luxembourgeoise actuarial researcher currently doing a postdoc at [UQÀM](https://math.UQÀM.ca/) in Montréal 🍁, where I spend my days somewhere between mathematics, (preferably bayesian) statistics, machine learning, and (fair) insurance pricing.

I recently (August 2026) completed my PhD at [UCLouvain](https://uclouvain.be/en/research-institutes/lidam/isba) in Belgium under the supervision of Prof. [Donatien Hainaut](https://sites.google.com/view/donatienhainaut/home). You can find my PhD thesis titled *Non-life insurance analytics* [here]().
I am now happily continuing down the research rabbit hole on the other side of the Atlantic with Prof. [Arthur Charpentier](https://freakonometrics.github.io/) (UQÀM).

My research focuses on using modern statistical and machine learning methods to tackle problems in insurance pricing, with a particular interest in bayesian modeling, fairness, interpretability, uncertainty, and synthetic data.

When I'm not doing research, I'm usually looking for an excuse to go hiking (or to talk about hiking). And, as a Belgian abroad, I feel it is my civic duty to mention Belgian beer somewhere on this page. I affectionately call my last PhD research project the Pesh Mel' Bush model. The name may or may not make considerably more sense after a sufficiently long explanation (or presentation).

So, welcome to my little corner of the internet! Here you can find my research, publications, talks, teaching activities, and forthcoming projects.

<div class="latest-section">

  <div class="latest-header">
    <h2>Latest & Upcoming</h2>
    <!-- <a href="{{ base_path }}/talks/">View all →</a> -->
  </div>

  <div class="latest-list">

    <!-- =========================================================
         UPCOMING TALKS
         ========================================================= -->

    {% assign upcoming_talks = site.talks
      | where: "upcoming", true
      | sort: "date" %}

    {% for post in upcoming_talks limit:2 %}

      <a href="{{ post.url | relative_url }}" class="latest-item">

      <div class="latest-date">
        <span class="latest-month">
          {{ post.date | date: "%b" | upcase }}
        </span>

        <span class="latest-day">
          {{ post.date | date: "%d" }}
        </span>

        <span class="latest-year">
          {{ post.date | date: "%Y" }}
        </span>
      </div>

      <div class="latest-content">

        <div class="latest-meta">
          <span class="latest-badge upcoming">Upcoming</span>
          <span>{{ post.event_type | default: post.type }}</span>
        </div>

        <div class="latest-title">
          {{ post.venue }}
        </div>

        {% if post.location %}
        <div class="latest-venue">
          {{ post.location }}
        </div>
        {% endif %}

      </div>

      <div class="latest-arrow">↗</div>

    </a>

    {% endfor %}


    <!-- =========================================================
         LATEST PUBLICATION
         ========================================================= -->

    {% assign latest_publication = site.publications
      | sort: "date"
      | reverse
      | first %}

    {% if latest_publication %}

      <a href="{{ latest_publication.url | relative_url }}"
         class="latest-item">

        <div class="latest-date">

          <span class="latest-month">
            {{ latest_publication.date | date: "%b" | upcase }}
          </span>

          <span class="latest-year">
            {{ latest_publication.date | date: "%Y" }}
          </span>

        </div>

        <div class="latest-content">

          <div class="latest-meta">
            <span class="latest-badge new">New</span>
            <span>Research</span>
          </div>

          <div class="latest-title">
            {{ latest_publication.title }}
          </div>

          {% if latest_publication.venue %}
          <div class="latest-venue">
            {{ latest_publication.venue }}
          </div>
          {% endif %}

        </div>

        <div class="latest-arrow">↗</div>

      </a>

    {% endif %}


    <!-- =========================================================
         LATEST TALK
         ========================================================= -->

    {% assign completed_talks = site.talks
      | where_exp: "talk", "talk.upcoming != true"
      | sort: "date"
      | reverse %}

    {% assign latest_talk = completed_talks | first %}

    {% if latest_talk %}

      <a href="{{ latest_talk.url | relative_url }}"
        class="latest-item">

        <div class="latest-date">

          <span class="latest-month">
            {{ latest_talk.date | date: "%b" | upcase }}
          </span>

          <span class="latest-year">
            {{ latest_talk.date | date: "%Y" }}
          </span>

        </div>

        <div class="latest-content">

          <div class="latest-meta">
            <span class="latest-badge new">New</span>
            <span>{{ latest_talk.event_type | default: latest_talk.type }}</span>
          </div>

          <div class="latest-title">
            {{ latest_talk.venue }}
          </div>

          {% if latest_talk.location %}
          <div class="latest-venue">
            {{ latest_talk.location }}
          </div>
          {% endif %}

        </div>

        <div class="latest-arrow">↗</div>

      </a>

    {% endif %}

  </div>

</div>