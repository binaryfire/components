# Access Log

[![Latest Stable Version](https://img.shields.io/packagist/v/friendsofhyperf/access-log)](https://packagist.org/packages/friendsofhyperf/access-log)
[![Total Downloads](https://img.shields.io/packagist/dt/friendsofhyperf/access-log)](https://packagist.org/packages/friendsofhyperf/access-log)
[![License](https://img.shields.io/packagist/l/friendsofhyperf/access-log)](https://github.com/friendsofhyperf/access-log)

The access log component for Hyperf.

## Installation

- Request

```bash
composer require friendsofhyperf/access-log
```

- Publish

```bash
php bin/hyperf.php vendor:publish friendsofhyperf/access-log
```

- Add logger group

```php
// config/autoload/logger.php
return [
    // ...
    'access' => [
        'handler' => [
            'class' => \Monolog\Handler\StreamHandler::class,
            'constructor' => [
                'stream' => BASE_PATH . "/runtime/logs/access_log.log",
                'level' => Monolog\Logger::DEBUG,
            ],
        ],
        'formatter' => [
            'class' => \FriendsOfHyperf\AccessLog\Formatter\AccessLogFormatter::class,
        ],
    ],
];
```

- Switch logger group

```php
// config/autoload/access_log.php
return [
    'enable' => env('ACCESS_LOG_ENABLE', false),
    'logger' => [
        'group' => 'access',
        'time_format' => 'd/M/Y:H:i:s O',
    ],
    'ignore_user_agents' => [
        'Consul Health Check',
    ],
    'ignore_paths' => [
        '/favicon.ico',
    ],
];

```

## Donate

> If you like them, Buy me a cup of coffee.

| Alipay | WeChat |
|  ----  |  ----  |
| <img src="https://hdj.me/images/alipay-min.jpg" width="200" height="200" />  | <img src="https://hdj.me/images/wechat-pay-min.jpg" width="200" height="200" /> |

## Contact

- [Twitter](https://twitter.com/huangdijia)
- [Gmail](mailto:huangdijia@gmail.com)

## License

[MIT](LICENSE)
