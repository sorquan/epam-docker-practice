FROM node:12-alpine AS builder
WORKDIR /usr/src/app
COPY / ./
RUN npm install && npm run build

FROM nginx:alpine
COPY --from=builder /usr/src/app/build /usr/share/nginx/html
RUN sed -i '/index.html index.htm;/a \\ttry_files $uri $uri/ /index.html;' /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
