## 10.	새로운 MVC 프레임워크 구현을 통한 점진적 개선

### 10.1 MVC 프레임워크 요구사항 3단계
#### 10.1.1 MVC 프레임워크 3단계 구현 실습
@TODO 실습 요구사항 및 힌트 문서

### 10.4 배포 자동화를 위한 쉘 스크립트 개선
#### 10.4.1 배포 자동화 실습
@TODO 실습 요구사항 및 힌트 문서

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