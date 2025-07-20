# Use a lightweight Node.js base image
FROM node:22-alpine

# Maintainer info (optional but good practice)
LABEL maintainer="acashgupta960@gmail.com"

# Set working directory inside the container
WORKDIR /app

# Copy dependency files first for better caching
COPY package*.json ./
COPY vite.config.* ./
COPY jsconfig.json ./

# Install app dependencies
RUN npm install

# Copy the rest of the app files
COPY index.html ./
COPY public ./public
COPY src ./src
COPY .eslintrc.js ./


# Build the production version of the React app
RUN npm run build

# Install a lightweight HTTP server to serve the static files
RUN npm install -g serve

# Expose port 3000 (can be changed as needed)
EXPOSE 3000

# Command to serve the build folder
CMD ["serve", "-s", "dist", "-l", "3000"]
