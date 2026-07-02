# Ordenar elementos en una colección

## Paradigma imperativo

```python
def ordenar(lista):
    lista = lista.copy()

    for i in range(len(lista)):
        for j in range(i + 1, len(lista)):
            if lista[i] > lista[j]:
                lista[i], lista[j] = lista[j], lista[i]

    return lista

numeros = [7, 2, 9, 5]

print(ordenar(numeros))
```

## Paradigma orientado a objetos

```python
class Coleccion:
    def __init__(self, elementos):
        self.elementos = elementos

    def ordenar(self):
        return sorted(self.elementos)

numeros = Coleccion([7, 2, 9, 5])

print(numeros.ordenar())
```

## Paradigma funcional

```python
def ordenar(lista):
    return sorted(lista)

numeros = [7, 2, 9, 5]

print(ordenar(numeros))
```

## Comparación

| Criterio                      | Imperativo | Objetos    | Funcional  |
| ----------------------------- | ---------- | ---------- | ---------- |
| Claridad y legibilidad        | Media-Alta | Alta       | Alta       |
| Nivel de abstracción          | Medio      | Alto       | Alto       |
| Eficiencia y rendimiento      | Alta       | Media-Alta | Alta       |
| Mantenimiento y escalabilidad | Media      | Alta       | Alta       |
| Expresividad y concisión      | Baja       | Media      | Alta       |
