FROM openjdk:8
# RUN curl -L https://github.com/signalfx/splunk-otel-java/releases/latest/download/splunk-otel-javaagent-all.jar -o splunk-otel-javaagent-all.jar /
 ADD splunk-otel-javaagent.jar /splunk-otel-javaagent-all.jar
 ADD spring-petclinic-2.5.0-SNAPSHOT.jar /Spring-docker.jar
 ENV OTEL_SERVICE_NAME=zappos-apm-demo
 ENV SPLUNK_ACCESS_TOKEN=6rS4cTusLBUn6RdmBhy8yQ
 ENV OTEL_RESOURCE_ATTRIBUTES="environment=dev,app.version=1.2.3-alpha"
 ENV OTEL_EXPORTER_OTLP_ENDPOINT="http://otel:4317"
 
# ADD target/Spring-docker.jar Spring-docker.jar
 EXPOSE 8080

ENTRYPOINT ["java","-javaagent:/splunk-otel-javaagent-all.jar","-jar","Spring-docker.jar"]
