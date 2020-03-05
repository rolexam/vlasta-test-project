## Test project

Laravel version 7.0

## Setting up the project

1. Clone the repository
1. Run `composer install`
1. Create a database and setup the database configuration inside `.env`
1. Run `php artisan key:generate`
1. Run `php artisan migrate`
1. Run `php artisan jwt:secret`
1. Run `npm install`
1. Use `php artisan tinker` to create a test user:

```
App\User::create(['name' => 'Test User', 'email' => 'test@email.com', 'password' => Hash::make('Password01')])
```

## Build
- Once you have made changes to the JavaScript or SCSS files you will want to run `npm run dev` or `npm run production`

