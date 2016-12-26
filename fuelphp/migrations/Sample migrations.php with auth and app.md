### Preparation

* Auth package configuration (e.g. simpleauth)
* App's migration files

### Command

```shell
php oil refine migrate -all
```
### The result after running

* Command output

```shell
# php oil refine migrate -all
Performed migrations for app:default:
001_create_accounts
002_create_payment_orders
Performed migrations for package:auth:
001_auth_create_usertables
002_auth_create_grouptables
003_auth_create_roletables
004_auth_create_permissiontables
005_auth_create_authdefaults
006_auth_add_authactions
007_auth_add_permissionsfilter
008_auth_create_providers
009_auth_create_oauth2tables
010_auth_fix_jointables
```

* fuel/app/config/env/migrations.php

```php
<?php
return array (
  'version' => 
  array (
    'app' => 
    array (
      'default' => 
      array (
        0 => '001_create_accounts',
        1 => '002_create_payment_orders',
      ),
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

* migration table

type | name | migration
---  |--- |----
app | default|001_create_accounts
app |default|002_create_payment_orders
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



