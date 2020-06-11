FROM node:alpine
ENV PATH /usr/app/node_modules/.bin:$PATH

WORKDIR /usr/app
COPY ./package.json ./
RUN npm install
COPY . .
RUN npm run build

FROM nginx:alpine
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --chown=nginx:nginx --from=0 /usr/app/build /usr/share/nginx/html
