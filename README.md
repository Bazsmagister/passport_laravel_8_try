Source:

https://www.itsolutionstuff.com/post/laravel-8-rest-api-with-passport-authentication-tutorialexample.html

https://laravel.com/docs/8.x/passport#introduction

composer require laravel/passport

php artisan migrate

php artisan passport:install

This command will create the encryption keys needed to generate secure access tokens. In addition, the command will create "personal access" and "password grant" clients which will be used to generate access tokens

We have to configuration on three place

in User Model -> use HasApiTokens,

AuthServiceProvider : -> Passport::routes();

and config/auth.php file -> 'driver' => 'passport',

php artisan make:resource Product

Using Insomnia
In login and register the Bearer is Bearer \$accessToken

But in the other routes : Bearer is Bearer (and the token is returned).

About passport:

Laravel makes API authentication a breeze using Laravel Passport, which provides a full OAuth2 server implementation for your Laravel application in a matter of minutes.

terminology:

https://oauth2.thephpleague.com/terminology/

we can publish files:

php artisan vendor:publish --tag=passport-config

If you would like your client's secrets to be hashed when stored in your database, you should call the Passport::hashClientSecrets method in the boot method of your AppServiceProvider:

Passport::hashClientSecrets();

Once enabled, all of your client secrets will only be shown one time when your client is created. Since the plain-text client secret value is never stored in the database, it is not possible to recover if lost.

php artisan passport:client

php artisan vendor:publish --tag=passport-views

php artisan vendor:publish --tag=passport-config

php artisan vendor:publish --tag=passport-migrations.

Typically, if you want to consume your API from your JavaScript application, you would need to manually send an access token to the application and pass it with each request to your application. However, Passport includes a middleware that can handle this for you. All you need to do is add the CreateFreshApiToken middleware to your web middleware group in your app/Http/Kernel.php file:

'web' => [
// Other middleware...
\Laravel\Passport\Http\Middleware\CreateFreshApiToken::class,
],
