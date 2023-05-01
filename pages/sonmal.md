# 🤟 손말
**🌐 [Explore Repository](https://github.com/pmi4202/Sonmal)**<br>

<img src="https://github.com/pmi4202/pmi4202/blob/main/sonmal_info.png?raw=true"/>

<details>
  <summary>시스템구조도</summary>
  <img src="https://user-images.githubusercontent.com/49026286/199017240-4da672b2-7141-4ccf-bb4c-e80bad827435.png"/>
</details>

- 한국 수어와 다른 한국어 + 구화/필담만으로 힘든 소통을 보조합니다.
- 수어가 익숙한 사람들을 위한 수어 번역 제공, 한국어가 익숙한 사람들을 위한 TTS+STT를 제공합니다.

<br>


## 💻 담당 업무
- 아이디어 기획
- DB, API 설계
- [DevOps] 자동배포 : Docker, Jenkins, Gitlab
- [DevOps] 보안 : SSL
- [SpringBoot] 소셜 로그인
- [SpringBoot] JWT
<br>

## 💡 성장 스토리

### 🛠️ 기술
- 빌드 속도 개선
  - [개선 전] Docker내에 전체 프로젝트를 복사 후, 빌드
  - [개선 후] build한 후, .jar파일만 Docker로 복사해서 Run
  <img src="https://github.com/pmi4202/pmi4202/blob/main/sonmal_build.png?raw=true" width="50%"/>
- Docker & Jenkins 자동 배포
  - Docker내의 Jenkins는 Volume을 통해, docker명령어를 사용하여 프로젝트를 컨테이너화할 수 있게 함
- 소셜 로그인 구현 과정
  - client(frontend)가 resource server에서 인가토큰을 받아 서버로 전달
  - 서버는 인가토큰으로 사용자의 정보를 자신의 서비스 DB에 저장하여 회원가입 완료
- JWT
  - Spring Security의 Filter를 활용
  - Access Token(30분)
    - 탈취가 되어도, 기간을 짧게 하여 리스크를 줄임
  - Refresh Token(2주)
    - 로그인 시, Access Token과 함께 발급
    - Access Token과 Refresh Token을 1:1 Map형식으로 저장하고, refresh할 때 맵핑 정보가 일치하면 refresh함
    - Refresh Token 만료 시, 재로그인 요구
    
### 👏 협업
- 개발 일지
  - 개발하면서, 마주한 문제들을 상세히 기록하는 일지
  - 정리하는 과정에서 
  - 팀원들과 함께 보며 의견을 공유
  <img src="https://github.com/pmi4202/pmi4202/blob/main/pages/sonmal_dev_articles.png?raw=true" width="60%"/>
- API 명세서
  - API설계에 요청, 응답을 상세히 작성
  <img src="https://github.com/pmi4202/pmi4202/blob/main/pages/sonmal_api.png?raw=true" width="80%"/>
  <img src="https://github.com/pmi4202/pmi4202/blob/main/pages/sonmal_api2.png?raw=true" width="80%"/>

