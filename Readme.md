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
```sh
$ ssh wikibooks02
$ ssh wikibooks03
$ ssh wikibooks04
$ start-dfs.sh
```

## 작업 완료 후  
```docker-compose down```

