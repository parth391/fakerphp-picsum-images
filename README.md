# Fakerphp Picsum Images

[![Latest Version on Packagist](https://img.shields.io/packagist/v/smknstd/fakerphp-picsum-images.svg?style=flat-square)](https://packagist.org/packages/smknstd/fakerphp-picsum-images)
[![GitHub Tests Action Status](https://img.shields.io/github/actions/workflow/status/smknstd/fakerphp-picsum-images/run-tests.yml?branch=main)](https://github.com/smknstd/fakerphp-picsum-images/actions?query=workflow%3ATests+branch%3Amain)
[![Total Downloads](https://img.shields.io/packagist/dt/smknstd/fakerphp-picsum-images.svg?style=flat-square)](https://packagist.org/packages/smknstd/fakerphp-picsum-images)

## Introduction

Alternative image provider for [fakerphp](https://github.com/fakerphp/faker) using [picsum.photos](https://picsum.photos)

_This package has been forked from [mmo/faker-images](https://github.com/morawskim/faker-images) for [fzaninotto/faker](https://github.com/fzaninotto/Faker) (deprecated [~ Oct 2020](https://marmelab.com/blog/2020/10/21/sunsetting-faker.html))._
 
## Ressources

- [Tutorial for laravel](https://smknstd.medium.com/fake-beautiful-images-in-laravel-51062967d1db)
 
## Installation

You can install the package via composer in dev dependency section:

```bash
composer require --dev smknstd/fakerphp-picsum-images
```

## Usage

```php
$faker = \Faker\Factory::create();
$faker->addProvider(new \Smknstd\FakerPicsumImages\FakerPicsumImagesProvider($faker));

// return a string that contains a url like 'https://picsum.photos/800/600/'
$faker->imageUrl(width: 800, height: 600); 

// return a string that contains a url which returns the same random image based on the provided seed
$filePath= $faker->image(width: 800, height: 800, seed: 'useremail@example.com');

// download a properly sized image from picsum into a file with a file path like '/tmp/13b73edae8443990be1aa8f1a483bc27.jpg'
$filePath= $faker->image(dir: '/tmp', width: 640, height: 480);
```

Also, there are some more options :
- alternative webp format
- effects (grayscale, blurry)
- seeding ensures you can get the same photo each time by providing a seed string
- returning a specific photo based on an id instead of a random one (ex: https://picsum.photos/id/1/800/600)

## Testing

```bash
composer test
```

## Contributing

Please see [CONTRIBUTING](.github/CONTRIBUTING.md) for details.

## Security Vulnerabilities

Please review [our security policy](../../security/policy) on how to report security vulnerabilities.

## Credits

- [Arnaud Becher](https://github.com/smknstd)
- [Marcin Morawski ](https://github.com/morawskim)

## License

The MIT License (MIT). Please see [License File](LICENSE.md) for more information.
