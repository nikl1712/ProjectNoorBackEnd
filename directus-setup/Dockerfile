# Use an official Node.js runtime as a parent image
FROM node:22-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
RUN npm install

# Copy the rest of the application code
COPY . .

# --- CORS und andere Einstellungen ---
# Diese werden besser direkt in Cloud Run gesetzt
ENV CORS_ENABLED=true
ENV CORS_ORIGIN=true
ENV PUBLIC_URL="https://projectnoorbackend-168591294204.europe-west3.run.app"

# Der CMD-Befehl startet Directus.
# Directus wird automatisch auf dem von Cloud Run vorgegebenen PORT lauschen.
CMD ["npx", "directus", "start"]