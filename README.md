# ![Symfony RealWorld Example App](logo.png)

> ### Symfony codebase containing real world examples (CRUD, auth, advanced patterns, etc) that adheres to the [RealWorld](https://github.com/gothinkster/realworld) spec and API.


This codebase was created to demonstrate a fully fledged fullstack application built with Symfony including CRUD operations, authentication, routing, pagination, and more.

We've gone to great lengths to adhere to the Symfony community styleguides & best practices.

For more information on how to this works with other frontends/backends, head over to the [RealWorld](https://github.com/gothinkster/realworld) repo.



# How it works

This app is using [Symfony](https://symfony.com/) with:

- [API Platform](https://api-platform.com/)
- [Doctrine ORM](https://github.com/doctrine/orm/)
- [LexikJWTAuthenticationBundle](https://github.com/lexik/LexikJWTAuthenticationBundle)

Docker services:

- [Nginx](https://hub.docker.com/_/nginx)
- [PHP-FPM](https://hub.docker.com/_/php)
- [PostgreSQL](https://hub.docker.com/_/postgres)

Code analysis:

- [GrumPHP](https://phpro.github.io/grumphp/)
- [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer)
- [PHP Parallel Lint](https://github.com/php-parallel-lint/PHP-Parallel-Lint)
- [PHP Mess Detector](https://phpmd.org/)
- [PHPStan](https://phpstan.org/)

Testing:

- [PHPUnit](https://phpunit.de/)
- [AliceBundle](https://github.com/theofidry/AliceBundle)
- [DoctrineTestBundle](https://github.com/dmaicher/doctrine-test-bundle)



# Getting started

### Run the application

Make sure you have [Docker](https://docs.docker.com/get-docker/) installed.

Clone the repository.

Create Docker environment file from the sample:
```
cp env.txt .env
```

Launch Docker services:
```
docker-compose up -d
```

That's it, now you can open http://localhost/ in your browser.

### Run tests

Override Docker settings to enable development features:
```
cp docker-compose.dev.yml docker-compose.override.yml
```

Restart Docker services:
```
docker-compose up -d --build
```

Open http://localhost/ to verify the app is running fine.

**Note**: If you see 502 Bad Gateway reload the page a few moments later :)

Run PHPUnit:
```
docker-compose exec app php bin/phpunit
```



# Learn more

- [Symfony: The Fast Track](https://symfony.com/doc/current/the-fast-track/en/index.html)
- [Getting Started With API Platform](https://api-platform.com/docs/distribution/)
