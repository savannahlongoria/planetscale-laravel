# Build a CRUD Web Application From Scratch Using Laravel & PlanetScale
## Prerequisites:
* Beginner Laravel knowledge
* [PHP](https://www.php.net/manual/en/install.php) — This tutorial uses v7.4~
* [Composer](https://getcomposer.org/) 
* [npm](https://www.npmjs.com/)
* A Free [PlanetScale account](https://auth.planetscale.com/sign-up)

## Creating a Laravel Project
Go to your terminal and run the following command to build a Laravel project. 

*  `composer create-project laravel/laravel --prefer-dist laravel-planetscale-app`
* `cd laravel-planetscale-app`

## PlanetScale Setup 
Before you dive into the code, let's get your database set up. Head over to PlanetScale to [sign up for an account](https://planetscale.com/sign-up) if you haven't already.

* Once you create an account you will be prompted to create a new database:
Give it a name, select the region closest to you or your application, and click "Create database"

> Your database comes with one default branch, `main`. This branch is designated as a development branch to start, with the goal to move it to production after you make any necessary schema changes. Promote the `main` branch to production now, and then create a new branch, `dev`, for development. 

### Connect your database
You can connect your development database to your Laravel application in one of two ways: using the PlanetScale proxy or with a username and password. This tutorial will show you how to connect with a username and password, but you can use either option.

### Connect with username and password:
1. Back in your PlanetScale dashboard, click on the "Branches" tab of your database and select `dev`
2. Click the "Connect" button
3. Click "New password"
4. Select "Laravel" from the dropdown that's currently set to "General" - Make sure to copy the full set of credentials. You won't be able to see the password again when you leave the page. You can always generate a new one if you do forget to store it.

You should see something like this: 
```DB_CONNECTION=mysql
DB_HOST=xxxxxxxxxx.us-east-3.psdb.cloud
DB_PORT=3306
DB_DATABASE=laravel-mood-tracker
DB_USERNAME=xxxxxxxxxxx
DB_PASSWORD=pscale_pw_xxxxxx-xx-xxxxxxxxxxxxxxxxxxxxxxxx
MYSQL_ATTR_SSL_CA=/etc/ssl/cert.pem
```

### In your local `laravel-planetscale-app` directory 

`nano` (MacOS) into .env & .env_example
Open the .env file and above and replace the `DB` section with the PlanetScale/Laravel code snippet from the step above. 

## Setting Up Migration and Model
We have created the database and configured the database by adding the credentials in the `.env` file. Now, we will set the migration by adding the data properties in the MySQL table. 
* To create a Model and Migration file to create the migrations, run the following command `php artisan make:model Student -m`
