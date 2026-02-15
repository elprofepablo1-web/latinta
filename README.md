# 🚀 La Tinta - Sistema de Gestión en Vercel

Sistema completo de gestión de estudiantes para La Tinta, desplegado en Vercel y conectado a Google Sheets.

---

## 📋 Contenido del Proyecto

- `index.html` - Sistema completo La Tinta
- `vercel.json` - Configuración de Vercel
- `README.md` - Este archivo

---

## ⚙️ CONFIGURACIÓN INICIAL (Solo una vez)

### **Paso 1: Obtener API Key de Google**

1. Ve a [Google Cloud Console](https://console.cloud.google.com/)
2. Click en **"Crear proyecto"** (arriba a la izquierda)
3. Nombre: "La Tinta" → **Crear**
4. Selecciona tu proyecto (arriba a la izquierda)
5. En el menú lateral: **APIs y servicios → Biblioteca**
6. Busca: **"Google Sheets API"**
7. Click en el resultado → **Habilitar**
8. Menú lateral: **Credenciales**
9. Click en **"+ Crear credenciales"** → **Clave de API**
10. **Copia tu API Key** (la necesitarás en el paso 3)
11. Click en **"Editar clave de API"**
12. En "Restricciones de API" → Selecciona **"Google Sheets API"**
13. **Guardar**

**Tu API Key se verá así:**
```
AIzaSyC-xxxxxxxxxxxxxxxxxxxxxxxxxxx-xxxxx
```

---

### **Paso 2: Preparar tu Google Sheet**

1. Abre tu archivo Excel de La Tinta en Google Drive
2. Click derecho → **"Abrir con → Google Sheets"**
3. **IMPORTANTE:** Renombra la hoja a **"Estudiantes"** (abajo a la izquierda)
4. Click en **"Compartir"** (arriba a la derecha)
5. En "Acceso general" → **"Cualquier persona con el enlace"**
6. Asegúrate que diga **"Lector"**
7. Click en **"Copiar enlace"**

**Tu enlace se verá así:**
```
https://docs.google.com/spreadsheets/d/1ABC...XYZ_ESTE_ES_TU_ID/edit
```

**Copia solo el ID** (la parte entre `/d/` y `/edit`):
```
1ABC...XYZ_ESTE_ES_TU_ID
```

---

### **Paso 3: Configurar index.html**

1. Abre el archivo **`index.html`** en un editor de texto
2. Busca estas líneas (están al principio del `<script>`):

```javascript
const CONFIG = {
    SPREADSHEET_ID: 'TU_SPREADSHEET_ID_AQUI',  // Cambiar por tu ID
    API_KEY: 'TU_API_KEY_AQUI',  // Cambiar por tu API Key
    SHEET_NAME: 'Estudiantes'
};
```

3. **Reemplaza:**
   - `TU_SPREADSHEET_ID_AQUI` → Tu ID del Paso 2
   - `TU_API_KEY_AQUI` → Tu API Key del Paso 1

**Ejemplo configurado:**
```javascript
const CONFIG = {
    SPREADSHEET_ID: '1ABC...XYZ_ESTE_ES_TU_ID',
    API_KEY: 'AIzaSyC-xxxxxxxxxxxxxxxxxxxxxxxxxxx-xxxxx',
    SHEET_NAME: 'Estudiantes'
};
```

4. **Guarda** el archivo

---

## 🚀 DESPLEGAR EN VERCEL

### **Opción A: Desde la Web (Más fácil)**

1. Ve a [vercel.com](https://vercel.com)
2. Inicia sesión con tu cuenta
3. Click en **"Add New..."** → **"Project"**
4. Click en **"Import Git Repository"**
5. Si no tienes el código en Git:
   - Click en **"Deploy from template"**
   - O sube los archivos directamente

### **Opción B: Subir archivos directamente**

1. Crea una carpeta en tu computadora llamada `latinta`
2. Copia estos 3 archivos:
   - `index.html` (configurado)
   - `vercel.json`
   - `README.md`
3. Arrastra la carpeta a Vercel
4. Click en **"Deploy"**

### **Opción C: Desde GitHub (Recomendado)**

1. Crea un repositorio en GitHub llamado `latinta`
2. Sube los 3 archivos
3. En Vercel: **"Import Git Repository"**
4. Selecciona tu repositorio
5. Click en **"Deploy"**

---

## ✅ ¡LISTO! Tu sistema está en la nube

Vercel te dará una URL como:
```
https://latinta.vercel.app
```

O:
```
https://latinta-tu-usuario.vercel.app
```

---

## 📖 CÓMO USAR EL SISTEMA

### **Lectura de datos:**
✅ **Automática** - Cada vez que abres la URL, carga los datos de Google Sheets

### **Guardar cambios:**
1. Haz tus cambios (altas, ediciones, eliminaciones)
2. Click en **"💾 Descargar Excel"**
3. Ve a Google Drive
4. Abre tu Google Sheet
5. **Archivo → Importar**
6. Selecciona el Excel descargado
7. **"Reemplazar hoja de cálculo"** → **Importar datos**
8. ¡Listo! Los cambios están guardados

---

## 🔄 ACTUALIZAR EL CÓDIGO

Si necesitas actualizar algo:

1. Edita `index.html` localmente
2. En Vercel: **Settings → Git → Reconnect**
3. O simplemente arrastra el nuevo `index.html` a Vercel

Vercel hace el **redeploy automático** en segundos.

---

## 🎯 FUNCIONALIDADES DISPONIBLES

✅ Calendario semanal
✅ Búsqueda avanzada (8 filtros)
✅ Alta de estudiantes
✅ Alta de grupos
✅ Editar estudiantes
✅ Eliminar estudiantes/grupos
✅ Gestión completa
✅ Opciones para nuevos estudiantes
✅ Estadísticas
✅ Acceso desde cualquier lugar
✅ Datos sincronizados con Google Sheets

---

## 🔐 SEGURIDAD

- ✅ API Key restringida solo a Google Sheets API
- ✅ Google Sheet solo con permisos de lectura (seguro)
- ✅ HTTPS automático (conexión segura)
- ✅ No se guardan datos en Vercel

---

## 💡 VENTAJAS DE ESTA CONFIGURACIÓN

✅ **Gratis para siempre** (Vercel Free tier)
✅ **Acceso desde cualquier lugar** con tu URL
✅ **Rápido** - CDN global de Vercel
✅ **Seguro** - HTTPS + API Key restringida
✅ **Simple** - Solo HTML, no necesita servidor
✅ **Confiable** - Vercel tiene 99.99% uptime
✅ **Escalable** - Soporta muchos usuarios simultáneos

---

## 🆘 SOLUCIÓN DE PROBLEMAS

### "Error al cargar datos: 403"
- Verifica que tu Google Sheet esté compartido como "Cualquier persona con el enlace"
- Verifica que la API Key esté bien configurada

### "Error al cargar datos: 400"
- Verifica que el SPREADSHEET_ID sea correcto
- Verifica que la hoja se llame exactamente "Estudiantes"

### "La hoja está vacía"
- Verifica que tu Google Sheet tenga datos
- Verifica que la primera fila sean los headers (nombres de columnas)

### No carga nada / Página en blanco
- Abre la consola del navegador (F12)
- Ve a "Console" para ver el error
- Verifica que CONFIG tenga tus datos reales (no los placeholder)

---

## 📞 SOPORTE

Si tienes problemas:
1. Revisa la consola del navegador (F12 → Console)
2. Verifica que seguiste todos los pasos
3. Verifica que el Google Sheet tenga la estructura correcta

---

## 🎨 Enjoy!

Tu sistema La Tinta ahora está en la nube, accesible desde cualquier lugar, con datos sincronizados con Google Sheets.

**URL de ejemplo:** https://latinta.vercel.app
