# 🚀 ServiHogar app - Plataforma de Servicios

Una aplicación Flutter completa para conectar clientes con expertos en servicios del hogar.

## ✨ Características Principales

### 🔐 **Autenticación Completa**
- Firebase Auth con Google Sign-In
- Gestión de perfiles (Cliente vs Experto)
- Sistema de aprobación para expertos

### 🎯 **Marketplace de Propuestas**
- Clientes publican solicitudes de trabajo
- Expertos pueden ver y enviar propuestas
- Sistema tipo Workana/Freelancer
- Clientes escogen la mejor propuesta
- Filtrado por especialidad y ubicación

### 💳 **Pagos Directos con Mercado Pago**
- **API directa** de Mercado Pago desde Flutter
- Formulario de pago personalizado
- Manejo completo de estados de pago
- Diálogos visuales para cada estado
- **Sin backend** - Todo desde el cliente

### 📍 **Servicios de Ubicación**
- Google Maps integration
- Geolocalización en tiempo real
- Permisos automáticos de ubicación

### 🔔 **Notificaciones Push**
- Firebase Cloud Messaging (FCM)
- Notificaciones locales para solicitudes
- Notificaciones en primer plano y background

## 🛠️ Tecnologías Utilizadas

- **Frontend**: Flutter con Provider para state management
- **Autenticación**: Firebase Auth + Google Sign-In
- **Base de Datos**: Firebase Firestore
- **Pagos**: Mercado Pago API directa
- **Notificaciones**: Firebase Cloud Messaging
- **Maps**: Google Maps Flutter
- **Ubicación**: Geolocator + Geocoding

## 📱 Funcionalidades Implementadas

### Para Expertos:
1. **Buscar Trabajos** - Explorar marketplace de solicitudes
2. **Enviar Propuestas** - Ofertar por trabajos disponibles
3. **Gestionar Trabajos** - Manejar propuestas aceptadas

### Para Clientes:
1. **Publicar Solicitud** - Crear trabajo en el marketplace
2. **Recibir Propuestas** - Ver ofertas de expertos
3. **Pago Directo** - Pagar propuesta aceptada con Mercado Pago

## 🚀 Instalación

### 1. Clonar el Repositorio
```bash
git clone https://github.com/tu-usuario/servi.git
cd servi
```

### 2. Instalar Dependencias
```bash
flutter pub get
```

### 3. Configurar Firebase
- Agregar `google-services.json` (Android)
- Agregar `GoogleService-Info.plist` (iOS)
- Configurar reglas de Firestore

### 4. Configurar Mercado Pago
- Obtener credenciales de test/producción
- Actualizar tokens en `lib/core/services/mercado_pago_service.dart`

### 5. Ejecutar la App
```bash
flutter run
```

## 🔧 Configuración de Mercado Pago

### Credenciales de Test
```dart
// En lib/core/services/mercado_pago_service.dart
static const String accessToken = 'TEST-tu-access-token';
static const String publicKey = 'TEST-tu-public-key';
```

### Credenciales de Producción
```dart
// Para producción, cambiar a:
static const String accessToken = 'APP_USR-tu-access-token';
static const String publicKey = 'APP_USR-tu-public-key';
```

## 📊 Flujo de la Aplicación

```
Cliente → Publica Solicitud → Estado "Pendiente" → Marketplace visible
                                                    ↓
Expertos ← Buscan en Marketplace ← Filtrado por Especialidad/Ubicación
                                                    ↓
Envían Propuestas → Cliente Revisa → Acepta Mejor Propuesta
                                                    ↓
Pago con Mercado Pago → Estado "Pagado" → Trabajo en Progreso
```

## 🏗️ Estructura del Proyecto

```
lib/
├── core/
│   ├── models/           # Modelos de datos
│   ├── providers/        # State management con Provider
│   ├── services/         # Servicios (MP, notificaciones, etc.)
│   ├── theme/           # Tema de la aplicación
│   └── utils/           # Utilidades
├── features/
│   ├── auth/            # Autenticación y perfiles
│   ├── home/            # Pantallas principales
│   ├── services/        # Gestión de servicios y pagos
│   └── legal/           # Términos y condiciones
└── main.dart            # Punto de entrada
```

## 🔒 Seguridad

### Pagos Seguros
- Tokens de Mercado Pago manejados de forma segura
- Validación de datos de tarjeta
- Estados de pago manejados correctamente
- Deep links para confirmaciones

### Autenticación
- Firebase Auth con tokens seguros
- Verificación de permisos por pantalla
- Gestión de sesiones automática

## 🧪 Testing

### Modo Debug
- Botones de simulación de estados de pago
- Logs detallados en consola
- Indicadores visuales para testing

### Tarjetas de Test (Mercado Pago)
```
Visa: 4509 9535 6623 3704
Mastercard: 5031 7557 3453 0604
American Express: 3711 803032 57522
```

## 📈 Próximos Pasos

- [x] Sistema de marketplace/propuestas
- [x] Sistema de calificaciones
- [x] Chat en tiempo real
- [x] Historial de trabajos
- [ ] Sistema de propinas
- [ ] Mapa de ubicación en tiempo real
- [ ] Reembolsos automáticos
- [ ] Filtros avanzados de búsqueda
- [ ] Sistema de favoritos

## 🤝 Contribución

1. Fork del repositorio
2. Crear rama feature (`git checkout -b feature/nueva-funcionalidad`)
3. Commit cambios (`git commit -am 'Agregar nueva funcionalidad'`)
4. Push a la rama (`git push origin feature/nueva-funcionalidad`)
5. Crear Pull Request

## 📞 Soporte

Para soporte técnico o preguntas:
- Revisar logs de la aplicación
- Verificar configuración de Firebase
- Consultar documentación de Mercado Pago

---

**🎉 ¡El sistema está listo para usar!**

✅ Autenticación completa  
✅ Sistema de marketplace de propuestas  
✅ Pagos directos con Mercado Pago  
✅ Sistema de calificaciones  
✅ Chat en tiempo real  
✅ Sin dependencias de backend  
