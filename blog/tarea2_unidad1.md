# Esto es Front Matter y es opcional, pero recomendado para blogs Jekyll
# Si tu tema de GitHub Pages usa Jekyll (títulos, fechas, layouts), es necesario.
# Si solo usas Markdown básico, puedes omitirlo o dejarlo vacío.
layout: post  # Usa 'post' si es un blog
title: "Tarea 2 - Ejercicios Unidad 1"
date: 2023-10-27 10:00:00 -0500 # Ajusta la fecha actual
categories: [Programación] # Opcional
---

# Tarea 2 - Ejercicios Unidad 1

El objetivo de esta actividad es resolver una serie de desafíos de programación, centrados en la recursión y en simular la lógica de la biblioteca gráfica `turtle` de Python utilizando solo texto (`print()` e `input()`).

---

## 🐢 Reto 1: Simula el comportamiento de la tortuga

**Enunciado:** Simula el comportamiento de la tortuga usando solo `print()` e `input()`. [...]

### Solución en Python:

```python
def simular_avance_tortuga(pasos_simulados):
    """
    Simula el avance de la tortuga hacia la derecha usando texto.
    """
    print("Creando una tortuga simulada...", end="")
    print(f" que da {pasos_simulados} pasos.", end=" ")
    print("-" * pasos_simulados + ">")

if __name__ == "__main__":
    # Puedes usar un valor fijo o el input()
    simular_avance_tortuga(50)
