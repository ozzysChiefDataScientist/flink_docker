## Outcomes
1. Spins up a Flink container_name
2. Runs a simple [streaming Word Count job](https://github.com/ozzysChiefDataScientist/flink_java_11_job) (credit: [Apache Software Foundation](https://github.com/apache/flink/tree/master/flink-examples/flink-examples-streaming/src/main/java/org/apache/flink/streaming/examples/wordcount))

## Prerequisites
1. Download the JAR file used in this example into the root folder
   1. Download pre-compiled jar with `curl https://github.com/ozzysChiefDataScientist/flink_java_11_job/blob/main/build/libs/my_first_flink_job_java_11.jar -o my_first_flink_job_java_11.jar`
   2. Alteratively, clone [this repo](https://github.com/ozzysChiefDataScientist/flink_java_11_job/tree/main) and run `gradle build`

## To Use
1. In terminal, run `docker compose up`
2. Visit [http://localhost:8081/#/overview](http://localhost:8081/#/overview) to see Flink dashboard
3. In a separate terminal tab, run:
   1. `docker cp my_first_flink_job_java_11.jar jobmanager:/job.jar`
   2. `docker exec -it jobmanager /bin/bash`
   3. Inside the docker container, run `./bin/flink run -c org.gradle.example.simple.WordCount /job.jar`
