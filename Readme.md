# hadoop 설정

## NameNode
- wikibooks01

## DataNode
- wikibooks02
- wikibooks03
- wikibooks04

<hr>  
기본 이미지: centos:hadoop  

-> 하둡이 깔려있는 centos
<br> <br>   

wikibooks01 컨테이너만 Datanode를 알려주기 위해 ./wikibooks01 디렉터리 하에 추가 설정 관련 Dockerfile 존재  
- $HADOOP_CONFIG_HOME/slaves 파일에 Datanode의 hostname 기재하는 작업


## 작업 시작
```cd 작업 디렉토리 최상위 ```  
```docker-compose build```  
```docker-compose up```   

## hadoop_wikibooks01 _1 컨테이너 내에서 데이터노드 연결
SSH 연결 후에는 해당 서버로 들어가므로 exit 하고 다시 wikibooks01로 나와야 함
```sh
$ ssh wikibooks02
$ exit
$ ssh wikibooks03
$ exit
$ ssh wikibooks04
$ exit
$ start-dfs.sh
```

## jps를 통한 자바 프로세스 확인
터미널에 ```jps``` 커맨드 수행
- wikibooks01
    - NameNode 떠있어야됨
- wikibooks02
    - DataNode, SecondaryNameNode 떠있어야됨

## 웹 인터페이스 확인
http://localhost:50070 혹은 http://172.28.0.2:50070 를 통해 웹 인터페이스 접근 가능  
![image](https://user-images.githubusercontent.com/55429237/195596927-1a967442-0a30-4d45-abab-f67205bf4660.png)

## 작업 완료 후  
```docker-compose down```

