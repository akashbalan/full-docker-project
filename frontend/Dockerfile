FROM node:20-alpine

WORKDIR /frontend

COPY package*.json ./

RUN npm install

COPY . .


EXPOSE 80

RUN npm run build

RUN apk add --no-cache nginx

RUN rm -rf /etc/nginx/conf.d/*

COPY nginx.conf /etc/nginx/conf.d/default.conf

CMD ["nginx", "-g", "daemon off;"]
