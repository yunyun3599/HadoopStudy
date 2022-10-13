## 기본적인 WordCount 예제를 통해 잘 작동하는 지 확인해보기 

### 수행 위치
- wikibooks01 컨테이너의 터미널
- 작업 경로는 cd $HADOOP_HOME

## 예제 파일
- $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.7.jar
```bash
$ ./bin/hadoop jar $HADOOP_HOME/share/hadoop/mapreduce/hadoop-mapreduce-examples-2.7.7.jar wordcount cetc/hadoop/hadoop-env.sh wordcount_output
```
- 하둡 명령어를 통해 jar 파일 실행  
- hadoop-mapreduce-examples-2.7.7.jar 파일의 wordcount 클래스를 실행하는데, 입력값으로 /conf/hadoop-env.sh 파일을, 출력값으로 output 폴더를 지정

로그 출력 후 명령 완료되면 fs 명령어에 cat 파라미터를 지정해 HDFS에 저장된 출력값을 확인
```bash
./bin/hadoop fs -cat wordcount_output/part-r-00000
```
