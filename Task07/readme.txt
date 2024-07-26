Task7:

connect the spring petclinic with mysql database
-create the network:
  docker network create -d bridge pett-network
-create and run the mysql container:
  docker run -d -p 3306:3306 -e MYSQL_ALLOW_EMPTY_PASSWORD=true -e MYSQL_USER=petclinic -e MYSQL_PASSWORD=petclinic -e MYSQL_DATABASE=petclinic --network pett-network --volume pettvolume:/var/lib/mysql --name pett-mysql-manual mysql
-create and run the petclinic app container of an image(pett) built using the Dockerfile:
  docker run -d -p 8080:8080 -e SPRING_PROFILES_ACTIVE=mysql -e MYSQL_URL=jdbc:mysql://pett-mysql-manual:3306/petclinic --network pett-network --name pett-app-manual pett
