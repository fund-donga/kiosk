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
## 개요
## 결제
### 결제API
- 아임포트 (https://www.iamport.kr/)
  - 복수의 결제대행사 이용시 효율적 개발과 유지보수를 위해 아임포트 이용예정
  - 참고자료
    - 대시보드 https://admin.iamport.kr/users/login
    - 개발가이드 https://www.iamport.kr/getstarted
    - 연동매뉴얼 https://docs.iamport.kr/
    - Github https://github.com/iamport
    - API문서 https://api.iamport.kr/
    - 결제DEMO https://www.iamport.kr/demo
  - 적용대상
    - 나이스페이 PG, 카카오페이
    - 키오스크에서 카카오페이 아임포트 적용 참고 [[kiosk-kakaopay.md]](kiosk-kakaopay.md)

### 결제수단
전체 결제수단의 개요정보입니다. 상세적용은 홈페이지, 키오스크간 상이할 수 있으니 아래쪽 관련내용과 함께 참조하시기 바랍니다.
#### 자동이체
- 결제대행사: 금융결제원CMS
- 프로세스
  1. 관리자 약정내역 엑셀 다운로드(웹 관리자 페이지)
  2. 금융결제원 업로드
  3. 이체결과 관리자 웹 업로드
  4. 결제내역 
#### 신용카드 (PG, 정기결제)
- 결제대행사: 나이스페이(PG, 가입예정)
- REST API방식  
  https://docs.iamport.kr/implementation/subscription  
  https://github.com/iamport/iamport-manual/blob/master/%EB%B9%84%EC%9D%B8%EC%A6%9D%EA%B2%B0%EC%A0%9C/example/nice-request-billing-key.md
#### 신용카드 (현장 일시불 결제)
- 결제대행사: KSNet(VAN, 가입예정)
- KSNET 제공 결제모듈 이용
- 키오스크에서만 지원하는 결제 방식
- 기부자에게 할부 수수료가 발생하므로 할부결제 이용하지 않음  
  분납 이용하고자 하는 기부자는 신용카드 정기결제로 처리
#### 카카오페이 (일시/정기결제)
- 결제대행사: 카카오페이(PG, 가입예정)
- 아임포트 이용
  - 일시결제  
    https://github.com/iamport/iamport-manual/blob/master/%EC%9D%B8%EC%A6%9D%EA%B2%B0%EC%A0%9C/sample/kakao.md
  - 정기결제  
    https://github.com/iamport/iamport-manual/blob/master/%EB%B9%84%EC%9D%B8%EC%A6%9D%EA%B2%B0%EC%A0%9C/example/kakaopay-request-billing-key.md
- 참고자료  
  - 카카오페이 개발자 센터  
  https://developers.kakao.com/docs/latest/ko/kakaopay/common
- 유사 웹페이지 적용 샤례
  - 서원대학교 발전기금 홈페이지 (일시/정기기부 적용)
  https://with.seowon.ac.kr/with/fund/step?menuId=MENU00353
  - 푸르메 재단 (일시기부 적용) https://purme.org/donation-apply

#### 썸패스 (일시결제)
- 결제대행사: 썸뱅크(직접 이체방식)
- 썸패스는 키오스크에만 적용 예정입니다.
- 부산은행 디지털사업부와 관련 문서, API제공에 대한 협의 예정입니다.
- 홈페이지에 네이버페이 적용 불가시 썸패스 적용 가능여부 검토예정입니다.
#### 네이버페이 (일시/정기결제)
- 결제대행사: 네이버페이 (PG, 가입예정)
- 네이버페이는 홈페이지만 적용 예정입니다.
  - 향후 적용여부 판단계획(홈페이지)
    - 아임포트측과 협의 후 적용 가부 판단
    - 아임포트 적용 불가시 직접 네이버페이 구현 여부 판단
    - 네이버페이 최종 적용 불가 판단 시 썸패스의 웹페이지 적용여부를 검토
    - 네이버페이, 썸패스 모두 웹 적용 불가 판단시 웹은 두가지 모두 구현하지 않음
- 아임포트 이용
  - 일시결제  
  https://github.com/iamport/iamport-manual/blob/master/NAVERPAY/sample/naverpay-pg.md
  - 정기결제  
  https://github.com/iamport/iamport-manual/blob/master/NAVERPAY/sample/naverpay-recurring.md
- 참고자료
  - 네이버페이 개발자 센터
  일시결제  
  https://developer.pay.naver.com/docs/v2/api#payments-payments_flow
  정기결제  
  https://developer.pay.naver.com/docs/v2/api#recurrent-recurrent_summary
- 유사 웹페이지 적용 사례
  - 굿네이버스  
  https://www.goodneighbors.kr/support_pay/regular.gn
  - 유니세프  
  https://www.unicef.or.kr/donation/?TrackCode=pc_donation_btn

## 홈페이지와의 연동
### 홈페이지 개발 정보
- 발전기금 홈페이지 프로토 타입  
https://xd.adobe.com/view/26be83b6-2348-4c67-ab75-79010b78b03e-73ed/
- 발전기금 홈페이지 개발자 가이드  
https://github.com/fund-donga/web_renewal/blob/main/Dev_guide.md
### 기본 통신방식
- 프로토콜 http, 형식 json
- 참고자료  
  https://stackoverflow.com/questions/5725430/http-test-server-accepting-get-post-requests

# :two: 기능별 개발 가이드
## QRCode 신분증 인식
- 동아대학교 학생증/교직원 신분증 APP상 QR코드를 리딩하면 암호화된 값을 읽을 수 있음
- QRCode 값 호출
  - http://idcard.donga.ac.kr/dongacard/qrdecode  
Type : POST  
Parameter : decode  
ex) http://idcard.donga.ac.kr/dongacard/qrdecode?decode=CAFF847E36E50C206D333FE4D9345C14735DC19876653DED4262CB65E7C2F833
  -  Response Json [학번:년월일시분초]
## 기부금 결제처리
### 무통장입금
### 자동이체
### 신용카드 정기결제
### QRCode 모드
### 전화번호 모드
### 기기 자체 결제 완료
### 홈페이지로 전송 후 사후 결제
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