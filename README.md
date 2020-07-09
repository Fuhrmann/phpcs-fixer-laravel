## Instructions

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
        "fix-style": "vendor/bin/php-cs-fixer fix --config=vendor/fuhrmann/phpcs-fixer-laravel/.php_cs.dist --ansi"
    }
}
```

Then execute the fixer with: `composer fix-style`.

### Composer hook

If you want to fix the styles on every commit, you can:

```json
{
       "extra": {
           "hooks": {
               "pre-commit": [
                   "fix-style"
               ],
               "pre-push": [
                   "fix-style --dry-run"
               ],
               "post-merge": "composer install",
               "...": "..."
           }
       }
   }
```

### Reference

Check [php-cs-fixer](https://cs.symfony.com/) official website for rules reference.


### Credits

Based on this [gist](https://gist.github.com/laravel-shift/cab527923ed2a109dda047b97d53c200) with a few changes. 
