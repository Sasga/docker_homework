FROM node:10-alpine as builder

WORKDIR /app

RUN chown node:node /app

USER node

COPY package*.json ./

RUN npm install

COPY --chown=node:node . .

RUN npm run build

FROM nginx:1.19.0

COPY nginx/default.conf /etc/nginx/conf.d/default.conf

WORKDIR /usr/share/nginx/html

RUN rm -rf ./*

COPY --from=builder /app/build .

EXPOSE 80

ENTRYPOINT ["nginx", "-g", "daemon off;"]
