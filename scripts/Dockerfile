FROM node

# Install CURL for ECS Helth Checks
RUN apt-get update && apt-get install -y --no-install-recommends curl

# Delete cached packages 
RUN apt-get clean && rm -rf /var/lib/apt/lists/*

WORKDIR /app
COPY package*.json ./
COPY client/ ./client
COPY server/ ./server
COPY assets/ ./assets

RUN npm install

EXPOSE 3001
CMD ["node", "server/server.js"]