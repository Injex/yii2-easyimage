Image Component for Yii2
========================
Image Component for Yii2

This extension is base on [yii-easyImage](https://github.com/zhdanovartur/yii-easyimage), used for Yii2.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require git407/yii2-easyimage
```

or add

```
"git407/yii2-easyimage": "^1.0"
```

to the require section of your `composer.json` file.


Usage
-----

Once the extension is installed, simply modify your application configuration as follows:

```php
return [
    ...
    'components' => [
        ....
        'easyImage' => [
            'class' => 'cliff363825\image\EasyImage',
            'driver' => 'GD',
            'quality' => 100,
            'cachePath' => '/easyimage/',
            'cacheTime' => 2592000,
            'retinaSupport' => false,
            'basePath' => '@webroot',
            'baseUrl' => '@web',
        ]
    ],
];
```
####Parameters
- string `$file` required - Image file path
- string `$driver` - Driver: `GD`, `Imagick`

### ThumbOf
You can create a thumbnail directly in the `View`:

// Create and autocache
```php
Yii::$app->easyImage->thumbOf('/path/to/image.jpg', ['rotate' => 90]);
```

// or
```php
Yii::$app->easyImage->thumbOf('image.jpg', ['rotate' => 90],  ['class' => 'image']);
```

// or
```php
Yii::$app->easyImage->thumbOf('image.png', [
    'resize' => ['width' => 100, 'height' => 100],
    'rotate' => ['degrees' => 90],
    'sharpen' => 50,
    'background' => '#ffffff',
    'type' => 'jpg',
    'quality' => 60,
  ]);
```
**Note.** This method return [Html::img()](http://www.yiiframework.com/doc-2.0/yii-helpers-basehtml.html)

####Parameters
- string `$file` required - Image file path
- array `$params` - Image manipulation methods. See [Methods](README.md#methods)
- array `$htmlOptions` - options for Html::img()

For full details on usage, see the [documentation](https://github.com/zhdanovartur/yii-easyimage).
