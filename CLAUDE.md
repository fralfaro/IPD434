# CLAUDE.md — IPD434: Soft Computing & Neural Networks

## Propósito de este archivo

Instrucciones para Claude Code al trabajar autónomamente en este repositorio.
El curso IPD-434 cubre Soft Computing: Fuzzy Logic, Computación Evolutiva, Redes Neuronales
y especialidades (RL/DRL, GAN, Transformers, ACO, PSO). Los notebooks son la fuente
canónica. Los PDF y HTML se **generan** desde los notebooks — no son fuente de verdad.

---

## Reglas absolutas

1. **Nunca modificar PDF ni HTML.** Son artefactos derivados. Si existen en el repo,
   ignorarlos. La fuente es siempre el `.ipynb`.
2. **No generar PDFs ni HTMLs** a menos que el usuario lo pida explícitamente.
3. **El notebook debe ser autocontenido:** toda explicación, código, visualización y
   ejercicio vive en el `.ipynb`, no en archivos auxiliares.
4. **No romper kernels.** Toda celda de código debe ejecutarse en orden sin errores
   en un entorno estándar (`pip install -r requirements.txt`).
5. **Preservar la estructura de celdas existente** al mejorar. Editar celdas, no
   reordenar masivamente sin justificación.

---

## Estructura del repositorio

```
IPD-434/
├── CLAUDE.md              ← este archivo
├── SKILLS.md              ← guías de contenido por módulo
├── README.md
├── requirements.txt
├── Clases/
│   ├── 00_Introduccion/
│   │   └── 00_Introduccion.ipynb          ← FUENTE
│   ├── 01_IntroduccionSoftComputing/
│   │   └── 01_IntroduccionSoftComputing.ipynb
│   ├── 02_SistemasDifusos/
│   │   ├── 02_SciKit_Fuzzy.ipynb
│   │   └── 02_SistemasDifusos.ipynb
│   ├── 03_ComputacionEvolutiva/
│   │   ├── 03_ComputacionEvolutiva.ipynb
│   │   └── 03_DEAP.ipynb
│   ├── 04_RedesNeuronales/
│   │   └── 04_RedesNeuronales.ipynb
│   ├── 05_EA_Especialidad/
│   │   └── 05_EA_Avanzado.ipynb
│   ├── 05-1_DeepReinforcementLearning/
│   │   └── 05-1_ReinforcementLearning.ipynb
│   ├── 05-2_Transformers/
│   ├── 05-3_GAN_AE/
│   └── 05-4_AdvancedCNNArchitectures/
└── Material/
    └── *.pdf              ← papers de referencia, no tocar
```

---

## Flujo de trabajo al mejorar un notebook

### Paso 1 — Diagnóstico
Antes de editar, ejecutar:
```bash
jupyter nbconvert --to script <notebook>.ipynb --stdout | head -50
```
Identificar: ¿tiene celda de objetivos? ¿tiene secciones claras? ¿hay celdas vacías
o outputs cacheados obsoletos?

### Paso 2 — Limpiar outputs cacheados
```bash
jupyter nbconvert --ClearOutputPreprocessor.enabled=True \
  --to notebook --inplace <notebook>.ipynb
```
Siempre limpiar antes de editar para evitar conflictos de merge y mantener el repo liviano.

### Paso 3 — Agregar/mejorar estructura
Seguir la plantilla de celda estándar definida en SKILLS.md → sección "Plantilla de notebook".

### Paso 4 — Validar ejecución
```bash
jupyter nbconvert --to notebook --execute \
  --ExecutePreprocessor.timeout=120 \
  --output <notebook>_executed.ipynb <notebook>.ipynb
```
Verificar que no hay errores. Eliminar el `_executed.ipynb` después.

### Paso 5 — Limpiar outputs nuevamente y commit
```bash
jupyter nbconvert --ClearOutputPreprocessor.enabled=True \
  --to notebook --inplace <notebook>.ipynb
git add <notebook>.ipynb
git commit -m "feat(<módulo>): mejora objetivos y contenido"
```

---

## Convenciones de commit

```
feat(<módulo>):   nueva sección o contenido
fix(<módulo>):    corrección de error en código o explicación
refactor(<módulo>): restructuración sin cambio de contenido
docs(<módulo>):   mejora de texto explicativo
```

Ejemplos:
- `feat(02_SistemasDifusos): agrega celda de objetivos y ejemplo FIS de temperatura`
- `fix(03_ComputacionEvolutiva): corrige función de fitness en DEAP`
- `refactor(04_RedesNeuronales): separa backprop manual de implementación Keras`

---

## Tareas recurrentes que Claude Code puede hacer sin preguntar

- Limpiar outputs de todos los notebooks del repo.
- Agregar celda de objetivos al inicio de notebooks que no la tengan.
- Unificar el estilo de títulos (Markdown H1/H2/H3).
- Eliminar celdas duplicadas o vacías sin contenido.
- Actualizar `requirements.txt` si se detectan imports no listados.

## Tareas que requieren confirmación antes de ejecutar

- Reordenar secciones completas de un notebook.
- Eliminar contenido (no solo celdas vacías).
- Agregar ejemplos nuevos extensos que cambien el alcance del módulo.
- Cambiar la librería principal de un módulo (ej. de scikit-fuzzy a otra).

---

## Dependencias del entorno

```txt
# requirements.txt mínimo esperado
numpy>=1.24
pandas>=2.0
matplotlib>=3.7
scikit-learn>=1.3
scikit-fuzzy>=0.4
deap>=1.4
tensorflow>=2.13
keras>=2.13
torch>=2.0
gymnasium>=0.29
transformers>=4.35
jupyter>=1.0
nbconvert>=7.0
```

---

## Planificación del curso (referencia para contexto de contenido)

| Semana | Tema principal                          | Especialidad            |
|--------|-----------------------------------------|-------------------------|
| 1      | Introducción al curso                   |                         |
| 2      | Feriado                                 |                         |
| 3      | Fuzzy Logic                             |                         |
| 4      | Fuzzy Logic (cont.)                     |                         |
| 5–6    | Redes Neuronales + Computación Evolutiva|                         |
| 7      | Fiestas Patrias                         |                         |
| 8      | Redes Neuronales + Comp. Evolutiva (cont)|                        |
| 9      | Especialidad 1                          | CCCV: RL+DRL / CSSJ: GA+GP |
| 10     | Semana Sansana                          |                         |
| 11     | Especialidad 2                          | CCCV: TNN / CSSJ: ACO  |
| 12     | Presentación Paper                      |                         |
| 13     | Feriado                                 |                         |
| 14     | Especialidad 2 (cont.) + Certamen       |                         |
| 15     | Especialidad 3                          | CCCV: GAN / CSSJ: PSO+SOA |
| 16     | Especialidad 3 (cont.)                  |                         |
| 17–18  | Trabajo Proyecto Final                  |                         |
