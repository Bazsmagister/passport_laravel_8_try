Source:

https://www.itsolutionstuff.com/post/laravel-8-rest-api-with-passport-authentication-tutorialexample.html

composer require laravel/passport

php artisan migrate

php artisan passport:install

php artisan make:resource Product

Using Insomnia
In login and register the Bearer is Bearer \$accessToken

But in the other routes : Bearer is Bearer (and the token is returned)
