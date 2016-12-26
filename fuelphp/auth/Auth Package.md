# Overview

* `Auth` is a package of FuelPHP

* Located in `fuel/packages/auth`

* Directory structure and important files
 * class `/auth/driver.php`: *to enable login, group, acl drivers*
 * config `/auth.php`: *to choose what auth package to use (simpleauth, ormauth...)*
 * lang
 * migrations: *contain files to create table for the auth package we use*
 * tasks
 * ...

# To enable to use auth

## Enable auth loading in `fuel/app/config/env/config.php`
```php
<?php
'always_load' => array(
    'packages' => array(
        'auth',
    )
),
```

## Config what auth package to use, e.g. `simple auth`

* File to make settings: `fuel/packages/auth/config/auth.php`     
`cp fuel/packages/auth/config/auth.php fuel/app/config/auth.php`

* Change the copied file     
```php
<?php
return array(
    'driver' => array('Simpleauth'),
    'verify_multiple_logins' => true,
    'salt' => 'some_salt',
    'iterations' => 1000,
);
```

* Settings for simple auth     
`cp fuel/packages/auth/config/simpleauth.php fuel/app/config/simpleauth.php`

* Change to copied file
 * If there is nothing to changes, we don't need to copy this file into the app's config

Simple auth stores users'data in db, group + role + right in `simpleauth.php`

## Create tables in database

* Config db information
* Run `php oil refine migrate --packages=auth`

**In case of `simpleauth`, the followings will be created based on files in `fuel/packages/auth/migrations/...`**

* `fuel/app/config/env/migrations.php`
```php
<?php
<?php
return array (
  'version' => 
  array (
    'app' => 
    array (
      'default' => 0,
    ),
    'module' => 
    array (
    ),
    'package' => 
    array (
      'auth' => 
      array (
        0 => '001_auth_create_usertables',
        1 => '002_auth_create_grouptables',
        2 => '003_auth_create_roletables',
        3 => '004_auth_create_permissiontables',
        4 => '005_auth_create_authdefaults',
        5 => '006_auth_add_authactions',
        6 => '007_auth_add_permissionsfilter',
        7 => '008_auth_create_providers',
        8 => '009_auth_create_oauth2tables',
        9 => '010_auth_fix_jointables',
      ),
    ),
  ),
  'folder' => 'migrations/',
  'table' => 'migration',
);
```

* Tables
 1. users
 1. users_clients
 1. users_providers
 1. users_scopes
 1. users_sessions
 1. users_sessionscopes
 1. and `migration` table      
_(can change the prefix `users` by the setting `table_name` in `simpleauth.php`)_

* Migration table's record

type | name | migration
---  |--- |----
package|auth|001_auth_create_usertables
package|auth|002_auth_create_grouptables
package|auth|003_auth_create_roletables
package|auth|004_auth_create_permissiontables
package|auth|005_auth_create_authdefaults
package|auth|006_auth_add_authactions
package|auth|007_auth_add_permissionsfilter
package|auth|008_auth_create_providers
package|auth|009_auth_create_oauth2tables
package|auth|010_auth_fix_jointables

## Enable Login, Group, Acl Drivers
