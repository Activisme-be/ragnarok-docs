# Installing Ragnarok boilerplate 

You can install The ragnarok boilerplate easily with the following steps
that are carefully documented below. 

## 1. Download 

You can download a copy of ragnarok on github and place it on your local development server. 
Alternatively you can also use `git clone` or the composer package manager. By example: 

```bash 
# Git clone 
$ git clone https://github.com/Activisme-be/Ragnarok

# Composer package manager 
$ composerr create-project --prefer-dist actb/ragnarok <YOUR DIRECTORY>
```

## 2. Environment configuration 

Ragnarok is shipped with an `.env.example` environment configuration file in the root directory of 
the application. this file needs to be renamed or copied to an file with the following name: `.env`

**NOTE:** Make sure that the .env file is hidden on your production server and only the server itself 
can read the file. 

## 3. Composer dependencies

The Ragnarok boilerplate uses composer as package manager. The first step for starting developing your application 
is to install the dependencies. You can do that it by opening your terminal and executing the following command in
the root directory of your application. 

```
$ composer install
```

## 4. NPM / Yarn 

For the frontend development Ragnarok uses Npm or Yarn, it is required to install the Node package manager on your 
local development machine. Or the Yarn package but that is optional. 

If you have only installed the npm package manager you can use the following command in the root directory of
your project to install the npm dependencies: 

```
$ npm install
```

Or if you have installed the yarn package manager u can use the following command: 

```
$ yarn
```

## 5. Create a database 

It is required to create a database on your server and to configure in your `.env` file. Edit the following environment
keys to configure successfully your database connection.

```
DB_CONNECTION=mysql 
DB_HOST=127.0.0.1
DB_DATABASE=laravel 
DB_USERNAME=root 
DB_PASSWORD=secret
```

## 6. Artisan commands (application key, database generation / seeding)

### Key generation

Raganarok is using the application key from the Laravel framework this key doesn't come with the framework or boilerplate. 
by default because this key is used your the internal encryption such as session, recovery codes for 2FA etc. 
 
You can generate an application key by executing the following command in the root of your application. 

```
$ php artisan key:generate
```

If everything went ok. you see a message in your terminal with a green background, and the application key. 
Also the value from `APP_KEY=` in your environment file should be filled in the the generated application key. 

### Database generation 

Ragnarok comes with a default database scheme and default data such as default logins. you can execute the following
commands in the root directory of your project.

```
# Import the database scheme (required)
$ php artisan migrate

# Import the default data (optional) 
$ php artisan db:seed 

# Import the scheme and default data (optional)
$ php artisan migrate --seed
```

## 7. PHPUnit 

After you performed all the steps above you can check if your application works perfectly at the start. You can 
simply do it by navigating to the root directory of your application, and execute the `composer test` command. 

If everything went good you should see no errors, and you are ready to go. 

## 8. Storage:link (optional)

Now that the Ragnarok boilerplate is successfully installed we recommend performing the command `php artisan storage:link`
if you are going to use the filesystem in the application. It links the public storage to the storage destination in your backend. 


## 9. Default logins 

After you installed Ragnarok boilerplate and imported the default database layout and data. You can fire up your local development
server and authenticate on your boilerplate with the following default user logins.

| Email                     | Password            | Access level                                       | 
| :------------------------ | :------------------ | :------------------------------------------------- |
| webmaster@domain.tld      | **password**        | Has access to the application and management kiosk |
| developer@domain.tld      | **password**        | Has access to the application and management kiosk |
| user@domain.tld           | **password**        | Has only access to the application                 |

## 10. What's next? 

At this moment there are no further installation steps. The only thing that you can do is navigation trough 
the boilerplate documentation. To get a good overview what does what and what u already can do in the
Ragnarok boilerplate.

