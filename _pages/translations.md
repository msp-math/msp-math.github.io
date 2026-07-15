---
layout: page
title: translations
permalink: /translations/
description: A collection of literary works I've translated between English and Korean.
nav: false
---

<style type="text/css">
  .translations-list {
    --tr-font-en: "Courier Prime", "Courier New", ui-monospace, monospace;
    --tr-font-ko: "Nanum Myeongjo", serif;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 1.25rem;
    margin-top: 1.5rem;
  }

  .translations-list .tr-card {
    display: flex;
    flex-direction: column;
    height: 100%;
    padding: 1.4rem 1.5rem;
    border: 1px solid var(--global-divider-color);
    border-radius: 8px;
    background-color: var(--global-card-bg-color);
    transition: transform 0.15s ease, box-shadow 0.15s ease;
  }

  .translations-list a.tr-card-link {
    text-decoration: none;
    color: inherit;
  }

  .translations-list a.tr-card-link:hover .tr-card {
    transform: translateY(-3px);
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.12);
  }

  .translations-list .tr-card-orig {
    font-family: var(--tr-font-ko);
    font-weight: 800;
    font-size: 1.25rem;
    line-height: 1.35;
    color: var(--global-text-color);
    margin-bottom: 0.35rem;
  }

  .translations-list .tr-card-title {
    font-family: var(--tr-font-en);
    font-style: italic;
    font-size: 0.95rem;
    color: var(--global-text-color-light);
    margin-bottom: 0.9rem;
  }

  .translations-list .tr-card-meta {
    margin-top: auto;
    font-family: var(--tr-font-en);
    font-size: 0.8rem;
    letter-spacing: 0.02em;
    color: var(--global-text-color-light);
  }

  .translations-list .tr-card-meta .tr-dot {
    margin: 0 0.4rem;
    opacity: 0.6;
  }
</style>

{% assign sorted_translations = site.translations | sort: "importance" %}

<div class="translations-list">
{% for work in sorted_translations %}
  <a class="tr-card-link" href="{{ work.url | relative_url }}">
    <div class="tr-card">
      {% if work.original_title %}
        <div class="tr-card-orig">{{ work.original_title }}</div>
      {% endif %}
      <div class="tr-card-title">{{ work.title }}</div>
      <div class="tr-card-meta">
        {% if work.author %}{{ work.author }}{% endif %}
        {% if work.author and work.year %}<span class="tr-dot">·</span>{% endif %}
        {% if work.year %}{{ work.year }}{% endif %}
      </div>
    </div>
  </a>
{% endfor %}
</div>
