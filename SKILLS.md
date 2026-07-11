# SKILLS.md — IPD434: Guías de Contenido por Módulo

Documento de referencia para Claude Code al mejorar o crear notebooks del curso.
Define la plantilla estándar, los objetivos esperados por módulo, y los criterios
de calidad de cada sección.

---

## Plantilla estándar de notebook

Todo notebook del curso debe seguir esta estructura de celdas en orden:

```
[CELDA 1 — Markdown] Encabezado y metadatos
[CELDA 2 — Markdown] Objetivos de aprendizaje
[CELDA 3 — Code]     Setup: imports y configuración global
[CELDA 4+]           Secciones de contenido (ver estructura por módulo)
[CELDA N-1 — Markdown] Resumen y próximos pasos
[CELDA N — Markdown]   Referencias
```

### Celda 1 — Encabezado (Markdown)

```markdown
# <Número>. <Título del Módulo>
### IPD434 — Computación Evolutiva e Inteligencia Artificial
**Universidad Técnica Federico Santa María**

---
```

### Celda 2 — Objetivos (Markdown)

```markdown
## 🎯 Objetivos de Aprendizaje

Al finalizar esta clase, el estudiante será capaz de:

1. **Comprender** [concepto fundamental del módulo].
2. **Implementar** [técnica o algoritmo central] en Python.
3. **Aplicar** [herramienta/librería] para resolver [tipo de problema].
4. **Analizar** [resultado o comportamiento] e interpretar [métrica o fenómeno].
5. **Comparar** [enfoque del módulo] con [alternativas o módulos anteriores].

> 💡 **Prerrequisitos:** [listar notebooks anteriores relevantes o conocimientos base]
```

### Celda 3 — Setup (Code)

```python
# ─── Setup ────────────────────────────────────────────────────────────────────
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import matplotlib as mpl

# Estilo unificado del curso
mpl.rcParams.update({
    "figure.figsize": (10, 6),
    "axes.titlesize": 14,
    "axes.labelsize": 12,
    "legend.fontsize": 11,
    "grid.alpha": 0.3,
})
np.random.seed(42)

print("✅ Entorno listo")
```

### Celda de sección (Markdown)

```markdown
## <N>. <Título de Sección>

<Párrafo de motivación: por qué es relevante esta sección, qué problema resuelve.>

### Conceptos clave
- **<Término>**: <definición breve y precisa>
- **<Término>**: <definición>

### Intuición
<Analogía o explicación sin fórmulas, 2-4 oraciones.>

### Formalización
<Ecuaciones en LaTeX si aplica. Ej:>
$$f(x) = \ldots$$
```

### Celda de ejercicio (Markdown + Code)

```markdown
### 🔬 Ejercicio: <Título>
**Objetivo:** <qué debe lograr el estudiante>
**Instrucciones:** ...
```
```python
# Tu código aquí
# ---
# PISTA: ...
```

### Celda de resumen (Markdown)

```markdown
## 📌 Resumen

| Concepto | Descripción breve |
|----------|-------------------|
| ...      | ...               |

## 🔗 Próximos pasos
- Módulo siguiente: [nombre y link relativo al `.ipynb`]
- Lecturas recomendadas: ver sección Referencias.
```

### Celda de referencias (Markdown)

```markdown
## 📚 Referencias

- **[Autor, Año]** Título. *Venue*. [link o DOI]
- **[Librería]** Documentación oficial: [URL]
```

---

## Módulos: objetivos y contenido esperado

### 00. Introducción al Curso

**Objetivos esperados:**
1. Conocer la estructura, evaluación y metodología del curso.
2. Entender qué es Soft Computing y en qué difiere del hard computing.
3. Identificar las áreas que cubre el curso: Fuzzy, EA, NN, RL, GAN, Transformers.

**Secciones sugeridas:**
- ¿Qué es Soft Computing? Definición y taxonomía.
- Panorama histórico (Zadeh, Holland, Rosenblatt, Turing).
- Mapa del curso: módulos, relaciones entre ellos, aplicaciones reales.
- Herramientas del curso: Python, Jupyter, librerías principales.
- Forma de evaluación y reglas.

**Criterio de calidad:** El estudiante sale con una imagen mental del campo completo
y entiende por qué cada módulo importa.

---

### 01. Introducción a Soft Computing

**Objetivos esperados:**
1. Distinguir sistemas deterministas vs. sistemas con incertidumbre.
2. Clasificar problemas según el tipo de Soft Computing apropiado.
3. Implementar un ejemplo mínimo de cada paradigma (fuzzy, EA, NN).

