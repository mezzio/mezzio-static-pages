# Configuration

Three steps are required to configure the package in your Mezzio project:

1. Configure the template path
1. Create the routes
1. Create the template files

## Configure the template path

To configure the template path, ensure that in your application's template paths list, there's one with the key `static-pages`, as in the example below.

```php
public function getTemplates() : array
{
    return [
        'paths' => [
            'static-pages' => [__DIR__ . '/../templates/static-pages'],
        ],
    ];
}
```

## Create the routes

To create a route for a static page, in your routing table add one or more named routes, where:

- The route's handler is `StaticPagesHandler::class`
- The route's name follows the convention: `static.<template_file_name_minus_file_extension>`

For example, let's assume that we are adding a route for a privacy page and that the template file is _privacy.phtml_.
In that case, we'd add the following to _config/routes.php_:

```php
$app->get('/privacy', StaticPagesHandler::class, 'static.privacy');
```

## Create the template files

Finally, you need to create the static template files in the nominated template directory.
The files can contain whatever you like, it doesn't matter.

All being well, this should be all that you need to rapidly serve static content files in your Mezzio applications.
