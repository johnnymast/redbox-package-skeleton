![redbox-logo-klein](https://cloud.githubusercontent.com/assets/121194/18277406/ac4d9868-744e-11e6-8994-86943704d0d4.png)



[![Build Status](https://travis-ci.org/johnnymast/redbox-hydrator.svg?branch=master)](https://travis-ci.org/johnnymast/redbox-hydrator)
[![Scrutinizer Code Quality](https://scrutinizer-ci.com/g/johnnymast/redbox-hydrator/badges/quality-score.png?b=master)](https://scrutinizer-ci.com/g/johnnymast/redbox-hydrator/?branch=master)
[![Code Coverage](https://scrutinizer-ci.com/g/johnnymast/redbox-hydrator/badges/coverage.png?b=master)](https://scrutinizer-ci.com/g/johnnymast/redbox-hydrator/?branch=master)
[![PHP 7.1 Ready](https://img.shields.io/badge/HHVM-Ready-green.svg)](http://hhvm.com/)
[![HHVM Ready](https://img.shields.io/badge/PHP 7.1-Ready-green.svg)](http://hhvm.com/)
[![Twitter URL](https://img.shields.io/twitter/url/http/shields.io.svg?style=social&label=Contact author)](https://twitter.com/intent/tweet?text=@mastjohnny)

# Redbox-hydrate
 
Hydrating an object is fancy talk for populating properties on PHP objects. This Hydrator helps you to quickly **hydrate** new class instances and returns the populated result. Please note it does not mether if you have private or protected properties in your class it will take care of that for you. Look in the examples folder for basic [examples](examples).

## Examples 

I have gone to great length to provide a special (read sexy) and tiny API for you. You can use any kind of API style you see fit in your operation for example.
 
### Static class method 

In this example we will hydrate a new instance of class User and return it as $result1 using with with() function.
 
```php
use Redbox\Hydrate\Hydrator;

/**
 * Method 1
 */
$result1 = Hydrator::hydrate(new User())->with(
    [
        'username' => 'abc',
        'password' => 'pass'
    ]
);

```
## Hydrate function

***Please note:*** the package provides a function called Hydrate. This function is not conceiled in any namespace so its globaly available when you have the package loaded into your application. If any function in your code already exists the function will not be declared so it will not colide with your code. See [src/helpers/Hydrator.php](https://github.com/johnnymast/redbox-hydrator/blob/master/src/helpers/Hydrator.php) for more information. In this example $result2 will be an instance of class User.
 
```php
use Redbox\Hydrate\Hydrator;

/**
 * Method 2
 */
$result2 = Hydrate(new User())->with(
    [
        'username' => 'abc',
        'password' => 'pass'
    ]
);


```

## Instantiate a new Hydrator

Plain old PHP, create an instance of the hydrator and call the with( ) function with the property values to fill an instance of the User class with. ***Please note*** There is something off with this method as if your doing this inside a loop it might consome some memory because of all the instances you create.

```php
use Redbox\Hydrate\Hydrator;

/**
 * Method 3
 */
$hydrator = new Hydrator(new User());
$result3 = $hydrator->with([
    [
        'username' => 'abc',
        'password' => 'pass'
    ]
]);
```

## System Requirements

This package only requires the following:

* PHP >= 5.40 (But higher is always better)
* [Composer](https://getcomposer.org/) for autoloading

## Installation

Using [composer](https://packagist.org/packages/redbox/scan):

```bash
$ composer require redbox/hydrate
```

## Installation trough archive download

If you download the package from a website (for example [github.io](https://github.com/johnnymast/redbox-hydrator/) or [phpclasses.org](http://www.phpclasses.org/package/9929-PHP-Quickly-Hydrate-classes-from-arrays.html) or any other) you will need composer installed on your machine.
The reason for this is that Redbox-hydrate comes without the vendor directory which is required to run the package.

First of all if you don't have composer installed you can find it [here](https://getcomposer.org/). Follow the instructions and please don't get intimidated in fact its really really easy to install.

In the this sample i will assume you have composer installed (on any machine). Go to the package root (where composer.json is located) and execute the following command.

```bash
$ composer install  --no-dev
```

Now your almost ready to go. In your project require the redbox-hydrate.php (located in the package root). Assuming that Redbox-hydrate was installed in ./lib/redbox-hydrate/ your php file would look like this.

```php
<?php
require 'lib/redbox-hydrate/redbox-hydrate.php';
// more of your nice code below
```

And you are ready use Redbox-hydrate in your application.

## Author

Redbox-hydrate is created and maintained by [Johnny Mast](mailto:mastjohnny@gmail.com). For feature requests and suggestions
you could consider sending me an e-mail.

## License

Redbox-hydrate is released under the MIT public license.

<https://github.com/johnnymast/redbox-hydrator/blob/master/LICENSE.md>

## Enjoy

 Oh and if you've come down this far, you might as well [follow me](https://twitter.com/mastjohnny) on twitter.
