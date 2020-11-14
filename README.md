# Nikzee
This is the readme file for Nikzee test and main servers.

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
* For test server we do not need moving data from old server into storage.

## FFMPEG
<a href="https://ffmpeg.org/download.html">
Install the ffmpeg package in the server.
</a>

After this copy the bin directory of ffmpeg and ffprobe into .env file at the end of file inside related places. Make sure the project has access into these directories.

* This process will be done just one time at the beginning.

## Handler
There is two files in "app/Exceptions" directory. First copy Handler.nikzee.php file into a new Handler.php file.

After that create a variable inside git with name "Handler". We need when this changed into "nikzee" then we need pipleline copy Handler.nikzee.php into Handler.php file. But if this change to "default" then Handler.default.php should be copied into Handler.php .
