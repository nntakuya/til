# Docker 環境構築

## 大まかな手順
1. ベースにするDockerイメージを決める
2. `docker run -it <docker-image> sh` でコンテナ内部で作業suru
3. 1行ずつ、うまくいったらどこかにメモ
4. 失敗したらいったん`exit`して再度`docker run`
5. オプション付きで`docker run`が必要なケース
6. 全部うまくいったら、Dockerfileにする



## 参考URL
- [効率的に安全な Dockerfile を作るには](https://qiita.com/pottava/items/452bf80e334bc1fee69a)
- [Alpine Linux で Docker イメージを劇的に小さくする](https://qiita.com/asakaguchi/items/484ba262965ef3823f61)
