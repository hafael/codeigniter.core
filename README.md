Multiple projects with CodeIgniter
================

### With this structure it is possible to manage multiple projects with CodeIgniter.

You can also work with multiple versions of the core.
Basta alterar o arquivo **index.php** de cada aplicação e definir o caminho da pasta **system** na variável **$system_path = '';**

Just change the file **index.php** each application and set the folder path **system** in the variable **$system_path = '';**

### Folder Structure

	- /admin/ ( For each application other than default )
		- .htaccess
		- index.php
	- /applications/ ( Folder applications )
		- /admin/ ( Application example )
			- .htaccess
			- index.php
		- /portal/ ( Example default application )
			- .htaccess
			- index.php
	- /CIcore_versions/ ( Contains the versions of CI Core used )
		- /system_2.1.3
	- index.php ( Index of default application )
	- /user_guide/


### Setting up a new application

Create a folder in the root with the pathname of the application, and create the following files:

**.htacess**


	RewriteEngine On
	RewriteCond %{REQUEST_FILENAME} !-f
	RewriteCond %{REQUEST_FILENAME} !-d
	RewriteRule ^(.*)$ index.php/$1 [L]


**index.php**

Copy the index.php file of the root folder and paste in the application folder, edit the following lines:


	$system_path = "../CIcore_versions/system_2.1.3"; /* Path to the version of the core CodeIgniter */

	$application_folder = "../applications/admin"; /* Folder path of the core version of CodeIgniter */

