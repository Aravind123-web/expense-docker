# frontend deployment in nginx
FROM nginx
# remove default nginx content
RUN rm -rf /usr/share/nginx/html/index.html
# remove default nginx configuration
RUN rm -rf /etc/nginx/nginx.conf
# remove default nginx configuration
RUN rm -rf /etc/nginx/conf.d/default.conf
# copy our custom nginx configuration to nginx configuration location
COPY expense.conf /etc/nginx/nginx.conf
# copy our frontend code to nginx content location
COPY code/ /usr/share/nginx/html


