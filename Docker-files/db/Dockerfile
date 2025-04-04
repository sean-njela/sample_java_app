FROM mysql:8.0.33
#labels can just be like tags 
LABEL "Project"="Sample_Java_App" 
LABEL "Author"="Sean"

#always check this with your developer or the source code main/resources/application.properties
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"  
ADD db_backup.sql docker-entrypoint-initdb.d/db-backup.sql  
#in the ADD above, we got the second path from docs (always read docs)

#by default mysql runs on port 3306 so no need for `EXPOSE`