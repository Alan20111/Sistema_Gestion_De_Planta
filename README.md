# Sistema de Gestión de Planta — TreFoods

Aplicación web de **gestión interna para la planta TreFoods**: un panel administrativo con login que permite registrar y consultar **pedidos, exportadores y peticiones** de la planta.

Construido con **CodeIgniter 3** (PHP) y **MySQL**.

## 🖥️ Demo

- **Demo visual** (login + panel, sin backend): ver carpeta [`demo/`](./demo). Muestra la interfaz exportada a HTML estático; los datos y el login **no** funcionan porque dependen del servidor PHP + MySQL.
- **App completa:** requiere hosting con PHP + MySQL. Ver [`DEPLOY.md`](./DEPLOY.md).

## ¿Qué hace?

- **Login de administrador** (`Admin::login`) validado contra la base de datos, con respuesta JSON.
- **Panel/Inicio:** lee y muestra tarjetas de **pedidos**, **exportador** y **peticiones** (`Inicio_model`).
- Operaciones de administración sobre los registros de la planta (`Admin_model`).
- Interfaz responsiva con **Bootstrap 5**.

## 🛠️ Stack

| Capa | Tecnología |
|------|------------|
| Backend | PHP 7+ / **CodeIgniter 3.1.13** (MVC, modelos `Admin_model` e `Inicio_model`) |
| Base de datos | **MySQL** (base `planta`, dump en `system/database/planta.sql`) |
| Frontend | HTML5, CSS3, **Bootstrap 5**, JavaScript (fetch a endpoints JSON) |

## 📁 Estructura (CodeIgniter)

```
application/
  controllers/   Admin.php  (login, inicio, panel, lectura de datos)
  models/        admin_model.php, inicio_model.php
  views/         login.php, inicio.php (panel), admin.php
  config/        config.php (base_url), database.php (conexión MySQL)
public/          bootstrap, css, js, img  (assets)
system/          núcleo de CodeIgniter
  database/planta.sql   ← dump de la base de datos
index.php        front controller
```

## ▶️ Cómo ejecutarlo en local

1. Instala PHP 7+, MySQL y un servidor (XAMPP/Laragon o `php -S`).
2. Crea la base de datos e importa el dump:
   ```bash
   mysql -u root -e "CREATE DATABASE planta;"
   mysql -u root planta < system/database/planta.sql
   ```
3. Configura la conexión en `application/config/database.php`.
4. Ajusta `base_url` en `application/config/config.php`.
5. Levanta el servidor con `php -S localhost:8080` y abre `http://localhost:8080`.

## 👤 Autor

**Alan Daniel Méndez Jiménez** — Ing. en Sistemas Computacionales, TecNM Celaya.
GitHub: [@Alan20111](https://github.com/Alan20111)
