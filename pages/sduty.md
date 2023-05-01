# ✏️ Sduty

<img src="https://github.com/pmi4202/pmi4202/blob/main/sduty_info.png?raw=true"/>

**[Explore Repository](https://github.com/pmi4202/Sduty)**<br>

- 타임라인 : 공부한 기록을 다른 사람들과 공유할 수 있어요.
- 타이머&리포트 : 공부한 시간을 측정하고, 나만의 리포트를 만들 수 있어요.
- 스터디 : 사람들과 함께 공부해요.

<br>


## 💻 담당 업무
- [MySQL] DB 설계 + Trigger 작성
   - <details>
         <summary>ERD</summary>
         <img src = "https://github.com/pmi4202/APT_Sale/blob/master/happyhouse_erd.png?raw=true"/>
   </details>
        
- API 설계
- [SpringBoot] 리포트 API
- [SpringBoot] 스터디 API - Quartz 스케쥴러, JPA 검색 필터
- [SpringBoot] 관리자 API
- [SpringBoot] 비밀번호(Bcrypt), 전화번호(AES256), 속성 파일 암호화(Jasypt)
<br>

## 💡 성장 스토리

### 🛠️ 기술
- Trigger 미작동으로 인한 데이터 일관성 깨짐
  - MySQL 공식 문서에서 CASCADE를 통한 삭제로는 Trigger가 발생하지 않는 것을 파악
  - Trigger를 모두 없애고, Spring 로직으로 구현
  - 추가적으로 효율적인 설계를 위해, 추측이 아닌 수치적으로 확인하며 개선해야 함을 깨달음
- Quartz Scheduler 사용
  - 각 객체마다 schedule을 저장, 실행, 검색, 정지가 가능해야 하기 때문에, Spring이 제공하는 @Scheduled로는 구현 불가능
  - Quartz를 사용해서, schedule을 저장, 검색이 가능
  - 프로젝트 회고하던 중, Quartz Scheduler에서 한정된 thread수로 문제가 발생할 수 있는 코드를 발견했다. 같은 시간에 처리할 수 있는 Job은 모아서 처리할 수 있을 것으로 예측됨.
  
### 👏 협업
- API 문서 체계화
- Agile 방법으로 빠르게 협업

