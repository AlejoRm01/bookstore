FROM node:13.12.0-alpine

WORKDIR /app


ENV PATH /app/node_modules/.bin:$PATH

COPY . ./

RUN npm install --silent

EXPOSE 5000

CMD ["npm", "start"]
