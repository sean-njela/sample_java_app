FROM nginx
#labels can just be like tags 
LABEL "Project"="Sample_Java_App"   
LABEL "Author"="Sean"

#remove the default configuration
RUN rm -rf /etc/nginx/conf.d/default.conf    
#then we copy our configuration into the folder
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf   

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

