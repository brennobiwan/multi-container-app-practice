### BUILD STEP ###

# pick a base image
FROM node:alpine as builder

# create a working dir
WORKDIR "/app"

# copy the dependency list
COPY ./package.json ./

# install the dependencies
RUN npm install

# copy all the code
COPY ./ ./

# create the production version of the app
RUN npm run build



### RUN STEP ###

# pick the image that will deliver the app/website
FROM nginx

# copy only the build version of the app
COPY --from=builder /app/build /usr/share/nginx/html

# copy the webserver custom config
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
