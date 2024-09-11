FROM node:21-alpine AS Base

workdir /app

copy package*.json ./

run npm install

copy . .


from node:21-alpine

workdir app

copy --from=Base /app .

copy .env.docker .env.local

expose 5173

CMD ["npm", "run", "dev", "--", "--host"]
