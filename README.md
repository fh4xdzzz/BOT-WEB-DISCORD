# TheDulcanDesign Discord Bot

Bot de Discord para TheDulcanDesign con integración completa con Supabase y sistema de notificaciones.

## 🎯 Características

- ✅ **Sistema de Tickets** - Soporte técnico con canales privados
- ✅ **Sistema de Tienda** - Catálogo de servicios sincronizado con Supabase
- ✅ **Comandos de Compra** - `!tienda`, `!comprar`, `!mispedidos`
- ✅ **Sistema de Roles** - Roles automáticos: Cliente, Staff, Admin, Owner
- ✅ **Sistema de Niveles y XP** - XP por mensajes y niveles
- ✅ **Integración Supabase** - Sincronización bidireccional
- ✅ **Webhook Server** - Flask en puerto 5000 para eventos de la web
- ✅ **Notificaciones DM** - Admins y owners reciben DMs de nuevos pedidos
- ✅ **Logs de Actividad** - Entradas, salidas, comandos, voz

## 📋 Requisitos

- Python 3.8+
- Discord Bot Token
- Supabase URL y Keys
- Servidor de Discord

## 🚀 Instalación

1. **Clonar el repositorio:**
```bash
git clone https://github.com/tu-usuario/thedulcandesign-discord-bot.git
cd thedulcandesign-discord-bot
```

2. **Instalar dependencias:**
```bash
pip install -r requirements.txt
```

3. **Configurar variables de entorno:**
Crea un archivo `.env` con las siguientes variables:
```env
DISCORD_BOT_TOKEN=tu_bot_token
DISCORD_CLIENT_ID=tu_client_id
DISCORD_GUILD_ID=tu_guild_id
DISCORD_STAFF_ROLE_ID=tu_staff_role_id
DISCORD_ADMIN_ROLE_ID=tu_admin_role_id
SUPABASE_URL=tu_supabase_url
SUPABASE_ANON_KEY=tu_supabase_anon_key
WEBHOOK_URL=opcional_webhook_url
DISCORD_WEBHOOK_SECRET=opcional_secret
```

4. **Ejecutar el bot:**
```bash
python main.py
```

## 📝 Comandos

### 🛒 Sistema de Tienda
- `!tienda` - Muestra el catálogo de servicios
- `!comprar <id>` - Compra un servicio por ID
- `!mispedidos` - Muestra tus pedidos

### 🎫 Sistema de Tickets
- `!ticket` - Crea un ticket de soporte
- `!cerrar` - Cierra el ticket actual

### 👥 Sistema de Roles
- Los roles se asignan automáticamente según el comportamiento del usuario

### 📊 Sistema de Niveles
- XP se gana por mensajes
- Niveles van de 1 a 10

## 🔧 Configuración en Sparked Host

1. **Subir archivos:**
   - Sube todos los archivos del repositorio a Sparked Host
   - Asegúrate de incluir el archivo `.env` con las variables correctas

2. **Configurar variables de entorno:**
   - Agrega las variables de entorno en el panel de Sparked Host
   - `DISCORD_BOT_TOKEN`
   - `DISCORD_GUILD_ID`
   - `SUPABASE_URL`
   - `SUPABASE_ANON_KEY`

3. **Instalar dependencias:**
   - Ejecuta: `pip install -r requirements.txt`

4. **Iniciar el bot:**
   - Ejecuta: `python main.py`

## 🌐 Webhook Endpoint

El bot tiene un servidor Flask en el puerto 5000 que recibe eventos de la web:

- **Endpoint:** `/webhook`
- **Método:** POST
- **Formato JSON:**
```json
{
  "event_id": "unique_id",
  "event_type": "order.created",
  "created_at": "2024-01-01T00:00:00Z",
  "payload": {
    "order_id": "123",
    "order_number": "ORD202401010001",
    "customer_name": "John Doe",
    "customer_email": "john@example.com",
    "service_name": "Service Name",
    "description": "Description"
  }
}
```

## 📦 Estructura del Proyecto

```
bot/
├── main.py              # Archivo principal del bot
├── event_processor.py   # Procesador de eventos web
├── cogs/                # Extensiones del bot
│   ├── admin.py
│   ├── events.py
│   ├── help.py
│   ├── role_sync.py
│   ├── services.py
│   ├── setup.py
│   ├── setup_server.py
│   └── tickets.py
├── config/              # Configuración
│   └── settings.py
├── database/            # Conexión a Supabase
│   ├── supabase_client.py
│   └── tickets.py
├── services/            # Lista de servicios
│   └── services_list.py
└── utils/               # Utilidades
    ├── helpers.py
    ├── logger.py
    └── security.py
```

## 🔐 Seguridad

- ⚠️ **Nunca compartas** tu DISCORD_BOT_TOKEN
- ⚠️ **Nunca subas** el archivo `.env` a GitHub
- ⚠️ **Usa variables de entorno** en producción
- ⚠️ **Rota las credenciales** si se exponen

## 📞 Soporte

Para soporte técnico, contacta a:
- Email: thedulcandesign@gmail.com
- Discord: https://discord.gg/EDaCnZgC6T

## 📄 Licencia

Este proyecto es propiedad de TheDulcanDesign.
