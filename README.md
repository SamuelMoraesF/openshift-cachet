# Setup

## Create OpenShift app

`rhc create-app myapp --env OPENSHIFT_NGINX_VERSION=1.8.0 https://raw.githubusercontent.com/SamuelMoraesF/openshift-nginx/master/openshift-cartridge-nginx`

## Add php cartridge

`rhc cartridge add -a myapp --env OPENSHIFT_PHP_VERSION=5.6.6 https://raw.githubusercontent.com/SamuelMoraesF/openshift-php/master/openshift-cartridge-php`

## Add mysql cartridge

`rhc cartridge add mysql-5.5 -a myapp`

# Add cron cartridge

`rhc cartridge add cron-1.4 -a myapp`

## Add custom domain

`rhc alias add myapp mydomain.com`

## Before install

- Save [this file](https://raw.githubusercontent.com/CachetHQ/Cachet/2.3/.env.example) at `/sandbox/.env` and change only `APP_*` vars.
- Create a database with name `cachet`

## Install

**TBD**: push this repo and run `php artisan app:install` over SSH

## After install

Run `cp $OPENSHIFT_REPO_DIR/.env /sandbox/.env`

## After update: 
- Run `php artisan app:update` over SSH
