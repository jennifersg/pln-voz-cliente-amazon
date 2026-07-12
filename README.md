# Sistema inteligente para el análisis de la voz del cliente

Proyecto final del módulo **Procesamiento de Lenguaje Natural** de la Maestría en Ciencia de Datos e Inteligencia Artificial.

## Descripción

El proyecto analiza reseñas de productos escritas en español y permite identificar:

- sentimiento: positivo, neutro o negativo;
- aspectos mencionados, como precio, calidad, entrega, funcionamiento y diseño;
- tema principal mediante modelado LDA;
- probabilidades de clasificación de los modelos Naive Bayes y LSTM.

La solución integra un pipeline completo de Procesamiento del Lenguaje Natural y una interfaz interactiva desarrollada con Gradio.

## Dataset

Se utiliza el dataset:

`KRadim/edit_amazon_reviews_multi_es`

Disponible en Hugging Face. El conjunto contiene aproximadamente 210.000 reseñas de productos en español.

Las calificaciones se transforman en tres clases:

- 1–2 estrellas: negativo;
- 3 estrellas: neutro;
- 4–5 estrellas: positivo.

## Estructura del repositorio

```text
pln-voz-cliente-amazon/
├── notebook/
│   └── Proyecto_Final_PLN_Voz_Cliente_Amazon_ES.ipynb
├── docs/
│   ├── Informe_Proyecto_Voz_del_Cliente.docx
│   └── Presentacion_Proyecto_Voz_del_Cliente.pptx
├── README.md
├── requirements.txt
└── .gitignore
```

## Tecnologías utilizadas

- Python
- Google Colab
- Hugging Face Datasets
- Pandas y NumPy
- Scikit-learn
- TensorFlow/Keras
- Gensim
- Gradio
- Matplotlib

## Técnicas y modelos implementados

### Representación del texto

- Bag of Words
- TF-IDF
- Word2Vec
- Tokenización y capa Embedding

### Modelado

- LDA para descubrimiento de temas
- Naive Bayes como modelo clásico
- LSTM como modelo neuronal
- Detección de aspectos mediante palabras clave

## Resultados principales

| Modelo | Accuracy | Precision macro | Recall macro | F1 macro |
|---|---:|---:|---:|---:|
| LSTM | 0.694 | 0.691 | 0.694 | 0.692 |
| Naive Bayes | 0.685 | 0.688 | 0.685 | 0.686 |

La LSTM obtuvo el mejor desempeño general, aunque Naive Bayes resultó competitivo con un menor costo computacional.

## Instrucciones de uso

### Opción recomendada: Google Colab

1. Abra el archivo ubicado en la carpeta `notebook/`.
2. En Google Colab, seleccione **Entorno de ejecución > Cambiar tipo de entorno de ejecución > GPU**.
3. Ejecute la **Parte A** en orden para:
   - descargar el dataset;
   - realizar el EDA y preprocesamiento;
   - entrenar LDA, Naive Bayes y LSTM;
   - guardar los modelos en Google Drive.
4. Autorice el acceso a Google Drive cuando Colab lo solicite.
5. Compruebe que los modelos se hayan guardado en:

```text
/content/drive/MyDrive/Proyecto_PLN_Amazon/modelos
```

6. Para utilizar la interfaz sin volver a entrenar, ejecute únicamente la **Parte B**:
   - Parte B.1: importación mínima y montaje de Drive;
   - Parte B.2: preprocesamiento;
   - Parte B.3: carga de modelos;
   - Parte B.4: funciones de predicción;
   - Parte B.5: interfaz Gradio.
7. La última celda generará un enlace temporal para abrir la aplicación.

## Instalación local

Para instalar las dependencias:

```bash
pip install -r requirements.txt
```

El notebook fue diseñado principalmente para Google Colab. Si se ejecuta localmente, deben ajustarse las rutas de Google Drive.

## Archivos de modelos

Los modelos entrenados no se incluyen obligatoriamente en el repositorio porque pueden regenerarse ejecutando la Parte A del notebook. También pueden almacenarse en Google Drive para utilizar la Parte B sin repetir el entrenamiento.

## Demostración

La interfaz permite ingresar una reseña y visualizar:

- sentimiento predicho por Naive Bayes;
- sentimiento predicho por LSTM;
- probabilidades por clase;
- tema principal identificado mediante LDA;
- aspectos detectados;
- texto preprocesado.

## Autora

**Jennifer Suarez Gutiérrez**  
Maestría en Ciencia de Datos e Inteligencia Artificial  
Universidad Católica Boliviana San Pablo  
Santa Cruz de la Sierra, Bolivia — 2026
