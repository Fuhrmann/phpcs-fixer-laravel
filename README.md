### Instructions

Add this repository to `composer.json` file:

```json
{
    "repositories": [
        {
            "url": "https://github.com/Fuhrmann/phpcs-fixer-laravel",
            "type": "git"
        }
    ]
}
```

```json
{
    "require-dev": {
        "fuhrmann/phpcs-fixer-laravel": "master"
    }
}
```

Add the command to the `scripts` section:

```json
{
    "scripts": {
        "fix-style": "vendor/bin/php-cs-fixer fix --config=vendor/fuhrmann/php-cs-fixer-laravel/.php_cs.dist --ansi"
    }
}
```
