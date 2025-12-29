# Servicio de Generación de PDFs - Standalone

Servicio independiente para generar PDFs de remitos usando Python y ReportLab.

## Características

- ✅ Funciona perfectamente en entornos serverless
- ✅ No tiene problemas con fuentes (ReportLab las incluye)
- ✅ API REST simple con FastAPI
- ✅ Listo para desplegar en Railway, Render, Fly.io, etc.

## Instalación Local

```bash
pip install -r requirements.txt
```

## Ejecutar Localmente

```bash
python main.py
```

O con uvicorn:

```bash
uvicorn main:app --reload --port 8000
```

## API

### POST /generate

Genera un PDF del remito.

**Request Body**: JSON con los datos del remito (ver estructura en `main.py`)

**Response**: PDF binario con Content-Type: `application/pdf`

### GET /health

Verifica que el servicio esté funcionando.

**Response**: 
```json
{
  "status": "ok",
  "service": "pdf-generator"
}
```

## Despliegue en Railway

1. Crea un nuevo repositorio en GitHub con este código
2. En Railway: New Project → Deploy from GitHub repo
3. Selecciona este repositorio
4. Railway detectará automáticamente que es Python
5. Obtendrás una URL como: `https://tu-proyecto.railway.app`
6. Configura esa URL en tu app Next.js como variable de entorno:
   ```
   PDF_SERVICE_URL=https://tu-proyecto.railway.app
   ```

## Variables de Entorno (Opcional)

El servicio tiene valores por defecto, pero puedes configurar:

- `EMPRESA_NOMBRE`
- `EMPRESA_DIRECCION`
- `EMPRESA_LOCALIDAD`
- `EMPRESA_CUIT`
- `EMPRESA_INGRESOS_BRUTOS`
- `EMPRESA_FECHA_INICIO`
- `EMPRESA_CONDICION_IVA`
- `EMPRESA_CODIGO`
