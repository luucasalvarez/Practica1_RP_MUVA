# Práctica 1 de Reconocimiento de Patrones

Máster Universitario en Visión Artificial · Universidad Rey Juan Carlos · Curso 2026/27

El objetivo es clasificar imágenes de campos estelares según contengan o no el patrón de referencia de Orión. Los modelos de aprendizaje deben ser de Scikit-Learn. El ajuste y la validación se realizan únicamente con el conjunto de entrenamiento. La métrica principal es la exactitud equilibrada.

- [Enunciado de la práctica](Contexto/Enunciado.md)
- [Hoja de ruta y esquema de la asignatura](Contexto/Hoja_de_ruta.md)
- [Plantilla de la memoria](Memoria/memoria.tex)

## Entorno de Python

El flujo parte de imágenes PNG. Pillow, NumPy y scikit-image permiten cargar y procesar las imágenes y extraer las características que recibe el clasificador de scikit-learn. El módulo estándar `csv` basta para leer las etiquetas y escribir las predicciones.

Con el entorno virtual activado, instala las dependencias iniciales desde la raíz del repositorio:

```sh
python -m pip install -r requirements.txt
```

## Datos locales

Descomprime `Datos_P1.zip` de modo que los archivos queden así. Git ignora el directorio `Datos/`.

```text
Datos/
├── train/
│   └── imagenes/          # 2.000 PNG de 96 × 96
├── test/
│   └── imagenes/          # 1.000 PNG de 96 × 96
├── Y_train.csv            # id,orion
└── referencia_orion.png  # Imagen de referencia suministrada
```

En la copia local están las 3.000 imágenes y las etiquetas de entrenamiento. Si la distribución original incluye `referencia_orion.png`, colócala en la raíz de `Datos/`.

## Memoria

Completa el grupo y los nombres en `Memoria/configuracion.tex` y redacta la memoria en `Memoria/secciones/`. Compila `memoria.tex` con pdfLaTeX desde `Memoria/`. La entrega admite un máximo de tres páginas de contenido más la portada.

## Entrega

- `RP_P1_GXX_predicciones.csv` se entrega por separado, en UTF-8, con cabecera `id,orion` y una etiqueta entera de 0 o 1 por cada imagen de test.
- `RP_P1_GXX_memoria_codigo.zip` debe incluir en su raíz `nombres.txt`, `RP_P1_GXX_memoria.pdf`, `entrenar.py`, `predecir.py` y los módulos auxiliares que utilicen. Añade `README.txt` si hacen falta instrucciones de ejecución. Excluye los datos, los entornos virtuales y el CSV de predicciones.
