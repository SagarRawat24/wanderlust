# Stage 1
FROM node:21-alpine AS base

# setup the working dir
WORKDIR /app

# code
COPY . .

# packages install
RUN npm install

# tests
RUN npm run test

# Stage 2
FROM node:21-alpine

# setup the working dir
WORKDIR /app

# copy the above stage as compressed
COPY --from=base /app .

COPY .env.docker .env

# Port
EXPOSE 8080

# App
CMD ["npm", "start"]
