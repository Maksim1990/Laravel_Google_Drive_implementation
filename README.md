# Implamentation of Google Drive API into Laravel application


## Install this application locally

```
git clone https://github.com/Maksim1990/Laravel_Google_Drive_implementation.git
composer install
```

### Package that is used for implamantation Google Drive API:

```
"nao-pon/flysystem-google-drive": "~1.1"
```

Added [GoogleDriveServiceProvider](app/Providers/GoogleDriveServiceProvider.php) that is located in `Providers` folder.
Also in [`config/app.php`](config/app.php) register new provider in`providers` array
In [`config/filesystems.php`](config/filesystems.php) add a `google` disk as below:

```php
'disks' => [

    // ...

    'google' => [
        'driver' => 'google',
        'clientId' => env('GOOGLE_DRIVE_CLIENT_ID'),
        'clientSecret' => env('GOOGLE_DRIVE_CLIENT_SECRET'),
        'refreshToken' => env('GOOGLE_DRIVE_REFRESH_TOKEN'),
        'folderId' => env('GOOGLE_DRIVE_FOLDER_ID'),
    ],

    // ...

],
```

## Create your Google Drive API keys

Detailed information on how to obtain your API ID, secret and refresh token:

-   [Getting your Client ID and Secret](README/1-getting-your-dlient-id-and-secret.md)
-   [Getting your Refresh Token](README/2-getting-your-refresh-token.md)
-   [Getting your Root Folder ID](README/3-getting-your-root-folder-id.md)

## Add Google Drive credentials to `.env` file

Fill in below lines with appropriate information and add it at the end of `.env` file.

```
FILESYSTEM_CLOUD=google
GOOGLE_DRIVE_CLIENT_ID=xxx.apps.googleusercontent.com
GOOGLE_DRIVE_CLIENT_SECRET=xxx
GOOGLE_DRIVE_REFRESH_TOKEN=xxx
GOOGLE_DRIVE_FOLDER_ID=null
```

Go to [`routes/web.php`] file and try to use routes for testing application.
