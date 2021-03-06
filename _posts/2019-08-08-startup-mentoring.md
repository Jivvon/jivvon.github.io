---
title: 농림축산식품 공공 및 빅데이터 활용 창업경진대회 멘토링 결과
tags: 농림축산식품부 농정원 창업경진대회 빅데이터 공공데이터
---

## 주요 변경 기능

- 사용자 로그인 -> 카카오
- API 요청
  - 동물등록정보 수정할 수 있는 정보들의 접근 권한 (홈페이지 회원가입 필요 -> 회원가입 필요 없이 견주 정보로 접근하여 수정할 수 있도록)
  - 대행업체가 구청에 등록신청을 하지 않아도 되도록. (대행업체를 적어서)
  
---

## TODO

- DB 변경
  - hospital_tb
    - 기존 user_tb
    - 계좌번호 + 은행명
  - pet_info_tb
    - **반려동물 key - 일련번호 (only 내장형)**
    - 반려동물 정보
    - _주인 key (primary)_
    - _대행업체 key (primary)_
  - user_tb(사용자 새로 만들 것)
    - **사용자 key**
    - 사용자 계정 정보 (카카오 계정) - 토큰
    - 닉네임
  - 후기\_tb
    - **후기 index**
    - _병원 key_
    - _사용자 key_
    - 내용
    - 작성일
  - 커뮤니티 분류
    - Q&A
    - trade
    - pet_find
    - pet_sale
  - 상품\_tb (추후)
    - **상품 index**
    - 상품 이미지
    - 설명
    - 가격

---

## 서버 변경

- url 수정 -> 수정사항 알려주기
- 라우터 적용
- 메일보내기 form 만들어서
- 기능
  - 예약 제거
  - 후기 작성, 수정, 제거
  - 커뮤니티 수정 제거
  - 사용자 회원 탈퇴
  - 병원 회원 탈퇴
  - 반려동물 정보 추가(예약완료 될 때)
- 관리자 페이지 대충

---

## TODO TODAY

- 라우터 적용
- node에서 메일 사용하기
