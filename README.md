# laravel-permission
Laravel Multi Authentication

#Install the Package

```
composer require codexshaper/laravel-permission
```
#Publish Resource, Configs, Migration and Seeding Database in a single command

```
php artisan permission:install
```
#Or Publish Resource, Configs, Migration and Seeding Database Manually
1. Publish Configs
```
php artisan vendor:publish --tag=permission.config
```
2. Publish Seeds
```
php artisan vendor:publish --tag=permission.seeds
```
3. Migrate Database
```
php artisan migrate
```
4. Run composer dump autoload
```
composer dump-autoload
```
5. Seeding Database
```
php artisan db:seed --class=PermissionDatabaseSeeder
```
6. Add Routes
```
Route::group(['prefix' => config('permission.prefix')], function () {
    Permission::routes();
});
```
#Import `use CodexShaper\Permission\Traits\HasRoles` or simply `use HasRoles` Trait into your `App\User` Model

#Example
```
namespace App;

use CodexShaper\Permission\Traits\HasRoles;

class User extends Authenticatable
{
    use HasRoles;
}
```
#To see demo got to ```/admin/permissions```

# Note : Before Install and use this package run below command
Before Laravel version 6.0
```
php artisan make:auth
```
From Laravel Version 6.0

```
1. composer require laravel/ui
2. php artisan ui vue --auth
3. npm install
4. npm run watch
```
