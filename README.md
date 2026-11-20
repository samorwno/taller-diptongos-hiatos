# Taller · Diptongos, triptongos e hiatos

Sesión interactiva de **30 minutos** para practicar la separación silábica y la
tildación de diptongos, triptongos e hiatos. Adaptación web del taller
`Ortografía_y_Acentuación_del_Español.html`.

- **Página publicada:** <https://samorwno.github.io/taller-diptongos-hiatos/>
- **Repositorio:** <https://github.com/samorwno/taller-diptongos-hiatos>

## Qué incluye

- **Cuatro estaciones**:
  1. Separación silábica (10 palabras).
  2. Clasificación de encuentros vocálicos (10 palabras).
  3. Tildación especial de hiatos acentuales (10 palabras).
  4. Corrección ortográfica de tres textos.
- **Temporizador de 30 minutos** con pausa, barra de avance y aviso al agotarse.
- **Puntaje sobre 100**, progreso (33 actividades) y precisión en tiempo real.
- **Guía rápida de reglas** desplegable.
- **Retroalimentación inmediata** y explicación de cada respuesta.
- **Informe final** con veredicto, gráfico por estación, desglose y recomendación
  pedagógica.
- **Exportación del reporte** a un archivo `.txt`.
- **Persistencia** del avance y del temporizador en `localStorage`.
- **Diseño adaptable** a escritorio y móvil, con foco visible y etiquetas ARIA.

## Estructura

```text
taller-diptongos-hiatos/
├── index.html      # toda la aplicación (HTML + CSS + JavaScript)
├── .nojekyll       # evita el procesamiento de Jekyll en GitHub Pages
└── README.md
```

No hay build ni dependencias de JavaScript. La tipografía (Archivo, Work Sans y
Space Mono) se carga desde Google Fonts; si no hay red, el navegador usa sus
fuentes del sistema.

## Uso

Abre la página publicada o sirve el archivo localmente:

```bash
cd ~/Work/paginas-web/taller-diptongos-hiatos
python3 -m http.server 8000
# abrir http://localhost:8000
```

1. Pulsa **Guía rápida de reglas** si necesitas repasar los conceptos.
2. Empieza la sesión con el botón de reproducción del temporizador; el
   temporizador también arranca al interactuar con el primer ejercicio.
3. Resuelve las cuatro estaciones. Cada estación tiene su propio banco de
   palabras y retroalimentación.
4. Al final, abre **Puntuación final** para ver el informe y exportarlo.

## Persistencia

El estado completo se guarda en `localStorage` con la clave
`taller-diptongos-hiatos/1`:

- estación activa, índices de cada estación y respuestas;
- segundos restantes y estado del temporizador;
- ediciones de los textos.

Al recargar se recupera el avance. El botón **Reiniciar sesión** pide una
segunda confirmación y empieza de cero. En modo privado, sin almacenamiento
disponible, el taller funciona pero no conserva el avance.

## Pruebas

Verificación realizada con Chromium headless a 1280 px y 390 px:

- carga sin errores de JavaScript;
- temporizador: inicia, pausa y muestra el tiempo;
- Estación 1: cortes de «línea», vista previa y comprobación correcta;
- puntaje y progreso se actualizan;
- cambio de estación y persistencia tras recargar;
- tabla y veredicto del resumen;
- sin desbordamiento horizontal en móvil.

Para repetir la comprobación, abre `index.html` y recorre las cuatro estaciones
en escritorio y móvil.

## Limitaciones

- No hay backend ni registro de estudiantes: el reporte se descarga en el
  navegador.
- La sesión se guarda por navegador, no por cuenta.
- El temporizador descuenta hasta 10 segundos de avance si se recarga la página
  entre dos guardados.
- Las fuentes se cargan desde Google Fonts.

## Créditos

Fuentes pedagógicas citadas por el taller: *Ortografía de la lengua española*
(RAE y ASALE, 2010), *Reglas de Ortografía* (Juan Antonio Marín Candón),
Enciclopedia Banrepcultural y *Taller de Diptongos e Hiatos* (Juicy Spanish).

Adaptación web y publicación: Sergio Moreno.
