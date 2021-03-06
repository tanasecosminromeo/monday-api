# Monday API
Monday.com API

## Installation & loading
Monday API is available on [Packagist](https://packagist.org/packages/tblack-it/monday-api) (using semantic versioning), and installation via [Composer](https://getcomposer.org) is the recommended way to install Monday API. Just add this line to your `composer.json` file:

```json
"tblack-it/monday-api": "~0.1"
```

or run

```sh
composer require tblack-it/monday-api
```

Note that the `vendor` folder and the `vendor/autoload.php` script are generated by Composer; they are not part of Monday API

Examples
--------

```php
<?php

require 'vendor/autoload.php';

$token = 'API_TOKEN';
$MondayBoard = new TBlack\MondayAPI\MondayBoard();
$MondayBoard->setToken(new TBlack\MondayAPI\Token($token));

// gel All Boards
$all_boards = $MondayBoard->getBoards();

// gel Board with id:12121212
$board = $MondayBoard->on(12121212)->getBoards();

// gel Board id:12121212 Columns
$boardColumns = $MondayBoard->on(12121212)->getColumns();

// Insert new Item on Board
$column_values = [ 'text1' => 'Value...','text2' => 'Other value...' ];
$boardColumns = $MondayBoard->on(12121212)->group('group_id')->addItem( 'My Item Title', $column_values );


```
