# WordPress Docker

使用 DOcker Compose 建立 NGINX + wordpress:fpm + MySQL 的系統

## 使用方法

1. 修改 `./docker/.env` 裡面的 MySQL 帳號密碼
2. 在 `./nginx/` 下準備 SSL 憑證（檔名是 `ssl.csr` 和 `ssl.key`）
   - 產生憑證：`openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout ssl.key -out ssl.csr`
3. 修改 `./nginx/nginx.conf`，將 `localhost` 改成自己的網域
4. 進到 `./docker` 目錄下，執行 `docker-compose up -d`

## Usage

1. Modify the file `./docker/.env` (account and password of MySQL)
2. Put SSL certificate files in `./nginx/` (filenames: `ssl.csr` and `ssl.key`)
   - Generate: `openssl req -x509 -nodes -days 3650 -newkey rsa:2048 -keyout ssl.key -out ssl.csr`
3. Modify `server_name` in `./nginx/nginx.conf`(recommand replace all `localhost`)
4. run `docker-compose up -d` in `./docker`
