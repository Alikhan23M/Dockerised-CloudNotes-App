# 1️⃣ Base Image
FROM node:18

# 2️⃣ Set working directory inside the container
WORKDIR /app

# 3️⃣ Copy only package.json and lock file first (for cache)
COPY package*.json ./

# 4️⃣ Install dependencies
RUN npm install

# 5️⃣ Copy the rest of the server code
COPY . .

# 6️⃣ Expose your backend port (same as in .env, usually 5000)
EXPOSE 5000

# 7️⃣ Start the server
CMD ["npx","nodemon", "server.js"]
