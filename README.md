## Mi_primera_pagina_personal_Marcela

Bienvenidos a mi primera pagina en GitHUb Pages 
Soy Marcela Muñoz, estudiante del programa desarrollo del software
En esta pagina compartire lo aprendido en clase sobre programacion y el uso de herramientas e inteligencia artificial 

## *Temas vistos en clase*

- Proyecto del software  
- Fundamentos de la programacion  
- Hardware - software  
- Elementos: Variables estructuras datos  
- Controladores flujo  
- Las tablas que implementan la suma aritmetica donde   
*0* es falso 
*1* verdadero

| A | B | Lo que sobra | Suma |
|---|---|---------------|------|
| 0 | 0 | 0             | 0    |
| 0 | 1 | 0             | 1    |
| 1 | 0 | 0             | 1    |
| 1 | 1 | 1             | 0    |

- Programar con la instalacion del aplicativo colaboraty interfaz de colaboracion (Colab)

## *Ejemplo*

print("¡Hola, mundo! Esta es mi primera página en GitHub.")  
nombre = "Marcela"
edad = 39
es_estudiante = True  

print(f"Nombre: {nombre}")
print(f"Edad: {edad}")
print(f"¿Es estudiante?: {es_estudiante}")  

def saludar(nombre):
    return f"Hola, {nombre}. ¡Bienvenido a mi página en GitHub!"

print(saludar("Marcela")) 

## *Reflexión*

Crear esta página me ayudó a comprender cómo se relacionan la programación, la documentación y la publicación web.
Aprendí a organizar proyectos en GitHub y a compartir código de forma sencilla.
También reforcé los conceptos básicos de Python y el uso ético de la inteligencia artificial en el aprendizaje.

## *Referencias de la IA*

- ChatGPT: conversación sobre realizar los primeros pasos de la pagina en Githun (https://chat.openai.com/share/...)
- Copilot: sugerencia de formato Markdown



# Tarea-2---Ejercicios-Unidad-1.

##Actividad

Aprendiendo a programar como una tortuga

import turtle

t = turtle.Turtle()   # Crea una tortuga

t.forward(100)        # Avanza 100 unidades
t.right(90)
t.forward(100)

turtle.done()

<img width="1920" height="1049" alt="image" src="https://github.com/user-attachments/assets/266441c7-74b4-48fb-87ff-f4e3513451db" />


##Reto 1
Intenta recrear el movimiento de la tortuga únicamente con texto, usando funciones, print() y input() para pedir valores al usuario.
def mover_tortuga():
    print("=== Simulación de tortuga ===")
    distancia = int(input("¿Cuántas unidades quieres que avance la tortuga?: "))

    print("\nPosición inicial:")
    print("🐢")

    print("\nTortuga avanzando...\n")
    for i in range(distancia):
        print("-" * i + "🐢")

    print("\nLa tortuga ha terminado su recorrido.")

mover_tortuga()


<img width="1919" height="1047" alt="image" src="https://github.com/user-attachments/assets/9f0e39b9-418c-4d0a-bd5e-22924ba4ef30" />

##Reto2

Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().
La salida esperada es similar a:

tortuga bajando

print("🐢 La tortuga está lista para moverse hacia abajo.")
pasos = int(input("¿Cuántos pasos hacia abajo debe dar la tortuga? "))

print("tortuga bajando...")
for i in range(pasos):
    print("|")
print("🐢")

<img width="1934" height="1044" alt="image" src="https://github.com/user-attachments/assets/474a1f9d-b035-4b93-a2cc-e5f566735de5" />

##Reto 3

Ahora la tortuga no solo avanza: también gira.
Observa cómo lo hace la versión gráfica:

import turtle

t = turtle.Turtle()   

t.forward(100)        
t.right(90)
t.forward(100)

t.left(90)
t.forward(100)       

t.right(90)
t.forward(100)

t.left(90)
t.forward(100)       

t.right(90)     
t.forward(100)
turtle.done()

<img width="1920" height="1047" alt="image" src="https://github.com/user-attachments/assets/8223f762-1b9f-4993-925b-acbc89d7c524" />

##Reto 4

Reescribe los retos anteriores creando funciones que representen los movimientos de la tortuga solo con texto.
Usa las siguientes funciones como interfaz:

# Movimiento hacia la derecha
def adelante(n):
    print("→ " * n)

# Movimiento hacia abajo, alineado con el final del tramo horizontal
def abajo(n):
    espacio = " " * (2 * n - 1)  # Ajusta el espacio para alinear ↓ con la última flecha →
    for _ in range(n):
        print(espacio + "↓")

# Ejemplo de uso
adelante(5)
abajo(3)

adelante(n)   # Dibuja el movimiento hacia la derecha (→) por n pasos
abajo(n)      # Dibuja el movimiento hacia abajo (↓) por n pasos

<img width="1920" height="1047" alt="image" src="https://github.com/user-attachments/assets/7840e8ed-72de-424a-b8cc-a15c5b44d3e2" />


##Reto 5

Ajusta tus funciones para que la tortuga pueda bajar escalones.
Cada escalón debe conservar la posición horizontal acumulada y dibujar correctamente tanto el tramo horizontal como el vertical.

def escalon(aforward, down):
    # Tramo horizontal
    print("→ " * aforward)
    # Tramo vertical
    for _ in range(down):
        print(" " * (forward * 2 - 1) + "↓")

# Programa principal
print("🐢 Simulación de tortuga bajando escalones")
num_escalones = int(input("¿Cuántos escalones debe bajar la tortuga? "))

for i in range(num_escalones):
    print(f"\n# Escalón {i + 1}")
    forward = int(input("  ¿Cuántas unidades hacia adelante? "))
    down = int(input("  ¿Cuántas unidades hacia abajo? "))
    escalon(forward, down)

print("\n✅ La tortuga ha completado su recorrido en escalones.")

<img width="1920" height="1041" alt="image" src="https://github.com/user-attachments/assets/53d2ea60-e133-4345-975b-cf90f881b209" />


## Referencias de IA

En cumplimiento del uso responsable de la inteligencia artificial en el curso, declaro que utilicé herramientas de IA para apoyar la elaboración de esta tarea.

- **ChatGPT**: usado para aclarar dudas sobre los retos, corregir el código de turtle y generar ejemplos de código en texto para la simulación de movimientos.  
- Fecha de uso: (agrega la fecha en que consultaste).  
- Conversación utilizada: (puedes pegar aquí el enlace a esta conversación si lo deseas).

No se utilizó ninguna otra herramienta adicional para la generación del código o el contenido de la entrada.

  
