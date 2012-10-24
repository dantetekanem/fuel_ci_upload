fuel_ci_upload
==============

CodeIgniter File Uploading class adapted for FuelPHP

Its really easy how to use, in the same way as CodeIgniter: http://codeigniter.com/user_guide/libraries/file_uploading.html

Put the files (as the directory structure on the git, class and lang file) on your project, and put it in the bootstrap autoload (at fuel/app/boostrap.php):
```php
Autoloader::add_classes(array(
	// Add classes you want to override here
	// Example: 'View' => APPPATH.'classes/view.php',
	'CI_Upload' => APPPATH.'classes/ci_upload.php',
));
```

And to do a upload:

```php
$upload 			= new CI_Upload(array(
	'upload_path'	=> DOCROOT.'/uploads/',
	'allowed_types'	=> 'jpg|gif|png',
	'max_size'		=> 5000, // 5mb
));

if($upload->do_upload('avatar'))
{
	Debug::dump($upload->data());
}
else
{
	Debug::dump($_FILES, $upload->display_errors());
}
```