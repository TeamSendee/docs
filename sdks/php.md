# PHP

The Sendee PHP SDK makes it easy to interact with the Sendee REST API from your PHP application. You can find the most recent version of the [Sendee PHP SDK on Packagist](https://packagist.org/packages/sendee/sendee-php).  The source code is also available on [Github](https://github.com/TeamSendee/sendee-php)

The recommended method for installing the SDK is via Composer.  You can add the SDK to your compose.json file with the require command.

```php
composer require sendee/sendee-php
```

{% hint style="info" %}
If you are using a framework like [Laravel](https://laravel.com), the Sendee SDK may be automatically loaded for you and ready to use.  If you're using composer in an environment that doesn't handle autoloading, you can [require the autoload file from the "vendor" directory create by composer](https://getcomposer.org/doc/01-basic-usage.md#autoloading).
{% endhint %}

#### Using This Library

**Send an SMS**

```php
// Send a single SMS using Sendee's REST API and PHP
<?php
$apiKey = "1|ZXXXXXX";

$client = new Sendee\SendeePhp\SendeeClient($apiKey);
$message =  $client->sendMessage(
  '+15555559410', // Text this Number
  [
    'from' => '+15555558108', // From a valid Twilio number
    'body' => 'Queue me up with Sendee'
  ]
);

print $message;
```

**Send a Bulk SMS**

```php
// Send a multiple SMS with the same body using Sendee's REST API and PHP
<?php
$apiKey = "1|ZXXXXXX";

$client = new Sendee\SendeePhp\SendeeClient($apiKey);
$message =  $client->sendBulkMessage(
  '+15555558108', // From a valid Twilio Number
  [
    'to' => [ // Text this array of numbers
        '+15555559410','+15555559411','+15555559412',
    ],
    'body' => 'this is an api test bulk'
   ]
);

print $message;
```
