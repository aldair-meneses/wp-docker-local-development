# wp-local-dev

## Start the environment

First, create the `.env` file from he `.env.sample`.

```sh
cp .env.sample .env
```

Run the followings commands to download the docker images and start the environment

```sh
docker compose build --pull
docker compose up -d
```

Run the followings command to give me permissions to host and set db credentials

```sh
sudo chown -R $(id -u):$(id -g) wordpress/
sudo chown -R $(id -u):$(id -g) src/

docker compose run -u $(id -u):$(id -g) --rm wp config create --dbhost="db" --dbname="wordpress" --dbuser="wordpress" --dbpass="wordpress" --locale=pt_BR --force --skip-check
``` 

Then, access `localhost` and you will be redirected to the page for the WordPress installation.

## Using WP-CLI

For use the WP-CLI, just run the wp service with a command to execute an action of your wish.

E.g: To install WooCommerce Plugin using WP-CLI

```sh
docker compose run -u $(id -u):$(id -g) --rm cli plugin install woocommerce
```