**Secciones sugeridas:**
- Incertidumbre, imprecisión y vaguedad: distinciones conceptuales.
- Taxonomía: Fuzzy Logic / Evolutionary Computation / Neural Networks / Hybrid.
- Caso motivador unificado: mismo problema resuelto con distintos enfoques.
- Métricas de comparación entre enfoques.

---

### 02. Sistemas Difusos (Fuzzy Logic)

**Objetivos esperados:**
1. Comprender la lógica difusa y las funciones de membresía.
2. Diseñar un sistema de inferencia difusa (FIS) Mamdani o Sugeno.
3. Implementar FIS con `scikit-fuzzy`.
4. Aplicar defuzzificación y evaluar la sensibilidad al diseño.

**Secciones sugeridas:**
- Conjuntos difusos vs. conjuntos clásicos. Funciones de membresía (triangular,
  trapezoidal, gaussiana, sigmoidal).
- Variables lingüísticas y reglas `SI ... ENTONCES`.
- Motor de inferencia: agregación, activación, acumulación.
- Defuzzificación: centroide, bisector, MOM.
- Ejemplo completo: control de temperatura o propina.
- `scikit-fuzzy`: `fuzz.trimf`, `fuzz.gaussmf`, `ctrl.Antecedent`, `ctrl.ControlSystem`.
- Comparación FIS Mamdani vs. Sugeno.

**Notebook existente:** `02_SistemasDifusos.ipynb` + `02_SciKit_Fuzzy.ipynb`
El segundo puede integrarse como sección práctica del primero, o mantenerse separado
como "laboratorio".

---

### 03. Computación Evolutiva

**Objetivos esperados:**
1. Comprender la metáfora evolutiva: selección, cruza, mutación.
2. Implementar un Algoritmo Genético (GA) desde cero y con DEAP.
3. Aplicar GA a un problema de optimización real.
4. Analizar convergencia y diversidad de la población.

**Secciones sugeridas:**
- Inspiración biológica. Representación del individuo (binaria, real, permutación).
- Operadores: selección (ruleta, torneo), cruza (un punto, uniforme), mutación.
- Función de aptitud (fitness): diseño y consideraciones.
- Algoritmo GA completo: implementación manual paso a paso.
- DEAP: `creator`, `toolbox`, `algorithms.eaSimple`, `tools.Statistics`.
- Curvas de convergencia. Exploración vs. explotación.
- Extensiones: Programación Genética (GP), Estrategias Evolutivas (ES).

**Notebook existente:** `03_ComputacionEvolutiva.ipynb` + `03_DEAP.ipynb`

---

### 04. Redes Neuronales

**Objetivos esperados:**
1. Entender el perceptrón y la representación matricial de una red.
2. Derivar e implementar backpropagation manualmente.
3. Construir una red con Keras/TensorFlow y entrenarla.
4. Interpretar curvas de aprendizaje y detectar overfitting.

**Secciones sugeridas:**
- Neurona biológica → neurona artificial. Funciones de activación.
- Perceptrón simple: limitación con XOR → motivación multicapa.
- Red feedforward: notación matricial, forward pass.
- Backpropagation: derivación de gradientes, regla de la cadena.
- Implementación NumPy pura (sin librerías de DL).
- Keras Sequential: Dense, activaciones, optimizadores, métricas.
- Regularización: Dropout, BatchNorm, Early Stopping.
- CNN básica: Conv2D, MaxPooling, aplicación a MNIST o CIFAR-10.

---

### 05-1. Deep Reinforcement Learning

**Objetivos esperados:**
1. Comprender el paradigma agente-entorno (MDP: estados, acciones, recompensas).
2. Implementar Q-Learning tabular.
3. Implementar Deep Q-Network (DQN) con replay buffer y target network.
4. Entrenar y evaluar un agente en un entorno Gymnasium.

**Secciones sugeridas:**
- El problema de RL: exploración vs. explotación, recompensa acumulada, descuento γ.
- MDP: definición formal S, A, R, P, γ.
- Ecuación de Bellman. Value function, Q-function.
- Q-Learning tabular: algoritmo y convergencia. Ejemplo: FrozenLake o Taxi.
- Limitaciones de Q-tabular → motivación para DQN.
- DQN: red neuronal como aproximador de Q, experience replay, target network.
- Implementación con PyTorch o Keras + Gymnasium (CartPole, LunarLander).
- Extensiones: Double DQN, Dueling DQN, Policy Gradient (REINFORCE).

**Notebook existente:** `05-1_ReinforcementLearning.ipynb`
Contiene checkpoints TensorFlow (`cp.ckpt.*`). Verificar que el checkpoint
se regenera con `--execute`, no depender de archivos binarios commiteados.

