---
cssclasses:
  - literature-note
tags:
date-created: "{{exportDate | format('YYYY-MM-DD')}}"
title: "{{title}}"
item-type: "{{itemType | capitalize}}"
signature: {% if archive %}"{{archive}}, {{archiveLocation}}, {{callNumber}}"{% endif %}
authors: {% for creator in creators | filterby("creatorType", "contains", "author") %}
  - "{{creator.lastName}}, {{creator.firstName}}"{% endfor %}
recipient: {% if itemType == "letter" %}"{{recipients}}"{% endif %}
lit-date-daily: {% if itemType == "newspaperArticle" or "report" or "letter" %}"{{date | format("YYYY-MM-DD")}}"{% endif %}
lit-date-yearly: "{{date | format("YYYY")}}"
editors: {% if itemType == "bookSection" %}"{{editors}}"{% endif %}
edited-book: {% if itemType == "bookSection" %}"{{bookTitle}}"{% endif %}
journal: {% if itemType == "journalArticle" %}"{{publicationTitle}}"{% endif %}
DOI: "{{DOI}}"
annotated: {% if annotations %}"true"{% else %}"false"{% endif %}
type: "zotero-entry"
---
# {{authors}}: {{title}} ({{date | format("YYYY")}})

>[!info] Metadata
>
>* Title: {{title}}
>* Item Type: {{itemType | capitalize}}{% if archive %}
>* Signatur: [[{{archive}}, {{archiveLocation}}, {{callNumber}}]]{% endif %}
>* Autor(s): {{authors}}{% if itemType == "letter" %}
>* Publikum: {{recipients}}{%endif %}{% if itemType == "newspaperArticle" or "report" or "letter" %}
>* Date: {{date | format("YYYY-MM-DD")}}{% else %}
>* Year: {{date | format("YYYY")}}{% endif %}{% if itemType == "bookSection" %}
>* In: {{editors}} (ed.): *{{bookTitle}}*{% elif itemType == "journalArticle" %}
>* In: *{{publicationTitle}}* {{volume}} ({{issue}}){% endif %}{% if DOI %}
>* DOI: {{DOI}}{% endif %}
>* Topics: {% for collection in collections %}[[{{collection.name}}]]{% if not loop.last %}, {% endif %}{% endfor %}
>* Cite key: @{{citekey}}

## Links
[Zotero-Link]({{select}})
{% if attachments %}
{% for attachment in attachments %}{% if attachment.select %}[{{attachment.title}}]({{attachment.select}}){% elif attachment.url %}[Online]({{attachment.url}}){% endif %}{% endfor %}{% endif %}

{%- macro citation(creators, pageLabel, annotlink) %}
{%- set auths = creators | filterby("creatorType", "startswith", "author") -%}
([{% if auths | length < 3 and auths | length != 0 %}{% for na in auths %}{{na.lastName}}{% if not loop.last %} and {% endif %}{% endfor %}{% elif auths | length %}{% for na in creators %}{% if loop.first %}{{na.lastName}} et al.{% endif %}{% endfor %}{% else %}@{{citekey}}{% endif %}](@{{citekey}}), {{date | format("YYYY")}}, [p. {{pageLabel}}]({{annotlink}}))
{% endmacro -%}
{%- set annots = annotations | filterby("date", "dateafter", lastImportDate) %}

{% persist "annotations" %}

{% if annots.length > 0 -%}
## Excerpts and Comments
{% for annot in annots -%}
{%- if annot.annotatedText or annot.imageRelativePath %}
> [!quote{% if annot.color %}|{{annot.color}}{% endif %}]
{%- if annot.annotatedText %}
> {{annot.annotatedText | nl2br}}
{%- endif -%}
{%- if annot.imageRelativePath %}
> ![[{{annot.imageRelativePath}}]]
{%- endif %}
{%- if annot.ocrText %}
> {{annot.ocrText}}
{%- endif %}
>
> {{citation(creators, annot.pageLabel, annot.desktopURI)}}
{%- if annot.comment %}
{{annot.comment | nl2br}}
{% endif %}{% else %}{% if annot.comment %}
{{annot.comment | nl2br}} {{citation(creators, annot.pageLabel, annot.desktopURI)}}{% endif -%}
{%- endif -%}
{%- endfor -%}
{% else %}
## Notes
{% endif %}
{% endpersist %}