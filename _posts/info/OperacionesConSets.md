
## Operaciones útiles con sets

Las siguientes son operaciones que pueden resultar útiles par le manejo de sets tanto en las ecuaciones como fuera de ellas, en cada caso se presenta la definición de cómo usarlo y un ejemplo aplicado al modelo.

Las descripciones están hechas suponiendo que se usa un modelo/instancia *m* y un set *s*. En los ejemplos aplicables al modelo se usa el set *gts* y la instancia *instance*. <br>
En caso de usar un modelo concreto *m* usar la sintaxis *m.s*. <br>
En caso de usar un modelo abstracto *m*, en la definición de las ecuaciones usar *m.s*, y una vez instanciado el modelo *m* con unos datos en la instancia *i*, usar *i.s*.

1. **Elementos** de un set en formato lista de python.
	```python
	list(m.s)
	list(instance.gts)
	```
2. **Elementos** de un set en formato set de python.
	```python
	m.s.value
	instance.gts.value
	```
3. **Valor** concreto de una posición de un set. <br>
    *pos*: posición, empieza en 1.
	```python
	m.s[pos]
	instance.gts[3]
	```
4. **Primer** elemento de un set.
	```python
	m.s.first()
	instance.gts.first()
	```
5. **Último** elemento de un set.
	```python
	m.s.last()
	instance.gts.last()
	```
6. **Índice** de un elemento en un set (el índice del último es la longitud). <br>
    *e*: elemento del set para el cual se quiere el índice.
	```python
	m.s.ord(e)
	instance.gts.ord(instance.gts.last())
	```
7. Elemento **siguiente/anterior** en forma lineal o circular. <br>
    *next*: siguiente en modo lineal (el ultimo no tiene siguiente). <br>
    *nextw*: siguiente en modo circular (el primero sigue al último). <br>
    *prev*: siguiente en modo lineal (el ultimo no tiene siguiente). <br>
    *prevw*: siguiente en modo circular (el último es el anterior al primero). <br>
    *k*: número de elementos a avanzar/retroceder, por defecto k=1. <br>
    *e*: elemento del set.
	```python
	m.s.next(e,k=paso)
	instance.gts.next(instance.gts.first(),k=1)
	```
8. **Eliminar** un elemento de un set. <br>
    *e*: elemento a eliminar del set.
	```python
	m.s.remove(e)
	instance.gts.remove(instance.gts.last())
	```
9. **Añadir** un elemento a un set. <br>
    *e*: nuevo elemento del set.
	```python
	m.s.add(e)
	instance.gts.add('g7')
	```