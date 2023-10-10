# 🥗 Begin Vegan

**주제 : 비건식당 서칭/예약/사전결제 서비스**  
**기간 : 2023.04 ~ 2023.06**  
**인원 : 4명** 
<br><br>

## 🎈 서비스 주요 기능  

> **이용자 관점**
1. OAuth 로그인 (Kakao, google)
2. 식당 검색 및 지도 기반 주변 식당 정보 확인
3. 식당 예약 및 결제
4. 식당 후기 작성, 별점 평가, 식당 즐겨찾기
5. 마이페이지 포인트/예약/결제/리뷰 정보 확인

> **관리자 관점**
1. 이벤트 포인트 일괄 및 개인 지급
2. 권한 부여 등 회원 관리
3. 식당을 등록 및 메뉴 관리
4. 예약 발생 추이 확인 및 분석
<br>

## 🛠 기술 스택

> 서비스 및 요구 사항 구현을 위해 활용된 기술 스택입니다.  
<img src="https://github.com/sungchanmin/sungchanmin/assets/97079985/e182a16a-e79b-4993-a7a4-fc8b8da39167" width="70%">
<br>
<img src="https://github.com/sungchanmin/sungchanmin/assets/97079985/ad23808b-f081-4de2-9ef3-1c227c8f7d15" width="70%">
<br><br><br>

 ## 🖥 요구사항 정리
 > 과제에 요구된 기본 요구사항(1\~8번)과 서비스를 위해 추가된 요구사항(9\~11번)입니다.
 <img src="https://github.com/BeginVegan/BV-Document/assets/97079985/f2aaf306-3279-44f9-a0ea-0235c3f5e64e" width="70%">
<br>
<img src="https://github.com/BeginVegan/BV-Document/assets/97079985/78b36ec0-4dc6-4fb6-ba84-b9ac754ba576" width="70%">
<br><br>

<details>
 <summary>  ✨ 요구 사항 Why, How 분석 </summary>
 <br>
  
  > ## 📍 기본 요구사항 8개
  
  ### ✔️ 1. 반응형 화면 구현  
     - Why: 다양한 크기의 디바이스에서도 사용자에게 적절한 UI를 제공.
     - How: 미디어 쿼리를 사용하여 뷰포트 크기를 감지하고, 레이아웃을 조정하는 CSS 스타일을 적용한다.
  
  ### ✔️ 2. 메서드 접근 로그 남기기
    - Why: 디버깅과 분석 용이성을 위해 메서드의 실행 시간, 호출 정보 등의 로그를 추적한다. 
    - How: Spring AOP로 공통 관심 사항(로깅)을 모듈화하고, 개발 코드와 분리한다.
  
  ### ✔️ 3. Scheduler를 이용한 배치프로그램 기능 구현
    - Why: 일정 주기로 반복되는 작업을 자동으로 처리.
    - How: Quartz 라이브러리를 사용하여 스케줄링이 필요한 작업을 등록한다.
  
  ### ✔️ 4. 권한 처리: 로그인한 사용자에게 허용된 페이지 외에는 예외 처리
    - Why: 권한이 없는 접근에 대해 예외 처리 함으로써 보안을 강화한다.
    - How: Filter를 통해 권한을 체크하여 메소드 접근을 제한하고, 또한 화면단에서 기능을 제한한다.
  
  ### ✔️ 5. 파일 첨부 기능 구현, 멀티 파일을 압축파일로 다운로드 하는 기능 구현
    - Why: 파일 업/다운로드 편의성 제공.
    - How: HTML form과 Spring MultipartResolver로 파일 처리.
  
  ### ✔️ 6. Transaction 처리
    - Why: 오류로부터 복구를 허용하고 데이터베이스를 일관성있게 유지하는 안정적인 작업 단위를 제공한다.
    - How:  Spring의 @Transactional로 트랜잭션 범위 지정 및 예외 처리.
  
  ### ✔️ 7. XHR(XML Http Request) 통신
    - Why: 동적 데이터 로드를 위한 백엔드 통신.
    - How: XHR, fetch, axios 등의 API를 사용하여 백엔드와 통신하고 동적으로 데이터를 로드하는 로직 구현.
  
  ### ✔️ 8. 테스트 코드 작성, 커버리지 결과 확인
    - Why: 테스트 범위 파악 및 버그를 사전에 발견하여 수정하여 비용을 절감하고 소프트웨어의 신뢰성을 높임.
    - How: Junit5를 이용한 테스트 코드 작성 및 JaCoCo를 이용한 코드 커버리지 분석 및 개선점 도출.

  <br>

  > ## 📍 추가 요구사항 3개
  
  ### ✔️ 9. OAuth 로그인
    - Why : 사용자는 외부 서비스의 로그인 정보로 편하게 로그인하고, 개발자는 사용자 인증 관련 기능을 간소화.
    - How : 구글, 카카오 등에서 제공하는 API를 활용하여 OAuth 로그인 구현.
  
  ### ✔️ 10. 지도 라이브러리
    - Why : 지리 정보를 활용한 서비스를 제공.
    - How : Kakao Maps API와 같은 지도 라이브러리의 API를 활용하여 구현.
  
  ### ✔️ 11. 결제 기능
    - Why : 결제 기능을 통한 온라인 거래 활성화 및 수익 증대.
    - How : IAMPORT API를 활용한 결제 기능 구현.

 </details>
<br>


## ⚙️ Devops CI/CD PipeLine 구성

<img src="https://github.com/BeginVegan/BV-Document/assets/97079985/b0107f70-3eff-46ab-afcc-9d16c8cb5f9a" width="70%">
<br><br><br>

## 🏗️ System Architecture
<img src="https://github.com/BeginVegan/BV-Document/assets/97079985/f81447b4-0d85-4d89-b011-43fe3bf6e570" width="70%">
<br><br><br>

## 기획 / 디자인
## **Figma 활용**
<br>

접속 URL : https://www.figma.com/file/c3Uld34o4YsqENxoiAUzNX/BeginVegan?type=design&node-id=0-1&t=27MQalCo43jBtLxc-0

## ERD
![image](https://github.com/BeginVegan/BV-Document/assets/70372082/63bf3d57-0da2-4db6-8025-41de31486a03)
![image](https://github.com/BeginVegan/BV-Document/assets/70372082/59ad4b03-a613-4855-8e10-cf5f83b1cbba)

## GIF TEST
<img src="https://github.com/BeginVegan/BV-Document/assets/97079985/e91b65d7-79d0-4265-a5b4-96c15c8328b0" width="840px">
<img src="https://github.com/BeginVegan/BV-Document/assets/97079985/fdba19d6-23e8-4cca-b5b6-fb4a3a8789e2" width="840px">
<img src="https://github.com/BeginVegan/BV-Document/assets/97079985/49521a31-afdd-4521-81d2-701aa9a848a4" width="840px">
