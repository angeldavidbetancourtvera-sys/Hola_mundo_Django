# Hola Mundo Django

Proyecto base de Django creado para desarrollar una aplicación sencilla en Python y Django.

## 📌 Descripción

Este proyecto contiene una configuración inicial de Django 6.0.4 con:

- Proyecto principal: `base_project`
- Base de datos: SQLite (`db.sqlite3`)
- Directorio de plantillas: `templates/`
- Aplicación prevista: `pages/`
- Archivo principal de comandos: `manage.py`

El objetivo es servir como punto de partida para crear y extender una aplicación web en Django.

## 🧭 Estructura principal del proyecto

- `manage.py` - comando de administración de Django.
- `base_project/` - proyecto Django principal con configuración, WSGI y ASGI.
  - `settings.py` - configuración del proyecto.
  - `urls.py` - enrutamiento de URLs.
- `pages/` - carpeta de aplicación Django (aún sin una configuración completa en `INSTALLED_APPS`).
- `templates/` - carpeta de plantillas HTML.
- `db.sqlite3` - base de datos SQLite local.
- `requirements.txt` - dependencias del proyecto.
- `.venv/` - entorno virtual local.

## ⚙️ Tecnologías utilizadas

- Python
- Django 6.0.4
- SQLite

## 🚀 Configuración inicial

1. Abrir terminal en la carpeta del proyecto.
2. Activar el entorno virtual (Windows PowerShell):

```powershell
.\.venv\Scripts\Activate.ps1
```

3. Instalar dependencias:

```powershell
pip install -r requirements.txt
```

4. Ejecutar migraciones:

```powershell
python manage.py migrate
```

5. Iniciar servidor de desarrollo:

```powershell
python manage.py runserver
```

6. Abrir en el navegador:

```text
http://127.0.0.1:8000/
```

## 🧪 Comandos útiles

- Crear una nueva aplicación Django:

```powershell
python manage.py startapp pages
```

- Crear migraciones:

```powershell
python manage.py makemigrations
```

- Aplicar migraciones:

```powershell
python manage.py migrate
```

- Crear usuario administrador:

```powershell
python manage.py createsuperuser
```

## 📝 Notas importantes

- `DEBUG` está activo en `base_project/settings.py`, por lo que este proyecto está listo para desarrollo, pero no para producción.
- El archivo `base_project/urls.py` actualmente solo incluye la ruta del panel administrativo (`/admin/`).
- Si deseas activar la aplicación `pages`, agrega `pages` en `INSTALLED_APPS` dentro de `base_project/settings.py` y configura sus URLs.

## 💡 Sugerencias de mejora

- Añadir `pages` a `INSTALLED_APPS` y crear vistas en `pages/views.py`.
- Agregar un archivo `pages/urls.py` y enlazarlo desde `base_project/urls.py`.
- Usar `DIRS` en `TEMPLATES` para apuntar a `templates/` si deseas tener plantillas globales.
- Configurar `STATICFILES_DIRS` y archivos estáticos para CSS/JS.

## 📄 Ejemplo de `urls.py` para `pages`

```python
from django.contrib import admin
from django.urls import path, include

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', include('pages.urls')),
]
```

## 🧾 Licencia

Este proyecto puede ser utilizado como plantilla de aprendizaje o como base para desarrollos posteriores.

---

¡Listo! Ahora tienes un README claro y completo para comenzar a trabajar con tu proyecto Django.