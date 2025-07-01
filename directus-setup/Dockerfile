# Use an official Node.js runtime as a parent image
FROM node:22-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the port that Directus will listen on
EXPOSE 8055

# --- CORS und andere Einstellungen ---
ENV CORS_ENABLED=true
ENV CORS_ORIGIN=true
ENV PUBLIC_URL="https://projectnoorbackend-564292521955.europe-west3.run.app"

# Der CMD-Befehl startet Directus.
# Directus wird automatisch auf dem von Cloud Run vorgegebenen PORT lauschen.
CMD ["npx", "directus", "start"]