FROM node:17.7.2-buster-slim AS development

ARG stage=production
ENV stage=$stage

WORKDIR /app

COPY package-lock.json package.json /app/

RUN npm ci

COPY src /app/src
COPY public /app/public

CMD ["npm", "start"]

FROM development AS build

RUN npm run build --verbose

FROM nginx:1.17.9 AS production

COPY --from=build /app/build /usr/share/nginx/html

CMD ["nginx", "-g", "daemon off;"]