# AWS-S3-PHPClass
With this class you can easily use Amazon S3.

### Edit ###
All you need to edit is, _on class_s3.php_:
```php
$array = array(
			'key' =>    'AcessKey'	,  // Your Amazon Acess Key.
			'secret' => 'SecretKey' ,  // Your Amazon Secret Key.
			'region' => 'Region'	,  // Your S3 Region (like: us-west-2).
		);
```

### Usage ###
It's so much soft to use, see this examples:

**Upload**

Simple Upload:
```php
$s3 = new s3('BucketName');
	$s3->write_file(
		'name_of_file.txt',
		'This is a example of uploading one .txt file :)'
	);
```
Upload setting permissions:
```php
$s3 = new s3('BucketName');
	$s3->write_file(
		'name_of_file.txt',
		'This is a example of uploading one .txt file :)',
		'public-read-write'
	);
```
*It can be: 'private' , 'public-read' , 'public-read-write' , 'authenticated-read' , 'bucket-owner-read' , 'bucket-owner-full-control' , 'log-delivery-write'.*

Uploading and returning informations of sent file:
```php
$s3 = new s3('BucketName');
	var_dump( 
		$s3->write_file(
			'name_of_file.txt',
			'This is a example of uploading one .txt file :)'
		);
	);
```

**Reading**

Let's read the same archive that we sent:
```php
$s3 = new s3('BucketName');
	echo $s3->read_file('name_of_file.txt');
```
