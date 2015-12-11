#####How to Encode/Decode JSON in php?

---

```php
// Decode JSON
$mydecodeddata = json_decode($my_json_string, true)

// Encode JSON
$my_json_string = json_encode($my_data, true)
```

---

#####Check if an array is having value for specific key or not

```php
if ( array_key_exists($key,$my_array) == false ) {
    echo "key doesn't exists";
} else {
	echo "key exists";
}

```

---

#####Foreach loop in php

```php
	foreach($array_to_check as $value) {
		echo "$value";
	}
```

---

#####PHP get request-body

```php
$rqstBody = @file_get_contents('php://input');
```

---

##### PHP get server protocol type - http or https

```php
	function get_protocol() {
		if (isset($_SERVER['HTTPS']) &&
		    ($_SERVER['HTTPS'] == 'on' || $_SERVER['HTTPS'] == 1) ||
		    isset($_SERVER['HTTP_X_FORWARDED_PROTO']) &&
		    $_SERVER['HTTP_X_FORWARDED_PROTO'] == 'https') {
			return 'https://';
		} else {
	  		return'http://';
		}
	}
```

---

#####PHP Get all headers

```php
$headers = getallheaders();
```

---

#####PHP - Get current file path / URL

```php
$path = $_SERVER['SERVER_NAME'] . dirname($_SERVER['PHP_SELF']);
echo $path;
```

---

#####PHP - Delete file at specified location

```php
$file_path_location = "https://myserver.com/myfolder/myfile.png"
unlink($file_path_location);
```

#####PHP Find a string & replace it within a string.

```php
$phrase = "This is my string. and text_to_replace is this.";
$find = "text_to_replace";
$replace = array('What the Hell');
$newphrase = str_replace($find, $replace, $phrase);
// output string would be "This is my string. and What the Hell is this."
```

---

#####PHP - Include another file or include once

```php
// to include file another
include 'my_another_file.php';

// to include one time only. This will help to avoid errors
include_once 'my_another_file.php';
```

---

#####PHP - get the request type

```php
$method = $_SERVER['REQUEST_METHOD'];
```

----

#####PHP - set the response format JSON

```php
header('Content-Type: application/json');
```