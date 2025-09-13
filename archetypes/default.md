---
title: "{{ replace .Name "-" " " | title }}"
date: {{ .Date }}
draft: false  # 修改为false，Hugo将构建draft: false的帖子
---