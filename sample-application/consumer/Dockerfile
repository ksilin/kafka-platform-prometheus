FROM maven:latest as mavenBuild
WORKDIR /app
COPY pom.xml .
# 
RUN mvn -B package -Dmaven.test.skip -Dmaven.main.skip && rm -r target
# Copy all other project files and build project
COPY src ./src
RUN mvn -B package -Dmaven.test.skip

FROM java:8
WORKDIR /app
COPY --from=mavenBuild ./app/target/*.jar ./
ENV JAVA_OPTS ""
CMD [ "bash", "-c", "java ${JAVA_OPTS} -jar *.jar -v"]
