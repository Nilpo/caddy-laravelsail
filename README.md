## Proof of Concept

This is a freshly installed Laravel 9 project created using the online builder script. It attempts to use Caddy as a reverse proxy for SSL testing with the Laravel Sail Docker workflow. The original concept is documented here.

- [https://mikefallows.com/posts/laravel-sail-vite-ssl-custom-domain/](https://mikefallows.com/posts/laravel-sail-vite-ssl-custom-domain/)

The issue demonstrated in this project is described here.

- [https://gist.github.com/gilbitron/36d48eb751875bebdf43da0a91c9faec?permalink_comment_id=4350497#gistcomment-4350497](https://gist.github.com/gilbitron/36d48eb751875bebdf43da0a91c9faec?permalink_comment_id=4350497#gistcomment-4350497).

Finally, the method being employed here is demonstrated more simply in the following Gist.

- [https://gist.github.com/Nilpo/e88d9d43623876921854d38851cd37e8](https://gist.github.com/Nilpo/e88d9d43623876921854d38851cd37e8)

## Deployment

Deploy this example as follows.

    git clone https://github.com/Nilpo/caddy-laravelsail.git && cd caddy-laravelsail
    docker run --rm --interactive --tty -v $(pwd):/app composer install
    ./vendor/bin/sail up -d

While it's not entirely necessary for this demo, you may also install database migrations, NPM dependencies, and run Vite in development.

    ./vendor/bin/sail artisan migrate
    ./vendor/bin/sail npm  install

If you make any major changes or alter the Caddy config, you'll need to rebuild all containers.

    ./vendor/bin/sail down && ./vendor/bin/sail up --build -d

## Caveats

For debugging purposes, the .env file has been committed to this repository. The is not a secure practice. As such, this project should **not** be forked or used as the basis of a production project.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

This proof of concept is released into the Public Domain without license.
