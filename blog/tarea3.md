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
   ``` 
  Reiniciando...

    ----->

```

**Ejercicio 2: Versión Orientada a Objetos (POO)**

#El objetivo es refactorizar el paquete anterior utilizando Clases y Objetos. Deberá eliminar las variables globales y aplicar Encapsulamiento.

Requerimientos Funcionales
*Clase Turtle: Toda la lógica debe estar dentro de una clase Tortuga.
*Encapsulamiento: El estado (posicion_x) debe ser un atributo de instancia (self.posicion_x), inicializado en 0 en el constructor. Prohibido usar global.
*Interfaz de Objetos: El usuario debe importar la Clase
```
from mini_turtle_oo import Tortuga
```

*Independencia: Se debe poder crear múltiples tortugas (objetos) que mantengan sus posiciones de forma independiente.

 ##Estructura de Archivos##

```
   mini_turtle_oo_task/
  │
  ├── mini_turtle_oo/
  │   ├── __init__.py
  │   └── turtle_class.py
  │
  ├── main.py
  └── README.md   (opcional)

```

## Pasos de Implementación

1. Clase (turtle_class.py): Define class Totuga. Usa __init__ para inicializar self.posicion_x. Convierte las funciones en métodos (usando self).
```
  mini_turtle_oo/turtle_class.py
```
self
```
  # turtle_class.py

  class Tortuga:
    def __init__(self):
        self.posicion_x = 0  # estado encapsulado

    def adelante(self, pasos):
        print(" " * self.posicion_x + "----->")
        self.posicion_x += pasos

    def abajo(self):
        print(" " * (self.posicion_x + 5) + "|")

    def reiniciar(self):
        self.posicion_x = 0
```

  Cumple: 
  self.posicion_x
  Encapsulamiento
  Métodos con self
  Sin variables globales


2. Interfaz (__init__.py): Expone la clase Tortuga.
```
mini_turtle_oo/__init__.py
```
Permite importar la clase directamente.

```

from .turtle_class import Tortuga
__all__ = ["Tortuga"]

```

Funciona: 
from mini_turtle_oo import Tortuga


3. Prueba (main.py): Importante: Crea dos objetos (t1 = Turtle() y t2 = Turtle()). Haz que se muevan distancias diferentes y demuestra que no interfieren entre sí.
```
main.py
```
Independencia entre tortugas 

```
  from mini_turtle_oo import Tortuga

  # Crear dos objetos independientes
  t1 = Tortuga()
  t2 = Tortuga()

  print("Tortuga 1:")
  t1.adelante(5)
  t1.abajo()
  t1.adelante(5)

  print("\nTortuga 2:")
  t2.adelante(10)
  t2.abajo()

  print("\nReiniciando Tortuga 1:")
  t1.reiniciar()
  t1.adelante(5)

```

Cada objeto mantiene su propia posicion_x
