## :zero: XD 디자인 가이드 문서   
### 업데이트 예정
- 바코드 스캔, 카드 사입시 위치알려주는 디자인 추가
- 전화번호 주소 등 정보 페이지 추가
### 프로토 타입
- QR코드 모드  
https://xd.adobe.com/view/d6e5840b-81a8-4ae9-824b-e48f9038e902-83b6/
- 전화번호 모드  
https://xd.adobe.com/view/0e93af62-ed1d-49b2-bbdf-8b188ff8de02-5bc0/
- 전체페이지  
  https://xd.adobe.com/view/0e93af62-ed1d-49b2-bbdf-8b188ff8de02-5bc0/
# :blue_book: 목차
## [XD 가이드 문서](#zero-xd-가이드-문서)
# :one: Background
## 홈페이지와의 연동
- 발전기금 홈페이지 프로토 타입  
https://xd.adobe.com/view/26be83b6-2348-4c67-ab75-79010b78b03e-73ed/
- 발전기금 홈페이지 개발자 가이드  
https://github.com/fund-donga/web_renewal
# :two: 기능별 개발 가이드
## QRCode 신분증 인증
## 약정서 송/수신
## 기기설정/현황
## SMS 발신
## VAN 구현
## PG 구현
## 썸패스 구현
- 썸패스 바코드 방식 구현
- 썸패스 결제성공시 알림 방식 확인 필요
- 참고자료
  - https://youtu.be/0asvCQThWNw?t=54
## 카카오페이 구현
- 일반사항 카카오페이 개발자 문서 참고
- 결제진행 단계에서의 QR코드
  - 일반적 개발단에서 문제점
    - WINDOWS 환경 기기에서 user-agent가 PC로 설정되면 웹 새창이 뜨게되면서 기기 컨트롤이 어려움
  - 개발방향
    - 제한된 환경에서 결제를 진행시키기 위해 카카오페이 결제준비 API Request시 Response 값 중 next_redirect_mobile_url 값을 QR코드로 자체변환하여 기기에 출력
  - 참고자료
    - https://developers.kakao.com/docs/latest/ko/kakaopay/subscription
    - https://devtalk.kakao.com/t/topic/90538