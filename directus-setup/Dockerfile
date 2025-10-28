FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

# --- Directus Configuration ---
# These variables were already set
ENV CORS_ENABLED=true
ENV CORS_ORIGIN=true
ENV PUBLIC_URL="https://projectnoorbackend-168591294204.europe-west3.run.app"

# --- Fix: Add these mandatory variables ---

# 1. A mandatory random string for security
#    REPLACE "your-long-random-secret-string-here" with your own secret


# 2. Database configuration (using the sqlite file from your repo)
ENV DB_CLIENT="sqlite3"
ENV DB_FILENAME="/app/directus-setup/data/niksdb.db"

# --- Cloud Run Port Configuration ---
# These are correct from the last attempt
ENV HOST=0.0.0.0
ENV PORT=8080

CMD ["npx", "directus", "start"]