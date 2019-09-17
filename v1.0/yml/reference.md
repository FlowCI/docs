# YAML Reference

- `env`: (optional)
	
	```yaml
	envs:
		FIRST_ENV: "first var"
		SECOND_ENV: "hello world"
	```

- `filter`: (optional) 

  - `branches`: (optional) 
  - `tags`: (optional) 
	
	```yaml
	envs:
		FIRST_ENV: "first var"
		SECOND_ENV: "hello world"

	filter:
		branches:
			- "develop"
			- "master"
			- "feature/*"
		tags:
			- "*"
	```	

- `selector`: (optional)
	- `tags`

	```yaml
	selector:
  	  tags:
    	- ios
    	- local
	```

- `cron`: (optional)

- `steps`

  - `name`: (optional)

  - `allow_failure`: (optional)
  
  - `envs`: (optional)

  - `before`: (optional)
	
  - `script`

  - `tail`: (optional)

  - `exports`: (optional)