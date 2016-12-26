# Test case

```php
<?php
public function test_action_create_withNoPost_returns_presenterAccountCreate(){
		$client = new \GuzzleHttp\Client();
		$response = $client->request('GET', 'http://localhost/payment_system/public/account/create');
		$expected_response = Presenter::forge('account/create', 'view', null, 'template');
		$this->assertEquals($expected_response, $response->getBody());
	}
?>
```

# Result

```diff
1) Test_Controller_Account::test_action_create_withNoPost_returns_presenterAccountCreate
GuzzleHttp\Psr7\Stream Object &0000000070fe67bb0000000057333ade (
    'stream' => resource(274) of type (stream)
    'size' => null
    'seekable' => true
    'readable' => true
    'writable' => true
    'uri' => 'php://temp'
    'customMetadata' => Array &0 ()
) is not instance of expected class "Presenter_Account_Create".
--- Expected
+++ Actual
@@ @@
-Presenter_Account_Create Object &0000000070fe67c20000000057333ade (
-    '_method' => 'view'
-    '_view' => Fuel\Core\View Object &0000000070fe67c40000000057333ade (
-        'request_paths' => Array &0 ()
-        'auto_filter' => true
-        'filter_closures' => true
-        'local_filter' => Array &0
-        'file_name' => 'E:\Xampp\htdocs\payment_system\fuel\app\views\template.php'
-        'data' => Array &0
-        'extension' => 'php'
-        'active_request' => false
-        'active_language' => 'en'
-    )
-    '_auto_filter' => null
-    '_active_request' => false
+GuzzleHttp\Psr7\Stream Object &0000000070fe67bb0000000057333ade (
+    'stream' => resource(274) of type (stream)
+    'size' => null
+    'seekable' => true
+    'readable' => true
+    'writable' => true
+    'uri' => 'php://temp'
+    'customMetadata' => Array &0 ()
 )
```
