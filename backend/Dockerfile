FROM gradle:7-jdk11-alpine

WORKDIR /app

COPY src/ /app/src
COPY build.gradle /app/build.gradle
CMD gradle bootRun
