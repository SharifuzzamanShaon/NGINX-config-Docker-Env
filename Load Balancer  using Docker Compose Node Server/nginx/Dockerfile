
FROM nginx:alpine

# Enable template-based configuration
ENV NGINX_ENVSUBST_TEMPLATE_DIR=/etc/nginx/templates

# Copy templates into expected location
COPY default.conf.template /etc/nginx/templates/default.conf.template
