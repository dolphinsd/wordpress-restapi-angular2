# Wordpress reastapi Angular (>2)

:fire: **Important!**

:point_right: I'm _rewriting_ this app ground up.

:hourglass_flowing_sand: Previous solution is stored in different branch: [v.1.0](https://github.com/artemdemo/wordpress-restapi-angular2/tree/v.1.0)

## Installation dev environment

I'm using [dockie/lamp](http://github.com/robloach/dockie)

1. Get last image.
    ```
    $ docker pull dockie/lamp
    ```

2. Install container.
    ```
    $ docker run -d -p 8000:80 -p 2200:22 -p 3306:3306 -v $(pwd)/www:/var/www/html:rw dockie/lamp
    ```
    
    Site will be available at http://localhost:8000/

3. Adding `wordpress` bd - http://localhost:8000/phpmyadmin

4. Copy last [wordpress CMS](https://wordpress.org/download/) to `www` folder.

5. Create `wp-config.php`.
    For development environment settings will be:
    ```php
    define('DB_NAME', 'wordpress');
    define('DB_USER', 'root');
    define('DB_PASSWORD', 'root');
    define('DB_HOST', 'localhost');
    define('DB_CHARSET', 'utf8');
    define('DB_COLLATE', '');
    ```

6. Build js and css
    ```
    $ npm run build
    ```
    
7. Activate theme.

8. Install plugins (message will appear in dashboard after theme will be active).

9. Activate [permalinks](http://localhost:8000/wp-admin/options-permalink.php) of type "Post name".
   
Now you should be able to use rest-api, for example to get all posts use link: http://localhost:8000/wp-json/wp/v2/posts

[Documentation for wp rest api](https://developer.wordpress.org/rest-api/using-the-rest-api/discovery/)


**CMS**

* [Wordpess](https://wordpress.org/download/) code tested for version 4.7.3
* [TGM Plugin Activation](https://github.com/TGMPA/TGM-Plugin-Activation) 2.6.1 (included in theme)
* [Rest API Plugin](https://wordpress.org/plugins/rest-api/) 2.0-beta15 (included in theme)

**Backend stack**

* [Dockie](../dockie)
* [Apache](https://httpd.apache.org/) 2.4.7
* [PHP](http://php.net/) 5.5.9
* [MySQL](http://www.mysql.com/) 5.5.37
* [phpMyAdmin](http://www.phpmyadmin.net/) 4.0.10
* [Composer](http://getcomposer.org) 1.0.0-alpha8
  
**MySQL**

Connect on `localhost:3306`, user `root`, password `root`.

### Useful links

https://github.com/preboot/angular-webpack
