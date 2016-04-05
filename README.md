Symfony 3 Wishlist Microservice 
===============================

Wishlist microservice based on symfony and the [wishlist php component](https://github.com/soerenmartius/Wishlist)

Launch a new instance of the microservice with docker 
-----------------------------------------------------

Requirements
------------

- [PHP 7](http://php-osx.liip.ch/)
- [MYSQL Community Server 5.7](https://dev.mysql.com/downloads/mysql/5.6.html) or [MongoDB 3.2](https://www.mongodb.org/)


Spawn a new instance of the microservice using docker-compose ( the cool way )
------------------------------------------------------------------------------
1. [Install docker](https://docs.docker.com/engine/installation/)

2. [Install docker compose](https://docs.docker.com/compose/install/) on OSX you don't need to install it as it comes with dockers default installation

3. Checkout the repository and switch to the docker-compose branch
    ```
    git clone git@github.com:soerenmartius/WishlistSymfonyMicroservice.git && cd WishlistSymfonyMicroservice && git checkout docker-compose
    ```
    
4. Start the machines
    ```
    docker-compose up
    ```
   docker-compose will now launch two containers for you. One webserver and one database. The containers are linked together to the webserver has access to the database.
   
5. Setup db
    ```
    php bin/console doctrine:database:create --if-not-exists && php bin/console doctrine:schema:update --force 
    ```
            
6. The service will be now available at [http://192.168.99.100:8081/wishlist](http://192.168.99.100:8081/wishlist) ( the ip might be different depending on your docker config )



Spawn a new instance of the microservice as a docker container ( the quick way )
-------------------------------------------------------------------------------

1. [Install docker](https://docs.docker.com/engine/installation/)
2. Launch a container ```
                        docker run soerenmartius/wishlist -p 8080:80
                      ```
3. the services is now available at [http://yourdockerhostmachineiphere:8080/wishlist](http://yourdockerhostmachineiphere:8080/wishlist)

Manual installation
-------------------

1. clone the repository
    ```
    git clone git@github.com:soerenmartius/WishlistSymfonyMicroservice.git
    ```
    
2. install dependencies ( during the install it will ask you for database credentials. It uses mysql by standart but you can switch to mongo easily )
    ```
    composer install
    ```
    
3. initalise database and schema
    ```
    php bin/console doctrine:database:create && php bin/console doctrine:schema:create
    ```
    
4. launch the server
    ```
    php bin/console server:run
    ```
    
5. the service is now available at [http://127.0.0.1:8000/wishlist](http://127.0.0.1:8000)
