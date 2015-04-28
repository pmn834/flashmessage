# CFlashmessage
Flashmessage for Anax MVC

Available at Packagist as [flashmessage](https://packagist.org/packages/pmn834/flashmessage).

## Using CFlashmessage

Copy the file *flashmessage.css* from the `CFlashmessage/css` folder to your Anax `webroot/css` folder. This stylesheet can then be added to your frontcontroller.

```php
$app->theme->addStylesheet("css/flashmessage.css");
```

Add CFlashmessage as a service.

```php
$di->setShared('flash', function() {
    $flashmessage = new \pmn834\CFlashmessage\CFlashmessage();
    return $flashmessage;
});
```

Start a session before using CFlashmessage.

```php
$app->session();
```

One or more flashmessages can then be added.

```php
$app->flash->info("Info flash message");
$app->flash->error("Error flash message");
$app->flash->success("Success flash message");
$app->flash->warning("Warning flash message");
```

To get all flashmessages as HTML use `flash->output()`.

```php
$app->flash->output();
```

The `CFlashmessage/test` folder includes the frontcontroller `flashtest.php` to test the CFlashmessage service.