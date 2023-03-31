---
title: How to create CRUD with datatables in Laravel 9.*
date: '2023-02-23'
tags: ['code', 'laravel', 'web-development', 'datatables']
draft: true
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

<h1>To be contineued</h1>
4. **Creating** :Set up routes in the routes/web.php file:


```php
Route::get('/users', [UserController::class, 'index'])->name('users.index');
Route::get('/users/create', [UserController::class, 'create'])->name('users.create');
Route::post('/users', [UserController::class, 'store'])->name('users.store');
Route::get('/users/{user}', [UserController::class, 'show'])->name('users.show');
Route::get('/users/{user}/edit', [UserController::class, 'edit'])->name('users.edit');
Route::put('/users/{user}', [UserController::class, 'update'])->name('users.update');
Route::delete('/users/{user}', [UserController::class, 'destroy'])->name('users.destroy');

```

5. **Yadda**:
   Create views for each CRUD operation using Blade templates.

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

   In the index.blade.php file, add a table using YajraBox DataTables:

```html
<table class="table-bordered table" id="users-table">
  <thead>
    <tr>
      <th>Name</th>
      <th>Email</th>
      <th>Actions</th>
    </tr>
  </thead>
</table>
```

7. In the `index.blade.php` file, add JavaScript and jQuery libraries to handle CRUD operations and AJAX requests:

```html
<script src="{{ asset('js/jquery.min.js') }}"></script>
<script src="{{ asset('js/jquery.dataTables.min.js') }}"></script>
<script src="{{ asset('js/dataTables.bootstrap4.min.js') }}"></script>
<script>
  $(function() {
      $('#users-table').DataTable({
          processing: true,
          serverSide: true,
          ajax: '{!! route('users.index') !!}',
          columns: [
              { data: 'name', name: 'name' },
              { data: 'email', name: 'email' },
              { data: 'action', name: 'action', orderable: false, searchable: false }
          ]
      });
  });
</script>
```

8. In the `EmployeeController.php` file, add methods to handle CRUD operations:

```php
public function index(Request $request)
{
    if ($request->ajax()) {
        $data = User::latest()->get();
        return Datatables::of($data)
            ->addIndexColumn()
            ->addColumn('action', function($row){
                $editUrl = route('users.edit', ['user' => $row

```

That's it! Now we have a basic understanding of how to yadda yadda Laravel 9.\*.
