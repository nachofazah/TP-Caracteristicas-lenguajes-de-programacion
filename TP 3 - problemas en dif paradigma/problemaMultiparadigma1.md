# Buscar en una colección



## Paradigma imperativo

```python
def buscar(lista, objetivo):
    for elemento in lista:
        if elemento == objetivo:
            return True
    return False

numeros = [7, 2, 9, 5]

print(buscar(numeros, 9))
```

## Paradigma orientado a objetos

```python
class Coleccion:
    def __init__(self, elementos):
        self.elementos = elementos

    def buscar(self, objetivo):
        return objetivo in self.elementos

numeros = Coleccion([7, 2, 9, 5])

print(numeros.buscar(9))
```

## Paradigma funcional

```python
def buscar(lista, objetivo):
    return any(map(lambda x: x == objetivo, lista))

numeros = [7, 2, 9, 5]

print(buscar(numeros, 9))
```

## Comparación

| Criterio                      | Imperativo | Objetos    | Funcional |
| ----------------------------- | ---------- | --------   | ----------|
| Claridad y legibilidad        | Alta       | Alta       | Media     |
| Nivel de abstracción          | Bajo       | Medio      | Alto      |
| Eficiencia y rendimiento      | Alta       | Media-Alta | Media     |
| Mantenimiento y escalabilidad | Alta       | Alta       | Alta      |
| Expresividad y concisión      | Media      | Media      | Alta      |
