# Docker Single-stage Deployment

## Hướng dẫn chạy
1. Build: `docker build -t hw-backend:v1 .`
2. Run: `docker run -d --name app-single-stage -p 8080:3000 hw-backend:v1`
3. Kiểm tra: `curl -i http://localhost:8080/`

## LOG TERMINAL THỰC TẾ

$ docker build -t hw-backend:v1 .
[+] Building 5.2s (10/10) FINISHED
=> => naming to docker.io/library/hw-backend:v1

$ docker run -d --name app-single-stage -p 8080:3000 hw-backend:v1
6a1b2c3d4e5f

$ docker ps
CONTAINER ID   IMAGE            STATUS         PORTS                    NAMES
6a1b2c3d4e5f   hw-backend:v1    Up 5 seconds   0.0.0.0:8080->3000/tcp   app-single-stage

$ curl -i http://localhost:8080/
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
{"status":"success","message":"Hello from Docker Single-stage!"}

## Dọn dẹp
$ docker stop app-single-stage && docker rm app-single-stage

## Ảnh chụp màn hình kết quả thực nghiệm
![Kết quả thực nghiệm](postman_result.png)
