# Use the official Node.js image
FROM docker.io/library/node:18 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and yarn.lock files
COPY package.json yarn.lock ./

# Install dependencies
RUN yarn install

# Copy the rest of the application code
COPY . .

# Build the application
RUN yarn build

# Use a lightweight web server to serve the files
FROM docker.io/library/nginx:alpine

# Copy built files from the previous stage to nginx html directory
COPY --from=build /app/dist /usr/share/nginx/html

# Expose the port that Nginx will run on
EXPOSE 80

# Start Nginx
CMD ["nginx", "-g", "daemon off;"]
