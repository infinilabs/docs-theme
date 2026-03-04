---
title: "{{ .Title }}"
date: {{ .Date.Format "2006-01-02" }}
{{- with .Lastmod }}
lastmod: {{ .Format "2006-01-02" }}
{{- end }}
{{- with .Description }}
description: "{{ . }}"
{{- end }}
{{- with .Params.tags }}
tags: [{{ range $i, $e := . }}{{ if $i }}, {{ end }}"{{ $e }}"{{ end }}]
{{- end }}
{{- with .Params.categories }}
categories: [{{ range $i, $e := . }}{{ if $i }}, {{ end }}"{{ $e }}"{{ end }}]
{{- end }}
{{- with .Summary }}
summary: "{{ . | plainify }}"
{{- end }}
---

{{ .RawContent }}