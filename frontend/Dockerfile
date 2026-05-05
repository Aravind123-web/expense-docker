# frontend deployment in nginx
FROM nginx
# remove default nginx content
RUN rm -rf /usr/share/nginx/html/index.html
# remove default nginx configuration
RUN rm -rf /etc/nginx/nginx.conf
# remove default nginx configuration
RUN rm -rf /etc/nginx/conf.d/default.conf
# create necessary directories for nginx and set appropriate permissions
RUN mkdir -p /var/cache/nginx/client_temp && \
        mkdir -p /var/cache/nginx/proxy_temp && \
        mkdir -p /var/cache/nginx/fastcgi_temp && \
        mkdir -p /var/cache/nginx/uwsgi_temp && \
        mkdir -p /var/cache/nginx/scgi_temp && \
        chown -R nginx:nginx /var/cache/nginx && \
        chown -R nginx:nginx /etc/nginx/ && \
        chmod -R 755 /etc/nginx/ && \
        chown -R nginx:nginx /var/log/nginx
# create a file for nginx to store its PID and set appropriate permissions
RUN touch /var/run/nginx.pid && \
    chown -R nginx:nginx /var/run/nginx.pid /run/nginx.pid
# copy our custom nginx configuration to nginx configuration location
COPY expense.conf /etc/nginx/nginx.conf
# copy our frontend code to nginx content location
COPY code /usr/share/nginx/html
# set nginx user to nginx to run the application with non-root privileges
USER nginx
