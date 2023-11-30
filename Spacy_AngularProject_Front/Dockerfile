# Use an official Node.js runtime as a base image
FROM node:16 AS builder

# Set the working directory in the container
WORKDIR /Spacy_AngularProject_Front


# Copy package.json and package-lock.json to the container
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY . .

# Build the Angular app
RUN npm run build --prod

# Use a smaller, official image for the production environment
FROM nginx:alpine

# Copy the built app from the builder stage to the nginx image
COPY --from=builder /Spacy_AngularProject_Front/dist/my-angular-app /usr/share/nginx/html

# Expose port 80 for the NGINX server
EXPOSE 80

# Command to start NGINX
CMD ["nginx", "-g", "daemon off;"]
