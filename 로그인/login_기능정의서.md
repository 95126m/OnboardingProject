
# 로그인 추가 기능


## 1. 기능명: 로그인
 
    기능 설명
    블로그에 가입된 경우 로그인을 수행할수 있습니다.    
 참고:https://help.naver.com/service/5640/contents/973?lang=ko

 입력항목
 - 아이디:  5~20자의 영문 소문자, 숫자와 특수기호 -, _ 만 사용 가능합니다. 
 - 패스워드: 8~16자 영문 대/소문자, 숫자, 특수문자만 사용 가능합니다
 - 사용 가능한 특수문자 33자: ! " # $ % & ' ( ) * + , - . / : ; ? @ [ ＼ ] ^ _ ` { | } ~ \

1.2 사용자 액션

- 추가 버튼 클릭
    - 로그인 버튼
    - 회원가입 (to. 서미님)
    - 로그인 상태유지
    - 비밀번호 찾기
    - 아이디 찾기
   

    로그인
- OAuth 2.0 인증 참고 : https://blog.naver.com/mds_datasecurity/222182943542
  
    ```mermaid
    flowchart TD
    E[로그인페이지] --> A[아이디 입력]-->B[패스워드 입력]-->c[로그인 체크 OAuth 2.0 인증]-->d[로그인성공]
    ```
        



## 2. 기능명: 비밀번호찾기

    기능 설명
    사용자가 아이디를 알고있을 경우 휴대폰 인증을 통해 가입된 이메일로 비밀번호를 새로 만든다. 

사용자 액션
- 아이디 입력
- 휴대전화로 본인인증
- 가입시 작성한 이메일로 패스워드 변경 페이지 발송 

```mermaid
flowchart TD
    k[로그인 페이지]-->A[비밀번호찾기 클릭]-->B[아이디 입력] -- 아이디 있음 --> c[회원시 등록된 휴대폰 확인 010-7***-7***]-->d[이름/휴대번호입력]-->e[인증번호 받기]-->f[인증번호 6자리 확인]

-->g[패스워드 변경 이메일 전송]-->h[가입된 이메일로 암호변경 링크 발송]
    B{아이디인증} -- 아이디 없음 -->h[아이디 확인 요청]

 
```

## 3. 기능명 : 아이디 찾기

    기능 설명
    가입한 사용자의 아이디를 확인합니다.

사용자 액션
- 아이디 찾기
- 본인인증
- 메일로 아이디 발송


```mermaid
flowchart TD
A[아이디찾기 클릭]-->B[본인인증]-->c[회원시 등록된 휴대폰 확인 010-7***-7***]-->d[이름/휴대번호입력]-->e[인증번호 받기]-->f[인증번호 6자리 확인]-->g[인증완료 jar***]-->h[가입된 이메일로 아이디 발송]
```

