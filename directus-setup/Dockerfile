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

# ─── Enable and configure CORS ─────────────────────────────────────────
ENV CORS_ENABLED=true
# Either echo back every incoming Origin:
ENV CORS_ORIGIN=true
# —or— lock it down to your frontend domain:
# ENV CORS_ORIGIN="https://projectnoorvocational-564292521955.europe-west3.run.app"

# (Optional: only if you need custom methods or headers)
ENV CORS_METHODS="GET,POST,PATCH,DELETE"
ENV CORS_ALLOWED_HEADERS="Content-Type,Authorization"
# ───────────────────────────────────────────────────────────────────────

ENV DB_CLIENT=sqlite3
ENV DB_FILENAME=/app/data.db
ENV PUBLIC_URL="https://projectnoorbackend-564292521955.europe-west3.run.app"

CMD ["npx", "directus", "start"]