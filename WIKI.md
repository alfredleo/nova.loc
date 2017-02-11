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