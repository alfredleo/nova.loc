TOOLS:
- Windows 7 on local development environment. WAMP, Apache 2.4.23, PHP 5.6.25, Mysql 5.7.14, PhpStorm 2016.3.2
- As production: c9.io Ubuntu 14.04.3 LTS. Apache/2.4.7, PHP 5.6.30, Mysql 5.5.53, Sublime like IDE

1. Before using composer to fetch yii use: 
	
	```bash
	composer global require "fxp/composer-asset-plugin: *"
	```
2. Add this to _composer.json_. On Windows default location is C:\Users\userName\AppData\Roaming\Composer\composer.json: 
Linux - ~/.composer/composer.json
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
			"github.com": "<generate a personal access token in https://github.com/settings/tokens>"
		}
	}
	```
3. Use ```composer install``` to get all dependencies or ```composer install --ignore-platform-reqs``` to skip errors on php version.