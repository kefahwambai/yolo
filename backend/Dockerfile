# Use a base image suitable for running a Node.js application
FROM node:latest

# Set the working directory
WORKDIR /yolo

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the backend files
COPY . .

# Set environment variables if necessary
# ENV ENV_VARIABLE=value

# Expose the port on which the backend application will run
EXPOSE 3001

# Specify the command to start the backend application
CMD ["npm", "start"]
