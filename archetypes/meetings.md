{{- $nameFmtErr := "File name '%s' should be of the form YYYY-MM-DD-speaker-id\n" -}}
{{- $lst := (split .Name "-") -}}
{{- if (ne (len $lst) 4) -}}
    {{- errorf $nameFmtErr .Name -}}
{{- end -}}
{{- $date := (delimit (first 3 $lst) "-") -}}
{{- $speaker := last 1 $lst  -}}
{{- if eq (index $.Site.Taxonomies.speakers $speaker) nil -}}
    {{- errorf "Speaker %s has not been created in content/speakers/ yet!\n" $speaker -}}
{{- end -}}
---
title: "Title goes here: Subtitle here"
speakers: {{ index $speaker 0 }}  # speaker id
date: {{ $date }}  # date of talk
publishDate: {{ .Date }}
time: "10:30"  # Time of talk (HH:MM 24-hr)
zoom:  # Zoom link goes here (if available)
archive:  # Archived video link goes here (if different from Zoom link)
abstract: >
    Multiline abstract
    goes here
draft: true  # remove when ready to publish
---
<!-- Content here will show up after meeting details and before abstract -->