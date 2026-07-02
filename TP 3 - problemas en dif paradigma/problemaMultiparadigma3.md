# Gestionar una lista de tareas pendientes (To-Do List)

## Paradigma imperativo

```python
tareas = []

def agregar_tarea(titulo, prioridad):
    tareas.append([titulo, prioridad, False])

def completar_tarea(titulo):
    for tarea in tareas:
        if tarea[0] == titulo:
            tarea[2] = True

def mostrar_pendientes():
    pendientes = []

    for tarea in tareas:
        if not tarea[2]:
            pendientes.append(tarea)

    pendientes.sort(key=lambda t: t[1])

    print(pendientes)

agregar_tarea("Estudiar", 1)
agregar_tarea("Comprar", 3)
agregar_tarea("Entrenar", 2)

completar_tarea("Comprar")

mostrar_pendientes()
```

## Paradigma orientado a objetos

```python
class Tarea:
    def __init__(self, titulo, prioridad):
        self.titulo = titulo
        self.prioridad = prioridad
        self.completada = False

class ListaTareas:
    def __init__(self):
        self.tareas = []

    def agregar(self, titulo, prioridad):
        self.tareas.append(Tarea(titulo, prioridad))

    def completar(self, titulo):
        for tarea in self.tareas:
            if tarea.titulo == titulo:
                tarea.completada = True

    def mostrar(self):
        pendientes = [
            tarea for tarea in self.tareas
            if not tarea.completada
        ]

        pendientes.sort(key=lambda t: t.prioridad)

        for tarea in pendientes:
            print(tarea.titulo)

lista = ListaTareas()

lista.agregar("Estudiar", 1)
lista.agregar("Comprar", 3)
lista.agregar("Entrenar", 2)

lista.completar("Comprar")

lista.mostrar()
```

## Paradigma funcional

```python
def agregar(tareas, titulo, prioridad):
    return tareas + [(titulo, prioridad, False)]

def completar(tareas, titulo):
    return [
        (t, p, True) if t == titulo else (t, p, c)
        for t, p, c in tareas
    ]

def mostrar(tareas):
    pendientes = filter(
        lambda x: not x[2],
        tareas
    )

    return sorted(
        pendientes,
        key=lambda x: x[1]
    )

tareas = []

tareas = agregar(tareas, "Estudiar", 1)
tareas = agregar(tareas, "Comprar", 3)
tareas = agregar(tareas, "Entrenar", 2)

tareas = completar(tareas, "Comprar")

print(mostrar(tareas))
```

## Comparación

| Criterio                      | Imperativo | Objetos | Funcional |
| ----------------------------- | ---------- | -------- | ---------- |
| Claridad y legibilidad        | Alta       | Alta     | Media |
| Nivel de abstracción          | Medio      | Alto     | Alto |
| Eficiencia y rendimiento      | Alta       | Media-Alta | Media |
| Mantenimiento y escalabilidad | Media      | Alta     | Alta |
| Expresividad y concisión      | Media      | Media    | Alta |
