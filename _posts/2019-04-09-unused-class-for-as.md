---
layout: post
title: Android Studio Unused Class 찾기
tags: [Android]
date: 2019-04-09 12:00:00
sitemap :
  changefreq : daily
  priority : 1.0
---
# 분리수거
>**IDE Environment**  
Android Studio 3.3.2  
Build #AI-182.5107.16.33.5314842, built on February 16, 2019  
JRE: 1.8.0_152-release-1248-b01 amd64  
JVM: OpenJDK 64-Bit Server VM by JetBrains s.r.o  
Windows 10 10.0

최근 프로젝트 리팩터링을 진행하면서 그동안 미뤄두었던 문제들을 해결하고자 했다. 문제 중 현재 사용하고 있지 않은 resource 및 class들을 제거하고 싶었는데 미사용 파일의 양이 많아 하나씩 체크하는 데에 많은 시간을 소모하고 있었다.  

## Resource.
---
Android Studio에서 사용하지 않는 resource 파일들은 전체 검색을 이용해 'unused' 정도만 검색하면 나오기 때문에 쉽게 찾을 수 있었다.

![2019-04-09-2](/assets/2019-04-09-2.jpg)
최상단에 unuserd Resources... 를 볼 수 있다.

>검색창의 단축키는  
Windows : **control + shift + A**  
Mac : **command + shift + A**  
각종 기능들을 검색할 때 유용하다.

## Class?
---
unused resource는 쉽게 찾을 수 있지만 unused class는 쉽게 검색이 되지 않았다. 구글의 힘을 빌려 찾아 본 결과 아래와 같이 검색하면 찾을 수 있었다.

![2019-04-09-3](/assets/2019-04-09-3.jpg)
Analze - Run Inspection by name...을 선택한다.  

![2019-04-09-4](/assets/2019-04-09-4.jpg)
검색창이 뜨면 resource와 똑같이 'unused'를 검색하고, 하단에 Unused declaration을 클릭한다.
*(Java라고 명시되어 있기 때문인지 unused kotlin file은 검색이 되지 않았다.)*  

![2019-04-09-5](/assets/2019-04-09-5.jpg)
Inspection scope는 검색할 범위, Inspection options에서는 검색하고 싶은 것을 체크한다. 전체 체크를 하고 OK를 누를 것이다.  

![2019-04-09-6](/assets/2019-04-09-6.jpg)
OK를 누르고 기다리면 '2 warnings'라고 검색이 된다. 실제로 사용하지 않는 class를 미리 생성해두었고 그 결과 Test.java 가 검색이 되었다. 또한 class 내부에 사용하지 않고 있는 sample() 메서드도 검색이 되었다.

## 노동 끝!
---
일일이 사용하는 곳을 검색해가며 지우던 반복 노동은 끝이 났다. 검색이 끝나면 자동으로 삭제까지 해주는 버튼이 존재한다. 하지만, unused resource에서 자동 삭제를 하다 하드코딩으로 사용 중인 리소스들도 지워버려 크래시가 발생한 적이 있었다. 그래서 class도 하나씩 체크하며 지울 것이다. 실제로 지워도 괜찮은지에 대한 판단은 사람이 하는 게 좋다고 생각한다.
