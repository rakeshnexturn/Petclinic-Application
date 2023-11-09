# base image
FROM nginx:latest

# Copy the Elastic APM agent JAR file
COPY elastic-apm-agent-1.43.0.jar /

# Copy Nginx configuration file
COPY nginx.conf /etc/nginx/nginx.conf

# Start Nginx with Elastic APM agent
CMD ["java", "-javaagent:/elastic-apm-agent-1.43.0.jar", "-Delastic.apm.service_name=nginx-app", "-Delastic.apm.secret_token=Pe0wcjHdiSHTkw6wIn", "-Delastic.apm.server_url=https://5602858c918a4628985b301a945d7c6d.apm.eastus2.azure.elastic-cloud.com:443", "-Delastic.apm.environment=my-environment", "nginx", "-g", "daemon off;"]
