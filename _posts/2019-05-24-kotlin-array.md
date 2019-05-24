---
layout: post
title: Kotlin - 타입 지정배열
tags: [Kotlin]
date: 2019-05-24 12:00:00
sitemap :
  changefreq : daily
  priority : 1.0
---
# Kotlin에서의 배열
Kotlin에서 Array 배열을 생성할 때 흔히 **arrayOf()** 함수를 이용하곤 한다. 하지만 이 함수로 생성된 배열은 모든 데이터 타입을 전부 추가할 수 있다. 만약 String 타입을만을 받고 싶다면 어떻게 해야 할까?



## Java와 Kotlin의 차이점
Java에서는 String을 받고 싶은 배열은 아래와 같이 제너릭 선언을 통해 얻을 수 있었다.

    List<String> list = new ArrayList<String>()

Kotlin에서도 똑같이 제너릭 선언을 통해 타입을 지정할 수 있다.

    var list = arrayOf<String>()
    list[0] = "value1"
    list[1] = 100
    list[2] = "value2"

위의 예시처럼 입력했을 경우 **list[1] = 100** 에서는 **The integer literal does not conform to the expected type String** 에러가 발생한다.

또한, Kotlin에서는 제너릭을 입력하지 않고도 타입별 Array를 생성할 수 있는 함수가 존재한다.

    booleanArrayOf()
    intArrayOf()
    longArrayOf()
    ...
