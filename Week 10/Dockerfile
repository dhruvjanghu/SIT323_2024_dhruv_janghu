# Use the official Node.js image from the Docker Hub as the base image
FROM node:14

# Create a directory for the app inside the Docker container and switch to it
WORKDIR /usr/src/app

# Copy the package.json and package-lock.json files to the WORKDIR
COPY package*.json ./

# Run the npm install command to install the app's dependencies
RUN npm install

# Copy the rest of the application code to the WORKDIR
COPY . .

# Create a new entrypoint script inside the Docker container
RUN echo -e "#!/bin/sh\nexec node index.js" > /usr/local/bin/docker-entrypoint.sh

# Make the entrypoint script executable
RUN chmod +x /usr/local/bin/docker-entrypoint.sh

# Open port 3000 on the Docker container
EXPOSE 3000

# Use the new entrypoint script to start the application
ENTRYPOINT ["/usr/local/bin/docker-entrypoint.sh"]
