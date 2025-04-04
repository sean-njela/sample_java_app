#build image
FROM maven:3.9.9-eclipse-temurin-21-jammy AS build_image
RUN git clone https://github.com/sean-njela/sample_java_app.git
# its best not to seperate commands to reduce number of layers 
RUN cd sample_java_app && mvn clean install -DskipTests


#service image
FROM tomcat:9-jdk21
# labels can just be like tags 
LABEL "Project"="Sample_Java_App"  
LABEL "Author"="Sean"
# sometimes you have to exec into the container to figure this path out 
RUN rm -rf /usr/local/tomcat/webapps*   
#--from keyword references earlier build and we are able to access it 
COPY --from=build_image /sample_java_app/target/*.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080

# image specific command to start the tomcat server
CMD ["catalina.sh", "run"]