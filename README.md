# IPD-434

Repositorio del curso **IPD434 – Seminario de Soft Computing** (UTFSM): clases, certamen y proyecto final.

## Estructura del repositorio

```
.
├── certamen/               # Solución del Certamen 2026-2
└── proyecto/               # Proyecto final del curso (en desarrollo)
```

- **`certamen/`**: solución de `Certamen_2026-2.ipynb`, con dos partes:
  - **Lógica difusa**: controlador Mamdani (3 entradas / 3 salidas) para una lavadora inteligente, implementado y validado con `scikit-fuzzy`.
  - **Computación evolutiva**: resolución del *Traveling Salesman Trolley Problem* (TSTP) sobre la instancia `berlin52` (TSPLIB), usando los datos en `rutas/`.
  - `papers/`: artículos de referencia usados para justificar el diseño del controlador difuso.
- **`proyecto/`**: carpeta reservada para el proyecto final (pendiente).

## Carpeta `data/`

Varios notebooks (p. ej. `certamen/Certamen_2026-2.ipynb`) esperan un directorio `data/` local (ej. `certamen/data/`) con imágenes de ejemplo (`Bee/`, `Beetle/`, `Fly/`). **Esta carpeta no se versiona en git** porque pesa varios cientos de MB; está excluida vía `.gitignore`. Para reproducir los notebooks, hay que crear esa carpeta localmente y copiar ahí los datos correspondientes antes de ejecutarlos.

## Instalación del ambiente (uv)

Este repositorio usa [`uv`](https://docs.astral.sh/uv/) para gestionar el entorno y las dependencias de Python.

1. Instalar `uv` (si no lo tienes):

   ```bash
   curl -LsSf https://astral.sh/uv/install.sh | sh
   ```

2. Crear el entorno virtual en la raíz del repositorio:

   ```bash
   uv venv
   ```

3. Activar el entorno:

   ```bash
   source .venv/bin/activate
   ```

4. Instalar las dependencias del certamen:

   ```bash
   uv pip install -r certamen/requirements.txt
   ```

5. Abrir el notebook:

   ```bash
   jupyter notebook certamen/Certamen_2026-2.ipynb
   ```

## Licencia

Ver el archivo [`LICENSE`](LICENSE).
