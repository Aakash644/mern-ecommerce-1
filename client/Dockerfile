# Use an official Node.js runtime as a parent image
FROM node:18

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY client/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY client/. .

# Build the React app
RUN npm run build

# Install a lightweight web server to serve the build files
RUN npm install -g serve

# Expose the port the app runs on
EXPOSE 3000

# Define the command to run the app
CMD ["serve", "-s", "build"]
