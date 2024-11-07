{% for src_path, stats in src_stats|dictsort %}
{% if stats.snippets_markdown %}

<details>
<summary>{{ src_path | replace(".", "&#46;") }}</summary>

{% for snippet in stats.snippets_markdown %}

{{ snippet }}





---

{% endfor %}

{% endif %}
{% endfor %}
</details>