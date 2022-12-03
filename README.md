## Proof of Concept

This is a freshly installed Laravel 9 project created using the online builder script. It attempts to use Caddy as a reverse proxy for SSL testing with the Laravel Sail Docker workflow. The original concept is documented here.

- [https://mikefallows.com/posts/laravel-sail-vite-ssl-custom-domain/](https://mikefallows.com/posts/laravel-sail-vite-ssl-custom-domain/)

The issue demonstrated in this project is described here.

- [https://gist.github.com/gilbitron/36d48eb751875bebdf43da0a91c9faec?permalink_comment_id=4350497#gistcomment-4350497](https://gist.github.com/gilbitron/36d48eb751875bebdf43da0a91c9faec?permalink_comment_id=4350497#gistcomment-4350497).

Finally, the method being employed here is demonstrated more simply in the following Gist.

- [https://gist.github.com/Nilpo/e88d9d43623876921854d38851cd37e8](https://gist.github.com/Nilpo/e88d9d43623876921854d38851cd37e8)

## Deployment

Deploy this example as follows.

    git clone https://github.com/Nilpo/caddy-laravelsail.git
    cd caddy-laravelsail
    ./vendor/bin/sail up -d
    ./vendor/bin/sail artisan migrate        // optional, not required for demo

Sail should handle all of the Composer and NPM dependencies by means of Docker Compose. Should you wish to force dependency updates, you may use the following while the Docker containers are running:

    ./vendor/bin/sail composer install
    ./vendor/bin/sail npm  install

## Caveats

For debugging purposes, the .env file has been committed to this repository. The is not a secure practice. As such, this project should **not** be forked or used as the basis of a production project.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

This proof of concept is released into the Public Domain without license.
