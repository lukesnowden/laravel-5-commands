
#Create Model Resources

Create a model along with migration, controller, interface, repository and views.

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
-resources
	-views
		-Post
			add.blade.php
			edit.blade.php
			list.blade.php
```

foreach model created to will have to register the interface binding in the applications/packages service provider

```php
	public function register()
	{
		$this->app->bind(
			'App\Http\Interfaces\PostInterface.php','App\Http\Repositories\PostRepository.php'
		);
	}
```

you can also pass a fields option to populate the migration and rules

```cli
artisan lukesnowden:model post --fields="name,category_id,slug,order"
```