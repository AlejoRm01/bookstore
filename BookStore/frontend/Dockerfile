FROM node:13.12.0-alpine AS builder

WORKDIR /app


ENV PATH /app/node_modules/.bin:$PATH

COPY . ./

RUN npm ci --silent
RUN npm install react-scripts@3.4.1 -g --silent


RUN npm run build

RUN ls /app/build

FROM nginx:alpine

WORKDIR /usr/share/nginx/html

RUN rm -rf ./*

COPY --from=builder /app/build .

RUN ls 

EXPOSE 80
EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]