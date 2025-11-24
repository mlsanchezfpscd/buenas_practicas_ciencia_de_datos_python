# 1. Gestión de entornos con Conda
**Fundación Progreso y Salud – Laboratorio de Ciencia de Datos (LCD)**

El uso de entornos Conda es obligatorio en el LCD. Cada proyecto debe ejecutarse dentro de un entorno aislado para asegurar reproducibilidad y evitar conflictos entre librerías, especialmente en JupyterHub.

---

## 1.1. Norma principal
Cada proyecto debe incluir un archivo:

environment.yml

Ese archivo describe el entorno.  
Los entornos se crean SIEMPRE usando ese archivo.

---

## 1.2. Ejemplo de environment.yml

```yaml
name: lcd_project
channels:
  - conda-forge
dependencies:
  - python=3.11
  - numpy
  - pandas
  - scipy
  - scikit-learn
  - matplotlib
  - seaborn
  - jupyterlab
  - ipykernel
  - pyarrow
  - pip
  - pip:
      - mlflow
      - pyreadstat

---

## 1.3. Crear el entorno
conda env create -f environment.yml


Activarlo:

conda activate lcd_project

---

## 1.4. Registrar el entorno en JupyterHub
python -m ipykernel install --user --name lcd_project --display-name "LCD Project"

---

## 1.5. Checklist

 Crear un archivo environment.yml en el proyecto

 Crear el entorno con conda

 Registrar el kernel en Jupyter

 No trabajar nunca en el entorno base
