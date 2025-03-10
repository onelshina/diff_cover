# Diff Coverage - {{ report_name }}

## Summary

- **Total**: {{ total_num_lines }} {% trans count=total_num_lines %}line{% pluralize %}lines{% endtrans %}

- **Missing**: {{ total_num_violations }} {% trans count=total_num_violations %}line{% pluralize %}lines{% endtrans %}

- **Coverage**: {{ total_percent_covered }}%

{% if src_stats %}
{% for src_path, stats in src_stats|dictsort %}
{% if stats.percent_covered < 100 %}
- {{ src_path | replace(".", "&#46;") }} ({{ stats.percent_covered|round(1) }}%): Missing lines {{ stats.violation_lines|join(',') }}
{% else %}
- {{ src_path | replace(".", "&#46;") }} (100%)
{% endif %}
{% endfor %}

{% else %}
No lines with coverage information in this diff.
{% endif %}

<details>
<summary>TEST DETAILS</summary>
{% include 'snippet_content.md' %}
</details>
