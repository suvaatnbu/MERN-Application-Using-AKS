# Stage 1: Build React app
FROM node:18 AS build
WORKDIR /app

# Copy package.json and install dependencies
COPY app/package*.json ./
RUN npm install

# Copy rest of the source code
COPY app/. .

# Build the production files
RUN npm run build

# Stage 2: Nginx server to serve React build
FROM nginx:alpine
COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]

