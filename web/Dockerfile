FROM node:14.7.0

# (1) パッケージアップデート
RUN apt-get update

# (2) NUXTソースファイルコピー
WORKDIR /webapp
COPY webapp /webapp
COPY wait-for-it.sh /usr/local/bin/

# (3) ライブラリを取得しビルド
RUN npm install
RUN npm run build

ENV HOST 0.0.0.0

CMD ["npm", "run", "start"]

EXPOSE 3000
