# Larave SSE

This library provides Server Sent Event for Laravel using [libSSE-php](https://github.com/tonyhhyip/libSSE-php)

## Supported Laravel Version
- 5.1 (**Higher Priority**) 
- 5.2
- 5.0

## Install - Composer
To install Laravel SSE as a Compsoer package to be used in Laravel 5, simply add this to your `composer.json`:

```json
"tonyhhyip/laravel-sse": "~1.0"
```

and run `composer update`.

Once it is installed, you can register the `SseServiceProvider` in `app/config/app.php` in `providers` array.
If you want, you can also add the alias SSE:

```php
'providers' => [
    ...
    \Sse\Laravel\SseServiceProvider::class
],
'alias' => [
    ...
    'SSE' => \Sse\Laravel\Facade:class
]
```

## Usage

You can inject the SSE in your controller
```php

class HomeController extends Controller
{
    public function sse(SSE $sse)
    {
        // Add your event listener
        return $sse->createResponse();
    }
}

```
