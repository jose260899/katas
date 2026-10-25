# DataProject - Katas de Python

Proyecto del módulo de Python del curso de Data Analytics. 41 katas y ejercicios prácticos de Python para afianzar la lógica de programación, el manejo de estructuras de datos, funciones de orden superior, excepciones y programación orientada a objetos.

## Estructura

- `README.md` esto
- `katas.ipynb` el notebook con los enunciados y las resoluciones de las katas

## Cómo lo he hecho

Antes de tirarme a escribir código me puse a revisar el bloque de ejercicios, sobre todo para identificar cuáles requerían funciones específicas de orden superior (`map`, `filter`, `reduce`) o expresiones `lambda` que al principio suponen un cambio de mentalidad frente a otros lenguajes.

Luego fui haciendo las katas por bloques. Empecé por las funciones más sencillas con diccionarios, bucles y gestión de excepciones (como la división por cero o validación de rangos de edad), y fui subiendo el nivel hacia la programación funcional, funciones anónimas y el diseño de clases (`Arbol`, `UsuarioBanco`).

Cada ejercicio lo he probado y validado ejecutándolo en el notebook, comprobando no solo que no diera errores de sintaxis, sino que los inputs y outputs tuvieran sentido (por ejemplo, validando los casos límite en los filtros o el comportamiento de las excepciones personalizadas).

## Cosas a tener en cuenta al corregir / decisiones que he tomado

- Uso `isinstance(x, int) and not isinstance(x, bool)` en la kata 20 para filtrar enteros puros, ya que en Python los booleanos (`True`/`False`) son subclases de `int` y de otra forma se colarían.
- En las funciones que emplean `reduce` (katas 17, 22, 23 y 24), es obligatorio importar previamente `from functools import reduce`.
- Para la kata de gestión de un banco (`UsuarioBanco`), las transferencias comprueban primero si el usuario origen tiene suficiente saldo mediante el método de retirada, lanzando una excepción controlada si no es posible para evitar estados inconsistentes.
- En la clase `Arbol`, el manejo de las posiciones de las ramas para eliminarlas utiliza índices basados en 0 (`0-based`), tal como se espera de una estructura de lista estándar en Python.

## Análisis rápido de los códigos y pruebas

Probé las funciones clave con diferentes juegos de datos en local para asegurar su robustez:

- Las funciones con `map` devuelven listados transformados correctamente y limpian iterables sin alterar los tipos de datos originales.
- Las validaciones con `try-except` capturan de forma limpia errores de tipo (`ValueError`) y divisiones inválidas (`ZeroDivisionError`).
- Las clases orientadas a objetos mantienen el estado interno de forma correcta a lo largo de los casos de uso solicitados (crecimiento de tronco, ramas y gestión de saldos bancarios).

## Autor

Jose Antonio Ayala Farell