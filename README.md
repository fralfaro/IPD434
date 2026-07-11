# IPD-434 — Soft Computing & Redes Neuronales

Material del curso **IPD434 – Seminario de Soft Computing** de la
**Universidad Técnica Federico Santa María (UTFSM)**.

El curso recorre las grandes familias del *Soft Computing* —**Lógica Difusa**,
**Computación Evolutiva** y **Redes Neuronales**— y sus especialidades modernas
(Aprendizaje por Refuerzo, Transformers, GAN, arquitecturas CNN avanzadas, ACO y PSO).

> 📓 **Los notebooks (`.ipynb`) son la única fuente de verdad.** Toda la teoría,
> el código, las visualizaciones y los ejercicios viven dentro de cada notebook.
> Los PDF/HTML son artefactos derivados y **no** se versionan (ver `.gitignore`).

---

## 📚 Contenido del curso

Cada carpeta en [`Clases/`](Clases/) es un módulo autocontenido. Todos los notebooks
comienzan con una celda de **🎯 Objetivos de Aprendizaje** y cierran con **Resumen**
y **Referencias**.

| # | Módulo | Notebook(s) | Tema principal | Librerías |
|---|--------|-------------|----------------|-----------|
| 00 | [Introducción](Clases/00_Introduccion/) | `00_Introduccion.ipynb` | Presentación del curso, ¿qué es Soft Computing?, mapa del campo | — |
| 01 | [Introducción a Soft Computing](Clases/01_IntroduccionSoftComputing/) | `01_IntroduccionSoftComputing.ipynb` | Incertidumbre/imprecisión/vaguedad, taxonomía de paradigmas | — |
| 02 | [Sistemas Difusos](Clases/02_SistemasDifusos/) | `02_SistemasDifusos.ipynb` (teoría) · `02_SciKit_Fuzzy.ipynb` (lab) · `..._Desarrollo-CCCV/CSSJ.ipynb` | Conjuntos difusos, funciones de membresía, FIS Mamdani/Sugeno, defuzzificación | `scikit-fuzzy` |
| 03 | [Computación Evolutiva](Clases/03_ComputacionEvolutiva/) | `03_ComputacionEvolutiva.ipynb` (teoría) · `03_DEAP.ipynb` (N-Reinas) | Algoritmos Genéticos, operadores, fitness, convergencia | `deap` |
| 04 | [Redes Neuronales](Clases/04_RedesNeuronales/) | `04_RedesNeuronales.ipynb` | Perceptrón, backpropagation, Keras, regularización, CNN | `numpy`, `keras`/`tensorflow` |

### Especialidades

El curso se ramifica en dos tracks de especialidad:

- **CCCV → Redes Neuronales avanzadas** ([`Clases/05_NN_Especialidad/`](Clases/05_NN_Especialidad/))
- **CSSJ → Computación Evolutiva avanzada** ([`Clases/05_EA_Especialidad/`](Clases/05_EA_Especialidad/))

| # | Módulo | Notebook(s) | Tema principal | Librerías |
|---|--------|-------------|----------------|-----------|
| 05 · EA | [EA Avanzado](Clases/05_EA_Especialidad/) | `05_EA_Avanzado.ipynb` | Operadores avanzados, selección (torneo/ranking/SUS), **ACO**, **PSO** | — |
| 05-1 | [Deep Reinforcement Learning](Clases/05_NN_Especialidad/05-1_DeepReninforcementLearning/) | `05-1_ReinforcementLearning.ipynb` | MDP, ecuación de Bellman, Q-Learning, **DQN**, Gymnasium | `gymnasium`, `tensorflow` |
| 05-2 | [Transformers](Clases/05_NN_Especialidad/05-2_Transformers/) | `Hugging Face Pipeline` · `Text Classification` · `Transfer Learning TF` | Atención, HuggingFace, clasificación de texto, transfer learning | `transformers`, `tensorflow` |
| 05-3 | [GAN & Autoencoders](Clases/05_NN_Especialidad/05-3_GAN_AE/) | `05-3_GAN_AE.ipynb` | Entrenamiento adversarial, DCGAN, AE, **VAE**, espacio latente | `keras`/`tensorflow` |
| 05-4 | [Arquitecturas CNN Avanzadas](Clases/05_NN_Especialidad/05-4_AdvancedCNNArchitectures/) | `05-4_AdvancedCNNArchitectures.ipynb` | VGG, ResNet, Inception, MobileNet, EfficientNet, transfer learning | `keras` (Applications) |

