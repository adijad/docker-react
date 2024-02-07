# Use an existing docker image as a baseFROM node:10-alpine
FROM node:10-alpine
RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app
WORKDIR /home/node/app

# Download and install dependencies
COPY package*.json ./
USER node
RUN npm install

COPY --chown=node:node . .
EXPOSE 8080

# Tell the image what to do when it starts 
CMD [ "node", "app.js" ]

