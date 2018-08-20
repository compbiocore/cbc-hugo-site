---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
description: ""
github_repo: "{{ print "https://www.github.com/compbiocore/" .Name }}"
documentation_page: "{{ print "https://compbiocore.github.io/" .Name }}"
draft: true
---
