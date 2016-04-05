Symfony 3 Wishlist Microservice 
===============================

Wishlist microservice based on symfony and the [wishlist php component](https://github.com/soerenmartius/Wishlist)

Run it with docker
------------------


Install it manually
-------------------

1. clone the repository ```
                        git clone git@github.com:soerenmartius/WishlistSymfonyMicroservice.git
                        ```
2. install dependencies ( during the install it will ask you for database credentials. It uses mysql by standart but you can switch to mongo easily )
                        ```
                        composer install
                        ```
3. initalise database and schema
                        ```
                        php bin/console doctrine:database:create && php bin/console doctrine:schema:create
                        ´´´
4. launch the server
                        ```
                        php bin/console server:run
                        ´´´
5. the service is now available at [http://127.0.0.1:8000/wishlist](http://127.0.0.1:8000)
