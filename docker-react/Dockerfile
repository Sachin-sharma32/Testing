# everything in docker is a layer
# Layer 1: Telling Docker to use the node:17-alpine image as the base image for the container.
# react needs node, so install node in container
FROM node:17-alpine

# Layer 2: Telling Docker to create a directory called `app` in the container and set it as the working directory.
WORKDIR /app

# Layer 3: Copying the package.json file from the root of the project to the `app` directory in the container.
# docker uses "layer caching" - if till layer 3 nothing change then these steps will be skipped when re-building image, saves image build time and size
# hance copied and installed packages in Layer 3 and 4 before copying files
COPY package.json .

# Layer 4: Installing the dependencies listed in the package.json file.
RUN npm install

# Layer 5: Copying all the files from the root of the project to the `app` directory in the container.
COPY . .

# Layer 6: Telling Docker that the container will listen on port 3000.
EXPOSE 3000

# Layer 7: Telling Docker to run the `npm start` command when the container is started.
CMD ["npm", "run", "dev"]

# docker build -t reactImage . -> build image, -t -> tag, . -> where the Dockerfile is located

# docker run --name dockerApp -p 3000:3000 -d reactImage 
#-> run docker container
#-> -p -> map container port with local host port to see the app in our computer
#-> -d -> run container in detached mode, to used the termainal when container is running

# docker stop dockerApp
# docker start dockerApp 
# docker rum dockerApp 

# VOLUMES
# docker run --name dockerApp -it -p 3000:3000 -v C:\Users\HP\Desktop\questions\docker-:/app -v /app/node_modules reactimage
#-> -it - iterative mode 
#-> -v - volume
#-> C:\Users\HP\Desktop\questions\docker-:/app  - use this directory instead of /app, helpful in development to reflect changes made in code without rebuilding image
#-> this does not make changes to the image, just the running contianer is tracking local files instead of image's files
#-> -v /app/node_modules - use node_modules of image's /app directory instead of the local direcoty we specified

