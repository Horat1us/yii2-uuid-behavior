# Yii2 UUID Behavior
[![Test & Lint](https://github.com/Horat1us/yii2-uuid-behavior/actions/workflows/php.yml/badge.svg?branch=master)](https://github.com/Horat1us/yii2-uuid-behavior/actions/workflows/php.yml)
[![codecov](https://codecov.io/gh/Horat1us/yii2-uuid-behavior/branch/master/graph/badge.svg)](https://codecov.io/gh/Horat1us/yii2-uuid-behavior)

Behavior to generate UUID values (mostly, for ActiveRecord primary key).

Compatibility: tested on PHP 8.4, PHP 8.5

## Installation
Using [packagist.org](https://packagist.org/packages/horat1us/yii2-uuid-behavior):
```bash
composer require horat1us/yii2-uuid-behavior:^1.0
```

## Usage
To generate UUID for primary key follow example:
```php
<?php

namespace App;

use Horat1us\Yii\UuidBehavior;
use yii\db;

/**
* Class Record
 * @package App
 * 
 * @property string $uuid // primary key in database, without default value and auto-increment
 */
class Record extends db\ActiveRecord
{
    public function behaviors(): array {
        return [
            'uuid' => [
                'class' => UuidBehavior::class,    
            ],    
        ];
    }
}
```
in followed example uuid in active record will be filled with random UUIDv4 before inserting.

## License
[MIT](./LICENSE)
