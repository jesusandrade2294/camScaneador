# camScaneador para Android

Escáner de documentos sin anuncios, sin pagos y sin marca de agua. Todo se procesa en el teléfono.

## Qué hace
- Cámara en vivo con detección automática de bordes y corrección de perspectiva
- Ajuste manual de esquinas con lupa
- Filtros: Limpio, Color mejorado, Original, Grises, Blanco y negro, más brillo y contraste
- Documentos de varias páginas: agregar, reordenar, girar, duplicar y eliminar
- Firma dibujada, guardada y ubicable sobre la página
- Cédula 2 en 1 (frente y reverso en una hoja)
- Extraer texto (OCR) sin internet, con el reconocimiento de texto de Google ML Kit
- Exportar a PDF (Carta, A4, Oficio; tres calidades; contraseña opcional), JPG/ZIP o texto
- Guarda en Descargas/camScaneador y permite compartir por WhatsApp, correo, Drive, etc.

## Opción A: compilar gratis en GitHub (sin instalar nada)
1. Crea una cuenta en github.com, si no la tienes, y crea un repositorio nuevo (puede ser privado).
2. En el repositorio, elige "Add file" → "Upload files" y arrastra **todo el contenido** de esta carpeta, incluida la carpeta `.github`. En el celular es más fácil hacerlo desde un computador.
3. Confirma con "Commit changes". La compilación empieza sola.
4. Ve a la pestaña **Actions**, abre la ejecución "Compilar APK camScaneador" y espera de 5 a 10 minutos hasta que aparezca el visto verde.
5. Abajo, en **Artifacts**, descarga `camScaneador-apk`. Es un .zip que trae `camScaneador.apk`.
6. Pasa el APK al teléfono, ábrelo y acepta "Instalar apps de origen desconocido" cuando Android lo pida.

Nota: si la carpeta `.github` no aparece al subir (en Windows y Mac las carpetas que empiezan con punto pueden estar ocultas), crea el archivo a mano en GitHub con "Add file" → "Create new file", nombre `.github/workflows/compilar-apk.yml`, y pega el contenido del archivo que viene en esta carpeta.

## Opción B: Android Studio
1. Instala Android Studio.
2. Elige File → Open y selecciona esta carpeta.
3. Espera a que termine la sincronización y luego elige Build → Build App Bundle(s) / APK(s) → Build APK(s).
4. El APK queda en `app/build/outputs/apk/debug/app-debug.apk`.

## Datos técnicos
- Paquete: `com.camscaneador.app` · Android 8.0 o superior (minSdk 26)
- La primera compilación descarga jsPDF y JSZip a `app/src/main/assets/lib/`. Desde ese momento, la app funciona sin internet.
- El APK de la opción A está firmado con la llave de depuración: sirve para instalar directamente, pero no para publicar en Play Store.
