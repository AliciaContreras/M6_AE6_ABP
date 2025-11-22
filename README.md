# 🐾 Plataforma de Gestión de Productos para Mascotas

Este proyecto es una implementación de un sistema administrativo seguro utilizando Django Admin. El objetivo principal es gestionar el inventario de una tienda de mascotas implementando una estricta política de control de acceso basada en roles (RBAC).

## 📋 Funcionalidades

*   **Gestión de Inventario:** Modelo de datos para productos con precio, stock y descripción.
*   **Panel Administrativo Personalizado:** Listados filtrables y búsqueda de productos.
*   **Control de Acceso:**
    *   Restricción de acceso solo a usuarios autenticados y con estatus de *Staff*.
    *   Manejo de errores de autenticación y permisos (403 Forbidden).
*   **Sistema de Roles (Grupos):**
    *   **Administradores:** Control total (CRUD).
    *   **Gestores de Productos:** Permiso para Crear, Leer y Actualizar, pero **sin permiso de Eliminar**.

## 🛠️ Tecnologías

*   Python 3
*   Django 5
*   SQLite

## 🚀 Puesta en Marcha

1.  **Clonar/Descargar el proyecto.**
2.  **Crear entorno virtual:** `python -m venv venv`
3.  **Instalar dependencias:** `pip install -r requirements.txt`
4.  **Migrar base de datos:** `python manage.py migrate`
5.  **Crear Superusuario:** `python manage.py createsuperuser`
6.  **Iniciar Servidor:** `python manage.py runserver`
7.  **Acceder:** [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)

## 👥 Configuración de Pruebas

Para verificar la seguridad, el sistema está diseñado para estos roles:

*   **Usuario Admin (Superuser):** Acceso total.
*   **Usuario Gestor (Staff):** Pertenece al grupo "Gestores de Productos". Puede editar precios y stock, pero no verá el botón "Eliminar".

## 📂 Estructura

*   `tienda_mascotas/`: Configuración del proyecto.
*   `productos/`: Aplicación principal.
    *   `models.py`: Definición del modelo `Producto`.
    *   `admin.py`: Registro y personalización del panel de control.