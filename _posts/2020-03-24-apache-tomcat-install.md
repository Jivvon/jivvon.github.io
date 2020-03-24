---
title: Mac 에서 Apache Tomcat 설치
tags: apache tomcat
---

### 설치

[http://tomcat.apache.org/](http://tomcat.apache.org/)에서 core의 tar.gz를 다운받는다.

이 후, 터미널에서 아래 명령어를 입력하면 설치가 완료된다.

```shell
sudo mkdir -p /usr/local

sudo mv ~/Desktop/apache-tomcat-8.5.53 /usr/local 

sudo rm -f ~/Library/Tomcat 

sudo ln -s /usr/local/apache-tomcat-8.5.53 /Library/Tomcat  

sudo chown -R [맥 user id] /Library/Tomcat  

sudo chmod +x /Library/Tomcat/bin/*.sh 
```

### 실행 중지

실행
```shell
sudo /Library/Tomcat/bin/startup.sh
```

종료
```shell
sudo /Library/Tomcat/bin/shutdown.sh
```

실행된 아파치 서버 확인은 `http://localhost:8080`에서 할 수 있다.