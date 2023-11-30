# Use an official Node.js runtime as a base image
FROM node:16

# Set the working directory in the container
WORKDIR /my-world-backend

# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY . .

# Expose the port on which the Nest.js app will run
EXPOSE 3000

# Command to start the Nest.js app
CMD ["npm", "start"]
