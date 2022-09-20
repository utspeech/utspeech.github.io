<!-- markdownlint-disable -->
| Date | Speaker | Affiliation | Title/Link |
| ---- | ------- | ----------- | ---------- |
{{ range sort .Site.Data.meetings "date" "desc" }}| {{ dateFormat "January 2, 2006" .date }} | {{ if ne .website nil }}[{{ .speaker | markdownify }}]({{ .website }}){{ else }}{{ .speaker }}{{ end }} | {{ .affiliation | markdownify }} | {{ if ne .archive nil }}[{{ default "Link" .title | markdownify }}]({{ .archive }}){{ else if ne .zoom nil }}[{{ default "Link" .title | markdownify }}]({{ .zoom }}){{ else }}{{ .title | markdownify }}{{ end }} |
{{ end }}
