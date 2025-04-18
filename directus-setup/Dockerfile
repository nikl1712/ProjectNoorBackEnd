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

# Set environment variables if needed (you can also set these in Cloud Run)
ENV DB_CLIENT=sqlite3
ENV DB_FILENAME=/app/data.db
ENV CORS_ALLOWED_ORIGINS="https://military-frontend-1023525350254.europe-west3.run.app,https://vocational-frontend-1023525350254.europe-west3.run.app,https://projectnoorvocational-564292521955.europe-west3.run.app"
ENV PUBLIC_URL="https://projectnoorbackend-564292521955.europe-west3.run.app"
# Update this after deployment

# Start Directus (adjust the start command if your setup differs)
CMD ["npx", "directus", "start"]
