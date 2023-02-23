---
title: How to create CRUD with datatables in Laravel 9.*
date: '2023-02-23'
tags: ['code', 'laravel', 'web-development', 'datatables']
draft: false
summary: 'Create a CRUD application using Laravel 9 and YajraBox Datatables involves building a web application using the Laravel PHP framework version 9 and integrating YajraBox Datatables to display and manage data in a tabular format. The application will allow users to perform CRUD (Create, Read, Update, Delete) operations on a database, with the data displayed and manipulated through an interactive datatable. Check it out...'
---

Here is a steps on how to create a CRUD Application with datatables in Laravel 9.\*:

1. **Tools Installation**:

   - Create a Laravel 9 project by running the following command in the terminal:

     ```bash
       composer create-project laravel/laravel employees "9.*"
     ```

   - Run the following command to install `yajra/laravel-datatables-oracle`:

     ```bash
       composer require yajra/laravel-datatables-oracle
     ```

2. **Configuration**

   - Edit the `.env` file to set up the connection with the database, here is the sample
     ```bash
     DB_CONNECTION=mysql
     DB_HOST=127.0.0.1
     DB_PORT=3306
     DB_DATABASE=laravel_your_db_name
     DB_USERNAME=your_uname
     DB_PASSWORD=your_pwd
     ```

3. **Model setup**: - In the terminal, command line, use `php artisan` to create a model called Employee with **several options**
   `bash php artisan make:model Employee -mcfs `
   where the options: <br/>
   -c, --controller Create a new controller for the model<br/>
   -f, --factory Create a new factory for the model<br/>
   -s, --seed Create a new seeder file for the model<br/>
   -m, --migration Create a new migration file for the model<br/>

   - Inside the employee migration file, add the `name`, `address`, `phone_nr` and `email` of employee as code follows:

     ```php
       <?php
        use Illuminate\Database\Migrations\Migration;
        use Illuminate\Database\Schema\Blueprint;
        use Illuminate\Support\Facades\Schema;

       return new class extends Migration{
           /**
            * Run the migrations.
            *
            * @return void
            */
           public function up(){
             Schema::create('employees', function (Blueprint $table) {
               $table->id();
               $table->string('name');
               $table->string('address');
               $table->string('phone_nr');
               $table->string('email');
               $table->rememberToken();
               $table->timestamps();
             });
           }

         /**
          * Reverse the migrations.
          *
          * @return void
          */
           public function down(){
             Schema::dropIfExists('employees');
           }
       };
     }
     ```

   - In `Employee.php`, model add following codes

     ```php
     <?php
      namespace App\Models;
      use Illuminate\Database\Eloquent\Factories\HasFactory;
      use Illuminate\Database\Eloquent\Model;

      class Employee extends Model{
         use HasFactory;
      }

      protected $table = 'employees';

      protected $fillable = [
         'name',
         'address',
         'phone_nr',
         'email'
      ];
     ```

   - We are going to generate dummy data using Factory class
     ```php
     <?php
      namespace Database\Factories;
      use Illuminate\Database\Eloquent\Factories\Factory;
      /**
       * @extends \Illuminate\Database\Eloquent\Factories\Factory<\App\Models\Employee>
       */
      class EmployeeFactory extends Factory{
       /**
         * Define the model's default state.
         *
         * @return array<string, mixed>
         */
       public function definition(){
           return [
               'name' => $this->faker->name(),
               'address' => $this->faker->address(),
               'phone_nr' => $this->faker->phoneNumber(),
               'email' => fake()->unique()->safeEmail(),
               'remember_token' => Str::random(10),
           ];
       }
     }
     ```
   - A hundred of fake employees will be generate by add line of code
     `\App\Models\Employee::factory(100)->create();` inside the run function

   ```php
      <?php
      namespace Database\Seeders;

      use Illuminate\Database\Console\Seeds\WithoutModelEvents;
      use Illuminate\Database\Seeder;

      class EmployeeSeeder extends Seeder{
          /**
           * Run the database seeds.
           *
           * @return void
           */
          public function run()
          {
              \App\Models\Employee::factory(100)->create();
          }
      }
   ```

   and inside the `DatabaseSeeder.php` the `EmployeerSeeder` class can be called by including this line of code
   `$this->call(EmployeeSeeder::class);`
   Fakes data can be verified on the database side,<br/>

   ![Employees](/static/images/laravel/Employees.png)

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
