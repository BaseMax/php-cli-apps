# php-cli-apps

A simple, fast, and fun example for building command line apps in PHP.

**max@base:~$ php donya.php**

```
Usage:
  donya [command]

Available Commands:
  help        Help about any command
  install     Installing package(s) in DonyaOS
  remove      Removing package(s) in DonyaOS
  list        Listing package(s) in DonyaOS
  search      Search package(s) in the repository of DonyaOS

Flags:
  -h, --help   help for donya

Use "donya [command] --help" for more information about a command.
```

### Sample Commands

```
php cli.php install php ; install php version 7.1
php cli.php i php ; install php version 7.1

php cli.php i php7.4 ; install php version 7.4
php cli.php i gcc ; install gcc

php cli.php s php ; search all package with php perfix
php cli.php search php ; search all package with php perfix

php cli.php r php ; remove php package
php cli.php remove php ; remove php package

php cli.php r php* ; remove all php prefix package

php cli.php i php* ; install all php prefix package
```

## Getting start commands

```php
function callCommand($command) {
	global $argv;
	$args=$argv;
	unset($args[0]); // software name. e.g: donya
	unset($args[1]); // command name
	$args=array_values($args); // start index of items from 0 in Array
	switch ($command) {
		case "i":
		case "install":
			commandInstall($args);
			break;
		case "r":
		case "remove":
			commandRemove($args);
			break;
		case "u":
		case "update":
			commandUpdate($args);
			break;
		case "l":
		case "list":
			commandList($args);
			break;
		case "s":
		case "search":
			commandSearch($args);
			break;
		case "h":
		case "help":
		default:
			help($command);
			break;
	}
}
```

---------

# Max Base

My nickname is Max, Programming language developer, Full-stack programmer. I love computer scientists, researchers, and compilers. ([Max Base](https://maxbase.org/))

## Asrez Team

A team includes some programmer, developer, designer, researcher(s) especially Max Base.

[Asrez Team](https://www.asrez.com/)

