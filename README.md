# wp-local-dev

## Start the environment

First, create the `.env` file from he `.env.sample`.

```sh
cp .env.sample .env
```

Run the following commands to download the docker images e start the environment

```sh
docker compose build --pull
docker compose up -d
```

Then, acess `localhost` and you will be redirect to the page for the WordPress instalation.

## Using WP-CLI

For use the WP-ClI, just run the wp service with a command to execute an action of your wish.

E.g: To install WooCommerce Plugin using WP-CLI

```sh
docker compose run -u $(id -u):$(id -g) --rm wp plugin install woocommerce
```
