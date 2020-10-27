---
layout: post
title: PlantUML 을 github md 안에서 사용하기
---

PlantUML 을 github md 안에서 사용하기

>검색 키워드 [github md plantuml](https://www.google.com/search?sxsrf=ALeKk02-Xi-IqyzDrz4DmtVELmavliQEhA%3A1603720426653&ei=6tSWX_u-J8eIr7wPqt67gA0&q=github+md+plantuml&oq=pla
uml+md+github&gs_lcp=CgZwc3ktYWIQAxgAMggIABAIEA0QHjoHCAAQsAMQHlDPZFjEaGCogQFoAXAAeACAAXGIAcgCkgEDMC4zmAEAoAEBqgEHZ3dzLXdpesgBAcABAQ&sclient=psy-ab)


PlantUml 을 Github 내에서 사용하기 

1. PlantUml 작성하기
아래와 같이 sample code를 확장자 .iuml로 지정하고 파일을 추가한다. plantuml 폴더 생성후 test-plantuml.iuml 을 생성하였다.

```
@startuml
actor client
node app
node car
node tshirt

car -> app
app -> client
client -> tshirt
@enduml
```

2. plantuml renderer 를 .md(markdown) 에 삽입
2.1 http://www.plantuml.com/plantuml/proxy?cache=no&src
2.2 src 에 test-plantuml.iuml 의 raw path를 추가한다.
```
![your-plantuml-file-name](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/chaehwanli/chaehwanli.github.io/gh-pages/plantuml/test-plantuml.iuml)
```
이렇게 된다.
```
![test-plantuml](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/chaehwanli/chaehwanli.github.io/gh-pages/plantuml/test-plantuml.iuml)
```
![test-plantuml](http://www.plantuml.com/plantuml/proxy?cache=no&src=https://raw.githubusercontent.com/chaehwanli/chaehwanli.github.io/gh-pages/plantuml/test-plantuml.iuml)

참조 사이트 : https://github.com/jonashackt/plantuml-markdown

이제 동작함.
