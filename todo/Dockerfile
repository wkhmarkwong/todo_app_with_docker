FROM node:16-alpine

WORKDIR /app

COPY package*.json ./
COPY prisma ./prisma/
COPY .env ./
COPY tsconfig.json ./

RUN npm i prisma --save-dev
RUN npx prisma migrate dev --name init
RUN npm i

COPY . .

EXPOSE 3000

# Do production build in container instead of local machine
CMD npm run build && npm start