# GitHub API Bundle

[![Build Status](https://img.shields.io/travis/scribenet/ScribeGitHubApiLibrary/master.svg?style=flat-square)](https://travis-ci.org/scribenet/ScribeGitHubApiLibrary)
[![Quality Score](http://img.shields.io/codeclimate/github/scribenet/ScribeGitHubApiLibrary.svg?style=flat-square)](https://codeclimate.com/github/scribenet/ScribeGitHubApiLibrary)
[![Coverage Status](http://img.shields.io/coveralls/scribenet/ScribeGitHubApiLibrary.svg?style=flat-square)](https://codeclimate.com/github/scribenet/ScribeGitHubApiLibrary)
[![Dependency Status](http://img.shields.io/gemnasium/scribenet/ScribeGitHubApiLibrary.svg?style=flat-square)](https://gemnasium.com/scribenet/ScribeGitHubApiLibrary)
[![Latest Version](http://img.shields.io/packagist/v/scribe/github-api-library.svg?style=flat-square)](https://packagist.org/packages/scribe/github-api-library)
[![Software License](http://img.shields.io/packagist/l/scribe/github-api-library.svg?style=flat-square)](LICENSE.md)

This is a simple, object oriented PHP5 client for [GitHub's API (v3)](http://developer.github.com/v3/), implemented with an intentionally similar API to GitHub's native RESTful API.

## Features

* **Code Standards**: Implements [PSR-0](http://www.php-fig.org/psr/psr-0/) code and structure standards to accommodate auto-loading using [Composer](https://getcomposer.org/) or another class auto-loading solution.
* **Speed and Familiarity**: Lightweight, fast, and friendly object model utilizing lazy loading with an intentional similarly to GitHub's own RESTful API.
* **Tests and Continuous Integration**: Extensive [PHPUnit](https://phpunit.de/) tests utilizing [Travis CI](https://travis-ci.org/scribenet/ScribeGitHubApiLibrary) as our continuous integration service.
* **Quality, Coverage and Dependencies**: Code quality reports with [Code Climate](https://codeclimate.com/github/scribenet/ScribeGitHubApiLibrary), coverage reports with [Coveralls](https://coveralls.io/r/scribenet/ScribeGitHubApiLibrary), and dependency version monitoring using [Gemnasium](https://gemnasium.com/scribenet/ScribeGitHubApiLibrary).
* **Documentation and Examples**: Comprehensive [examples](doc/) written in markdown and automatically generated [API documentationn](https://scribenet.github.io/ScribeGitHubApiLibrary/).

## Requirements

This library requires a short list of dependencies for both a production installation or a development build.

### Production

* PHP >= [5.5](http://php.net/manual/en/migration55.changes.php) or [HHVM](http://hhvm.com/)
* The [Curl](http://php.net/manual/en/book.curl.php) extension
* The [Guzzle](https://github.com/guzzle/guzzle) [HTTP request framework](http://docs.guzzlephp.org/en/latest/)

### Development

* [PHPUnit](https://phpunit.de/) >= 4.0
* [Coveralls Reporter](https://github.com/satooshi/php-coveralls) >= 0.6.1
* [Code Climate Reporter](https://github.com/codeclimate/php-test-reporter) >= 0.1.2
* [Sami](https://github.com/fabpot/sami) >= 2.0

## Installation

This library can be included into your project easily using [Composer](http://getcomposer.org) by adding the dependency to the `require` section of your `composer.json` project file.

```json
{
    "require": {
        "scribe/github-api-library": "dev-master"
    }
}
```

## Usage

### Basic Usage

```php
<?php

require_once 'vendor/autoload.php';

$client = new \Github\Client();
$repositories = $client->api('user')->repositories('ornicar');
```

### Cached Usage

```php
<?php

require_once 'vendor/autoload.php';

$client = new \Github\Client(
    new \Github\HttpClient\CachedHttpClient(array('cache_dir' => '/tmp/github-api-cache'))
);

$client = new \Github\HttpClient\CachedHttpClient();
$client->setCache(
    new \Github\HttpClient\Cache\FilesystemCache('/tmp/github-api-cache')
);

$client = new \Github\Client($client);
```

## Documentation

For general usage and examples, you can check the [doc](doc/) directory. For a comprehensive API reference, check this project's [github.io webpage](https://scribenet.github.io/ScribeGitHubApiLibrary/).

## Contributors

This project has code contributed from an [array of individuals](https://github.com/scribenet/ScribeGitHubApiLibrary/graphs/contributors).