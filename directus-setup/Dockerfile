FROM node:18-alpine

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the project
COPY . .

# Expose Directus port
EXPOSE 8055

# Run Directus in development mode
CMD ["npx", "directus", "start"]
