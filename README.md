# n8n con Persistencia y Credenciales Seguras

Este proyecto ejecuta n8n en Docker con persistencia y **sin exponer credenciales en GitHub**.

## 🚀 Ejecución Local

1. Copiar el archivo `.env.example` a `.env` y editar credenciales:
   ```bash
   cp .env.example .env
   nano .env
   ```

2. Levantar el contenedor:
   ```bash
   docker compose up -d
   ```

3. Abrir en el navegador:
   ```
   http://localhost:5678
   ```

## ☁️ Ejecución en AWS Lightsail

1. Crear una instancia con Docker preinstalado.
2. Subir este repositorio.
3. Configurar variables de entorno en Lightsail:
   ```bash
   export N8N_BASIC_AUTH_USER=admin
   export N8N_BASIC_AUTH_PASSWORD=contraseña_segura
   export N8N_PORT=5678
   ```
4. Ejecutar:
   ```bash
   docker compose up -d
   ```

## 🔒 Seguridad

- **Nunca** subas `.env` a GitHub (ya está en `.gitignore`).
- En producción, usa AWS Secrets Manager o variables de entorno configuradas en el servicio.

