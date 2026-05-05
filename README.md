# Práctica 2 — Determinación de Tipos de Estrellas

**Asignatura:** Aprendizaje Automático  
**Universidad:** Universidad Carlos III de Madrid  

## Descripción

Aplicación de técnicas de aprendizaje no supervisado para la clasificación
de estrellas a partir de sus características físicas y espectrales. Se aplica
PCA para reducción de dimensionalidad seguido de tres algoritmos de clustering
(K-Means, Clustering Jerárquico y DBSCAN), comparando sus resultados y
contrastándolos con la clasificación astronómica de tipos estelares.

## Dataset

240 estrellas con los siguientes atributos:
- **Temperature**: temperatura promedio de superficie (K)
- **L**: luminosidad relativa al Sol
- **R**: radio relativo al Sol
- **A_M**: magnitud absoluta
- **Color**: color principal del espectro
- **Spectral_Class**: clasificación espectral (O, B, A, F, G, K, M)

## Estructura del proyecto
practica2_clustering/
├── data/                  → dataset original
├── notebooks/             → notebook principal
├── requirements.txt       → dependencias
└── README.md
## Instalación

```bash
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

## Resultado principal

El pipeline recomendado (StandardScaler + PCA(2) + K-Means K=6) recupera
de forma no supervisada los 6 tipos estelares reconocidos astronómicamente
(enana roja, secuencia principal, gigante, supergigante, hipergigante).

| Algoritmo | Silhouette | Davies-Bouldin |
|-----------|------------|----------------|
| K-Means (K=6) | 0.6488 | 0.5164 |
| Jerárquico Ward (K=6) | 0.6126 | 0.6148 |
| DBSCAN (eps=0.4, ms=5) | 0.6789 | 0.3890 |

## Autoría

Práctica realizada para la asignatura de Aprendizaje Automático,
Grado en Ingeniería Informática, UC3M.