# YouTrack PHP SDK

![cog-youtrack-php-sdk](https://cloud.githubusercontent.com/assets/1849174/26231643/46fa08ba-3c59-11e7-81d6-8962c1fe90a5.png)

<p align="center">
<a href="https://travis-ci.org/cybercog/youtrack-php-sdk"><img src="https://img.shields.io/travis/cybercog/youtrack-php-sdk/master.svg?style=flat-square" alt="Build Status"></a>
<a href="https://styleci.io/repos/91754157"><img src="https://styleci.io/repos/91754157/shield" alt="StyleCI"></a>
<a href="https://codeclimate.com/github/cybercog/youtrack-php-sdk"><img src="https://img.shields.io/codeclimate/github/cybercog/youtrack-php-sdk.svg?style=flat-square" alt="Code Climate"></a>
<a href="https://github.com/cybercog/youtrack-php-sdk/releases"><img src="https://img.shields.io/github/release/cybercog/youtrack-php-sdk.svg?style=flat-square" alt="Releases"></a>
<a href="https://github.com/cybercog/youtrack-php-sdk/blob/master/LICENSE"><img src="https://img.shields.io/github/license/cybercog/youtrack-php-sdk.svg?style=flat-square" alt="License"></a>
</p>

## Introduction

YouTrack PHP Software Development Kit provides set of tools to interact with [JetBrains YouTrack Issue Tracking and Project Management software](https://www.jetbrains.com/youtrack/).

## Contents

- [Features](#features)
- [Requirements](#requirements)
- [Provides packages](#provides-packages)
- [Frameworks support](#frameworks-support)
- [Installation](#installation)
- [Usage](#usage)
    - [Initialize API client](#initialize-api-client)
    - [Repositories methods](#repositories-methods)
- [Change log](#change-log)
- [Contributing](#contributing)
- [Testing](#testing)
- [Security](#security)
- [Credits](#credits)
- [Alternatives](#alternatives)
- [License](#license)
- [About CyberCog](#about-cybercog)

## Features

- Framework agnostic.
- Using contracts to keep high customization capabilities.
- YouTrack Entities with relationships.
- Multiple authorization strategies: Token, Cookie.
- Following PHP Standard Recommendations:
  - [PSR-2 (Coding Style Guide)](http://www.php-fig.org/psr/psr-2/).
  - [PSR-4 (Autoloading Standard)](http://www.php-fig.org/psr/psr-4/).
  - [PSR-7 (HTTP Message Interface)](http://www.php-fig.org/psr/psr-7/).
- Covered with unit tests.

## Requirements

- YouTrack >= 3.0 with REST-API enabled (always enabled, by default)
- PHP >= 7.1
- Guzzle HTTP Client >= 6.2

## Provides packages

- [YouTrack REST API PHP Client](https://github.com/cybercog/youtrack-rest-php#readme) maintained by [Anton Komarev](https://github.com/a-komarev)

**Haven't found required functionality? [We are open](CONTRIBUTING.md) for Pull Requests!**

## Frameworks support

YouTrack PHP SDK is framework agnostic package and could be easily used in any PHP framework you want.

### Framework integrations list

- [Laravel YouTrack SDK](https://github.com/cybercog/laravel-youtrack-sdk#readme) maintained by [Anton Komarev](https://github.com/a-komarev)

**Haven't found your favorite framework in the list? [We are open](CONTRIBUTING.md) for Pull Requests!**

## Installation

The preferred method is via [composer](https://getcomposer.org). Follow the
[installation instructions](https://getcomposer.org/doc/00-intro.md) if you do not already have
composer installed.

Once composer is installed, execute the following command in your project root to install this library:

```sh
$ composer require cybercog/youtrack-php-sdk
```

### Without framework

Be sure to include the autoloader in your project:

```php
require_once '/path/to/your-project/vendor/autoload.php';
```

## Usage

### Initialize API client

#### Token Authorizer

Starting with YouTrack 2017.1 release [authorization based on permanent tokens](https://www.jetbrains.com/help/youtrack/standalone/2017.2/Manage-Permanent-Token.html) is recommended as the main approach for the authorization in your REST API calls. 

```php
// Instantiate HTTP Client
$http = new \GuzzleHttp\Client([
    'base_uri' => 'https://example.com',
]);

// Instantiate YouTrack API Token Authorizer
$authorizer = new \Cog\YouTrack\Rest\Authorizer\TokenAuthorizer([
    'token' => 'YOUTRACK_API_TOKEN',
]);

// Instantiate YouTrack API Client
$client = new \Cog\YouTrack\Rest\YouTrackClient($http, $authorizer);
```

#### Cookie Authorizer

```php
// Instantiate HTTP Client
$http = new \GuzzleHttp\Client([
    'base_uri' => 'https://example.com',
]);

// Instantiate YouTrack API Cookie Authorizer
$authorizer = new \Cog\YouTrack\Rest\Authorizer\CookieAuthorizer([
    'username' => 'YOUTRACK_USERNAME',
    'password' => 'YOUTRACK_PASSWORD',
]);

// Instantiate YouTrack API Client
$client = new \Cog\YouTrack\Rest\YouTrackClient($http, $authorizer);
```

## Change log

Please see [CHANGELOG](CHANGELOG.md) for more information on what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Testing

Run the tests with:

```sh
$ composer test
```

## Security

If you discover any security related issues, please email oss@cybercog.su instead of using the issue tracker.

## Credits

|  | @mention |
|---|---|
| ![@a-komarev](https://avatars2.githubusercontent.com/u/1849174?s=64) | [@a-komarev](https://github.com/a-komarev) |

[YouTrack PHP SDK contributors list](../../contributors)

## Alternatives

*Feel free to add more alternatives as Pull Request.*

## License

- `YouTrack PHP SDK` package is open-sourced software licensed under the [MIT License](LICENSE).

## About CyberCog

[CyberCog](http://www.cybercog.ru) is a Social Unity of enthusiasts. Research best solutions in product & software development is our passion.

<a href="http://cybercog.ru"><img src="https://cloud.githubusercontent.com/assets/1849174/18418932/e9edb390-7860-11e6-8a43-aa3fad524664.png" alt="CyberCog"></a>