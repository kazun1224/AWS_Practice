FROM node:16

RUN npm install -g http-server
# 作業ディレクトリの作成＆指定
WORKDIR /app
# COPYはホストマシンからコンテナ側にコピー
COPY package*.json ./
# COPYしたpackage.json、package-lock.jsonをもとにアプリケーションをインストール
RUN npm install
# インストールしたアプリケーションをコピー
COPY . .
RUN npm run build
# 公開するポート番号
EXPOSE 8080
# 下記のコマンドを実行してサーバーを起動
CMD ["http-server","dist"]
