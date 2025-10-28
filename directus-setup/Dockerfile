FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
ENV CORS_ENABLED=true
ENV CORS_ORIGIN=true
ENV PUBLIC_URL="https://projectnoorbackend-168591294204.europe-west3.run.app"

# Fix: Add these two lines to force the correct host and port
ENV HOST=0.0.0.0
ENV PORT=8080

CMD ["npx", "directus", "start"]