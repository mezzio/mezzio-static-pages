# Installation

If you want the package to be automatically enabled when running composer require/install/update, your project needs to use the [laminas-component-installer][laminas-component-installer-url].
If it does, when the package is installed you'll be asked if you want to enable its ConfigProvider. Answer with Y and the package will be ready to use.

If you don't use laminas-component-installer, or for some reason or other can't, then ensure that `\StaticPages\ConfigProvider::class`, is in the `ConfigAggregator` list in _config/config.php_, as in the example below.

```php
$aggregator = new ConfigAggregator([
    \StaticPages\ConfigProvider::class,
]);
```

[laminas-component-installer-url]: https://docs.laminas.dev/laminas-component-installer/
