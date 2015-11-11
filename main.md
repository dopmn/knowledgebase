### Index
* [Laravel](#laravel)
* [some other file](./web/index.md)


### Laravel

*this page starts with laravel 5.1, but I have started laravel from version 3, and used it through 4, 4.1 , 4.2*

Laravel is an amazing framework, inspired by ruby on rails, it shows how the web evolved to me the most powerful platform for applications.`

**Installation**

1. Install [composer](https://getcomposer.org/doc/00-intro.md#globally)

    `curl -sS https://getcomposer.org/installer | php
    mv composer.phar /usr/local/bin/composer`
2. Install laravel

    `composer global require "laravel/installer=~1.1"`

    (Optional) Install [xampp](https://www.apachefriends.org/download.html) (*if you haven't*)

3. Include composer in the $PATH
in the .bash_profile add the following lines

    `export PATH="$PATH:~/.composer/vendor/bin"`

4. now cd in the *htdocs* folder of xampp, and do,

    `laravel new myapp`

   _And you're done!!!_

---
**Configuration**

**Getting Along with CRUD in MVC...**

Following are the boilerplate that I use for MVC in laravel. I also intend to make a shell script to generate these files.

in brief `routes > schema > model > controller > view`

1. in routes.php, add the following line :

   `Routes::resource("EntityName");`
2. Schema (migration)

   `php artisan make:migration create_entities_table --create=entities`
3. Model

   `php artisan make:model User`
4. Controller

   `php artisan make:controller EntityController`
5. View

   // need to create the specific views
---
** Crud Automation **

*this is an implementaion of a [sitepoint artice](http://www.sitepoint.com/crud-create-read-update-delete-laravel-app/)*

Lets assume that our entity name is BaseEntity
1. in routes.php add the following line in the end of the file

    `Routes::resource("BaseEntity");`
2. To add the schema in our database
    
    * using terminal we need to run the following command, in the project directory
    
        `php artisan make:migration create_base_entities_table --table=base_entities`
    
        or (as --table is optional, only needed when the BaseEntity needs a specific name)
        
        `php artisan make:migration create_base_entities_table`
    * then we need to add our attributes; to do this
    
        ~~`php artisan make:migration add_initial_attributes_to_entities_table --attributes`~~
        
        in the migrations folder, in the file starting with create_base_entities_table, write the
        following
            
        ```
            <?php

            use Illuminate\Database\Schema\Blueprint;
            use Illuminate\Database\Migrations\Migration;
            
            class CreateFlightsTable extends Migration
            {
                /**
                 * Run the migrations.
                 *
                 * @return void
                 */
                public function up()
                {
                    Schema::create('flights', function (Blueprint $table) {
                        $table->increments('id');
                        $table->string('attribute1');
                        $table->string('attribute2');
                        $table->timestamps();
                    });
                }
            
                /**
                 * Reverse the migrations.
                 *
                 * @return void
                 */
                public function down()
                {
                    Schema::drop('flights');
                }
            }
        ```
3. in the model folder we need to 
    
    * add a new file BaseEntity.php
        alternatively we can run `php artisan make:model BaseEntity`
    * in the file BaseEntity.php, add the following lines 
    
        ```
        class Task extends Model {
             /**
            * Fillable fields
            * 
             * @var array
            */
            protected $fillable = [
                'attribute1',
                'attribute2'
            ];
        }
        ```
4. to add the controller do this
    * 
