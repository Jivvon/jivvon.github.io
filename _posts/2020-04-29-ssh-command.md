---
title: ssh를 이용하여 로그인하자
tags: ssh ssh-keygen
---

### ssh

##### ssh-keygen 으로 생성하기

```shell
$ ssh-keygen -t rsa
```

-t rsa : rsa라는 암호화 방식으로 키를 생성한다.<br />passphrase : 일종의 비공개키이다. (자동 로그인을 위해 생략)

키는 기본적으로 ~/.ssh 폴더에 **id_rsa**(private key)와 **id_rsa.pub**(public key)가 생성된다. 여기서 public key인 id_rsa.pub 파일을 접속하려는 서버의 **~/.ssh/authorized_keys**에 입력하면 된다.

##### 서버로 파일 전송

```shell
$ scp $HOME/.ssh/id_rsa.pub me@remotebox:id_rsa.pub
```

remotebox에 id_rsa.pub라는 이름으로 전송한다.

##### public key 서버에 등록하기

```shell
$ cat ~/.ssh/id_dsa.pub | ssh me@remotebox "cat >> ~/.ssh/authorized_keys"
$ ssh-copy-id me@remotebox
```

위는 둘 다 Client에서 서버로 한번에 등록하는 명령어이다. (같은 기능이므로 하나만 실행하도록 하자) 이 때, 서버에 .ssh 폴더가 없다면 가서 직접 만들어 줘야한다. 서버에 .ssh 폴더가 있다면 서버로 파일 전송도 안 하고 위 명령어만 Client에서 입력하면 된다.

```shell
$ ssh me@remotebox
$ mkdir ~/.ssh
$ cat $HOME/id_rsa.pub >> $HOME/.ssh/authorized_keys
```

위 명령어는 **서버로 파일 전송**을 하고난 뒤 해야 한다. '>>'는 서버에 이미 파일이 있을 경우 overwrite가 아닌 뒤에 append 한다.

**서버 접속**

```shell
$ ssh me@remotebox
$ ssh -i other_rsa.pub me@remotebox
```
-i : 다른 public key로 접속할 때 사용한다.


###### 참고

- [ssh 사용시 암호 대신 SSH key로 인증하기](https://arsviator.blogspot.com/2015/04/ssh-ssh-key.html) 원리부터 동작방식, 사용법 다 상세하게 적혀있다.