FROM node:alpine as builder
WORKDIR /app
COPY package*.json .
RUN yarn
COPY . .
RUN yarn build

### Single container deployment
FROM nginx
EXPOSE 3000
COPY --from=builder /app/nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html

# docker build .