---

## 📄 Material de referencia

Papers de apoyo en [`Material/`](Material/):

| Archivo | Referencia | Relación con el curso |
|---------|-----------|-----------------------|
| [`Turing_Paper_1936.pdf`](Material/Turing_Paper_1936.pdf) | A. M. Turing (1936), *On Computable Numbers, with an Application to the Entscheidungsproblem*, Proc. London Math. Soc. | Fundamentos de computabilidad y la máquina de Turing (módulo **01**). |
| [`Wulandari_2018_..._384_012044.pdf`](Material/Wulandari_2018_IOP_Conf._Ser.__Mater._Sci._Eng._384_012044.pdf) | N. Wulandari & A. G. Abdullah (2018), *Design and Simulation of Washing Machine using Fuzzy Logic Controller (FLC)*, IOP Conf. Ser.: Mater. Sci. Eng. **384** 012044. | Aplicación práctica de un controlador difuso (módulo **02**). |
| [`sobhy-2015-ijca-906083.pdf`](Material/sobhy-2015-ijca-906083.pdf) | S. M. Sobhy (2015), *Developing of Fuzzy Logic Controller for Air Condition System*, Int. J. of Computer Applications. | Controlador difuso de aire acondicionado; base del desarrollo del módulo **02**. |

---

## 🗂️ Estructura del repositorio

```
IPD-434/
├── README.md                 ← este archivo
├── CLAUDE.md                 ← guía de trabajo autónomo en el repo
├── SKILLS.md                 ← plantilla y criterios de calidad de los notebooks
├── LICENSE
├── Clases/
│   ├── 00_Introduccion/
│   ├── 01_IntroduccionSoftComputing/
│   ├── 02_SistemasDifusos/
│   ├── 03_ComputacionEvolutiva/
│   ├── 04_RedesNeuronales/
│   ├── 05_EA_Especialidad/            ← especialidad CSSJ (ACO, PSO)
│   └── 05_NN_Especialidad/            ← especialidad CCCV
│       ├── 05-1_DeepReninforcementLearning/
│       ├── 05-2_Transformers/
│       ├── 05-3_GAN_AE/
│       └── 05-4_AdvancedCNNArchitectures/
└── Material/                 ← papers de referencia (PDF)
```

Cada módulo incluye una subcarpeta `images/` (y en algunos casos `data/`) con los
recursos que embebe el notebook.

---

## 🚀 Uso

Se recomienda Python 3.10+ y un entorno virtual.

```bash
# 1. Clonar
git clone https://github.com/fralfaro/IPD-434.git
cd IPD-434

# 2. Entorno virtual
python3 -m venv .venv
source .venv/bin/activate        # Windows: .venv\Scripts\activate

# 3. Dependencias principales
pip install numpy pandas matplotlib scikit-learn scikit-fuzzy deap \
            tensorflow keras torch gymnasium transformers jupyter

# 4. Abrir los notebooks
jupyter notebook
```

> 💡 Los notebooks de las especialidades (Deep RL, Transformers, GAN, CNN) requieren
> `tensorflow`/`torch` y pueden beneficiarse de una GPU. No es necesario ejecutar todos
> los módulos para estudiar uno en particular: cada notebook es autocontenido.

---

## 🤝 Contribuir

- Edita siempre el `.ipynb`; **nunca** los PDF/HTML (son derivados).
- Limpia los outputs antes de commitear:
  `jupyter nbconvert --ClearOutputPreprocessor.enabled=True --to notebook --inplace <notebook>.ipynb`
- Sigue la plantilla y los criterios de calidad definidos en [`SKILLS.md`](SKILLS.md).

## 📜 Licencia

Ver el archivo [`LICENSE`](LICENSE).
