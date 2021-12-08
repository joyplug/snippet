---
layout: post
title:  "[shell] grep Vs select-string"
date:   2021-11-10 09:00:00 +0900
categories: [shell]
---

#### Linux Shell
```bash
grep -nir "world" .
```
<br>

#### Window PowerShell
```bash
select-string *.txt -pattern "world"
select-string *, */* -pattern "world"
```
<br>