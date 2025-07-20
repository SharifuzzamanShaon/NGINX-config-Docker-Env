# Dockerfile
FROM ubuntu:22.04

# Install Nginx
RUN apt update && \
    apt install -y nginx && \
    apt clean

# Remove default HTML
RUN rm -rf /var/www/html/*

# Copy our HTML and nginx config
COPY index.html /var/www/html/
COPY nginx.conf /etc/nginx/nginx.conf

# Expose port
EXPOSE 80

# Start nginx in foreground
CMD ["nginx", "-g", "daemon off;"]
