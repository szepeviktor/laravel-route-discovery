---
title: Installation & setup
weight: 4
---

You can install the package via composer:

```bash
composer require spatie/laravel-route-discovery
```

## Publishing the config file

Optionally, you can publish the `route-discovery` config file with this command.

```bash
php artisan vendor:publish --tag="route-discover-config"
```

This is the content of the published config file:

```php
return [
    /*
     * Routes will be registered for all controllers found in
     * these directories.
     */
    'discover_controllers_in_directory' => [
        app_path('Http/Controllers'),
    ],

    /*
     * Routes will be registered for all views found in these directories.
     * The key of an item will be used as the prefix of the uri. 
     */
    'discover_views_in_directory' => [
        // 'docs' => [resource_path('views/docs']
    ],
];
```

## A word on performance

Discovering routes during each application request may have a small impact on performance. For increased performance, we highly recommend [caching your routes](https://laravel.com/docs/8.x/routing#route-caching) as part of your deployment process.
