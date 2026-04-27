# Telar

Calendario interno de coordinación del Convenio 1022 de 2025 — Artes para la Paz.

Cubre los tres carriles del primer semestre de 2026:

- **C1 · Formación Puente** (conducen Mercy Arias y Jeimmy Ruiz, con dos sesiones de Felipe).
- **C2 · Autonomía Digital** (conduce Felipe).
- **C3 · Identidad Mujeres** (Felipe con el comité de la Red de Mujeres).
- **HITO** para los momentos clave (Minga Inaugural, presentación de identidad, Acta de Transferencia).

---

## Cómo editar las fechas

Toda la información del calendario vive en un solo archivo: **`data.json`**. No es necesario tocar HTML ni CSS.

### Desde la web de GitHub (recomendado para Mercy y Jeimmy)

1. Entra al repositorio en `github.com`.
2. Haz clic en el archivo `data.json`.
3. Haz clic en el ícono del lápiz (esquina superior derecha del archivo).
4. Edita lo que necesites mover.
5. Abajo del editor escribe un mensaje corto del cambio (por ejemplo: *"Cambio hora Comunicaciones I al 8 may 2pm"*).
6. Haz clic en **Commit changes**.

GitHub Pages re-publica el sitio automáticamente en uno o dos minutos.

### Mover una sesión de fecha

Busca la sesión por su `titulo` y cambia el campo `fecha`. El formato es **`AAAA-MM-DD`** (año-mes-día con ceros).

```json
{
  "fecha": "2026-05-15",
  "carril": "C1",
  "titulo": "Comunicaciones II",
  ...
}
```

Para moverla del 15 al 22 de mayo: cambia `"2026-05-15"` por `"2026-05-22"`.

### Cambiar la hora o el lugar de una sesión

Edita los campos `hora`, `duracion`, `lugar`, `notas`. Pueden quedar vacíos (`""`) si todavía no se confirma.

```json
{
  "fecha": "2026-05-07",
  "hora": "10:00 AM",
  "duracion": "1h 15min",
  "lugar": "Microsoft Teams"
}
```

### Añadir una sesión nueva

Copia un bloque de evento existente y pégalo dentro de la lista `eventos`. Cambia los datos. **No olvides la coma** entre eventos.

```json
{
  "fecha": "2026-06-15",
  "carril": "C2",
  "titulo": "Sesión nueva",
  "hora": "Por confirmar",
  "duracion": "1h 30min",
  "lugar": "Microsoft Teams",
  "notas": "Lo que sea importante recordar."
}
```

### Borrar una sesión

Borra el bloque entero de esa sesión. Cuida que las comas entre eventos sigan siendo correctas (no debe quedar una coma sobrante al final de la lista).

### Marcar una sesión como destacada

Las sesiones destacadas aparecen en oscuro con una estrella. Útil para hitos o momentos clave del proceso. Añade `"destacado": true`:

```json
{
  "fecha": "2026-07-17",
  "carril": "HITO",
  "titulo": "Acta de Transferencia",
  "destacado": true
}
```

### Cambiar el nombre o descripción de un carril

Si en algún momento se decide renombrar la Formación Puente o el Ciclo de Autonomía, edita el bloque `carriles` arriba en `data.json`. El cambio se refleja en toda la página.

---

## Cómo se publica

Este repositorio está configurado para publicarse con **GitHub Pages**. Para activarlo la primera vez:

1. En el repositorio, abre la pestaña **Settings** (Configuración).
2. En el menú izquierdo, haz clic en **Pages**.
3. En **Source**, escoge `Deploy from a branch`, selecciona la rama `main` y la carpeta `/ (root)`.
4. Haz clic en **Save**.

GitHub te da una URL del estilo `https://[usuario].github.io/[repo]/`. Esa es la dirección del Telar para compartirla por WhatsApp del comité.

---

## Cómo previsualizar antes de subir cambios

Si quieres ver cómo se verán los cambios antes de hacer commit, abre una terminal en la carpeta del repositorio y corre:

```bash
python3 -m http.server 8000
```

Después abre en tu navegador `http://localhost:8000`.

> Nota: si abres `index.html` con doble clic directo, el navegador bloquea la lectura de `data.json` por seguridad. Necesitas un servidor (la línea de arriba) o subir a GitHub Pages.

---

## Estructura del repositorio

```
telar/
├── index.html       ← La página visual. No editar a menos que sea necesario.
├── data.json        ← Aquí vive toda la información. Este es el archivo que se edita.
└── README.md        ← Este documento.
```

---

## Fuentes y crédito

Tipografías:

- **Work Sans** — Wei Huang · SIL Open Font License (titulares y cuerpo)
- **DM Sans** — Colophon Foundry · SIL Open Font License (cuerpo y metadata)
- **Caveat** — Pablo Impallari · SIL Open Font License (acentos manuscritos)

Las tres familias provienen de los manuales de identidad de la RIJ y la Red de Mujeres.

Diseño y construcción:

- **Felipe Camacho Otero** — Enlace de comunicaciones del Convenio 1022 de 2025.

Editoras del Telar:

- **Mercy Tatiana Arias** — Orientadora de la Red de Mujeres Artistas y Gestoras.
- **Jeimmy Johanna Ruiz** — Orientadora de la Red Intercultural Juvenil.
- **Felipe Camacho Otero** — Enlace de comunicaciones.

---

## Versiones

- **v1** · 27 abril 2026 — Versión inicial. Incluye mayo, junio y julio de 2026.

Para futuros trimestres se actualiza el rango en `index.html` (líneas con la constante `RANGO`) y se agregan los eventos nuevos en `data.json`.

---

*Donde las historias se tejen y transforman — y seguimos tejiendo.*
