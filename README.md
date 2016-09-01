# PHP User Input Data Filters
This is a pretty straight forward PHP class. It's meant to be an additional filter when using PHP's PDO before binding parameters to a prepared statement.

## Usage
```php
<?php
	$param = $_GET['username']; // From the URL bar 
	$param = Filter::String( $param ); // Filters the data from the URL

	// Add to database using PDO with bound param
	$sample = $con->prepare("SELECT column FROM table WHERE username = :param LIMIT 1");
	$sample->bindParam(':param', $param, PDO::PARAM_STR);
	$sample->execute(); 
?>
```

## Supports
This class supports the following (so far)
- `Filter::Email( $email );`
- `Filter::String( $string, $encode_html_or_not );`
- `Filter::URL( $url );`
- `Filter::Int( $integer );`

Feel free to branch and update this class.
