FROM ubuntu:latest AS build
RUN apt-get upate
RUN apt-get install openjdk-17-jdk -y

COPY . .

RUN apt-get install maven -y
RUN mvn clean install

COPY --from=build /target/todoList-1.0.0.jar app.jar

ENTRYPOINT [ "java", "-jar", "app.jar" ]