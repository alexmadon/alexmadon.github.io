---
date: '2017-10-21T03:10:00.001-0700'
tags: linux screencast
---

to do shell screen cast, you can use asciinema

```sh
asciinema play asciicast-98639.json 
```

jq will dump the session:

```sh
jq -r '[.stdout[][1]]|add ' asciicast-98639.json  > tt
```