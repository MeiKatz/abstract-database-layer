Abstract Database Layer
=======================

An abstract database layer based on PDO, but with some improvements.

How to use
-----------------------
```php
$adl = AbstractDatabaseLayer::establish( 'mysql', [
  'database' => 'foobar',
  'hostname' => 'example.org',
  'username' => 'for',
  'password' => 'bar42',
  'port'     => 3307
]);

$stmt   = $adl->prepare( 'SELECT * FROM users WHERE username = :username AND password = :password' );
$result = $stmt->execute([
  'username' => 'some',
  'password' => 'body'
]);

foreach ( $result as $user ) {
  echo 'user ', $user[ 'username' ], ' has the password "', $user[ 'password' ], '"';
}
```

How to include it
-----------------------
```php
require_once 'abstract_database_layer/include.php';

# here you go ...
```
