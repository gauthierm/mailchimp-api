MailChimp PHP API Wrapper 1.3
=============================
API Version: 1.3
Tested under: PHP 5

Requires:
 * PHP 5
 * PHP 4 may work, but it has not and won't be tested

About
-----
Our MCAPI (MailChimp API) wrapper class is provided to help jump-start your PHP
development efforts. Using it allows you to ignore the whole network
connectivity and data transfer pieces that are typically necessary when using an
API. When using this, you will simply create a PHP object and start calling
the methods that you need.

The examples contained in this package are simply the examples interspersed
throughout our API documentation. They are not meant to be full working
programs that do something useful. Rather they are provided to give you working
examples of most methods we expose to play around with, start getting
comfortable with, and work into your own programs as necessary.

These examples were also written from and intended to be run from a Shell/
Terminal/Command Line. If you are not familiar with executing PHP code from a
command line, see here:
    http://us3.php.net/features.commandline

Getting Started
---------------
 1. Open the inc/config.inc.php file and fill in at least these values:
    * API Key (from http://admin.mailchimp.com/account/api/)(
    *  other parameters are necessary for more in-depth examples)

 2. Try running `mcapi_lists.php` from the command line. Something like this:
    `php -f mcapi_lists.php`

NOTE: the one major difference between using this wrapper and the API
documentation is that your will *never* have to provide the `API_KEY` parameter
when using the wrapper class. It's done for you in the background.

Finally, please do not forget to do error checking. At least 60% of the problems
we see people having are due to them ignoring or not checking for error
messages. The examples provided show some very reasonable methods of performing
the requisite error checking.

Advanced Options
----------------

### SSL support

Our API does supporting connecting via SSL for those worried about Man-in-the-Middle
attacks/data collection. To use it in the MCAPI wrapper, simple do this:

```php
$api = new MCAPI($apikey);
$api->useSecure(true);
```

That can be turned on and off as necessary.

### Custom Timeouts

This wrapper defaults the Timeout value for a call to 300 seconds. To adjust
that for various calls, simply run:

```php
$api->setTimeout($your_value_in_seconds);
```

That can be changed between calls without reinstantiating the MCAPI object.
