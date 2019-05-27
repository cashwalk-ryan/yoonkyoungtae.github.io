---
layout: post
title: Kotlin - 유용한 for문
tags: [Kotlin]
date: 2019-05-27 12:00:00
sitemap :
  changefreq : daily
  priority : 1.0
---
## 반복문의 선언
Kotlin에서 for문은 다양하고 편리하게 이용할 수 있다. for문의 반복을 결정할 때, range 개념을 사용하는데 '1..100' 처럼 콤마 두개로 선언한다. '1..100'의 의미는 첫번째 인덱스부터 마지막 인덱스를 포함하여 반복한다는 의미이다.

    // 1부터 100까지 반복
    for (i in 1..100) {}

    // 1부터 99까지 반복 (100을 포함하지 않는다)
    for (i until 1..100) {}

    // 2부터 100까지 2씩 증가하며 반복
    for (i in 2..100 step 2) {}

    // 100부터 1까지 감소하며 반복
    for (i in 100 downTo 1) {}

    // 100부터 1까지 감소 2씩 감소하며 반복
    for (i in 100 downTo 1 step 2) {}

**until, step, downTo** 는 Java에서는 없었기 때문에 잘 기억 해두어야 적당한곳에 사용 할 수 있을것이다.



## 반복문의 탈출 (라벨 이용)
Kotlin의 for문 탈출 방법 중 라벨(label)이라는 명령어가 있다. 흔히 중첩 for문등을 사용하면서 안쪽 for문에서 break, continue 명령어를 사용하면 해당 for문에만 명령어가 적용된다. 하지만 라벨을 이용하면 특정 for문에 명령어를 지정하여 사용 할 수 잇다.

    testLabel@ for(i in list) {
        for(j in list2) {
            if (true) {
                break@testLabel
            }    
        }
    }

위의 for문에서 break@testLabel 이라는 선언이 보인다. 원래대로 break만 선언했다면 j index의 for문만 break가 적용되고 나머지 i index for문은 남은 데이터를 처리하며 반복하겠지만, testLabel을 i index라벨을 붙이고 break@testLabel의 형태로 선언한다면 i index for문에 break가 적용된다.



---
