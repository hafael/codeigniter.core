codeigniter.core
================

## Multiplos projetos com CodeIgniter

### Com esta estrutura é possível gerenciar multiplos projetos com o CodeIgniter.

Também é possível trabalhar com várias versões do core.
Basta alterar o arquivo **index.php** de cada aplicação e definir o caminho da pasta **system** na variável '$system_path = "";'

### Estrutura das pastas

* admin (para cada aplicação que não seja default)
* 	.htaccess
* 	index.php
* applications (pasta das aplicações)
* 	admin
*		.htaccess
* 	portal
*		.htaccess
* CIcore_versions
*	system_2.1.3
* index.php
* user_guide

### Configurar uma nova aplicação

Crie uma pasta no root com o pathname da aplicação, e crie os seguintes arquivos:

**.htacess**

'
RewriteEngine On
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
RewriteRule ^(.*)$ index.php/$1 [L]

'

**index.php**

Copie o arquivo index.php da pasta root e cole na pasta da aplicação, edite as seguintes linhas:

'
$system_path = "../CIcore_versions/system_2.1.3";

$application_folder = "../applications/admin";
'
