Task9:

make two docker-compose files: (.dev & .prod) with two different databases (mysql & postgres)
docker compose -f docker-compose.yaml -f docker-compose.dev.yaml up
docker compose -f docker-compose.yaml -f docker-compose.dev.yaml down
docker compose -f docker-compose.yaml -f docker-compose.prod.yaml up
