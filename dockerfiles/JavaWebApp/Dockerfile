# Stage 1: Build the application
FROM maven:3.6.3-jdk-8 AS BUILD

# Set the working directory
WORKDIR /app

# Copy the entire project into the container
COPY . .

# Build the application
RUN mvn clean package

# Stage 2: Create the runtime image
FROM tomcat:8.5.69-jdk8-openjdk

# Copy the WAR file from the build stage to the Tomcat webapps directory
COPY --from=BUILD /app/target/my-web-app*.war /usr/local/tomcat/webapps/

# Expose the port that Tomcat runs on
EXPOSE 8080

# Start Tomcat
CMD ["catalina.sh", "run"]