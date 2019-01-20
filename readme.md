# PHP Spintax
[![Build Status](https://travis-ci.org/madeITBelgium/Spintax.svg?branch=master)](https://travis-ci.org/madeITBelgium/Spintax)
[![Coverage Status](https://coveralls.io/repos/github/madeITBelgium/Spintax/badge.svg?branch=master)](https://coveralls.io/github/madeITBelgium/Spintax?branch=master)
[![Latest Stable Version](https://poser.pugx.org/madeITBelgium/Spintax/v/stable.svg)](https://packagist.org/packages/madeITBelgium/Spintax)
[![Latest Unstable Version](https://poser.pugx.org/madeITBelgium/Spintax/v/unstable.svg)](https://packagist.org/packages/madeITBelgium/Spintax)
[![Total Downloads](https://poser.pugx.org/madeITBelgium/Spintax/d/total.svg)](https://packagist.org/packages/madeITBelgium/Spintax)
[![License](https://poser.pugx.org/madeITBelgium/Spintax/license.svg)](https://packagist.org/packages/madeITBelgium/Spintax)

With this (Laravel) package you can create multiple articles based on a single text.

# Installation

Require this package in your `composer.json` and update composer.

```php
"madeitbelgium/spintax": "~1.0"
```

# Documentation
## Usage
```php
use \MadeITBelgium\Spintax\Facade\Spintax();

Spintax::spin('Your {text|content} here.');
```

The complete documentation can be found at: [http://www.madeit.be/](http://www.madeit.be/)


# Support
Support github or mail: tjebbe.lievens@madeit.be

# Contributing
Please try to follow the psr-2 coding style guide. http://www.php-fig.org/psr/psr-2/

# License
This package is licensed under LGPL. You are free to use it in personal and commercial projects. The code can be forked and modified, but the original copyright author should always be included!
