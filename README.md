## Description

This is a simple site that I following this [tutorial](https://laracasts.com/series/laravel-8-from-scratch) created.

You can find the  instructor's version [here](https://github.com/JeffreyWay/Laravel-From-Scratch-Blog-Project).

## How to use

I use Sail to run this repository in WSL.

The following will share my method.

#### prerequisite
 - install [docker desktop](https://www.docker.com/products/docker-desktop/) in your Windows(yes, Windows not WSL).

---

1. use `git clone` or any method to clone this project to your local.
2. run `cp .env.example .env`
3. run 
```
  docker run --rm \
    -u "$(id -u):$(id -g)" \
    -v $(pwd):/var/www/html \
    -w /var/www/html \
    laravelsail/php81-composer:latest \
    composer install --ignore-platform-reqs
```

4. run `./vendor/bin/sail up -d`
5. run  `./vendor/bin/sail artisan key:generate`
6. run `./vendor/bin/sail artisan migrate` or `./vendor/bin/sail artisan migrate --seed`
7. open browser and go to  http://localhost
