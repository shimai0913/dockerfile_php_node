# dockerfile_php_node
laravel, nodeが初期から使えるコンテナを建てる

```
# php -v
PHP 7.4.1 (cli) (built: Dec 28 2019 14:45:59) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
```
```
# php artisan -V
Laravel Framework 6.20.38
```

```
# node -v
v16.13.0
```

## exec commands
.envを作成、編集

`copy .env.example .env`

image作成

`docker compose build`

コンテナ起動

`docker compose up -d`
