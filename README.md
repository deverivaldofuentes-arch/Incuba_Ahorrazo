# 🛒 Ahorrazo - Plataforma Backend (Laravel 10 + PostgreSQL + Docker)

Proyecto **Ahorrazo** basado en **Laravel 10**, totalmente dockerizado y listo para trabajar con **PostgreSQL**.

---

## 📋 Requisitos Previos

Para ejecutar este proyecto en cualquier sistema operativo (Linux, macOS o Windows):

1. **Docker** y **Docker Compose** (instalados a través de Docker Desktop para Windows/macOS o Docker Engine en Linux).
2. **Git**.

> 💡 **Nota:** No se requiere instalar PHP, Composer ni PostgreSQL en tu máquina local. Todos los servicios se ejecutan dentro de los contenedores Docker.

---

## 🚀 Cómo Ejecutar el Proyecto

### 1. Clonar el repositorio e iniciar los servicios

```bash
# 1. Clonar el proyecto (si aún no lo has hecho)
git clone https://github.com/deverivaldofuentes-arch/Incuba_Ahorrazo.git
cd Ahorrazo

# 2. Copiar el archivo de variables de entorno
cp .env.example .env

# 3. Construir e iniciar los contenedores en segundo plano
docker compose up -d --build

# 4. Generar la clave de la aplicación Laravel
docker compose exec app php artisan key:generate

# 5. Ejecutar las migraciones de la base de datos
docker compose exec app php artisan migrate
```

### 2. Abrir la Aplicación

Abre tu navegador web e ingresa a:

👉 **[http://localhost:8000](http://localhost:8000)**

---

## 🛠️ Comandos de Uso Diario

| Acción | Comando |
|---|---|
| **Iniciar servicios** | `docker compose up -d` |
| **Detener servicios** | `docker compose down` |
| **Reconstruir contenedores** | `docker compose up -d --build` |
| **Ver estado de contenedores** | `docker compose ps` |
| **Ver logs en tiempo real** | `docker compose logs -f` |
| **Ejecutar comandos Artisan** | `docker compose exec app php artisan <comando>` |
| **Ejecutar comandos Composer** | `docker compose exec app composer <comando>` |
| **Acceder a la consola PostgreSQL** | `docker compose exec db psql -U ahorrazo -d ahorrazo` |
| **Acceder al bash del contenedor App** | `docker compose exec app bash` |

---

## 🗄️ Persistencia de Datos

La base de datos PostgreSQL utiliza el volumen Docker persistente: `ahorrazo_postgres_data`.  
Ejecutar `docker compose down` detiene los servicios **sin borrar** tus datos.
