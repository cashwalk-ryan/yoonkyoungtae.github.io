---
layout: post
title: Kotlin - 타입확인과 캐스팅 (is)
tags: [Kotlin]
date: 2019-05-23 12:00:00
sitemap :
  changefreq : daily
  priority : 1.0
---
# 타입확인과 캐스팅
Java와 Kotlin에서는 타입확인과 캐스팅에 있어서 차이점이 있다.

## Java
우선 자바에서는 instanceof 연산자로 타입확인을 할 수 있다.

    public void test(Object obj) {
        if (obj instanceof String) {
            // String 타입
        }
    }

## Kotlin
코틀린에서는 is 연산자로 타입확인을 할 수 있다.

    fun test(obj: Any) {
        if (obj is String) {
            // String 타입
        }
    }

## 캐스팅에 있어서 Kotlin의 장점
자바에서는 instanceof 연산자를 통과해도 아래와 같이 캐스팅을 해준뒤 String의 형태로 사용 가능하다.

    public void test(Object obj) {
        if (obj instanceof String) {
            String val = (String) obj;
            val.length(); // 캐스팅 된 후 lenth()를 호출
        }
    }

하지만 코틀린에서는 추가로 is 연산자를 통과한 경우 자동으로 **스마트 캐스팅** 을 지원해준다.

    fun test(obj: Any) {
        if (obj is String) {
            obj.length // 스마트 캐스팅 된 후 lenth를 호출
        }
    }

위와 같이 바로 String의 함수를 호출 할 수 있다.

---

즉, is 연산자를 이용하여 타입을 확인하고 obj가 String의 형태면 자동으로 String의 타입으로 캐스팅되어 사용 가능하다.
