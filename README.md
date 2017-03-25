# spark-docker-example
run a very simple spark example on docker container



docker pull gettyimages/spark

docker run -d   -it  -p 4040:4040  -p 9999:8080  gettyimages/spark 

mvn package

docker cp target\spark-examples-1.0-SNAPSHOT.jar 27a76af3e4e4:/usr/spark-2.1.0/examples/jar/spark-examples-1.0-SNAPSHOT.jar

# find docker hash

docker exec -it 27a76af3e4e4  bash

./bin/spark-submit  --class "com.spark.example.SimpleApp"   --master local[4]   examples/jar/spark-examples-1.0-SNAPSHOT.jar


you can also open http://192.168.99.100:9999/
