---
title: Options Package
description: You can create options, reuse them and rely on them at a later time. Inspired by the WordPress system and built on the Laravel framework.
extends: _layouts.documentation
section: content
---

# laraveleg\options
You can create options, reuse them and rely on them at a later time. Inspired by the [WordPress](https://codex.wordpress.org/Options_API) system and built on the `Laravel` framework.

## Install

```bash
composer require laraveleg/options
```


## Usage

You can manage options in a simple way by helpers.

## Cache Mode

### add_option
You can add an option through the following line :-
```php
add_option($key, $value, $expiration);
```
`$key`: The option ID that you will use to fetch its value.

`$value`: Put the value of any type of data.

`$expiration`: Expiration date. This can be unused and saved all the time. Ex: `add_option($key, $value)`.

### get_option
Fetching value for a specific option :-
```php
get_option($key, $default)
```
`$key`: The option ID.
`$default`: You can specify a default value if the option is not found.

### has_option
Make sure the option is there :-
```php
has_option($key)
```
`$key`: The option ID.

### remove_option
You can delete any option :-
```php
remove_option($key)
```
`$key`: The option ID.

---

## Eloquent Mode
You can put the settings to a specific element in a specific model.

### Set config
Go to `laraveloptions.php` file in configs directory
```php
'eloquent_mode' => true, // Enable Eloquent Mode
```

### Use for model
Add the trait in your specific model.

```php
use LaravelEG\LaravelOptions\Traits\LaravelOptionEloquentMode;

class Unit extends Model
{
    use LaravelOptionEloquentMode;
```

### add_option
You can add an option through the following line :-
```php
$unit = Unit::find(1);
$unit->addOption($key, $value, $expiration);
```
`$key`: The option ID that you will use to fetch its value.

`$value`: Put the value of any type of data.

`$expiration`: Expiration date. This can be unused and saved all the time. Ex: `add_option($key, $value)`.

### get_option
Fetching value for a specific option :-
```php
$unit = Unit::find(1);
$unit->getOption($key, $default)
```
`$key`: The option ID.
`$default`: You can specify a default value if the option is not found.

### has_option
Make sure the option is there :-
```php
$unit = Unit::find(1);
$unit->hasOption($key)
```
`$key`: The option ID.

### remove_option
You can delete any option :-
```php
$unit = Unit::find(1);
$unit->removeOption($key)
```
`$key`: The option ID.

> You an use this `Trait` in any model on your app.

## Testing

Run the tests with:

```bash
vendor/bin/phpunit
```


## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.


## Security

If you discover any security-related issues, please email komicho1996@gmail.com instead of using the issue tracker.


## License

The MIT License (MIT). Please see [License File](/LICENSE.md) for more information.