# SummonWire

ProcessWire module providing an API for [Summoning](https://github.com/arnobaer/Summoning) HTML5 code generator.

## Installation

See ProcessWire module [install](http://modules.processwire.com/install-uninstall/) instructions.

## Usage

Include the `SummonWire` module and call method `create` to create new Summoning `Node` instances. 

```php
// create document root node
$html = $modules->get('SummonWire')->create('html');

// add an attribute
$html->lang($user->language->iso639);

// add head and title elements
$html->head()->title($page->title);

// add some more page content
$body = $html->body()->id('main');
$body->h1($page->title)->id($page->name)->class('w3-blue');
$body->append($page->content);

// render document
echo $html;
```

The above example will render the following valid HTML5 code:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>Hello world!</title>
  </head>
  <body id="main">
    <h1 id="home" class="w3-blue">Hello world!</h1>
    <p>Yet another lazy method to create valid HTML5!</p>
  </body>
</html>
```

See the [Summoning](https://github.com/arnobaer/Summoning) project on GitHub for detailed instructions.

## License

SummonWire and Summoning are licensed under the GNU General Public License Version 3.
