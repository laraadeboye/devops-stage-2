# Use an official image
FROM node:latest

# Set working directory
WORKDIR /app

# Copy the all of the project files
COPY . .

# Install dependencies
RUN npm install

# Expose port
EXPOSE 5173

# Start the Vite development server
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0", "--port", "5173"]
 