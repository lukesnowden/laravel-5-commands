
#Create Model Resources

Create a model along with migration, controller, interface and repository.

Add the reference to the commands kernel.
/app/Console/Kernel.php

```php
	'App\Console\Commands\CreateModelResources'
```

#CLI

```cli
artisan lukesnowden:model post
```

will generate the following

```cli
-app
	-Http
		-Controllers
			PostContoller.php
		-Interfaces
			PostInterface.php
		-Repositories
			PostRepository.php
			Repository.php
		-Models
			Post.php
-database
	-migrations
		0000_00_00_000000_create_posts_table.php
```