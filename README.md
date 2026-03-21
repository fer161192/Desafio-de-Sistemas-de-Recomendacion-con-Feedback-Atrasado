# Desafio-de-Sistemas-de-Recomendacion-con-Feedback-Atrasado

## Objetivo: 

Predecir la probabilidad de un usuario le de una "recompensa positiva" (Un "like", una compra, un click) a un ítem. 

## Argumento: 

En la vida real, la gente no reacciona al instante. Uno ve un producto hoy, pero quizas se lo compra a los tres días. Este modelo tiene que aprender a predecir ese "Si" basandose en una interacción inicial.u
La salida debe ser un archivo con una probabilidad entre 0 y 1 para cada fila del test.

## Mapa de datos: Como se relacionan?
Para la realización de este problema se cuenta con cuatro datasets (Existe un quinto pero sirve solamente como modo de prueba) que se pueden pensar como una especie de base de datos relacional:

| Dataset | Contenido Clave | Relación |
| :--- | :--- | :--- |
| `users.csv` | Edad, región, dispositivo, nivel de actividad. | Se une a las interacciones por el `user_id`. |
| `items.csv` | Categoría, complejidad, novedad, calidad. | Se une a las interacciones por el `item_id`. |
| `train_interactions.csv` | El "pasado". Tiene el `interaction_time`, el `reward_time` (cuánto tardó en reaccionar) y el `observed_reward` (si fue 1 o 0). | Es tu set para entrenar al "cerebro" del modelo. |
| `test_interactions.csv` | El "futuro". Solo tenés quién interactuó con qué y cuándo. | Aquí es donde tenés que adivinar la probabilidad del reward. |
