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
| `users.csv` | Edad (age), región (region), dispositivo (device), nivel de actividad (activity_level). | Se une a las interacciones por el `user_id`. |
| `items.csv` | Categoría (category), complejidad (complexity), novedad (novelty), calidad (quality). | Se une a las interacciones por el `item_id`. |
| `train_interactions.csv` | `interaction_time`: Marca de tiempo de la interacción; `reward_time`: cuánto tardó en reaccionar; `observed_reward`: Resultado observado (1 = recompensa positiva, 0 = ninguna recompensa). | Es tu set para entrenar al "cerebro" del modelo. |
| `test_interactions.csv` | El "futuro". Solo tenés quién interactuó con qué y cuándo. | Aquí es donde tenés que adivinar la probabilidad del reward. |
