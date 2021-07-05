---
layout: page
title: Not a typography
description: A story about oranges, design, corruption, and thunderstorms.
permalink: /about/
image: '/images/about/01.jpg'
---

Commit Sans started as a thing and now it's another thing.

<br />


<div class="about">
    <div class="portfolio__gallery animate mb-lg-2">
        <div class="container">
            <h3>Clients</h3>
            <p>People and companies we've worked with</p>
            <div class="row">
                {% for card in site.data.settings.about.clients %}
                    {% include card.html %}
                {% endfor %}
            </div>
        </div>
    </div>
    <div class="portfolio__gallery animate mb-lg-2">
        <div class="container">
            <h3>The Core Team</h3>
            <p>The foundations</p>
            <div class="row">
                {% for card in site.data.settings.about.core %}
                    {% include card-horizontal.html %}
                {% endfor %}
            </div>
        </div>
    </div>
    <div class="portfolio__gallery animate mb-lg-2">
        <div class="container">
            <h3>The Network</h3>
            <p>People we work/have worked with</p>
            <div class="row">
                {% for card in site.data.settings.about.network %}
                    {% include card.html %}
                {% endfor %}
            </div>
        </div>
    </div>
    <div class="portfolio__gallery animate mb-lg-2">
        <div class="container">
            <h3>The Wishlist</h3>
            <p>People we want to work with</p>
            <div class="row">
                {% for card in site.data.settings.about.wishlist %}
                    {% include card.html %}
                {% endfor %}
            </div>
        </div>
    </div>
</div>