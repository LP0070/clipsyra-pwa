# CLIPSYRA PWA

App instalable generada desde los diseños aprobados:
- `clipsyra-mobile-design-v2.html` → 10 pantallas (Inicio, Crear, Studio, Parallel 2.0, SYRA, Calendario, Proyectos, Analytics, Facturación, Más)
- `clipsyra-lock-watermark.html` → lock screen como puerta de entrada (logo animado + WebAuthn + PIN)

## Probar local
```
cd clipsyra-pwa && python3 -m http.server 8080
```
Abrir http://localhost:8080 en el móvil (misma red) o en Chrome → DevTools → Application → Manifest para verificar instalabilidad.

## Instalar
- Android/Chrome: menú ⋮ → "Instalar app" / "Añadir a pantalla de inicio".
- iOS/Safari: Compartir → "Añadir a pantalla de inicio".

## Desplegar (Render, costo $0)
1. Nuevo **Static Site** en Render apuntando a esta carpeta (o súbela a un repo).
2. Build command: (vacío). Publish directory: `.`
3. Render sirve con HTTPS → la PWA es instalable y el Service Worker funciona.

## Notas
- El lock usa WebAuthn (huella/Face ID) si el dispositivo lo soporta; si no, cae al PIN.
- El PIN se crea en el primer uso y se guarda solo en el dispositivo (demo-grade, no es cifrado real).
- Funciona offline tras la primera carga (app shell en caché).
