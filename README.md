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

### Composer (docker) hooks

*Assuming you have a container just for composer.* 

If you want to fix the styles on every commit, you can:

```json
{
       "extra": {
           "hooks": {
               "pre-commit": [
                   "docker-compose run --rm composer fix-style"
               ],
               "...": "..."
           }
       }
   }
```

Declare in the scripts section so the hooks keep updated:

```json
{
    "scripts": {
        "cghooks": "vendor/bin/cghooks",
        "post-install-cmd": "docker-compose run --rm composer cghooks add --ignore-lock",
        "post-update-cmd": "docker-compose run --rm composer cghooks update"
    }
}
```

### Reference

- Check [php-cs-fixer](https://cs.symfony.com/) official website for rules reference.
- Check [composer-git-hooks](https://github.com/BrainMaestro/composer-git-hooks) for the documentation.


### Credits

Based on this [gist](https://gist.github.com/laravel-shift/cab527923ed2a109dda047b97d53c200) with a few changes. 
