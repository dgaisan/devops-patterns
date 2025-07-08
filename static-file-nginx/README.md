# 🍊 Static File Server using NGINX

This project demonstrates a simple Dockerized static file server using **NGINX**.  
It serves a JSON file listing fruits.
---

## 📁 Project Structure
- `Dockerfile`: Builds a lightweight NGINX image with custom static content.
- `static/fruits.json`: The static file that gets served.
- `nginx.conf`: NGINX config file.

---

## 🛠️ Build the Docker Image

```bash
docker build -t fruit-list:1.0.0 .
```
## 🚀 Run the Container

```bash
docker run --name fruitlist -d -p 8080:80 fruit-list:1.0.0
```

## 🧼 Stop and Remove Container
```bash
docker stop fruitlist && docker rm fruitlist
```
