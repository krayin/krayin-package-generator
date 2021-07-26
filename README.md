# Krayin Package Generator

## 1. Introduction

Krayin Package Generator will create a sample package for you with a single command

It packs in lots of demanding features that allows your business to scale in no time:

* Create package with a single command.

## 2. Requirements

* **Krayin**: v1.0.0 or higher.

## 3. Installation

### Install with composer

Go to the root folder of **Krayin** and run the following command

~~~php
composer require krayin/krayin-package-generator
~~~

> That's it, now just execute the project on your specified domain.

## 4. Summary

After setting up, you will see that there are list of package commands which help you to make your package creation smooth.

Below are the list of commands,

| S. No. | Commands                               | Info                                                                                                            | Required Arguments                     | Optional Arguments  |
| :----- | :------------------------------------- | :-------------------------------------------------------------------------------------------------------------- | :------------------------------------- | :------------------ |
| 01.    | package:make                           | [Create a new package.](#1-create-a-new-package)                                                                |  package-name                          | --force, --plain    |
| 02.    | package:make-controller          | [Create a new controller.](#2-create-a-new-controller)                                              |  controller-name, package-name         | --force             |
| 03.    | package:make-route               | [Create a new routes file.](#3-create-a-new-routes-file)                                            |  package-name                          | --force             |
| 04.    | package:make-model                     | [Create a new model class.](#4-create-a-new-model-class)                                                        |  model-name, package-name              | --force             |
| 05.    | package:make-model-proxy               | [Create a new model proxy class.](#5-create-a-new-model-proxy-class)                                            |  model-proxy-name, package-name        | --force             |
| 06.    | package:make-model-contract            | [Create a new model contract.](#6-create-a-new-model-contract)                                                  |  model-contract-name, package-name     | --force             |
| 07.    | package:make-migration                 | [Create a new migration class.](#7-create-a-new-migration-class)                                                |  migration-name, package-name          |                     |
| 08.    | package:make-seeder                    | [Create a new seeder class.](#08-create-a-new-seeder-class)                                                     |  seeder-name, package-name             | --force             |
| 09.    | package:make-request                   | [Create a new request class.](#09-create-a-new-request-class)                                                   |  request-name, package-name            | --force             |
| 10.    | package:make-middleware                | [Create a new middleware class.](#10-create-a-new-middleware-class)                                             |  middleware-name, package-name         | --force             |
| 11.    | package:make-datagrid                  | [Create a new datagrid class.](#11-create-a-new-datagrid-class)                                                 |  datagrid-name, package-name           | --force             |
| 12.    | package:make-repository                | [Create a new repository class.](#12-create-a-new-repository-class)                                             |  repository-name, package-name         | --force             |
| 13.    | package:make-provider                  | [Create a new service provider class.](#13-create-a-new-service-provider-class)                                 |  provider-name, package-name           | --force             |
| 14.    | package:make-event                     | [Create a new event class.](#14-create-a-new-event-class)                                                       |  event-name, package-name              | --force             |
| 15.    | package:make-listener                  | [Create a new listener class.](#15-create-a-new-listener-class)                                                 |  listener-name, package-name           | --force             |
| 16.    | package:make-notification              | [Create a new notification class.](#16-create-a-new-notification-class)                                         |  notification-name, package-name       | --force             |
| 17.    | package:make-mail                      | [Create a new mail class.](#17-create-a-new-mail-class)                                                         |  mail-name, package-name               | --force             |
| 18.    | package:make-command                   | [Create a new command class.](#18-create-a-new-command-class)                                                   |  command-name, package-name            | --force             |
| 19.    | package:make-module-provider           | [Create a new module service provider class.](#19-create-a-new-module-service-provider-class)                   |  provider-name, package-name           | --force             |


**--force** : To overwrite the files

**--plain** : When you need only directory structure template, files are not included when this argument is passed

## 5. Usage

### Let's get started with our first command

#### 01. Create a new package

This command will generate all the necessary files which previously you create manually for your package.

~~~php
php artisan package:make ACME/TestPackage
~~~

For e.g., If you want to create a package which named as '**TestPackage**', then you need to use the command like this,

~~~php
php artisan package:make ACME/TestPackage
~~~

This will create whole directory structure for you automatically so that you don't want to do manually like registering routes, views, etc.

##### New package with just directory structure

If you want to do things manually only need folder structures, then there is a optional argument known as '**plain**'. Below is the sample,

~~~php
php artisan package:make ACME/TestPackage --plain
~~~

##### New package with force command

If somehow folder or package is already present, then simple command won't work. So to overcome this problem we need to use force command.

~~~php
php artisan package:make ACME/TestPackage --force
~~~

#### 02. Create a new controller

This command will generate a new controller for your portion.

~~~php
php artisan package:make-controller TestController ACME/TestPackage
~~~

##### Create a new controller with force command

If controller is already present, then you need to use the force command.

~~~php
php artisan package:make-controller TestController ACME/TestPackage --force
~~~

#### 03. Create a new routes file

If you want to create an route, then you need to use this command and then register your routes file in the service provider i.e. '**ACME\TestPackage\Providers\TestPackageServiceProvider**'.

~~~php
php artisan package:make-route ACME/TestPackage
~~~

##### Create a new routes file with force command

If routes file already present and you want to override this, then you need to use force command.

~~~php
php artisan package:make-route ACME/TestPackage --force
~~~

#### 04. Create a new model class

This command will create a following files,

* New model class in '**packages/ACME/TestPackage/src/Models**' directory.
* New model proxy class in '**packages/ACME/TestPackage/src/Models**' directory.
* New model contract in '**packages/ACME/TestPackage/src/Contracts**' directory.

~~~php
php artisan package:make-model TestModel ACME/TestPackage
~~~

##### Create a new model with force command

This command will overwrite all three files.

~~~php
php artisan package:make-model TestModel ACME/TestPackage --force
~~~

#### 05. Create a new model proxy class

This command will create a new model proxy class in '**packages/ACME/TestPackage/src/Models**' directory.

~~~php
php artisan package:make-model-proxy TestModelProxy ACME/TestPackage
~~~

##### Create a new model proxy with force command

If model proxy class already present then you can use force command for overwriting.

~~~php
php artisan package:make-model-proxy TestModelProxy ACME/TestPackage --force
~~~

#### 06. Create a new model contract

This command will create a new model contract in '**packages/ACME/TestPackage/src/Contracts**' directory.

~~~php
php artisan package:make-model-contract TestContract ACME/TestPackage
~~~

##### Create a new model contract with force command

If model contract already present then you can use force command for overwriting.

~~~php
php artisan package:make-model-contract TestDataGrid ACME/TestPackage --force
~~~

#### 07. Create a new migration class

This command will create a new migration class in '**packages/ACME/TestPackage/src/Database/Migrations**' directory.

~~~php
php artisan package:make-migration TestMigration ACME/TestPackage
~~~

#### 08. Create a new seeder class

This command will create a new seeder class in '**packages/ACME/TestPackage/src/Database/Seeders**' directory.

~~~php
php artisan package:make-seeder TestSeeder ACME/TestPackage
~~~

##### Create a new seeder class with force command

If seeder class already present then you can use force command for overwriting.

~~~php
php artisan package:make-seeder TestSeeder ACME/TestPackage --force
~~~

#### 09. Create a new request class

This command will create a new request class in '**packages/ACME/TestPackage/src/Http/Requests**' directory.

~~~php
php artisan package:make-request TestRequest ACME/TestPackage
~~~

##### Create a new request class with force command

If request class already present then you can use force command for overwriting.

~~~php
php artisan package:make-request TestRequest ACME/TestPackage --force
~~~

#### 10. Create a new middleware class

This command will create a new middleware class in '**packages/ACME/TestPackage/src/Http/Middleware**' directory.

~~~php
php artisan package:make-middleware TestMiddleware ACME/TestPackage
~~~

##### Create a new middleware class with force command

If middleware class already present then you can use force command for overwriting.

~~~php
php artisan package:make-middleware TestMiddleware ACME/TestPackage --force
~~~

#### 11. Create a new datagrid class

This command will create a new data grid class in '**packages/ACME/TestPackage/src/Datagrids**' directory.

~~~php
php artisan package:make-datagrid TestDataGrid ACME/TestPackage
~~~

##### Create a new datagrid class with force command

If data grid class already present then you can use force command for overwriting.

~~~php
php artisan package:make-datagrid TestDataGrid ACME/TestPackage --force
~~~

#### 12. Create a new repository class

This command will create a new repository class in '**packages/ACME/TestPackage/src/Repositories**' directory.

~~~php
php artisan package:make-repository TestRepository ACME/TestPackage
~~~

##### Create a new repository with force command

If repository class already present then you can use force command for overwriting.

~~~php
php artisan package:make-repository TestRepository ACME/TestPackage --force
~~~

#### 13. Create a new service provider class

This command will create a new service provider class in '**packages/ACME/TestPackage/src/Providers**' directory.

~~~php
php artisan package:make-provider TestServiceProvider ACME/TestPackage
~~~

##### Create a new service provider with force command

If service provider class already present then you can use force command for overwriting.

~~~php
php artisan package:make-provider TestServiceProvider ACME/TestPackage --force
~~~

#### 14. Create a new event class

This command will create a new event class in '**packages/ACME/TestPackage/src/Events**' directory.

~~~php
php artisan package:make-event TestEvent ACME/TestPackage
~~~

##### Create a new event with force command

If event class already present then you can use force command for overwriting.

~~~php
php artisan package:make-event TestEvent ACME/TestPackage --force
~~~

#### 15. Create a new listener class

This command will create a new listener class in '**packages/ACME/TestPackage/src/Listeners**' directory.

~~~php
php artisan package:make-listener TestListener ACME/TestPackage
~~~

##### Create a new listener class with force command

If listener class already present then you can use force command for overwriting.

~~~php
php artisan package:make-listener TestListener ACME/TestPackage --force
~~~

#### 16. Create a new notification class

This command will create a new notification class in '**packages/ACME/TestPackage/src/Notifications**' directory.

~~~php
php artisan package:make-notification TestNotification ACME/TestPackage
~~~

##### Create a new notification with force command

If notification class already present then you can use force command for overwriting.

~~~php
php artisan package:make-notification TestNotification ACME/TestPackage --force
~~~

#### 17. Create a new mail class

This command will create a new mail class in '**packages/ACME/TestPackage/src/Mail**' directory.

~~~php
php artisan package:make-mail TestMail ACME/TestPackage
~~~

##### Create a new mail class with force command

If mail class already present then you can use force command for overwriting.

~~~php
php artisan package:make-mail TestMail ACME/TestPackage --force
~~~

#### 18. Create a new command class

This command will create a new command class in the '**packages/ACME/TestPackage/src/Console/Commands**' directory.

~~~php
php artisan package:make-command TestCommand ACME/TestPackage
~~~

##### Create a new command class with force command

If command class already present then you can use force command for overwriting.

~~~php
php artisan package:make-command TestCommand ACME/TestPackage --force
~~~

#### 19. Create a new module service provider class

This command will create a new module service provider class in '**packages/ACME/TestPackage/src/Providers**' directory.

~~~php
php artisan package:make-module-provider TestServiceProvider ACME/TestPackage
~~~

##### Create a new module service provider with force command

If module service provider class already present then you can use force command for overwriting.

~~~php
php artisan package:make-module-provider TestServiceProvider ACME/TestPackage --force
~~~