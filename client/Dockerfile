# Step 1: Build the frontend
FROM node:18 AS builder

# Set working directory
WORKDIR /app

# Copy package.json and install dependencies
COPY package*.json ./
RUN npm install

# Copy all other source files and build
COPY . .
RUN npm run build

# Step 2: Serve with Nginx
FROM nginx:stable-alpine

# Copy built files to Nginx's public directory
COPY --from=builder /app/dist /usr/share/nginx/html

# Step 2: Serve with Nginx
# Step 2: Serve with Nginx
FROM nginx:stable-alpine

COPY --from=builder /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf  
# Expose port (usually 80 for frontend)
EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
