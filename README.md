# Navano
This is the readme file for Navano test and main servers.

## Composer
After project pull into server we should run composer update.

* there should be warnings in the composer update process. as project use lots of depricated package this is normal.

## Database
As there is some required data in db and there is no seeder for them and in the other hand producing seeder for these will require more time and we can't handle it without the project owner's request then we should execute the main DB into server.

* This process will be done just one time at the beginning.

## .env file
Copy the .env.example file into a new .env file and fix the database related fields in the .env file and in the end run "php artisan key:generate" command.

## Copy migrations
Delete the migrations table from the database and execute the new migrations into DB.

* This process will be done just one time at the beginning.

## Migrate
Run php artisan migrate command after each commit. this will be needed for CI/CD.

## Storage
Make sure the "storage/app/public" and "bootstrap/cache" directories has read/right access. after that link the storage with "php artisan storage:link" command.

After this make sure the created shortcut for storage inside public path has read and right access to the project and at the end move the storage data from old server into new server in the "storage/app/public" path.

* This process will be done just one time at the beginning.

## Ready the project
Run "php artisan db:seed --class=PriorityTable" .

* This process will be done just one time at the beginning.
