## 10.	새로운 MVC 프레임워크 구현을 통한 점진적 개선

### 10.1 MVC 프레임워크 요구사항 3단계
#### 10.1.1 MVC 프레임워크 3단계 구현 실습
[MVC 프레임워크 3단계 구현 실습 문서](10.1 MVC 프레임워크 3단계 구현 실습.pdf)

### 10.4 배포 자동화를 위한 쉘 스크립트 개선
#### 10.4.1 배포 자동화 실습
[배포 자동화를 위한 쉘 스크립트 개선 실습 문서](10.4 배포 자동화를 위한 쉘 스크립트 개선 실습.pdf)

#### 10.4.4	동영상을 통한 배포/원복
https://youtu.be/UqocnEIX-mA 동영상은 심볼릭 링크를 활용해 원복이 가능한 구조를 설계하고 이를 쉘 스크립트를 구현하는 과정을 다룬다. 심볼릭 링크 기반으로 배포하는 배포 스크립트는 다음과 같다.

```
#!/bin/bash

REPOSITORIES_DIR=~/repositories/jwp-basic
TOMCAT_HOME=~/tomcat
RELEASE_DIR=~/releases/jwp-basic

cd $REPOSITORIES_DIR
pwd
git pull
mvn clean package

C_TIME=$(date +%s) 

mv $REPOSITORIES_DIR/target/jwp-basic $RELEASE_DIR/$C_TIME
echo "deploy source $RELEASE_DIR/$C_TIME directory"

$TOMCAT_HOME/bin/shutdown.sh

rm -rf $TOMCAT_HOME/webapps/ROOT
ln -s $RELEASE_DIR/$C_TIME $TOMCAT_HOME/webapps/ROOT

$TOMCAT_HOME/bin/startup.sh

tail -500f $TOMCAT_HOME/logs/catalina.out
```

https://youtu.be/7OSzN16FqCw 동영상은 서비스 배포 후 장애가 발생하는 경우 이전 버전으로 원복하는 스크립트를 작성하는 과정을 다룬다. 동영상에서 구현한 원복 스크립트는 다음과 같다.

```
#!/bin/bash

RELEASES_DIR=~/releases/jwp-basic
TOMCAT_HOME=~/tomcat

RELEASES=$(ls -1tr $RELEASES_DIR)
echo "releases : $RELEASES"
REVISIONS=(${RELEASES//\n/})

if [ "${#REVISIONS[@]}" -lt 2 ]; then
  echo "release source length more than 2"
else
  echo "rollback directory : ${REVISIONS[1]}"

  $TOMCAT_HOME/bin/shutdown.sh

  rm -rf $TOMCAT_HOME/webapps/ROOT
  ln -s $RELEASES_DIR/${REVISIONS[1]} $TOMCAT_HOME/webapps/ROOT

  $TOMCAT_HOME/bin/startup.sh

  tail -500f $TOMCAT_HOME/logs/catalina.out
fi
```

----
# Table of Contents
### 1부. 첫 번째 양파 껍질
##### [1. 첫 번째 양파 껍질 벗기기](../chapter1)
### [2부. 두 번째 양파 껍질](../2nd-onion.md)
##### [2. 문자열 계산기 구현을 통한 테스트와 리팩토링](../chapter2)
##### [3. 개발 환경 구축 및 웹 서버 실습 요구사항](../chapter3)
##### [4. HTTP 웹 서버 구현을 통해 HTTP 이해하기](../chapter4)
##### [5. 웹 서버 리팩토링, 서블릿 컨테이너/서블릿 과의 관계](../chapter5)
##### [6. 서블릿/JSP를 활용해 동적인 웹 애플리케이션 개발하기](../chapter6)
##### [7. DB를 활용해 데이터를 영구적으로 저장하기](../chapter7)
##### [8. Ajax를 활용해 새로고침 없이 데이터 갱신하기](../chapter8)
##### [9. 두 번째 양파 껍질을 벗기기 위한 중간 점검](../chapter9)
##### [10. 새로운 MVC 프레임워크 구현을 통한 점진적 개선](../chapter10)
##### [11. 의존관계 주입(이하 DI) 을 통한 테스트하기 쉬운 코드 만들기](../chapter11)
##### [12. 확장성 있는 DI 프레임워크로 개선](../chapter12)
### 3부. 세 번째 양파 껍질
##### [13. 세 번째 양파 껍질](../chapter13)