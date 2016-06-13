## 3. 개발 환경 구축 및 웹 서버 실습 요구사항
[Model1, Model2, Struts 개발 방식의 비교 분석](http://www.javajigi.net/pages/viewpage.action?pageId=73)

### 3.2	로컬개발환경 구축
이 책의 실습으로 사용할 Github 저장소 URL은 다음 2개의 저장소를 실습으로 사용한다.

* https://github.com/slipp/web-application-server: 3 ~ 6장 실습에서 사용할 저장소
* https://github.com/slipp/jwp-basic: 6장 ~ 12장 실습에서 사용할 저장소

이클립스 프로젝트로 가져오는(import) 작업 후 실습하는 과정을 https://youtu.be/xid_GG8kL_w 동영상을 참고한다. 

만약 이클립스에서 직접 clone하지 않고 터미널에서 저장소를 clone한 후 이클립스 프로젝트로 가져와 실습을 진행할 수 있다. 이 과정은 https://youtu.be/5hjYe_PggJI 동영상을 참고해 진행할 수 있다.

### 3.3	원격 서버에 배포
이 책의 배포 실습을 AWS로 하려면 AWS에 회원가입한 후 EC2 인스턴스를 우분투로 생성하면 된다. 이 책을 쓰는 시점에 AWS가 지원하는 우분투 버전은 Ubuntu Server 14.04 LTS이다. AWS에 대한 회원가입, 우분투 운영체제 설치, SSH를 통한 접근은 https://opentutorials.org/module/1946 문서를 참고해 진행할 수 있다. 만약 배포할 서버로 사용할 수 있는 원격 서버가 있다면 굳이 AWS를 사용하지 않아도 된다.

#### 3.3.1, 3.3.2 원격 서버 배포 실습
@TODO

#### 3.3.3	동영상을 활용한 배포 실습
리눅스 서버에 소스 코드를 배포한 경험이 없는 독자들은 위 힌트만으로 서버 설정을 하는데 어려움이 있을 것이다. 위 힌트만으로 성공하지 못한 독자들은 다음 동영상을 참고해 소스 코드를 배포한다.

* https://youtu.be/dWGzApCuF9M 동영상은 한글 인코딩 설정, 자바 8 설치 및 설정, 메이븐 설치 및 설정 과정을 다룬다.
* https://youtu.be/N8iLAuAo-Qw 동영상은 앞의 동영상에 이어 Git 설치, Github 저장소 클론, 메이븐을 활용한 빌드, HTTP 웹 서버 시작, 소스 코드 수정 시 재배포 과정을 설명한다.

#### 3.3.4	리눅스, 터미널과 친해지기
리눅스에 접속해 무엇을 해야할지 막막하다면 일단 이 책의 배포 자동화 과정을 같이 진행할 수 있다. 이 책을 통해 알게된 리눅스 기본 명령어 중 더 깊이 있게 학습하고 싶은 내용이 있다면 “리눅스 커맨드라인 완벽 입문서(윌리엄 E. 샤츠 주니어 저/이종우, 정영신 역, 비제이퍼블릭/2013년 1월)” 책을 통해 학습할 수 있다. 이 책은 리눅스 기본 명령어 뿐만 아니라 이후에 다루게 될 쉘 스크립트 내용까지 학습할 수 있다. 이 책의 영어 버전은 http://linuxcommand.org/tlcl.php에서 무료로 다운로드받을 수도 있다.

책보다 동영상을 선호한다면 https://youtu.be/JbH-xzD7IkE 동영상을 통해 터미널 환경에서 반드시 알아야하는 명령어에 대해 살펴볼 수 있다.

크롬 개발자 도구에 대한 학습 비용은 작다. 작은 학습 비용 투자로 웹 애플리케이션 개발을 하는데 많은 도움을 받을 수 있는 만큼 반드시 학습할 것을 추천한다. 크롬 개발자 도구에 대한 학습은 다음 동영상만으로 충분히 학습할 수 있다. 총 5개의 동영상으로 25분만 투자하면 된다.

http://goo.gl/Mq6hRd : 이 동영상은 넥스트에서 웹 UI 전공을 담당했던 윤지수님이 촬영한 동영상이다.

### 3.4	웹 서버 실습

#### 3.4.3	실습 요구사항
@TODO

* 마크다운은 텍스트 기반의 마크업 언어로 쉽게 쓰고 읽을 수 있으며, HTML로 변환이 가능하다. Github에서 사용할 수 있는 마크다운 문법은 https://guides.github.com/features/mastering-markdown/에서 참조할 수 있다. 

### 3.5	추가 학습 자료
#### 3.5.1 Git과 Github
> 이 내용은 정호영님이 공유한 [learngit](https://github.com/honux77/practice/wiki/learngit) 문서를 기반으로 작성한 내용이다.

##### 3.5.1.1	Git 학습을 시작하는 개발자에게 추천
* http://backlogtool.com/git-guide/kr/: “누구나 쉽게 이해할 수 있는 Git 입문”이라는 제목으로 공개된 자료로 그림을 통해 Git에 대해 쉽게 설명하고 있다. Git을 시작하는 단계에 참고하기 좋은 내용이며, Git과 관련한 전반적인 내용을 모두 학습할 수 있다.
* http://rogerdudler.github.io/git-guide/index.ko.html: Git 설치, 기본 사용법에 대한 간편 안내서
* http://www.slideshare.net/ibare/dvcs-git: Git의 commit과 push의 개념잡기

##### 3.5.1.2	조금 익숙해 졌을 때
앞의 자료를 학습하는 것만으로 Git에 대한 기본적인 사용은 가능하다. 좀 더 깊이 있는 학습을 하고 싶다면https://www.atlassian.com/git/tutorials 문서를 통해 학습한다.

##### 3.5.1.3	직접 해보는 실습
* https://try.github.io/levels/1/challenges/1: Git 15분만에 배우는 실습
* http://pcottle.github.io/learnGitBranching/: 브랜치 rebase등을 배우는 실습

##### 3.5.1.4	동영상 강의
* http://opentutorials.org/course/1492: 생활 코딩  Git 강좌

##### 3.5.1.5	무료 이북
* http://dogfeet.github.io/articles/2012/progit.html: progit, 공짜책, 거기다 한글!

##### 3.5.1.6	추천하는 Git GUI 도구
* http://www.sourcetreeapp.com: Mac, 윈도우 모두에서 사용할 수 있는 GUI 도구

#### 3.5.2	빌드 도구 메이븐
메이븐 빌드 도구를 학습하려면 먼저 https://slipp.net/wiki/pages/viewpage.action?pageId=10420233에서 제공하는 문서를 참고한다. 이 문서는 필자가 쓴 “자바 세상의 빌드를 이끄는 메이븐” 책의 6장까지 공개하고 있다.

동영상을 통해 학습하는 것이 익숙한 독자는 다음 동영상을 활용해 학습한다. 동영상을 통해 학습하면 문서를 통해 전달할 수 없는 부분도 학습할 수 있다는 장점이 있다.

* http://youtu.be/Eg1Ebl_KNFg 동영상은 빌드 도구에 대한 초간단 설명, 이클립스에서 메이븐 디렉토리 구조의 프로젝트 생성, JUnit 라이브러리에 대한 의존성 추가, 메이븐 의존성 전이에 대해 설명한다.
* http://youtu.be/A8h1y-qXCbU 동영상은 이클립스 effective pom 탭을 통해 메이븐 부모 pom 설명, 메이븐 기본 명령어인 compile/test/package 페이즈(phase) 설명, 이클립스에서 메이븐 명령 실행을 다룬다.
* http://youtu.be/58yiJQU0xEY 동영상은 메이븐의 페이즈(phase)와 골(goal)과의 관계 설명, compiler 플러그인과 eclipse 플러그인 재정의 및 빌드, 이클립스에서 메이븐 골 실행 방법을 설명한다.

개발하고 있는 프로젝트의 디렉토리 구조를 변경하지 않으면서 메이븐을 적용할 수 있다. 메이븐을 적용할 경우 Github에 공유하던 많은 소스 코드를 공유하지 않아도 된다. 특히 이클립스 관련 설정과 jar 라이브러리를 공유하지 않아도 되는 것은 큰 장점이다.

* http://youtu.be/ovpVzUaQtSM 동영상은 메이븐이 적용되어 있지 않은 프로젝트에 메이븐을 적용하는 과정,  Github에서 jar 파일을 버전 관리하지 않도록 설정하는 과정을 다룬다.

빌드 도구에 대한 학습을 반드시 메이븐부터 시작하지 않아도 된다. 최근 경향은 메이븐에서 그래들로 바뀌어가고 있는 단계이기 때문에 학습 시작단계부터 그래들로 시작하는 것도 좋은 선택이다. 그래들에 대한 학습은http://kwonnam.pe.kr/wiki/gradle 문서를 활용해 시작할 수 있다.

#### 3.5.3	디버깅을 위한 로깅(logging)
동영상을 통해 학습하는 것이 익숙한 독자는 다음 동영상을 활용해 학습한다.

* https://youtu.be/TcKEGh7KShI 동영상은 로깅 라이브러리가 필요한 이유, 로깅 라이브러리 설정 방법에 대해 다루고 있다. 동영상의 모든 내용은 책에서 이미 다룬 내용이다.

* https://youtu.be/040Y3MBNnyw 동영상은 로깅 레벨 설명, 패키지별 로깅 라이브러리 설정, 동적인 메시지 구현시 주의할 점, 로깅을 위해 반복적으로 추가되는 설정을 이클립스 템플릿(template)으로 해결, 이클립스 formatter 설정 방법을 설명한다. 특히 로깅 메시지를 추가하기 위해 매번 반복적으로 구현해야 하는 코드를 이클립스 템플릿을 활용해 해결하는 방법은 반드시 익혀두면 좋겠다.

