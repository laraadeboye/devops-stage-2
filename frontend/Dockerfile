# Use an official image
FROM node:latest

# Set working directory
WORKDIR /app

# Copy requirements
COPY package.json package-lock.json ./

# Install dependencies
RUN npm install

# Copy the rest of the project files
COPY . .

# Expose port
EXPOSE 5173

# Start the Vite development server
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0", "--port", "5173"]
 