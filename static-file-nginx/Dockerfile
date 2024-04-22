FROM nginx:latest

ADD nginx.conf /etc/nginx/nginx.conf
ADD static/fruits.json /usr/share/nginx/html/fruits.json

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

