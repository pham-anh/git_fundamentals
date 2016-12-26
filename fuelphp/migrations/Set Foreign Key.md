# Mysql Foreign Key

## Create a table with FK to a column of another table

```sql
CREATE TABLE `users` (
    `id` int(11) NOT NULL AUTO_INCREMENT,
    `po_id` int(11) UNSIGNED NOT NULL,
    `email` varchar(50) NOT NULL,
    `title` varchar(50) DEFAULT 'mr.' NOT NULL,
    `password` varchar(125) NOT NULL,
    PRIMARY KEY `id` (`id`),
    CONSTRAINT constraintA FOREIGN KEY (po_id) REFERENCES payment_orders (id) ON UPDATE CASCADE ON DELETE RESTRICT)
ENGINE = InnoDB  DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
```

#### Note

* The reference table, column must exist
* The data type of the target columns must be the same

#### How to use `FuelPHP` with this

```sql
\DBUtil::create_table(
    'users',
    array(
        'id' => array('constraint' => 11, 'type' => 'int', 'auto_increment' => true),
        'po_id' => array(constraint' => 11, 'type' => 'int'),
        'email' => array('constraint' => 50, 'type' => 'varchar'),
        'title' => array('constraint' => 50, 'type' => 'varchar', 'default' => 'mr.'),
        'password' => array('constraint' => 125, 'type' => 'varchar'),
    ),
    array('id'), false, 'InnoDB', 'utf8_unicode_ci',
    array(
        array(
            'constraint' => 'constraintA',
            'key' => 'po_id',
            'reference' => array(
                'table' => 'payment_orders',
                'column' => 'id',
            ),
            'on_update' => 'CASCADE',
            'on_delete' => 'RESTRICT'
        ),
    ),
);
```

* Refs: http://fuelphp.com/docs/classes/database/dbutil.html#/method_create_table

#### What if the migration contains field settings that is unknown to `FuelPHP`?

e.g.

```sql
'email' => array('constraint' => 50, 'type' => 'varchar', 'abc' => true),
```

Or

```sql
'email' => array('constraint' => 50, 'type' => 'varchar', 'unique' => true),
```

* `'abc' => true`
* `'unique' => true`

are unknown to FuelPHP, and will not be read when we run `oil refine migrate`
