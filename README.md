# SmarterOS n8n Workflows

Biblioteca de workflows de automatización para SmarterOS.

## 📦 Estructura

```
/
├── automation-manifest.json    # Catálogo de workflows
├── templates/                  # Plantillas base
│   └── chatwoot-basic.json
└── install-template-tenant.json # Instalador automático
```

## 🚀 Uso

### 1. Instalar workflow automático

Importa `install-template-tenant.json` en tu n8n.

### 2. Obtener JWT

```bash
curl -X POST https://api.smarteros.cl/auth/issue \
  -H "Content-Type: application/json" \
  -d '{"clerk_token":"YOUR_CLERK_TOKEN","tenant":"rut12121212"}'
```

### 3. Instalar plantilla

```bash
curl -X POST https://n8n.smarterbot.cl/webhook/install-template \
  -H "Authorization: Bearer YOUR_JWT" \
  -H "Content-Type: application/json" \
  -d '{"tenant":"rut12121212","template":"chatwoot-basic"}'
```

## 🔐 Multi-tenant

Cada workflow clonado se nombra: `{template}-{tenant}`

Ejemplo: `chatwoot-basic-rut12121212`

## 📚 Workflows Disponibles

Ver `automation-manifest.json` para lista completa.
