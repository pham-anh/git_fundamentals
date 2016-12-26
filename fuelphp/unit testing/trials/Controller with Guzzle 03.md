# Test code

```php
<?php
public function test_action_create_withNoPost_returns_presenterAccountCreate(){
		$client = new \GuzzleHttp\Client();
		$response = $client->request('GET', 'http://localhost/payment_system/public/account/create');
		
		$expected_response = Presenter::forge('account/create', 'view', null, 'template');
		$this->assertEquals($expected_response->get_view(), $response->getBody()->getContents());
	}
```

# Result

```html
There was 1 failure:

1) Test_Controller_Account::test_action_create_withNoPost_returns_presenterAccountCreate
Failed asserting that '<!DOCTYPE html>
<html>
<head>
        <meta charset="utf-8">
        <title>Accounts .. New Account</title>
                <link type="text/css" rel="stylesheet" href="http://localhost/payment_system/public/assets/css/bootstrap.css?1474694256" />
                <link type="text/css" rel="stylesheet" href="http://localhost/payment_system/public/assets/css/stylesheet.css?1477414325" />
        <style>
                body { margin: 40px; }
        </style>
</head>
<body>
        <div class="container">
                <div class="col-md-12">
                        <h2>Accounts <span class='glyphicon glyphicon-flag'> </span> New Account</h2>
                        <hr>
                </div>
                <div class="col-md-12">
<!--<h2>New Account</h2>-->
<!--<br>-->


<form class="center-block" action="http://localhost/payment_system/public/account/create" accept-charset="utf-8" method="post">
<fieldset>
        <div class="form-group col-sm-6">
                <label class="control-label" for="form_account_name">Account name</label>
                        <input class="form-control " placeholder="Account name" name="account_name" value="" type="text" id="form_account_name" />
        </div>
        <div class="form-group col-sm-6">
                <label class="control-label col-sm-4" for="form_account_no">Account no</label>
                        <input class="form-control col-sm-8" placeholder="Account no" name="account_no" value="" type="text" id="form_account_no" />
        </div>
        <div class="form-group col-sm-6">
                <label class="control-label text-overflow" for="form_bank">Bank</label>
                        <input class="form-control" placeholder="Bank" ="" name="bank" value="" type="text" id="form_bank" />
                </div>
        <div class="form-group col-sm-6">
                <label class="control-label" for="form_province">Province</label>
                        <input class="form-control" placeholder="Province" name="province" value="" type="text" id="form_province" />
                </div>
                <div class="form-group col-sm-6 text-right">
                        <label class='control-label'>&nbsp;</label>
                        <input class="btn btn-primary" name="submit" value="Save" type="submit" id="form_submit" />             </div>
                <div class="form-group col-sm-3">
                        <a class="btn btn-default" href="http://localhost/payment_system/public/account">Cancel</a>             </div>
</fieldset>
</form>

<!--<p></p>-->
                </div>
                <footer>
                        <p class="pull-right">Page rendered in 0.5005s using 2.545mb of memory.</p>
                        <p>
                                <a href="http://fuelphp.com">FuelPHP</a> is released under the MIT license.<br>
                                <small>Version: 1.8</small>
                        </p>
                </footer>
        </div>
</body>
</html>
' matches expected Fuel\Core\View Object &0000000076e4d03a000000005a79185e (
    'request_paths' => Array &0 ()
    'auto_filter' => true
    'filter_closures' => true
    'local_filter' => Array &0
    'file_name' => 'E:\Xampp\htdocs\payment_system\fuel\app\views\template.php'
    'data' => Array &0
    'extension' => 'php'
    'active_request' => false
    'active_language' => 'en'
).
```
