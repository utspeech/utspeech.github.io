{{ $name := .Name }}{{ $date := .Date }}{{ range $key, $value := .Site.Data.meetings }}{{ if eq $key $name }}{{ with $value }}---
title: "{{ .title | title }}"
date: {{ $date }}
draft: true
---

On {{ dateFormat "January 2, 2006" .date }} at {{ .time }} EST, {{ if ne .website nil }}[{{ .speaker }}]({{ .website }}){{ else }}{{ .speaker }}{{ end }} from {{ .affiliation }} will be presenting "{{ .title | title }}." [Zoom link]({{ .zoom }}).{{ if ne .abstract nil }}

## Abstract

{{ .abstract | markdownify }}{{ end }}{{ end }}{{ end }}{{ end }}
