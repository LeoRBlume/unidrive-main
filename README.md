# Unidrive

## Desenvolvimento (todas as alterações no front são atualizadas ao salvar pelo artisan)
- docker-compose.yml
    - Comentar o serviço do laravel
- unidrive-laravel/.env
    - DB_HOST=127.0.0.1
- `docker compose up` para subir o MySQL(localhost:3306) e a Spring Boot(localhost:8080) pelo docker
- Rodar o comando estando na pasta unidrive-laravel
    - `php php artisan serve` para subir o Laravel(localhost:80)

## Teste (qualquer alteração no front deve restartar o 'docker compose' para ver o efeito)
- docker-compose.yml
    - Descomentar o serviço do laravel
- unidrive-laravel/.env
    - DB_HOST=spring
- `docker compose up` para subir o MySQL(localhost:3306), Spring Boot(localhost:8080) e o Laravel(localhost:80) pelo docker