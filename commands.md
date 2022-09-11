``` powershell
docker run --name keycloak_test -p 8080:8080 -e KEYCLOAK_ADMIN=admin -e KEYCLOAK_ADMIN_PASSWORD=admin docker.io/bitnami/keycloak:latest start-dev
``` 