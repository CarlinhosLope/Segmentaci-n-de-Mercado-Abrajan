# Segmentación de Clientes con K-Means Clustering

## Descripción del Proyecto
Este proyecto implementa un modelo de Machine Learning no supervisado (K-Means Clustering) para segmentar a los clientes de un centro comercial en grupos con características similares de comportamiento de compra.

## Propósito
Ayudar al área de marketing a identificar grupos de clientes para diseñar estrategias personalizadas como promociones, descuentos y campañas dirigidas a cada perfil, optimizando los recursos de la empresa.

## Contexto Empresarial
Un centro comercial con más de 200,000 registros de clientes necesita optimizar sus recursos de marketing. En lugar de enviar la misma oferta a todos, este modelo identifica distintos tipos de clientes con comportamientos diferentes, permitiendo tomar decisiones basadas en datos y mejorar la competitividad del negocio.

## Funcionalidades del Proyecto
1. Carga y limpieza de la base de datos
2. Aplicación del algoritmo K-Means
3. Determinación del número óptimo de clusters mediante el método del codo
4. Visualización de los segmentos
5. Generación de perfiles de cliente
6. Búsqueda de clientes por ID

## Estructura del Proyecto
Segmentacion-de-Mercado-Abrajan/
│
├── data/
│ └── mall_customers_200k.csv
│
├── images/
│ ├── elbow_method.png
│ ├── clusters.png
│
├── Segmentación.ipynb
├── requirements.txt
└── README.md
## Requisitos
- Python 3.8 o superior
- Jupyter Notebook o Google Colab

## Instalación
Instalar dependencias con:
pip install pandas numpy matplotlib seaborn scikit-learn o 
O usando requirements.txt: pip install -r requirements.txt
## Uso
1. Clonar el repositorio: git clone https://github.com/tu-usuario/segmentacion-abrajan.git
2. Entrar al directorio: cd segmentacion-abrajan
3. Ejecutar Jupyter Notebook: jupyter notebook
4. Abrir el archivo Segmentación.ipynb  
5. Ejecutar las celdas en orden  

## Parámetros Modificables
- n_clusters: define cuántos grupos se generan. Un valor incorrecto puede generar segmentos poco útiles o sobreajuste.
- Variables seleccionadas: determinan el criterio de segmentación. Cambiar variables cambia completamente los resultados.
- Escalado: evita que variables con mayor magnitud dominen el modelo.
- PCA: reduce dimensiones y facilita visualización, pero puede perder información.

Ejemplo: kmeans = KMeans(n_clusters=5, random_state=42)

## Ejemplos de Uso

Aplicación de K-Means: Este código entrena el modelo K-Means con 5 clusters:
from sklearn.cluster import KMeans

kmeans = KMeans(n_clusters=5)
kmeans.fit(X)
labels = kmeans.labels_

Método del codo:
inertia = []
for k in range(1, 10):
kmeans = KMeans(n_clusters=k)
kmeans.fit(X)
inertia.append(kmeans.inertia_)

Visualización:
plt.scatter(X_pca[:,0], X_pca[:,1], c=labels)
plt.title("Segmentación de Clientes")
plt.show()

### Resultados

## Método del codo
El método del codo permitió identificar el número óptimo de clusters para el modelo. Se observa un punto donde la disminución de la inercia comienza a estabilizarse, indicando que agregar más clusters no aporta mejoras significativas. En este caso, se seleccionó un valor adecuado de clusters para lograr una segmentación eficiente sin sobreajuste.
![Método del Codo](imágenes/ElbowMethod.png)
## Segmentación de clientes
La gráfica de clusters muestra la distribución de los clientes en distintos grupos, donde cada color representa un segmento diferente. Esto permite visualizar cómo se agrupan los clientes según sus características.
![Clusters](imágenes/Clusters.png)
Segmentación por Spendig Core:
![Segmentación](SegmentacióndeMercadoSpendigScore.png)
Métricas de Validación:
![Validación del Modelo K-Means](imágenes/MétricasdeValidación.png)

## Análisis de segmentos

A partir del modelo de K-Means, se identificaron distintos perfiles de clientes:

- **Cluster 1:** Clientes con alto ingreso y alto nivel de consumo. Representan un segmento estratégico para programas de fidelización.
- **Cluster 2:** Clientes con ingreso medio y consumo frecuente. Son ideales para promociones regulares.
- **Cluster 3:** Clientes con bajo ingreso y bajo consumo. Representan un segmento sensible al precio.
- **Cluster 4:** Clientes con alto ingreso pero bajo consumo. Oportunidad para incentivar compras.
- **Cluster 5:** Clientes con comportamiento intermedio. Segmento mixto con potencial de crecimiento.

---

### Datos procesados
Se realizó una limpieza y transformación de los datos para asegurar la calidad del análisis, incluyendo selección de variables relevantes y normalización.


### Conclusión
El modelo de segmentación permite identificar patrones de comportamiento en los clientes, facilitando la toma de decisiones estratégicas basadas en datos. La correcta selección de variables y parámetros es fundamental para obtener resultados útiles en un contexto empresarial real.


## Interpretación de Resultados
El modelo identifica diferentes perfiles de clientes, como clientes de alto valor, frecuentes, ocasionales y de bajo consumo.

## Tecnologías Utilizadas
- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

## Conclusión

El modelo de segmentación permite identificar patrones de comportamiento en los clientes, facilitando la toma de decisiones estratégicas basadas en datos. La correcta selección de variables y parámetros es clave para obtener resultados útiles en un contexto empresarial.
