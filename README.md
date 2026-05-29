# Dayal Pólizas — Deploy en Netlify

## Estructura del proyecto
```
dayal-polizas/
├── netlify/
│   └── functions/
│       └── chat.js        ← Proxy seguro a la API de Anthropic
├── index.html             ← Tu sitio web
├── netlify.toml           ← Config de Netlify
├── .env                   ← Solo para desarrollo local (NO subir a GitHub)
└── .gitignore             ← Protege el .env
```

## Pasos para publicar

### 1. Sube a GitHub
```bash
git init
git add .
git commit -m "Dayal Pólizas v1"
git remote add origin https://github.com/TU_USUARIO/dayal-polizas.git
git push -u origin main
```

### 2. Conecta Netlify
1. Ve a https://netlify.com
2. "Add new site" → "Import from Git"
3. Selecciona tu repo `dayal-polizas`
4. Build command: (vacío)
5. Publish directory: `.`
6. Haz clic en "Deploy site"

### 3. Agrega la API key en Netlify (MUY IMPORTANTE)
1. Ve a tu sitio en Netlify
2. **Site configuration → Environment variables**
3. Haz clic en "Add a variable"
4. Key: `ANTHROPIC_API_KEY`
5. Value: `sk-ant-api03-oyWjBmhsAYGO7EcJswret_...` (tu key completa)
6. Guarda y haz **Redeploy**

### 4. ¡Listo!
Tu sitio estará en: `https://tu-proyecto.netlify.app`

## Notas importantes
- El archivo `.env` es SOLO para pruebas locales
- El `.gitignore` evita que la API key se suba a GitHub
- La key en producción vive SOLO en las variables de entorno de Netlify
- Nunca compartas el archivo `.env` ni lo subas a GitHub
