# Stage 1: Install dependencies
FROM node:18-alpine AS build
WORKDIR /app
COPY package*.json ./
RUN npm install --only=production 

# Stage 2: Run the application
FROM node:18-alpine
WORKDIR /app
COPY --from=build /app/node_modules ./node_modules
COPY app.js package.json ./
EXPOSE 3000
CMD ["node", "app.js"]
