FROM openjdk:8-jdk-alpine
MAINTAINER jonas.iggbom@axiomatics.com
ENV ADS_HOME=/usr/share/ads

RUN mkdir ${ADS_HOME}
#RUN adduser --disabled-password tomcat
#USER tomcat
COPY access-decision-service-1.2.0.jar ${ADS_HOME}
#COPY /pip/* ${ADS_HOME}/
#COPY /httpAndParser-PIP ${ADS_HOME}
COPY /conf ${ADS_HOME}/conf

EXPOSE 9090 8081
ENTRYPOINT $JAVA_HOME/bin/java -cp "${ADS_HOME}/*" com.axiomatics.ads.App server ${ADS_HOME}/conf/deployment.yml
#ENTRYPOINT $JAVA_HOME/bin/java -cp "${ADS_HOME}/access-decision-service-1.2.0.jar:${ADS_HOME}/table-attribute-connector-6.0.0.47.jar:${ADS_HOME}/h2-1.4.194.jar" com.axiomatics.ads.App server ${ADS_HOME}/conf/deployment.yml
