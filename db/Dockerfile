FROM mysql:5.7
# M1 Macな人は、暫定的に下の行を有効にしてください(2020-12-30現在)
# FROM mysql@sha256:dce31fcdd15aaedb5591aa89f19ec37cb79981af46511781fa41287d88ed0abd

# (1) パッケージアップデート
RUN apt-get update

# (2) スクリプトと各種設定ファイルのコピー
COPY etc/mysql/mysql.conf.d/mysqld.cnf /etc/mysql/mysql.conf.d/
COPY etc/mysql/conf.d/mysql.cnf /etc/mysql/conf.d/
COPY init.d/* /docker-entrypoint-initdb.d/
COPY prepare.sh /usr/local/bin/
COPY init-data.sh /usr/local/bin/
COPY sql /sql

# (3) mysqldの実行
CMD ["mysqld"]
