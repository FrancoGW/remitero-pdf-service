# Instrucciones de Despliegue

## Paso 1: Subir a GitHub

1. Crea un nuevo repositorio en GitHub (ej: `remitero-pdf-service`)
2. No inicialices con README, .gitignore, etc.
3. Ejecuta estos comandos:

```bash
cd pdf-service-standalone
git remote add origin https://github.com/TU_USUARIO/remitero-pdf-service.git
git branch -M main
git push -u origin main
```

## Paso 2: Desplegar en Railway

1. Ve a https://railway.app
2. Inicia sesión o crea cuenta
3. Click en "New Project"
4. Selecciona "Deploy from GitHub repo"
5. Autoriza Railway a acceder a tu GitHub
6. Selecciona el repositorio `remitero-pdf-service`
7. Railway detectará automáticamente que es Python
8. Espera a que termine el despliegue (2-3 minutos)
9. Railway te dará una URL como: `https://remitero-pdf-service-production.up.railway.app`
10. **Copia esa URL**, la necesitarás para el frontend

## Paso 3: Verificar que funciona

Abre en tu navegador:
```
https://tu-url-de-railway.app/health
```

Deberías ver:
```json
{"status":"ok","service":"pdf-generator"}
```

## Paso 4: Configurar en el Frontend (Next.js)

1. Ve a tu proyecto en Vercel
2. Settings → Environment Variables
3. Agrega nueva variable:
   - **Name**: `PDF_SERVICE_URL`
   - **Value**: La URL de Railway (ej: `https://remitero-pdf-service-production.up.railway.app`)
4. Guarda
5. Vuelve a desplegar tu app Next.js

¡Listo! Ahora tu frontend usará el servicio Python para generar PDFs.

