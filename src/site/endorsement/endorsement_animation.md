---
title: 'Endorsement test'
githubLink:
dateStartedString: { day: '10', month: '01', year: '2024' }
language: { en: 'english', iso6392B: 'eng-3', locale: 'english' }
chapterid: { chapterid: endorsement, chapterid_subid: 'animation'}
translators: []
layout: endorsement
pageOrder: 1
parmalink: "/endorsement/animation/"
---
<h1>This is a test page for pulling data from external folder.</h1>
This page is lacking *.json file to determine permalink definition, etc.
<p>Number of Repositories: {{ repos.length }}</p>
<br>
{%- if repos.length > 0 -%}
<h1>animation</h1>
    {%- for repo in repos -%}
        {%- for item in repo['tags'] -%}
            {%- if 'animation' == item -%}    
            <div>
              <a href="{{ repo.download_url }}" target="_blank">{{ repo.name }}</a>
              {%- if repo.description.length > 0 -%}
                {{ repo.description }}
              {%- endif -%}    
                {%- readdynamiccode repo.download_url -%}
            </div>
            {%- endif -%}
        {% endfor %}
    {%- endfor -%} 

{%- else -%}
    <p>No repository data to display</p>
{%- endif -%}