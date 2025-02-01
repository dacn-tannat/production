# Stage 1
FROM node:22-alpine as build-stage

WORKDIR /app

COPY client/ .

RUN npm install

RUN npm run build

# Stage 2
FROM nginx:1.27

WORKDIR /usr/share/nginx/html

# Remove default nginx static assets
RUN rm -rf ./*

COPY --from=build-stage /app/dist /usr/share/nginx/html

# Mở port 80 cho Nginx
EXPOSE 80 

# Chạy Nginx (detached mode)
CMD ["nginx", "-g", "daemon off;"]