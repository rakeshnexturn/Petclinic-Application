# base image
FROM node:12.2.0

# Set the working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package.json /app/package.json
RUN npm install
RUN npm install -g @angular/cli@latest

# Copy the Elastic APM agent JAR file
COPY elastic-apm-agent-1.43.0.jar /

# Add the Angular app
COPY . /app

# Start the app with Elastic APM agent
CMD ["java", "-javaagent:/elastic-apm-agent-1.43.0.jar", "-Delastic.apm.service_name=angular-app", "-Delastic.apm.secret_token=Pe0wcjHdiSHTkw6wIn", "-Delastic.apm.server_url=https://5602858c918a4628985b301a945d7c6d.apm.eastus2.azure.elastic-cloud.com:443", "-Delastic.apm.environment=my-environment", "ng", "serve", "--host", "0.0.0.0", "--port", "4200", "--disableHostCheck", "true"]
