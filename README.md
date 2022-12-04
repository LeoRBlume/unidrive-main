# Unidrive

    Para baixar este repositório com os submodulos, usar o comando abaixo:
- `git clone --recurse-submodules https://github.com/weslleyrichardc/unidrive.git`

---

## Desenvolvimento ([Docker Compose](./docker-compose.dev.yml))
1. Subir Banco de Dados e Backend
    - `docker compose -f docker-compose.dev.yml up -d` para subir o MySQL (localhost:3306) e o [Spring Boot](http://localhost:8080/swagger-ui.html) pelo docker
2. Dentro da pasta do [Laravel](./unidrive-laravel/) rodar os comandos
    - Executar o Laravel 
        - `php artisan serve` para subir o [Laravel](http://localhost:8000) 
        - `sudo php artisan serve --port=80` para subir o [Laravel](http://localhost)
    - Executar o Vite (gera os arquivos css e atualiza a página ao salvar)
        - `npm run dev` para subir o Vite (localhost:5173)
            - Compila as mudanças feitas ao salvar e adiciona as classes css usadas pelo tailwind
        - `npm run build` para compilar o mudanças de css e otimizações para produção
---
## Teste - Com banco de dados local ([Docker Compose](./docker-compose.test.yml))
- `docker compose -f docker-compose.test.yml up -d` para subir o MySQL (localhost:3306), [Spring Boot](http://localhost:8080/swagger-ui.html) e o [Laravel](http://localhost) pelo docker
---
## Teste - Com banco de dados externo ([Docker Compose](./docker-compose.prod.yml))
- Verificar arquivos se estão com as credenciais de produção
    - [.env](./unidrive-laravel/.env)
        - `DB_HOST`
        - `DB_PORT`
        - `DB_DATABASE`
        - `DB_USERNAME`
        - `DB_PASSWORD`
    - [application.properties](./unidrive-spring-boot/src/main/resources/application.properties)
        - `spring.datasource.url`
- `docker compose -f docker-compose.prod.yml up -d` para subir o MySQL (localhost:3306), [Spring Boot](http://localhost:8080/swagger-ui.html) e o [Laravel](http://localhost) pelo docker