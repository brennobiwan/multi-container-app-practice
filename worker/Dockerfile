# pick a base image
FROM node:alpine

# create a working dir
WORKDIR "/app"

# copy the list of dependencies
COPY ./package.json ./

# install the dependencies
RUN npm install 

# copy all the code
COPY ./ ./

# set the start up command
CMD ["npm", "run", "start"]
