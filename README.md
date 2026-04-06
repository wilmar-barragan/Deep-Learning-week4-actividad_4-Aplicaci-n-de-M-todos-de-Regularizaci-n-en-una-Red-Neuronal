# Deep-Learning-week4-actividad_4-Aplicaci-n-de-M-todos-de-Regularizaci-n-en-una-Red-Neuronal
Evidencia de Overfitting / Underfitting

Análisis y Conclusiones
1. Evidencia de Overfitting / Underfitting

1.2.	En el Modelo Base, al observar las gráficas, se evidencia un overfitting (sobreajuste). La pérdida de entrenamiento (train loss) se acerca a cero continuamente, mientras que la pérdida de validación (val loss) comienza a aumentar de forma sostenida después de ciertas épocas. Esto indica que el modelo está memorizando el ruido de los datos de entrenamiento y perdiendo capacidad predictiva en datos nuevos.
No se observa un underfitting (subajuste) severo inicial porque la red es lo suficientemente compleja como para aprender los patrones rápidamente.

1.3.	Efecto de la Regularización:
En el Modelo Regularizado, la curva de pérdida de validación se mantiene mucho más estable y paralela a la pérdida de entrenamiento a lo largo de las 500 épocas.
La inclusión de penalizaciones L2 forzó a los pesos a mantenerse pequeños, y el Dropout evitó la co-adaptación de neuronas. La métrica de evaluación final (Accuracy) en el conjunto de prueba demuestra empíricamente que el modelo regularizado tiene un impacto positivo en el desempeño real, logrando una mejor tasa de aciertos y una generalización superior.

1.4.	Hallazgos o Dificultades:
Hallazgo: Una red más compleja no siempre es mejor si no está controlada. El modelo base aprendió patrones falsos (ruido). El modelo regularizado demuestra que podemos usar arquitecturas profundas de forma segura si aplicamos restricciones correctas.
Dificultades típicas: Encontrar el equilibrio exacto. Si el factor L2 o la tasa de Dropout son demasiado altos (ej. Dropout > 0.8), el modelo regularizado habría sufrido de underfitting, siendo incapaz de aprender el patrón básico de los datos. Requirió un ajuste sutil (L2 de 0.01 y Dropout de 0.4) para encontrar el balance óptimo (trade-off sesgo-varianza).
