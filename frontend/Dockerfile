FROM node
COPY spa /root/spa
WORKDIR /root/spa
RUN echo 'VUE_APP_API_ENDPOINT="http://localhost:4001/api"' >> .env.production.local
RUN npm install
RUN npm run build

FROM nginx  
COPY --from=0 /root/spa/ .
COPY nginx.conf /etc/nginx/nginx.conf   
EXPOSE 80
