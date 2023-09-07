FROM node:17-alpine 
RUN npm install -g nodemon 
WORKDIR /app
COPY package.json .
RUN npm install
COPY . . 
EXPOSE 8000 
# package.json -> "dev": "nodemon server.js"
CMD ["npm", "run", "dev"] 

# docker build -t nodeimage1 .
# docker run --name nodecontainer1 -it -p 8000:8000 -v path/to/docker-nodejs:/app -v /app/node_modules nodeimage1
