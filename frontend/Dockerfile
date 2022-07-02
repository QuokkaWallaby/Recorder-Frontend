FROM nginx:1.21.0

# web build 결과 저장용 디렉토리 생성
RUN mkdir -p /app/build
WORKDIR /app
ADD ./build ./build

# nginx 설정 add
RUN rm /etc/nginx/conf.d/default.conf
COPY ./nginx.conf /etc/nginx/conf.d/direct-seller-ui.conf

# nginx log 디렉토리 생성
RUN mkdir /etc/nginx/logs
RUN chown -R nginx:root /etc/nginx/logs

# expose http, https port
EXPOSE 80
EXPOSE 443

CMD ["nginx", "-g", "daemon off;"]