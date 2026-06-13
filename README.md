# studio-datos 📦

Repositorio de **datos** del estudio de medios: aquí viven la configuración, los
proyectos y el **historial de todo lo generado** (imágenes, voz y transcripciones)
por la app de estudio local. No es código ejecutable, es la capa de persistencia.

## ¿Qué contiene?

| Archivo / carpeta | Qué guarda |
|---|---|
| `config.json` | Configuración del estudio: carpeta de guardado y estilos de voz (TTS). |
| `proyectos.json` | Índice de proyectos, cada uno con su estilo, referencias y estilo de video. |
| `historial.json` | Registro de cada generación: archivo, tipo (`image`/`tts`/`stt`), prompt, modelo, costo y fecha. |
| `historial/` | Los archivos generados: imágenes (`img_*.png`), audio (`voz_*.mp3`), transcripciones (`tx_*.txt`). |
| `proyectos/<nombre>/` | Guías de estilo por proyecto (`estilo.md`, `estilo-video.md`) y referencias. |

## ¿Para quién es?

Es el almacén de datos personal del estudio (uso propio). La app de estudio lee y
escribe estos archivos para recordar proyectos, estilos y el historial de costos
de cada generación.

## Cómo se usa

No se instala ni se ejecuta por sí solo: la **app de estudio** apunta su carpeta de
datos a este repositorio y lo va actualizando.

```bash
git clone https://github.com/giopark4444-commits/studio-datos.git
```

### Ejemplo: una entrada del historial

Cada generación queda registrada en `historial.json` así:

```json
{
  "file": "voz_20260612_075227_2336.mp3",
  "kind": "tts",
  "prompt": "Hola Gio, el estudio ya habla.",
  "voice": "nova",
  "model": "tts-1",
  "mode": "audio",
  "cost": 0.00045,
  "ts": "2026-06-12 07:52",
  "project": ""
}
```

Y un proyecto en `proyectos.json` agrupa estilo, referencias y estilo de video:

```json
{
  "Stel": { "style": "", "refs": [], "style_video": "" }
}
```

## Nota

Los archivos temporales (`*.tmp`, `*.bak`, `*.log`, `jobs.json`, `.DS_Store`) están
excluidos por `.gitignore`. Por ser un repo público, evita guardar aquí contenido
sensible o privado.
