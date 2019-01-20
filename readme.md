# PHP Spintax
[![Build Status](https://travis-ci.org/madeITBelgium/Spintax.svg?branch=master)](https://travis-ci.org/madeITBelgium/Spintax)
[![Coverage Status](https://coveralls.io/repos/github/madeITBelgium/Spintax/badge.svg?branch=master)](https://coveralls.io/github/madeITBelgium/Spintax?branch=master)
[![Latest Stable Version](https://poser.pugx.org/madeITBelgium/Spintax/v/stable.svg)](https://packagist.org/packages/madeITBelgium/Spintax)
[![Latest Unstable Version](https://poser.pugx.org/madeITBelgium/Spintax/v/unstable.svg)](https://packagist.org/packages/madeITBelgium/Spintax)
[![Total Downloads](https://poser.pugx.org/madeITBelgium/Spintax/d/total.svg)](https://packagist.org/packages/madeITBelgium/Spintax)
[![License](https://poser.pugx.org/madeITBelgium/Spintax/license.svg)](https://packagist.org/packages/madeITBelgium/Spintax)

With this (Laravel) package you can create multiple articles based on a single text.
A forked and extended version of https://github.com/chilloutdevelopment/ChillDevSpintax

# Installation

Require this package in your `composer.json` and update composer.

```php
"madeitbelgium/spintax": "~1.0"
```

# Documentation
## Usage
### Get a random spin
```php
use MadeITBelgium\Spintax\Facade\Spintax;

Spintax::parse('Your {text|content} here.')->generate();
```

```php
use MadeITBelgium\Spintax\Spintax;

$spintax = Parser::parse('Schrödinger’s Cat is {dead|alive}.');
$string = $spintax->generate();
```

### Get all possible spins:
```php
use MadeITBelgium\Spintax\Facade\Spintax;

Spintax::parse('Your {text|content} here.')->getAll();
```

```php
use MadeITBelgium\Spintax\Spintax;

$spintax = Parser::parse('Schrödinger’s Cat is {dead|alive}.');
$strings = $spintax->getAll();
```
### Other examples
But there is much more that than that in our library. First of all nested structures are supported:

```php
use MadeITBelgium\Spintax\Spintax;

$spintax = Parser::parse('I {love {PHP|Java|C|C++|JavaScript|Python}|hate Ruby}.');
$string = $spintax->generate();
```

Still not finished! With our brilliant library you can detect the path used to generate given variant and re-use it later:

```php
use MadeITBelgium\Spintax\Spintax;

$path = [];

$spintax = Parser::parse('I {love {PHP|Java|C|C++|JavaScript|Python}|hate Ruby}.');
// since $path is empty, random values will be used for missing indices and $path will be filled with them
$string = $spintax->generate($path);

// from now you can use $path to re-create the same combination
// all these calls will keep returning same string value
$spintax->generate($path);
$spintax->generate($path);
$spintax->generate($path);
$spintax->generate($path);

// this will force generating "I love Java."
$path = [0, 1];
$spintax->generate($path);
```

Paths are counted from 0, each entry is next step.

You can also use partial paths to define just the starting path and all missing parts will be choosen randomly:

```php
use MadeITBelgium\Spintax\Spintax;

$path = [0];

$spintax = Parser::parse('I {love {PHP|Java|C|C++|JavaScript|Python}|hate Ruby}.');
// this will generate one of "I love {}." variants
$string = $spintax->generate($path);
```

For all this there is a shortcut method `Parser::replicate()` (you can use comma-separated number in a single string as second argument in this shortcut method):

```php
use MadeITBelgium\Spintax\Spintax;

echo Parser::replicate('I {love {PHP|Java|C|C++|JavaScript|Python}|hate Ruby}.', '0,0');
```

The complete documentation can be found at: [http://www.madeit.be/](http://www.madeit.be/)


# Support
Support github or mail: tjebbe.lievens@madeit.be

# Contributing
Please try to follow the psr-2 coding style guide. http://www.php-fig.org/psr/psr-2/

# License
This package is licensed under LGPL. You are free to use it in personal and commercial projects. The code can be forked and modified, but the original copyright author should always be included!
