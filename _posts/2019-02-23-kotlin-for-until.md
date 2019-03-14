---
layout: post
title: Kotlin - for문의 until
tags: [kotlin, for문, until]
date: 2019-02-23 12:00:00
sitemap :
  changefreq : daily
  priority : 1.0
---

# Kotlin 토이 프로젝트!
요새 kotlin으로 토이 프로젝트를 만들고 있다. 처음으로 코틀린을 사용하여 만드는 프로젝트라 만들면서 알게된 kotlin 문법에 대해 알게 된 것들을 정리할 예정이다.

## for문의 until.
kotlin을 사용하면서 java와 for문의 사용법이 달랐던 부분이 있었다.

[Java]

    for(int i=0; i<list.size(); i++) {
        //
    }

나는 보통 java에서 for문을 사용할 때 list.size()보다 미만의 사이즈를 사용하는 편이다.

[Kotlin]

    for(i in 0..list.size()) {
        //
    }

 하지만 kotlin에서는 list.size()를 사용하면 0부터 size()까지의 for문을 돌면서 OutOfIndexException이 발생했다.

     for(i in 0..list.size() - 1) {
         //
     }

이렇게 size()에 -1을 주어 컨트롤 하는 방법도 있지만 검색해보니 kotlin에서는 **until** 이라는 키워드를 제공했다.

    for(i in 0 until list.size()) {
        //
    }

위와 같이 **until** 을 **..** 를 대신해 사용하면 원하는 대로 for문을 돌릴 수 있게 된다.
