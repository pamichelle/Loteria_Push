# 🎴 Lotería Push

Notificaciones push (Firebase Cloud Messaging) en Flutter, con un cantor de Lotería en la nube.
Práctica TDD · Desarrollo Móvil Integral · UTNG

**Alumna:** Rodríguez Bárcenas María Guadalupe · GTID235

## Estructura

```
loteria_push/
  server/   <- el cantor (Node puro, 61 pruebas con node:test)
  app/      <- la app Flutter (52 pruebas con flutter_test)
```

## 1. Servidor (Node)

```
cd server
npm test
npm start
```

`npm start` levanta el cantor en `http://localhost:8080` con push **simulado** (se imprime en consola).

## 2. App (Flutter)

```
cd app
flutter create . --project-name loteria_push
del test\widget_test.dart
flutter pub get
flutter test
```

Para correr la app hace falta Firebase (`flutterfire configure` genera `lib/firebase_options.dart`).
Las pruebas NO lo necesitan.

## Tabla de pruebas ROJO / VERDE (app)

| Ronda | Archivo de prueba | Se renombra para ROJO |
|---|---|---|
| 6 | `test/evento_lineas_test.dart` | `lib/dominio/evento.dart` |
| 6 | `test/evento_lineas_test.dart` | `lib/dominio/lineas.dart` |
| 6 | `test/partida_test.dart` | `lib/dominio/partida.dart` |
| 7 | `test/controlador_test.dart` | `lib/dominio/controlador.dart` |
| 9 | `test/pantalla_test.dart` | `lib/presentacion/pantalla_juego.dart` |

Servidor (Rondas 2–5): renombrar `baraja.js`, `lineas.js`, `mensajes.js`, `sala.js`, `servidor.js` y correr `node --test test/<archivo>.test.js`.

## Evidencias

_(Aquí van las capturas ROJO / VERDE de cada ronda y de la app ejecutada.)_
