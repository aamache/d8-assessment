# Assessment Getting Started

1. First, ensure you have pygmy installed.
2. Clone this repository.
3. Run `composer install` and `yarn` to install dependencies.
4. Run `docker-compose up -d` to start the Docker instance.
5. Run `docker-compose exec --user drupal drupal bash` to connect into the Docker instance.
6. Run `drush si --config-dir=../config/sync -y` from the `~/public_html/web` directory inside the Docker instance to install and setup the database.
7. Run `drush uli` to get a one-time login link.
8. Begin your assessment task in a new branch, make sure to commit regularly your changes.
9. Create a pull-request for review.
10. Export the database by running this command inside the Docker container: `drush sql-dump --result-file --gzip`, then move the generated dump from the `/var/www/drupal/drush-backups/drupal` folder to `~/public_html/web` so that you can easily access the file outside of your Docker instance, in order to commit it or attach and send it via mail if required.