---

### 05-2. Transformers

**Objetivos esperados:**
1. Comprender el mecanismo de atención (self-attention, multi-head attention).
2. Entender la arquitectura Transformer (encoder-decoder).
3. Usar `transformers` (HuggingFace) para fine-tuning o inferencia.
4. Aplicar un transformer pre-entrenado a una tarea NLP o de secuencia.

**Secciones sugeridas:**
- Limitaciones de RNN → motivación para atención.
- Scaled dot-product attention: $\text{Attn}(Q,K,V)$.
- Multi-head attention y positional encoding.
- Bloque Transformer: LayerNorm, FFN, residual connections.
- BERT vs. GPT: encoder vs. decoder. Casos de uso.
- HuggingFace: `AutoTokenizer`, `AutoModel`, `pipeline`.
- Fine-tuning en una tarea downstream (clasificación de sentimientos, QA).
- Visualización de pesos de atención.

---

### 05-3. GAN y Autoencoders

**Objetivos esperados:**
1. Comprender el entrenamiento adversarial (generador vs. discriminador).
2. Implementar una GAN simple (Vanilla GAN) y una DCGAN.
3. Entender Autoencoders (AE) y Variational Autoencoders (VAE).
4. Generar y evaluar muestras sintéticas.

**Secciones sugeridas:**
- Modelos generativos: latent space, distribución de datos.
- GAN: función de pérdida minimax, modo collapse, entrenamiento alternado.
- Vanilla GAN en MNIST. DCGAN con convoluciones transpuestas.
- Autoencoder: encoder, cuello de botella, decoder. Reconstrucción.
- VAE: reparametrización, ELBO, espacio latente continuo.
- Generación e interpolación en el espacio latente.
- Métricas: FID, IS (si el tiempo lo permite).

---

### 05-4. Arquitecturas CNN Avanzadas

**Objetivos esperados:**
1. Comprender las innovaciones de VGG, ResNet, Inception, MobileNet.
2. Aplicar transfer learning con modelos pre-entrenados en ImageNet.
3. Realizar fine-tuning para un dominio específico.
4. Comparar trade-offs: accuracy vs. parámetros vs. latencia.

**Secciones sugeridas:**
- Evolución histórica: AlexNet → VGG → ResNet → Inception → EfficientNet.
- Residual connections: solución al vanishing gradient.
- Depthwise separable convolutions (MobileNet).
- Transfer learning: feature extraction vs. fine-tuning.
- Keras Applications: `ResNet50`, `MobileNetV2`, `EfficientNetB0`.
- Benchmark en dataset propio o TensorFlow Datasets.

---

## Criterios de calidad transversales

### Texto explicativo
- Cada sección tiene al menos un párrafo de motivación antes del código.
- Las ecuaciones se escriben en LaTeX inline (`$...$`) o display (`$$...$$`).
- Los términos técnicos se definen la primera vez que aparecen.
- Las analogías son precisas y no inducen a error.

### Código
- Las celdas de código son cortas (< 50 líneas por celda como regla general).
- Cada bloque de código tiene un comentario de encabezado que explica qué hace.
- Las visualizaciones tienen `xlabel`, `ylabel`, `title` y `legend` donde corresponde.
- No hay imports duplicados ni imports al final del notebook.
- No hay `!pip install` dentro del notebook (van en `requirements.txt`).

### Ejercicios
- Cada módulo tiene al menos 2 ejercicios: uno guiado y uno abierto.
- Los ejercicios están claramente marcados con el emoji 🔬 o un header `### Ejercicio`.
- Existe una celda de validación o criterio de éxito para cada ejercicio.

### Visualizaciones
- Cada concepto abstracto tiene una visualización que lo ilustra.
- Las figuras usan el estilo unificado del setup (ver Plantilla, Celda 3).
- Figuras interactivas con `ipywidgets` son bienvenidas para parámetros continuos.

---

## Checklist antes de hacer commit de un notebook mejorado

```
[ ] Celda de objetivos presente y con ≥ 4 objetivos específicos
[ ] Setup en celda única al inicio con seed fijada
[ ] Outputs limpios (nbconvert --ClearOutputPreprocessor)
[ ] Sin celdas vacías
[ ] Sin imports duplicados
[ ] Todas las secciones tienen párrafo de motivación
[ ] Al menos 2 ejercicios con criterio de validación
[ ] Celda de resumen al final
[ ] Celda de referencias al final
[ ] Notebook ejecuta sin errores (timeout 120s por celda)
[ ] No hay rutas absolutas hardcodeadas (usar paths relativos)
[ ] requirements.txt actualizado si se agregaron nuevas librerías
```
