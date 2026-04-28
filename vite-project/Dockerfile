FROM node:22-alpine

WORKDIR /app

# Install deps first (better caching)
COPY package*.json ./
RUN npm install

# Copy the rest of the app
COPY . .

EXPOSE 5173

CMD ["npm", "run", "dev"]

