### Test code

```php
<?php
public function test_action_create_withNoPost_returns_presenterAccountCreate(){
		$client = new \GuzzleHttp\Client();
		$response = $client->request('GET', 'http://localhost/payment_system/public/account/create');
		//echo $response->getBody();
		$expected_response = Response::forge(Presenter::forge('account/create', 'view', null, 'template'));
		
		$this->assertEquals($expected_response, $response);	
	}
?>
```




### Result

```diff
1) Test_Controller_Account::test_action_create_withNoPost_returns_presenterAccountCreate
GuzzleHttp\Psr7\Response Object &0000000073d3be3f000000006cc9e96d (
    'reasonPhrase' => 'OK'
    'statusCode' => 200
    'headers' => Array &0 (
        'Date' => Array &1 (
            0 => 'Wed, 26 Oct 2016 14:49:30 GMT'
        )
        'Server' => Array &2 (
            0 => 'Apache/2.4.23 (Win32) OpenSSL/1.0.2h PHP/5.6.24'
        )
        'X-Powered-By' => Array &3 (
            0 => 'PHP/5.6.24'
        )
        'Set-Cookie' => Array &4 (
            0 => 'fuelcid=vUoqoq5aTnS7J-2o_wNYioujoqNHzRfOzqXdiT13rF0vZCTV4PWC3ZJO6giusO9fO952-R0_nI0ztGmJVVcr69QVmGu1gk0Bs_nROP4VM8Eeu5H6b_qrDCIpZQ9vCeWNqSUkI-aejhtUw9Mr66SIj0Pg2jEpJ2z74dOW6NDvxnonseCYGmJqlEMtQAxs5Utrq57UR4EU6T7-hDorwJPAcQpvSoh8tZ20GsaJyHLZ2__ZysHksjNYwOFou_k5gerI5PVFzaI2cCDNMJYN0mlL3Mq0r-mS4dcbWUmIO6_AIZXVvpr_eP8WRqjQfwnJu8_brIb05088PVMcRpfqksDGBYEjF1KYwRYimalzHpF5XBhSlibQGEhZ3-pFPnF8SOjW9papPILVhQJbtbpoouce7XdEUU42ZlpMdnp2dzFjYWVPUTFhTkhkM1hyQ1lZcmRBVHdmb3N5bS1Vcnc; expires=Wed, 26-Oct-2016 16:49:30 GMT; Max-Age=7200; path=/'
        )
        'Content-Length' => Array &5 (
            0 => '2353'
        )
        'Content-Type' => Array &6 (
            0 => 'text/html; charset=UTF-8'
        )
    )
    'headerNames' => Array &0
    'protocol' => '1.1'
    'stream' => GuzzleHttp\Psr7\Stream Object &0000000073d3be3d000000006cc9e96d (
        'stream' => resource(274) of type (stream)
        'size' => null
        'seekable' => true
        'readable' => true
        'writable' => true
        'uri' => 'php://temp'
        'customMetadata' => Array &7 ()
    )
) is not instance of expected class "Fuel\Core\Response".
--- Expected
+++ Actual
@@ @@
-Fuel\Core\Response Object &0000000073d3be35000000006cc9e96d (
-    'status' => 200
-    'headers' => Array &0 ()
-    'body' => Presenter_Account_Create Object &0000000073d3be44000000006cc9e96d (
-        '_method' => 'view'
-        '_view' => Fuel\Core\View Object &0000000073d3be42000000006cc9e96d (
-            'request_paths' => Array &1 ()
-            'auto_filter' => true
-            'filter_closures' => true
-            'local_filter' => Array &1
-            'file_name' => 'E:\Xampp\htdocs\payment_system\fuel\app\views\template.php'
-            'data' => Array &1
-            'extension' => 'php'
-            'active_request' => false
-            'active_language' => 'en'
+GuzzleHttp\Psr7\Response Object &0000000073d3be3f000000006cc9e96d (
+    'reasonPhrase' => 'OK'
+    'statusCode' => 200
+    'headers' => Array &0 (
+        'Date' => Array &1 (
+            0 => 'Wed, 26 Oct 2016 14:49:30 GMT'
         )
-        '_auto_filter' => null
-        '_active_request' => false
+        'Server' => Array &2 (
+            0 => 'Apache/2.4.23 (Win32) OpenSSL/1.0.2h PHP/5.6.24'
+        )
+        'X-Powered-By' => Array &3 (
+            0 => 'PHP/5.6.24'
+        )
+        'Set-Cookie' => Array &4 (
+            0 => 'fuelcid=vUoqoq5aTnS7J-2o_wNYioujoqNHzRfOzqXdiT13rF0vZCTV4PWC3ZJO6giusO9fO952-R0_nI0ztGmJVVcr69QVmGu1gk0Bs_nROP4VM8Eeu5H6b_qrDCIpZQ9vCeWNqSUkI-aejhtUw9Mr66SIj0Pg2jEpJ2z74dOW6NDvxnonseCYGmJqlEMtQAxs5Utrq57UR4EU6T7-hDorwJPAcQpvSoh8tZ20GsaJyHLZ2__ZysHksjNYwOFou_k5gerI5PVFzaI2cCDNMJYN0mlL3Mq0r-mS4dcbWUmIO6_AIZXVvpr_eP8WRqjQfwnJu8_brIb05088PVMcRpfqksDGBYEjF1KYwRYimalzHpF5XBhSlibQGEhZ3-pFPnF8SOjW9papPILVhQJbtbpoouce7XdEUU42ZlpMdnp2dzFjYWVPUTFhTkhkM1hyQ1lZcmRBVHdmb3N5bS1Vcnc; expires=Wed, 26-Oct-2016 16:49:30 GMT; Max-Age=7200; path=/'
+        )
+        'Content-Length' => Array &5 (
+            0 => '2353'
+        )
+        'Content-Type' => Array &6 (
+            0 => 'text/html; charset=UTF-8'
+        )
+    )
+    'headerNames' => Array &0
+    'protocol' => '1.1'
+    'stream' => GuzzleHttp\Psr7\Stream Object &0000000073d3be3d000000006cc9e96d (
+        'stream' => resource(274) of type (stream)
+        'size' => null
+        'seekable' => true
+        'readable' => true
+        'writable' => true
+        'uri' => 'php://temp'
+        'customMetadata' => Array &7 ()
     )
 )
```
