---
title: Simple Spatie Laravel Permission Integration in Laravel 9.*
date: '2023-02-07'
tags: ['code', 'laravel', 'web-development', 'libraries']
draft: false
summary: 'Laravel Permission allows managing user roles & permissions in Laravel by defining roles and permissions, assigning them to users, and checking them before performing actions.'
---

Here is a steps on how to use spatie/laravel-permission with Laravel 9.\*:

1. **Installation**:
   Open the terminal and navigate to the Laravel project's root directory.

   - Run the following command to install spatie/laravel-permission:

   ```php
   composer require spatie/laravel-permission
   ```

2. **Configuration**

   - Run the following command to publish the migration and config files:

   ```php
   php artisan vendor:publish --provider="Spatie\Permission\PermissionServiceProvider"
   ```

   - Run the following command to migrate the database: `php artisan migrate`

3. **Model setup**:

   - In the User model, add the following line to use the HasRoles trait provided by the package:

   ```php
   use Spatie\Permission\Traits\HasRoles;
   class User extends Authenticatable{
       use HasRoles;
   ...
   }
   ```

4. **Creating Roles and Permissions**:
   In the application code, roles and permissions can be created using the following code:

   ```php
   use Spatie\Permission\Models\Role;
   use Spatie\Permission\Models\Permission;
   $role = Role::create(['name' => 'writer']);
   $permission = Permission::create(['name' => 'edit articles']);

   $role->givePermissionTo($permission);
   ```

5. **Assigning Roles and Permissions to Users**:

   - Roles and permissions can be assigned to users using the following code:

   ```php
   $user->assignRole('writer');
   $user->givePermissionTo('edit articles');
   ```

6. **Checking Permissions**:

   - it can be checked if a user has a specific permission using the following code:

   ```php
   if ($user->can('edit articles')) {
       // User has permission
   }
   ```

7. **Middleware**:
   - The `authorize` middleware can be used to check if a user has the required permission to access a specific resource.
   - To add the middleware, add the following code to the `app/Http/Kernel.php` file:
   ```php
   protected $routeMiddleware = [
       ...
       'permission' => \Spatie\Permission\Middlewares\PermissionMiddleware::class,
   ];
   ```
   - Then can be added the middleware to the routes as follows:
   ```php
   Route::get('/edit', function () {
       //
   })->middleware('permission:edit articles');
   ```

That's it! Now we have a basic understanding of how to use spatie/laravel-permission with Laravel 9.\*. More information and advanced usage examples in the package documentation can be found on their website.
