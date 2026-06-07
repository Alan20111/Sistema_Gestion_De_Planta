# Despliegue — TreFoods (CodeIgniter 3 + MySQL)

Esta aplicación es una **herramienta administrativa con login y base de datos**, por lo que **no se fuerza a Vercel** (Vercel no ejecuta PHP+MySQL nativamente). El frontend depende por completo del backend.

## Opción A — Demo visual (Vercel) ✅

La carpeta [`demo/`](./demo) contiene la interfaz (login + panel) exportada a HTML estático, solo para mostrar el diseño. **No hay funcionalidad real** (login, pedidos y datos requieren el servidor).

## Opción B — App completa en hosting con PHP + MySQL (recomendado)

| Plataforma | Notas |
|------------|-------|
| **Railway** | PHP + MySQL administrado, despliegue desde GitHub. |
| **Render** | Web service PHP + base de datos externa. |
| **InfinityFree** | Hosting PHP/MySQL gratuito (cPanel), ideal para CodeIgniter. |

### Pasos generales

1. Sube el proyecto al hosting (Git o FTP).
2. Crea la base de datos MySQL e **importa** `system/database/planta.sql`.
3. Configura credenciales en `application/config/database.php` (`hostname`, `username`, `password`, `database`).
4. Ajusta `base_url` en `application/config/config.php` a tu dominio.
5. Verifica que el login y los endpoints JSON respondan correctamente.

### ⚠️ Variables / datos que NO deben subirse al repo

- Credenciales reales de la base de datos del hosting.
- Usuarios/contraseñas de administrador de producción.
- Cualquier `.env` con secretos.

> En desarrollo `database.php` usa valores por defecto (`root` / sin contraseña / `planta`). Sustitúyelos en producción **sin** publicarlos.
