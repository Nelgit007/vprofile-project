#Stage 1 - BUild Artifact
#The app was writtent in java and requires maven build tool,
#thus we need jdk as a base image, to install maven
FROM openjdk:11 AS BUILD_IMAGE
#confirm the base image of your openjdk (requires yum or apt)
RUN apt update && apt install maven -y
#clone source code
RUN git clone https://github.com/Nelgit007/vprofile-project.git
RUN cd vprofile-project && git checkout docker && mvn install

#Stage 2 - Build and package app image
#App written in Java require web server functionality support,
#so we use tomcat a java  servlet container, and web server
FROM tomcat:9-jre11
#Remove default artifact from tomcat server
RUN rm -rf /usr/local/tomcat/tomcat/webapps/*
#copy artifact from build stage-1
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]

