FROM gradle:7-jdk11-alpine

WORKDIR /backend

COPY src/ /backend/src
COPY build.gradle /backend/build.gradle
CMD gradle bootRun
