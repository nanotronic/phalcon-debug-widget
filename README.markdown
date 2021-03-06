Phalcon Debug Widget (PDW)
===

The Phalcon Debug Widget is designed to make development easier by displaying debugging information directly in your browser window. Currently it displays php globals such as $_SESSION as well as outputing resource usage and database queries and connection information. It includes syntax highlighting via [Prismjs.com](http://prismjs.com/).

If it looks familiar, its because its modeled after the [Yii debug toolbar](https://github.com/malyshev/yii-debug-toolbar)


## Installation

Copy the main PDW folder into your project where you keep third-party libraries.
For example (app/library or app/vendor or /vendor). Copy or move the pdw-assets folder to your public folder.

## Usage and Configuration



Define a debug or environment flag in your main index.php file so you can easily disable the Phalcon Debug Widget on production environments. Example:

```php
defined('PHALCONDEBUG') || define('PHALCONDEBUG', true);
```

After you have setup your \Phalcon\Loader and \Phalcon\DI\FactoryDefault() create a new instance of the debug widget. Here we will tell phalcon about the PDW namespace and instantiate the widget with the $di. (Assuming $di is your dependency injector and $loader is your \Phalcon\Loader)
```php
if (PHALCONDEBUG == true) {
	$namespaces = array_merge($loader->getNamespaces(), array('PDW'=>realpath('/path/to/PDW')));
	$loader->registerNamespaces($namespaces);
	$debugWidget = new \PDW\DebugWidget($di);
}
```


## Preview

![](/preview.png)

## Attribution:

Bug Icon designed by [Nithin Viswanathan](http://thenounproject.com/nsteve) from the [Noun Project](http://thenounproject.com)

JQuery Syntax Highlighting implemented with [Prismjs.com](http://prismjs.com/)


