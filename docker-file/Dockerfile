FROM ubuntu:22.04

# Update package lists and install necessary packages
RUN apt-get update && \
    apt-get install -y nginx git

# Configure NGINX (relevant when you are running NGINX within a Docker container)
RUN echo "daemon off;">>/etc/nginx/nginx.conf

# Clone the repository into a temporary directory
RUN git clone https://github.com/kmarjun/projects.git /tmp/app

# Move the contents of the temporary directory to the desired destination
RUN mv /tmp/app/* /var/www/html/ && \
    rm -rf /tmp/app

# Expose port 80
EXPOSE 80

# Set the command to start NGINX
CMD ["/usr/sbin/nginx", "-c", "/etc/nginx/nginx.conf"]

