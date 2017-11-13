## Simple Cache Client Adapter ##
PHP Cache library built by PSR-16 simple cache interface

You can find implementations of the specification by looking for packages providing the psr/simple-cache-implementation virtual package.

#### Installation
- Run this command: `composer require previewtechs/simple-cache:dev-master`

#### Usages
- Create a file named `test.php` in your root directory and add these following codes: 
```php
<?php

require "vendor/autoload.php";

$cache = new Memcached();
$cache->addServers([
    ['localhost', 11211, 1]
]);

$cache = new Previewtechs\SimpleCache\Memcached($cache);

// Set Cache key.
$data = [
    'sample' => 'data',
    'another' => 'data'
];

$cache->set('your_custom_key', $data);

// Check cached key exists or not.
$cache->has('your_custom_key');

// Get Cached key data.
$cache->get('your_custom_key');

```
- then run `php test.php`

#### For Documentations
[psr/simple-cache-implementation](https://packagist.org/providers/psr/simple-cache-implementation)