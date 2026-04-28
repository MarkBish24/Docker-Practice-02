FROM node:20-alpine

# Create app user
RUN addgroup -S app && adduser -S app -G app

WORKDIR /app

# Copy package files first (for cache)
COPY package*.json ./

# Install deps as root (faster, no permission pain)
RUN npm install

# Copy rest of app
COPY . .

# Fix ownership ONCE
RUN chown -R app:app /app

USER app

EXPOSE 5173

CMD ["npm", "run", "dev", "--", "--host"]
