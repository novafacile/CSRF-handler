# CSRF-Handler
<b>CSRF protection</b> class file for <b>PHP</b>.<br><br>
Original: https://github.com/banujan6/CSRF-handler


# Functions

| Function  | Description |
| ------------- | ------------- |
| get()  | Validate CSRF only for GET requests  |
| post()   | Validate CSRF only for POST requests   |
| all()   | Validate CSRF for GET & POST requests   |
| token()   | Generate CSRF Token   |
| flushToken()  | Remove all tokens |


# Installation

<p>Use namespace & class.</p>

```php
	<?php
		//If you are using any frameworks, It will load autoload.php automatically. So you don't need.
		require_once __DIR__ . '/../../vendor/autoload.php';
		use novafacile\csrf as csrf;
	?>
```

<br>
<br>
<i><b>Including File</b></i>
<br><br>
<p>Download the <b>csrf.php</b> file in directory <b>src</b>. Then include it in your PHP file.</p>
<br><br>

```php
<?php 
  require_once("path/csrf.php");
  use novafacile\csrf as csrf;
?>
```

# Usages

<p>
 This <b>CSRF-Handler</b> will look for a <i>form-data</i> / <i>url-parameter</i> called <b>_token</b>. To verify the request, <i>POST</i> request need to have a <b>_token</b> in <i>form-data</i>. And <i>GET</i> request need to have a <b>_token</b> in <i>url-parameter</i>.  
</p>


### Generating Token

```php
<form>
  <input type="hidden" name="_token" value="<?php echo csrf::token(); ?>">
</form>
```

### Validating Request

<b>GET Request Only</b>

```php
  $isValid = csrf::get(); // return TRUE or FALSE
  
  if ( $isValid ) {
  
    //Do something if valid
  
  } else {
  
    //Do something if not vaid
  
  }
```

<b>POST Request Only</b>

```php
  $isValid = csrf::post(); // return TRUE or FALSE
  
  if ( $isValid ) {
  
    //Do something if valid
  
  } else {
  
    //Do something if not vaid
  
  }
```

<b>GET & POST Request</b>

```php
  $isValid = csrf::all(); // return TRUE or FALSE
  
  if ( $isValid ) {
  
    //Do something if valid
  
  } else {
  
    //Do something if not vaid
  
  }
```


### Clear All Active Tokens

```php
  csrf::flushToken(); // will destroy all active tokens
```


# Examples

<p>
  You can find basic examples in <b><i>example/</i></b> directory. 
  </p>
  
# License

Licensed under MIT
