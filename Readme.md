# Installation Step

1. Extract zip file
2. Open terminal and go to project directory
3. build docker `docker-compose up -d --build`
4. Login into php container `docker-compose exec php /bin/bash`
5. Run Migration `php bin/console doctrine:migration:migrate -n`
6. Run Fixture `php bin/console doctrine:fixture:load -n`
    * user below credentials to login in to system
        * `admin // admin_1234`
        * `moderator // moderator_1234`
7. use command inside php container to get the latest news `php bin/console app:sync-news` it will add that in rabbitMq
8. You can run on browser via [http://localhost:8080](http://localhost:8080)
9. You can run command `php bin/console messenger:consume async -vv` to execute all rabbitMq process 
