# Use an official Node.js runtime as a parent image
FROM node:22-alpine

# Set the working directory to /app
WORKDIR /app

# Install pnpm globally
RUN npm install -g pnpm

# Copy package.json and pnpm-lock.yaml
COPY package.json pnpm-lock.yaml ./

# Install project dependencies
RUN pnpm install --frozen-lockfile

# Copy the rest of the application's source code
COPY . .

# Run the build command
RUN pnpm run build

# Expose the port
EXPOSE 3000

# Start the application
CMD [ "node", "dist/main" ]