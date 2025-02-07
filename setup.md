install docker
complete docker post installation steps
install ddev
install composer

1. Create and goto new dir
2. ddev config --project-type=drupal --docroot=web
3. ddev start
4. ddev composer create drupal/recommended-project
5. ddev composer require drush/drush
6. ddev drush site:install --account-name=admin --account-pass=admin -y
7. ddev drush uli


```bash
ddev start
ddev composer create drupal/recommended-project
ddev composer require drush/drush
ddev drush site:install --account-name=admin --account-pass=admin -y
ddev drush uli
```
