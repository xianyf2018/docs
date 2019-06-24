---
layout: default
language: 'en'
version: '4.0'
title: 'Phalcon\Image'
---

* [Phalcon\Image](#Image)
* [Phalcon\Image\Adapter\AbstractAdapter](#Image_Adapter_AbstractAdapter)
* [Phalcon\Image\Adapter\AdapterInterface](#Image_Adapter_AdapterInterface)
* [Phalcon\Image\Adapter\Gd](#Image_Adapter_Gd)
* [Phalcon\Image\Adapter\Imagick](#Image_Adapter_Imagick)
* [Phalcon\Image\Exception](#Image_Exception)
* [Phalcon\Image\ImageFactory](#Image_ImageFactory)
        
<h1 id="Image">Class Phalcon\Image</h1>

[Source on GitHub](https://github.com/phalcon/cphalcon/tree/v{{ page.version }}.0/phalcon/image.zep)

| Namespace  | Phalcon |

This file is part of the Phalcon Framework.

(c) Phalcon Team <team@phalconphp.com>

For the full copyright and license information, please view the LICENSE.txt
file that was distributed with this source code.


## Constants
```php
const AUTO = 4;
const HEIGHT = 3;
const HORIZONTAL = 11;
const INVERSE = 5;
const NONE = 1;
const PRECISE = 6;
const TENSILE = 7;
const VERTICAL = 12;
const WIDTH = 2;
```

        
<h1 id="Image_Adapter_AbstractAdapter">Abstract Class Phalcon\Image\Adapter\AbstractAdapter</h1>

[Source on GitHub](https://github.com/phalcon/cphalcon/tree/v{{ page.version }}.0/phalcon/image/adapter/abstractadapter.zep)

| Namespace  | Phalcon\Image\Adapter |
| Uses       | Phalcon\Image, Phalcon\Image\Exception |
| Implements | AdapterInterface |

All image adapters must use this class


## Properties
```php
//
protected static checked = false;

//
protected file;

/**
 * Image height
 *
 * @var int
 */
protected height;

//
protected image;

/**
 * Image mime type
 *
 * @var string
 */
protected mime;

//
protected realpath;

/**
 * Image type
 *
 * Driver dependent
 *
 * @var int
 */
protected type;

/**
 * Image width
 *
 * @var int
 */
protected width;

```

## Methods
```php
public function background( string $color, int $opacity = 100 ): Adapter;
```
 Set the background color of an image
 

```php
public function blur( int $radius ): Adapter;
```
 Blur image
 

```php
public function crop( int $width, int $height, int $offsetX, int $offsetY ): Adapter;
```
 Crop an image to the given size
 

```php
public function flip( int $direction ): Adapter;
```
 Flip the image along the horizontal or vertical axis
 

```php
public function getHeight(): int
```


```php
public function getImage()
```


```php
public function getMime(): string
```


```php
public function getRealpath()
```


```php
public function getType(): int
```


```php
public function getWidth(): int
```


```php
public function liquidRescale( int $width, int $height, int $deltaX, int $rigidity ): Adapter;
```
This method scales the images using liquid rescaling method. Only support
Imagick

@param int $width   new width
@param int $height  new height
@param int $deltaX How much the seam can traverse on x-axis. Passing 0 causes the seams to be straight.
@param int $rigidity Introduces a bias for non-straight seams. This parameter is typically 0.


```php
public function mask( mixed $watermark ): Adapter;
```
 Composite one image onto another
 

```php
public function pixelate( int $amount ): Adapter;
```
 Pixelate image
 

```php
public function reflection( int $height, int $opacity = 100, bool $fadeIn = false ): Adapter;
```
 Add a reflection to an image
 

```php
public function render( string $ext, int $quality = 100 ): string;
```
 Render the image and return the binary string
 

```php
public function resize( int $width, int $height, int $master ): Adapter;
```
 Resize the image to the given size
 

```php
public function rotate( int $degrees ): Adapter;
```
 Rotate the image by a given amount
 

```php
public function save( string $file, int $quality = -1 ): Adapter;
```
 Save the image
 

```php
public function sharpen( int $amount ): Adapter;
```
 Sharpen the image by a given amount
 

```php
public function text( string $text, mixed $offsetX = false, mixed $offsetY = false, int $opacity = 100, string $color = 000000, int $size = 12, string $fontfile ): Adapter;
```
 Add a text to an image with a specified opacity
 

```php
public function watermark( mixed $watermark, int $offsetX, int $offsetY, int $opacity = 100 ): Adapter;
```
 Add a watermark to an image with the specified opacity
 


        
<h1 id="Image_Adapter_AdapterInterface">Interface Phalcon\Image\Adapter\AdapterInterface</h1>

[Source on GitHub](https://github.com/phalcon/cphalcon/tree/v{{ page.version }}.0/phalcon/image/adapter/adapterinterface.zep)

| Namespace  | Phalcon\Image\Adapter |

This file is part of the Phalcon Framework.

(c) Phalcon Team <team@phalconphp.com>

For the full copyright and license information, please view the LICENSE.txt
file that was distributed with this source code.


## Methods
```php
public function background( string $color, int $opacity = 100 );
```
//

```php
public function blur( int $radius );
```
//

```php
public function crop( int $width, int $height, int $offsetX, int $offsetY );
```
//

```php
public function flip( int $direction );
```
//

```php
public function mask( mixed $watermark );
```
//

```php
public function pixelate( int $amount );
```
//

```php
public function reflection( int $height, int $opacity = 100, bool $fadeIn = false );
```
//

```php
public function render( string $ext, int $quality = 100 );
```
//

```php
public function resize( int $width, int $height, int $master );
```
//

```php
public function rotate( int $degrees );
```
//

```php
public function save( string $file, int $quality = 100 );
```
//

```php
public function sharpen( int $amount );
```
//

```php
public function text( string $text, int $offsetX, int $offsetY, int $opacity = 100, string $color = 000000, int $size = 12, string $fontfile );
```
//

```php
public function watermark( mixed $watermark, int $offsetX, int $offsetY, int $opacity = 100 );
```
//


        
<h1 id="Image_Adapter_Gd">Class Phalcon\Image\Adapter\Gd</h1>

[Source on GitHub](https://github.com/phalcon/cphalcon/tree/v{{ page.version }}.0/phalcon/image/adapter/gd.zep)

| Namespace  | Phalcon\Image\Adapter |
| Uses       | Phalcon\Image\Adapter\AbstractAdapter, Phalcon\Image\Exception |
| Extends    | AbstractAdapter |

This file is part of the Phalcon Framework.

(c) Phalcon Team <team@phalconphp.com>

For the full copyright and license information, please view the LICENSE.txt
file that was distributed with this source code.


## Properties
```php
//
protected static checked = false;

```

## Methods
```php
public function __construct( string $file, int $width, int $height );
```
//

```php
public function __destruct();
```
//

```php
protected function processBackground( int $r, int $g, int $b, int $opacity );
```
//

```php
protected function processBlur( int $radius );
```
//

```php
protected function processCreate( int $width, int $height );
```
//

```php
protected function processCrop( int $width, int $height, int $offsetX, int $offsetY );
```
//

```php
protected function processFlip( int $direction );
```
//

```php
protected function processMask( mixed $mask );
```
//

```php
protected function processPixelate( int $amount );
```
//

```php
protected function processReflection( int $height, int $opacity, bool $fadeIn );
```
//

```php
protected function processRender( string $ext, int $quality );
```
//

```php
protected function processResize( int $width, int $height );
```
//

```php
protected function processRotate( int $degrees );
```
//

```php
protected function processSave( string $file, int $quality );
```
//

```php
protected function processSharpen( int $amount );
```
//

```php
protected function processText( string $text, int $offsetX, int $offsetY, int $opacity, int $r, int $g, int $b, int $size, string $fontfile );
```
//

```php
protected function processWatermark( mixed $watermark, int $offsetX, int $offsetY, int $opacity );
```
//


        
<h1 id="Image_Adapter_Imagick">Class Phalcon\Image\Adapter\Imagick</h1>

[Source on GitHub](https://github.com/phalcon/cphalcon/tree/v{{ page.version }}.0/phalcon/image/adapter/imagick.zep)

| Namespace  | Phalcon\Image\Adapter |
| Uses       | Phalcon\Image\Adapter\AbstractAdapter, Phalcon\Image\Exception |
| Extends    | AbstractAdapter |

Image manipulation support. Allows images to be resized, cropped, etc.

```php
$image = new \Phalcon\Image\Adapter\Imagick("upload/test.jpg");

$image->resize(200, 200)->rotate(90)->crop(100, 100);

if ($image->save()) {
    echo "success";
}
```


## Properties
```php
//
protected static checked = false;

//
protected static version = 0;

```

## Methods
```php
public function __construct( string $file, int $width, int $height );
```
\Phalcon\Image\Adapter\Imagick constructor


```php
public function __destruct();
```
Destroys the loaded image to free up resources.


```php
public function getInternalImInstance(): \Imagick;
```
Get instance


```php
public function setResourceLimit( int $type, int $limit );
```
Sets the limit for a particular resource in megabytes

@link http://php.net/manual/ru/imagick.constants.php#imagick.constants.resourcetypes


```php
protected function processBackground( int $r, int $g, int $b, int $opacity );
```
Execute a background.


```php
protected function processBlur( int $radius );
```
Blur image

@param int $radius Blur radius


```php
protected function processCrop( int $width, int $height, int $offsetX, int $offsetY );
```
Execute a crop.


```php
protected function processFlip( int $direction );
```
Execute a flip.


```php
protected function processLiquidRescale( int $width, int $height, int $deltaX, int $rigidity );
```
This method scales the images using liquid rescaling method. Only support
Imagick

@param int $width   new width
@param int $height  new height
@param int $deltaX How much the seam can traverse on x-axis. Passing 0 causes the seams to be straight.
@param int $rigidity Introduces a bias for non-straight seams. This parameter is typically 0.


```php
protected function processMask( mixed $image );
```
Composite one image onto another


```php
protected function processPixelate( int $amount );
```
Pixelate image

@param int $amount amount to pixelate


```php
protected function processReflection( int $height, int $opacity, bool $fadeIn );
```
Execute a reflection.


```php
protected function processRender( string $extension, int $quality ): string;
```
Execute a render.


```php
protected function processResize( int $width, int $height );
```
Execute a resize.


```php
protected function processRotate( int $degrees );
```
Execute a rotation.


```php
protected function processSave( string $file, int $quality );
```
Execute a save.


```php
protected function processSharpen( int $amount );
```
Execute a sharpen.


```php
protected function processText( string $text, mixed $offsetX, mixed $offsetY, int $opacity, int $r, int $g, int $b, int $size, string $fontfile );
```
Execute a text


```php
protected function processWatermark( mixed $image, int $offsetX, int $offsetY, int $opacity );
```
Execute a watermarking.



        
<h1 id="Image_Exception">Class Phalcon\Image\Exception</h1>

[Source on GitHub](https://github.com/phalcon/cphalcon/tree/v{{ page.version }}.0/phalcon/image/exception.zep)

| Namespace  | Phalcon\Image |
| Extends    | \Phalcon\Exception |

This file is part of the Phalcon Framework.

(c) Phalcon Team <team@phalconphp.com>

For the full copyright and license information, please view the LICENSE.txt
file that was distributed with this source code.


        
<h1 id="Image_ImageFactory">Class Phalcon\Image\ImageFactory</h1>

[Source on GitHub](https://github.com/phalcon/cphalcon/tree/v{{ page.version }}.0/phalcon/image/imagefactory.zep)

| Namespace  | Phalcon\Image |
| Uses       | Phalcon\Config\Config, Phalcon\Factory\AbstractFactory, Phalcon\Helper\Arr, Phalcon\Image\Adapter\AdapterInterface |
| Extends    | AbstractFactory |

Phalcon\Image/ImageFactory


## Methods
```php
public function __construct( array $services );
```
TagFactory constructor.


```php
public function load( mixed $config ): AdapterInterface;
```
Factory to create an instace from a Config object


```php
public function newInstance( string $name, string $file, int $width, int $height ): AdapterInterface;
```
Creates a new instance


```php
protected function getAdapters(): array;
```
//
