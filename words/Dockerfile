FROM maven AS builder

COPY pom.xml .
RUN mvn verify

COPY src src
RUN mvn verify


FROM openjdk:8-jre-alpine

COPY --from=builder target/ /target

CMD exec java -Xmx8m -Xms8m -jar target/words.jar


#FROM ubuntu
#RUN apt update
#RUN apt-get install -y maven openjdk-8-jdk
#COPY . .

#compilation
#CMD ["mvn verify","cd ./target","java -Xmx8m -Xms8m -jar words.jar"]


#FROM maven AS builder
#COPY pom.xml .
#RUN mvn verify

#COPY src src 
#RUN mvn verify 
#from openjdk:8-jre-alpine

#COPY --from=builder target/ /target

#CMD exec java -Xmx8m -Xms8m -jar words.jar
