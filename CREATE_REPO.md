# Crear Repositorio en GitHub

## Opción 1: Usando GitHub CLI (más rápido)

Si tienes GitHub CLI instalado, ejecuta:

```bash
cd "/Users/francolautarogaray/Documents/Desarrollos /Forestal Argentina/Remitero/pdf-service-standalone"
gh repo create remitero-pdf-service --public --source=. --remote=origin --push
```

## Opción 2: Manual (paso a paso)

### Paso 1: Crear repo en GitHub
1. Ve a https://github.com/new
2. Repository name: `remitero-pdf-service`
3. Description: `Servicio para generar PDFs de remitos`
4. Elige Public o Private
5. **NO** marques "Add a README file"
6. **NO** marques "Add .gitignore"
7. **NO** marques "Choose a license"
8. Click en "Create repository"

### Paso 2: Conectar y subir
Una vez creado el repo, GitHub te dará instrucciones. Ejecuta estos comandos:

```bash
cd "/Users/francolautarogaray/Documents/Desarrollos /Forestal Argentina/Remitero/pdf-service-standalone"
git remote add origin https://github.com/TU_USUARIO/remitero-pdf-service.git
git branch -M main
git push -u origin main
```

Reemplaza `TU_USUARIO` con tu nombre de usuario de GitHub.

