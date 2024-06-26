mvn clean install

docker-compose up -d db-inventory db-orders db-products db-keycloak zookeeper kafka keycloak


# Para api-gateway
cd api-gateway
mvn clean install
mvn spring-boot:run

# Para discovery-server (si es requerido)
cd ../discovery-server
mvn clean install
mvn spring-boot:run

# Para cada uno de los servicios (inventory, orders, products)
cd ../inventory-service
mvn clean install
mvn spring-boot:run

cd ../orders-service
mvn clean install
mvn spring-boot:run

cd ../products-service
mvn clean install
mvn spring-boot:run


https://www.youtube.com/watch?v=HycJwRUipwE&list=PLlYjHWCxjWmAt5hE3OEaemlWkZBZa7w4e&index=3
http://localhost:8080/*
{baseUrl}/login/oauth2/code/keycloak