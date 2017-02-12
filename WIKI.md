1. Before using composer to fetch yii use:
```
composer global require "fxp/composer-asset-plugin: *"
```
2. Add this to composer.json
```json
"extra": {
	"asset-installer-paths": {
		"npm-asset-library": "vendor/npm",
		"bower-asset-library": "vendor/bower"
	}
},
"config": {
	"preferred-install": "dist",
	"github-protocols": ["https","http"],
	"github-oauth": {
		"github.com": "aa9a906cf406370b509bbce3a78829202b41b8e6"
	}
}
```
3. In case you have older version of php you can upgrade it. On C9.io I found this way works fine:
```bash
$ sudo apt-get update
$ sudo apt-get install libmcrypt-dev
```
Next, we download phpbrew and move it to /usr/local/bin:
```bash
$ curl -L -O https://github.com/phpbrew/phpbrew/raw/master/phpbrew
$ chmod +x phpbrew
$ sudo mv phpbrew /usr/local/bin/
$ phpbrew init

# add this to your ~/.bashrc
$ [[ -e ~/.phpbrew/bashrc ]] && source ~/.phpbrew/bashrc

$ phpbrew lookup-prefix ubuntu
```
Once set up, we install and load PHP 5.6:
```
$ phpbrew install 5.6 +default
$ phpbrew switch php-5.6.30
$ phpbrew use php-5.6.30
$ php -v
PHP 5.6.30 (cli) (built: Feb 11 2017 15:34:39) 
Copyright (c) 1997-2016 The PHP Group
Zend Engine v2.6.0, Copyright (c) 1998-2016 Zend Technologies
```