# dockerfile_php_node
laravel, nodeが初期から使えるコンテナを建てる

## exec commands
.envを作成、編集

`copy .env.example .env`

image作成

`docker compose build`

コンテナ起動

`docker compose up -d`
