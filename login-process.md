# 로그인 요구사항 정의

## 기능 요구사항

1. 로그인 정보가 올바르지 않은 경우 `아이디 혹은 비밀번호를 확인해주세요.` 라는 메시지를 응답한다.
2. 사용자는 아이디와 패스워드를 입력하고 올바른 정보인 경우 로그인한다.
3. 서비스 접속 기간이 1년을 넘기면 휴면 계정으로서 탈퇴 처리를 한다.
4. 휴면 계정 탈퇴 처리 시, 탈퇴 사용자 이력을 남긴다.
5. 탈퇴 사용자가 재 로그인 시, 마지막 접속일 및 탈퇴 전환일을 응답하고 로그인에 실패한다.
6. 사용자 계정이 미 승인 상태인 경우, 승인 대기 메시지를 응답한다.

## 로그인 상태전환표

| **현재 상태** | **조건**     | **상태전환** |
|:----------|:-----------|:---------|
| 익명 유저     | 탈퇴 이력 존재 시 | 탈퇴 유저    |
| 활성 유저     | 미 승인 시     | 미승인 유저   |
| 익명 유저     | 모든 조건 통과 시 | 로그인 유저   |