FROM node:alpine
WORKDIR /app
COPY package.json .
RUN npm install
COPY . .
CMD [ "npm", "run", "start" ]

# docker build . --> 28a9bc0c6e79