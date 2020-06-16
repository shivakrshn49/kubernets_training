FROM ubuntu:18.04
# Install OS Update
RUN apt-get update
# Install apache
RUN apt-get -y install apache2
# Create index.html
RUN echo "docker training" > /var/www/html/index.html
# Create script to start apache in foreground
RUN echo ". /etc/apache2/envvars" > /run.sh
RUN echo "mkdir -p /var/run/apache2" >> /run.sh
RUN echo "mkdir -p /var/lock/apache2" >> /run.sh
RUN echo "/usr/sbin/apache2 -D FOREGROUND" >> /run.sh
# Provide execute permission for script
RUN chmod 755 /run.sh
# Expose port number
EXPOSE 80
# Define running process
CMD /run.sh
