# Use the latest Node.js 20 image as the base image
FROM node:20-alpine3.22
# Expose port 8080 for the application
EXPOSE 8080 
# Set the environment variable DB_HOST to mysql, which is the hostname of the MySQL container. This allows the application to connect to the MySQL database using this hostname.
ENV DB_HOST=mysql
# Create a new user named 'expense'
# creatung group named 'expense' and adding user 'expense' to that group. This is done to ensure that the application runs with a non-root user, which is a best practice for security reasons.
RUN addgroup -s expense && adduser -s expense -G expense
# Set the working directory to /opt/server
RUN mkdir /opt/server
# Set the ownership of the /opt/server directory to the 'expense' user
RUN chown -R expense:expense -R /opt/server
# switch to opt server directory
WORKDIR /opt/server
# Copy the package.json file to the /opt/server directory
COPY package.json .
# Copy all the .js files in to the opt/server directory
COPY *.js .
# Install all dependencies defined in the package.json file
RUN npm install
# cmd to run the application using node index.js when the container starts
CMD ["node", "index.js"]


