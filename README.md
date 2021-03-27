# WeatherApp

Learning React Native by building a Weather App

# part #0 (introduction)

- #0.0 Introduction
  - 날씨 앱을 만들 것이다.
  - 간단한 소개
- #0.1 Requirements
  - React Native를 하기 위해 필요한 것
    - 10.0이상의 node version
    - npm
    - Android Studio or phone(expo를 google playstore에서 설치)
    - `npm install -g expo-cli`
- #0.2 Expo vs RN CLI
  - React native CLI
    - native files 들을 더 많이 컨트롤 하고 싶을 때
  - Expo
    - 휴대폰에서 앱을 테스트 할 수 있다.
    - 장점
      - 모든 native files 들을 숨기고, 모든걸 관리해준다.
      - 여러가지 기능들이 많다.
    - 단점
      - native files 들을 크게 제어 할 수 없다.
  - Expo vs RN CLI 에 대한 노마드 코더 의견
    - Expo 가 더 좋다.
    - Expo 의 단점이 있지만 보통은 native files 들을 크게 제어할 필요가 없다고 한다.
- #0.3 Creating the Project
  - 프로젝트 생성
    1. 원하는 경로로 이동
    2. `expo init 프로젝트명`
    3. blank 선택
    4. github과 연동
       1. repository 생성
       2. `git remote add origin [https://github.com/sgbo5003/WeatherApp.git](https://github.com/sgbo5003/WeatherApp.git)`
       3. `git pull origin main —allow-unrelated histories`
    5. `npm start`
       - 자동으로 export DEV tools 를 오픈해준다.
    6. 핸드폰으로 할 경우
       - Run on Android device/emulator 클릭
       - Run on iOS simulator 클릭
    7. 안드로이드에서 QR 코드 스캔 해도 안되고 에러 뜨는 경우
       - [https://studioplug.tistory.com/362](https://studioplug.tistory.com/362) 참고
  - github 관련
    - [https://13akstjq.github.io/reactnative/2019/06/07/reactnative-create-new-expo-project-gitsetting.html](https://13akstjq.github.io/reactnative/2019/06/07/reactnative-create-new-expo-project-gitsetting.html)
- #0.4 Getting to know Expo
  - 오류
    - `npm start` 를 해서 export DEV tools 를 오픈한 뒤, Run on Android device/emulator 를 눌렀지만 Android Emulator 화면에는 아무런 반응이 없었다.
  - 오류 해결
    - Android Emulator를 먼저 실행 시킨 뒤 Run on Android device/emulator 를 눌렀더니 정상적으로 실행이 됐다.
  - 기기들이 같은 wifi에 연결 되어 있는지 확인
  - live reloading vs hot reloading
    - live reload
      - hot reload와 약간 다르게 수정을 하고 저장을 하면 페이지 전체가 자동으로 리로딩 되는 현상
    - hot reload
      - 소스상에서 무엇인가 수정을 하고 저장을 했을 때 전체 페이지 리로딩 없이 수정한 부분만 자동으로 화면에 적용되는 현상
    - hot reload는 html, css와 같이 화면상에 즉각 변경이 필요한 작업에 사용하는게 좋고 live reload는 데이터 변경이 일어나는 작업에 사용하는게 좋다.
  - Android Emulator에서 개발자 메뉴 열기
    - `ctrl + m`
- How does React Native Work?

  - 모바일 앱을 만드는 3가지 방법
    - 완전 native
      - Swift or objective-c로 ios 앱 만드는 것, java or 코틀린 가지고 만드는 Android앱
      - Xcode
      - Android studio
    - 앱 기반 웹뷰
      - Cordova or PhoneGap 을 이용해 간단한 앱을 만든 후 그 안에 HTML,CSS를 넣는다.
      - 앱 안에서 작동하는 웹사이트 같은 개념 ( 하이브리드 웹뷰 방식)
      - native쪽에 많은 예산이 없는 회사들이 사용
    - React native
      - 자바스크립트를 이용하여 ios or Android의 네이티브 엔진에게 메세지를 보낸다.
      - 연결을 이어주는 브릿지 (항상 브릿지가 필요하다) → 자바스크립트와 폰 사이의 커뮤니케이션을 위해서
      - 느린성능을 유발 할 수도 있다.
        - 브릿지로 많은 데이터를 보내면 부하가 걸리기 때문에
      - 데이팅 앱 같은 것을 리엑트 네이티브로 만드는 것은 매우 쉽다.
      - 3D 비디오 게임 같은 것을 만드는 것에는 최선은 아니다.
        - 코드를 최적화 하는데 시간을 많이 써야 하기 때문에 (브릿지가 느려지지 않도록)
      - 자바스크립트와 폰의 코드 사이의 커뮤니케이션을 쉽게 하려고 만들어 졌다.
  - <View>
      - = <div>
  - <Text>
      - = <span>
  - style 지정
