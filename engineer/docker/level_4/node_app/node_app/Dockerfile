FROM node:10-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install

COPY --chown=node:node . .
USER node
EXPOSE 3002
CMD [ "node", "server.js" ]