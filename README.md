# Smartarget Whatsapp - contact Us for Bagisto
![Packagist Downloads](https://img.shields.io/packagist/dt/smartarget/bagisto-whatsapp-contact-us) ![Packagist License](https://img.shields.io/packagist/l/smartarget/bagisto-whatsapp-contact-us)

This extension integrates [https://smartarget.online/demo.html?ref=bagisto-composer&app=whatsapp](Smartarget Whatsapp - Contact Us) plugin.

## Requirements
- [Bagisto](https://github.com/bagisto/bagisto)

## Installation

### Install with composer

Require this package with Composer

	composer require smartarget/bagisto-whatsapp-contact-us

Add the ServiceProvider to the providers array in **config/app.php**

```php
Smartarget\WhatsappContactUs\Providers\WhatsappContactUsServiceProvider::class
```

Run below commands before publishing assets to the public folder:
```
composer dump-autoload
php artisan optimize:clear
php artisan storage:link
```

Run below command to publish config and additional assets files to make it compatible with Bagisto backend theme

	php artisan vendor:publish --provider='Smartarget\WhatsappContactUs\Providers\WhatsappContactUsServiceProvider'

In your config/elfinder.php, you can change the default folder, the access callback or define your own roots.
Rest of the configuration details are mentioned in [barryvdh/laravel-elfinder](https://github.com/barryvdh/laravel-elfinder) media manager.

### Install with package folder
1. Unzip all the files to **packages/Ridhima/MediaManager**.
2. Run composer command to download the required package
```
composer require barryvdh/laravel-elfinder:^0.4.6
```
3. Goto composer.json file inside the Bagisto root directory then add the following line under 'psr-4'
```
"Ridhima\\MediaManager\\": "packages/Ridhima/MediaManager/src"
```
4. Goto **config/app.php** file then add the following line under 'webkul packages'
```
Ridhima\MediaManager\Providers\MediaManagerServiceProvider::class
```
5. Run below commands before publishing assets to the public folder:
```
composer dump-autoload
php artisan config:clear
php artisan cache:clear
php artisan storage:link
```
6. Run below artisan command to download the required assets files to the public folder:
```
php artisan mediamanager:publish
```
7. After that run below command to publish config and additional assets files to make it compatible with Bagisto backend theme
```
php artisan vendor:publish --provider='Ridhima\MediaManager\Providers\MediaManagerServiceProvider'
```
8. Add below lines of code in **config\filesystems.php** to add a new disk.
```
'mediamanager' => [
    'driver' => 'local',
    'root'   => storage_path('app/public/media'),
]
```
Now you can manage the static media files from the dedicated section as well as from the editor.
