FROM maven:latest AS build
COPY src /usr/src/app/src
COPY pom.xml /usr/src/app
RUN mvn -f /usr/src/app/pom.xml clean package

FROM openjdk:11-jre
COPY --from=build /usr/src/app/target/*.jar /usr/app/app.jar
ENTRYPOINT ["java","-jar","/usr/app/app.jar"]
