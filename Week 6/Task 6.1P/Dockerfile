# this is a from instruction starts a new build stage, i am using official node.js 18 image from docker hub
FROM node:18-slim

# setting the working directory in the container, if directory doesn't exist then docker will make one 
WORKDIR /usr/src/app

# copying the package.json and package-lock.json into the working directory in the container 
COPY package.json ./

# installing any dependencies 
RUN npm install

# copying the application's source code form my local directory, to the working directory in the container 
COPY . . 

# the expose instruction will inform docker that the containter listens on the 3000 network port at runtime
EXPOSE 3000

# with the CMD command, i am defining the command to run my application 
CMD ["node", "index.js"]
