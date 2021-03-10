FROM openjdk:8-slim
#FROM weaveworksdemos/msd-java:jre-latest

WORKDIR /usr/src/app
COPY orders.jar ./app.jar
COPY dd-java-agent.jar ./
COPY java.sh /usr/local/bin/java.sh 
RUN chmod +x /usr/local/bin/java.sh 
RUN	chown -R ${SERVICE_USER}:${SERVICE_GROUP} ./app.jar

USER ${SERVICE_USER}

ENTRYPOINT ["/usr/local/bin/java.sh","-jar","./app.jar", "--port=80"]
