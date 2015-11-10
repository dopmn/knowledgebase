### Index
* [Laravel](#laravel)
* [some other file](./something/index.md)


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

---
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

