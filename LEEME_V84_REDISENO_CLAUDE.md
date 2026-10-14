# FerrariPOS V84 — Rediseño visual · 15 temas Claude

## Qué cambió
Los temas anteriores se eliminaron y se reemplazaron por 15 temas "Claude + color", iguales en
Windows, Android Manager y Panel web:

Neón oscuro: Claude Arcilla, Cian, Magenta, Violeta, Lima, Esmeralda, Rojo, Azul
Claros: Claude Marfil, Cian Claro, Violeta Claro, Coral Claro, Menta Claro
Cristal: Claude Cristal Azul, Claude Cristal Ámbar

Los temas guardados por instalaciones anteriores se convierten solos al equivalente (por ejemplo
Claro -> Claude Marfil, Rojo Ferrari -> Claude Rojo). Tema de fábrica: Windows = Claude Cian, Android = Claude Rojo.

### Panel web (WebDashboardServer.cs) — rediseño completo
- Vidrio (glass), aurora animada, neón y modo claro. Selector de 15 temas dentro del panel (se recuerda en el navegador).
- Entrada y salida animadas: pestañas con fundido de salida y entrada, selector de temas que se abre y se cierra, tickets desplegables, tarjetas y gráficos que aparecen escalonados.
- No se tocó ninguna ruta de API, token, Cloudflare ni cálculo de datos.

### Windows (ThemeService.cs)
- 15 paletas nuevas, detección de temas claros, migración de temas viejos, y entrada con fundido en ventanas secundarias.
- Program.cs: el tema elegido ahora se conserva al reiniciar (antes se forzaba "Graphite" en cada inicio). El brillo 140 de arranque se mantiene.

### Android Manager (MainActivity.kt / Prefs.kt)
- 15 paletas nuevas, migración de nombres viejos, y el resplandor de los botones ahora usa los colores del tema.

## Verificación
- Panel web: probado en navegador (escritorio y celular) con datos de ejemplo.
- Windows (C#) y Android (Kotlin): NO se pudieron compilar en este entorno (no hay .NET ni Gradle).
  Los cambios son de datos y declaraciones simples; compilar con GitHub Actions / COMPILAR_WINDOWS10.bat antes de distribuir.
