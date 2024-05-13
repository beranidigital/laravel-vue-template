# Setup

## Prerequisite

1. Git, Web Server, MySQL, PHP 8.2, Composer, NodeJS 16+

 ```bash
sudo apt install -y apache2 git mariadb-server unzip
apt -y install php8.2 php8.2-{cli,gd,mysql,pdo,mbstring,tokenizer,bcmath,xml,fpm,curl,zip,intl} 
# Install composer
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer 
```

[If you're Windows users click here <--](docs/Setup.md)

```mysql
# Create database
CREATE DATABASE berani_system_architect_web;
# Create user
CREATE USER 'berani_system_architect_web'@'localhost' IDENTIFIED BY 'berani_system_architect_web_passwd';
GRANT ALL PRIVILEGES ON berani_system_architect_web.* TO 'berani_auth_web'@'localhost';
FLUSH PRIVILEGES;
```

## Step

1. `git clone https://github.com/beranidigital/berani-system-architect-web`
    1. Add `-b <branch>` to clone specific branch
2. `cd berani-system-architect-web`
3. `composer install`
4. `cp .env.example .env`
5. Set up the env
6. `php artisan key:generate`
7. `php artisan migrate --seed`
8. `npm install && npm run build`
    1. `npm run dev` for development
9. `php artisan storage:link` to link storage and FilePond to work
