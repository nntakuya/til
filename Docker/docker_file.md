# Docker fileの書き方

### ローカルのDockerで、swaggerを実行するコマンド
```
docker run --rm -d -p 8080:8080 -v $(pwd):/usr/share/nginx/html/swagger-template -e API_URL=http://localhost:8085/swagger-template/swagger.yaml swaggerapi/swagger-ui
```

## Multi Stage Buildとは
アプリケーションの開発用ビルドとランタイムの依存を分離できる



### 参考文献
- [Use multi-stage builds](https://docs.docker.com/develop/develop-images/multistage-build/)
- [Docker マルチステージビルドのユースケースと実践](https://qiita.com/MtFootFrontier/items/04a82193e57713e993d6)
- [Docker multi stage buildで変わるDockerfileの常識](https://qiita.com/minamijoyo/items/711704e85b45ff5d6405)
