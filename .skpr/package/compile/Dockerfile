FROM skpr/php-cli:8.4-v2-latest AS build

ADD composer.json composer.json
ADD composer.patches.json composer.patches.json
ADD PATCHES PATCHES
RUN composer install --prefer-dist --no-progress

ADD drush drush
ADD recipes recipes
ADD app/modules/custom/ app/modules/custom/
ADD app/sites/default/settings.php app/sites/default/settings.php
ADD app/sites/default/services.yml app/sites/default/services.yml

RUN mkdir config-export
