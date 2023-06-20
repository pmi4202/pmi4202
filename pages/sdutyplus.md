# 🤟 Sduty+
**🌐 [Explore Repository](https://github.com/pmi4202/SdutyPlus)**<br>

<img src="https://github.com/pmi4202/pmi4202/blob/main/sdutyplus_info.png?raw=true"/>

<details>
  <summary>시스템구조도</summary>
  <img src="https://user-images.githubusercontent.com/49026286/202906377-f1317e67-ebb5-4aef-a444-806d1eee1bab.png"/>
</details>

- 타이머로 공부시간을 측정하고, 리포트에 수행한 업무를 기록할 수 있습니다.
- 공부한 내용은 다양한 템플릿을 활용하여, 다른 사람들과 공유할 수 있습니다.

<br>


## 💻 담당 업무
- 기획
- DB, API 설계
- 이전 프로젝트 복구 : maven to gradle, DB변경
- [SpringBoot] 리포트 API: CRUD
- [SpringBoot] 타임라인 API: CRUD, 페이징, 이미지 파일 처리
- [SpringBoot] Exception Handling
- [SpringBoot] Querydsl 최적화 및 JMeter 부하 테스트
- [DevOps] 자동 배포: Docker, Jenkins, Gitlab
- [DevOps] DB 세팅: MariaDB설치, root계정 변경
- [DevOps] 보안: SSL
- [DevOps] Docker 컨테이너 간 네트워크 연결

**유지보수**

- [DevOps] AWS 재배포
- [SpringBoot] 테스트 계정 자동 생성
<br>

## 💡 성장 스토리

### 🛠️ 기술
- **query 개선**
  - 게시물 조회 시, 게시글을 최신 순으로 내림차순 기준을 PK로 변경
  - 중복 여부 확인 시, 조회 결과가 1이상으로 확인하는 쿼리를 exist로 확인하도록 변경
  - 사용한 테스트 : Sql Profile & Explain, JMeter
  - 확인 결과 처리량이 1.4배 향상됨
- **infra 개선**
  - 서버에서 DB로 도메인 주소로 접근하여, DNS 서버를 거치는 시간 낭비가 있었음
  - Docker Network를 생성하여, 서버 내부에서 직접 접근하도록 수정
- **동시성 문제로 중복 아이디 생성**
  - **문제상황** : 동시에 테스트 계정 생성을 요청하면서, 중복 아이디가 생성됨
  - **고민 및 시도 과정**
    - 동시성 문제로 접근
      |해결책|적용하지 않은 이유|
      |-----|:------:|
      |JPA락|Insert를 통과시키며, User가 연관관계 주인이 아닌 연관관계가 없어 간접적으로도 적용 불가|
      |Transaction 격리 수준을 높임|DeadLock 발생|
      |synchronized|단일 서버에서만 동작하며, 동시성을 막는 행위는 서버 성능을 저하시킴|
   - **최종 해결 방안**
     - 랜덤 문자열 생성 라이브러리로 중복 발생률을 줄임
     - Column에 unique속성을 부여하여 DB에서 Exception발생하여 Rollback
- **배포할 때, 유의할 점**
  - DB 보안을 위해, root계정값 및 port번호 변경
- **Querydsl**
  - 복잡한 query 오류를 compile time에 확인 가능
- **Exception Handling**
  - 클린 코드와 신뢰성 있는 운영을 위해 커스텀 예외를 사용
  ```java
   {
     "status": 400,
     "code": "G004",
     "message": "존재하지 않는 직업입니다."
   }
  ```
- **Lombok 활용**
  - DTO, Entity는 @NoargsConstructor(AccessLevel.PROTECTED)로 의미없는 객체 생성을 막음
    
### 👏 협업
- **코드 리뷰**
  - Github의 PR 탬플릿을 만들어 내용을 공유
  - Merge전에 코드를 보며, 함께 토론함으로써 성장
  <img src="https://github.com/pmi4202/pmi4202/blob/main/pages/sdutyplus_pr.png?raw=true"/>

