## 🐢 Tarea Práctica: Evolución de Mini-Turtle

**Ejercicio 1: Versión Funcional (Modularidad)**

El objetivo es transformar las funciones sueltas adelante() y abajo() en un paquete Python distribuible llamado mini_turtle. Esto demostrará la separación entre la lógica  y la interfaz pública.

```
  mini_turtle_task/
  ── mini_turtle/
  │   ├── __init__.py
  │   └── drawer_logic.py
  ├── main.py
  ├── pyproject.toml  (opcional)
  └── README.md
```

## Pasos de Implementación
1. Módulo de Lógica (drawer_logic.py): Mueve las funciones y la variable global aquí. Implementa reiniciar() usando global posicion_x.
   
Aquí vive la posición horizontal (posicion_x) y las funciones reales.

```
  # mini_turtle/drawer_logic.py

  posicion_x = 0  # estado global
  def adelante(espacios):
    global posicion_x
    posicion_x += espacios
    print(" " * posicion_x + "----->")

  def abajo():
    # la línea vertical se dibuja donde terminó la horizontal
    print(" " * (posicion_x + 5) + "|")

  def reiniciar():
    global posicion_x
    posicion_x = 0

```

  **Clave para explicar:** posicion_x es un estado global 
global posicion_x permite modificarla desde las funciones

2. Interfaz (__init__.py): Importa las funciones desde drawer_logic para exponerlas. Define __all__.
Este archivo permite que el usuario haga:

```
  from mini_turtle import adelante, abajo, reiniciar

  # mini_turtle/__init__.py

  from .drawer_logic import adelante, abajo, reiniciar

  __all__ = ["adelante", "abajo", "reiniciar"]

```
Qué explicar: __all__ define qué funciones son públicas
El usuario no ve drawer_logic.py


3. Prueba (main.py): Crea un script que importe las funciones, dibuje una escalera, use reiniciar() y dibuje algo nuevo.
Aquí se demuestra que el paquete funciona.

```

  # main.py

  from mini_turtle import adelante, abajo, reiniciar

  # Dibujar una escalera
  adelante(2)
  abajo()
  adelante(2)
  abajo()
  adelante(2)
  abajo()

  print("\nReiniciando...\n")
  reiniciar()

  # Dibujar algo nuevo
  adelante(4)
  abajo()
  
```

Cuando lo expliques, puedes decir: Separé la lógica del dibujo en un módulo interno 
Creé una interfaz limpia para el usuario
Usé estado global controlado
Apliqué modularidad y encapsulación

El paquete es reutilizable y escalable

✨ Resultado visual esperado (ejemplo)

  ----->
       |
    ----->
         |
      ----->
           |

Reiniciando...

    ----->

    
