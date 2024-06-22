FROM nginx
LABEL "Project"="vprofile"
LABEL "Author"="Nelson"

#Remove defalt nginx conf files
RUN rm -rf /etc/nginx/conf.d/default.conf

#Copy own conf and place in right location
#ensure file is in same location with Dockefile
#ENSURE to run container with the name (vproapp)
COPY nginvproapp.conf /etc/nginx/conf.d/vproapp.conf


