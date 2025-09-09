# LABORATORIO 1 — Reproducibilidad con *notebooks* (originales)

Este repositorio conserva **los Jupyter Notebooks originales** con sus anotaciones y organiza todo para cumplir el **Punto 3 (RA5)**.

## Estructura
```
data/
  raw/
    paired_bladder_2022_clinical_data.tsv
  processed/
  paired_bladder_2022_clinical_data_clean.csv
notebooks/
  selection_and_audit.ipynb
  LIMPIEZA_DE_DATOS.ipynb
reports/
  figures/
  EDA_descriptivo.docx
  bitacora.md
```

## Cómo ejecutar (solo notebooks)
1) Abre `notebooks/selection_and_audit.ipynb` y ejecútalo (auditoría).  
2) Abre `notebooks/LIMPIEZA_DE_DATOS.ipynb` y al final **exporta el dataset limpio** a:
   `data/processed/clinical_tidy.csv`
3) Ejecuta el modelo que desees (regresion lineal, cox, etc).

**Sugerencia de celda final para exportar** (pegar al final si tu notebook aún no guarda el archivo):
```python
# Asegura carpeta y exporta el tidy
from pathlib import Path
Path("data/processed").mkdir(parents=True, exist_ok=True)
tidy_df.to_csv("data/processed/clinical_tidy.csv", index=False)
print("OK -> data/processed/clinical_tidy.csv")
```

3) (Opcional) Crea/guarda tus figuras en `reports/figures/` desde el notebook de EDA o desde el doc adjunto.

## Entregables que cubre este repo
- Estructura reproducible + **README** (este archivo).
- **Pipeline ejecutable vía notebooks** que genera `data/processed/paired_bladder_2022_clinical_data_clean.csv` y figuras.

## Requisitos
- Jupyter Notebook / JupyterLab (Anaconda o VS Code también sirven).  
- Python 3.10+ y librerías usadas en sus notebooks (`pandas`, `numpy`, `matplotlib`, etc.).
