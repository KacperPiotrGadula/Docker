FROM node:13.10 AS development

#Initialization of a variable
ARG NODE_ENV=production 
#Indication of the value for the variable (later it will be changeable at the time of image building)
ENV NODE_ENV=$NODE_ENV

#Copy file from host to container
WORKDIR /code
COPY package-lock.json package.json /code/
#In this place dockerfile crate and move to container node_modules
RUN npm ci
#Copy app file to container
COPY src /code/src
COPY public /code/public

#Turn on npm for start process in container
CMD ["npm", "start"]

#Next stage
FROM development AS builder

#Build react.js app
RUN npm run build 

#Next stage - production ngnix
FROM nginx:1.17.9 AS production

#copy from secend stage app file from /code/build and move to path in container /usr/share//ngnix/html
COPY --from=builder /code/build /usr/share/nginx/html

#Uruchomienie ngnix 
CMD [ "nginx", "-g", "daemon off;" ]