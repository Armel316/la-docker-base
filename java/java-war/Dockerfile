FROM tomcat:10-jre21
ENV JAVA_OPTS="-XX:MaxRAMPercentage=70 -XX:InitialRAMPercentage=40"
COPY target/app.war /usr/local/tomcat/webapps/ROOT.war
EXPOSE 8080