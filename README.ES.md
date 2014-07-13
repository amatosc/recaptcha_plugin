Guia rápida de uso
================================================================================

1. Obten una clave reCAPTCHA.
--------------------------------------------------------------------------------
 - <http://www.google.com/recaptcha>

2. Ajustes.
--------------------------------------------------------------------------------
 - Descarga `recaptchalib.php` de:
  - <http://code.google.com/p/recaptcha/downloads/list?q=label:phplib-Latest>
 - Colocalo dentro de `/app/Plugin/Recaptcha/Vendor/`


3. Configuracion.
--------------------------------------------------------------------------------
Inserta la clave en /app/Plugin/Recaptcha/Config/key.php.
```php
<?php
	$config = array(
		'Recaptcha' => array(
			'Public'  => 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx',
			'Private' => 'xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx',
		),
	);
```

Carga el Plugin en `/app/Config/bootstrap.php` inserta

```php
<?php
CakePlugin::load('Recaptcha');
```


4. Control.
--------------------------------------------------------------------------------
```php
<?php
	public $components = array('Recaptcha.Recaptcha');
	public $helpers = array('Recaptcha.Recaptcha');
```

5. Vista.
--------------------------------------------------------------------------------
Dentro de la etiqueta `<form>`:
```php
<?php

	echo $this->Recaptcha->show();
	echo $this->Recaptcha->error();
```
Si quieres usar algun theme de reCAPTCHA deberias escribir esto:
```php
<?php echo $this->Recaptcha->show('white'); ?>
```

**Posibles valores**: 'red' | 'white' | 'blackglass' | 'clean';
**Valor por defecto**: 'red';
