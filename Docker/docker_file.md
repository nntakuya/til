# Docker fileの書き方

### ローカルのDockerで、swaggerを実行するコマンド
```
docker run --rm -d -p 8080:8080 -v $(pwd):/usr/share/nginx/html/swagger-template -e API_URL=http://localhost:8085/swagger-template/swagger.yaml swaggerapi/swagger-ui
```
