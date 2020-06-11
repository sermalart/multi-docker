FROM node:alpine
ENV PATH /usr/app/node_modules/.bin:$PATH

WORKDIR /usr/app
COPY ./package.json ./
RUN npm install
COPY . .

CMD ["npm", "run", "start"]
