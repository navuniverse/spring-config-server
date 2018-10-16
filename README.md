# spring-config-server

Spring Cloud Config Server integrated to load properties from file system and git.

Steps to use -

1. Start the application as spring boot and open the URL - http://localhost:8888/myapp/default. Here `myapp` stands for application name and `default` stands for active profile in your spring application.

   If you have a different file name on git and file system to load properties then you may have to use the URL as - http://localhost:8888/{fileName}/{profile}


2. You should see the property files loading from git and file system both

```
{
	"name": "myapp",
	"profiles": ["default"],
	"label": null,
	"version": null,
	"state": null,
	"propertySources": [{
		"name": "classpath:/myapp.yml",
		"source": {
			"property.file.second": "Property Loaded From Config File"
		}
	}, {
		"name": "https://github.com/navuniverse/spring-vault-properties/myapp.yml",
		"source": {
			"myapp.git.property": "Application Property from git"
		}
	}]
}
```

