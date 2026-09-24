## 🐳 Docker Multi-Stage Build

Implemented a **multi-stage Docker build** using `nginx:alpine` to create a lightweight production image.

### 🔹 What I Implemented

- **Builder Stage** → Downloads and extracts the website template.
- **Production Stage** → Copies only the required files into Nginx.
- **Alpine Image** → Reduces unnecessary packages and overall image size.
- **Port 80** → Exposes the Nginx web application.

### 🔹 Key Concept

**Builder → Extract Application → Copy Required Files → Lightweight Nginx Image**

### 🔹 Benefit

Multi-stage builds help create **smaller, cleaner, and more efficient Docker images** by keeping build-time dependencies separate from the final production image.

````
FROM nginx:alpine AS builder 
WORKDIR /opt
ADD https://templatemo.com/download/templatemo_632_machina ./
RUN apk add --no-cache unzip
RUN mv templatemo_632_machina file.zip
RUN unzip file.zip -d /opt


FROM nginx:alpine
COPY --from=builder /opt/templatemo_632_machina/ /usr/share/nginx/html/
EXPOSE 80
CMD ["nginx", "-g", "daemon off;"]
````
