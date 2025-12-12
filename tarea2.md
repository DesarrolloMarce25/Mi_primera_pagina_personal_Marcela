#Aprendiendo a programar como una tortuga

# Tarea-2---Ejercicios-Unidad-1.

##Actividad#

Aprendiendo a programar como una tortuga

import turtle

t = turtle.Turtle()   # Crea una tortuga

t.forward(100)        # Avanza 100 unidades
t.right(90)
t.forward(100)

turtle.done()


## Ejercicio 1
**Enunciado:**  
Escribe un programa que…

**Solución en Python:**
```python
print("Hola, mundo")


<img width="1920" height="1049" alt="image" src="https://github.com/user-attachments/assets/266441c7-74b4-48fb-87ff-f4e3513451db" />


##---Reto 1---

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

##---Reto2---

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

##---Reto 3---

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

##---Reto 4---

Reescribe los retos anteriores creando funciones que representen los movimientos de la tortuga solo con texto.
Usa las siguientes funciones como interfaz:

# Movimiento hacia la derecha
def adelante(n):
    print("→ " * n)

# Movimiento hacia abajo, alineado con el final del tramo horizontal
def abajo(n):
    espacio = " " * (3 * n - 1)  # Ajusta el espacio para alinear ↓ con la última flecha →
    for _ in range(n):
        print(espacio + "↓")

# Ejemplo de uso
adelante(5)
abajo(3)

adelante(n)   # Dibuja el movimiento hacia la derecha (→) por n pasos
abajo(n)      # Dibuja el movimiento hacia abajo (↓) por n pasos

<img width="1920" height="1048" alt="image" src="https://github.com/user-attachments/assets/7570c4dc-c10a-49c5-a71f-ae5f7317d407" />




##---Reto 5---

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


## Realice la union de todos los retos 

<img width="1920" height="1040" alt="image" src="https://github.com/user-attachments/assets/7339b280-295c-4574-9b56-e52f778df71c" />

# --- Fragmento 1 ---
def mover_tortuga():
    print("=== Simulación de tortuga ===")
    distancia = int(input("¿Cuántas unidades quieres que avance la tortuga?: "))
    print("\nPosición inicial:\n🐢")
    print("\nTortuga avanzando...\n")
    for i in range(distancia):
        print("-" * i + "🐢")
    print("\nLa tortuga ha terminado su recorrido.")

# --- Fragmento 2 ---
def tortuga_abajo():
    print("🐢 La tortuga está lista para moverse hacia abajo.")
    pasos = int(input("¿Cuántos pasos hacia abajo debe dar la tortuga? "))
    print("tortuga bajando...")
    for i in range(pasos):
        print("|")
    print("🐢")

# --- Fragmento 3 ---
def tortuga_turtle():
    import turtle
    t = turtle.Turtle()
    t.forward(100); t.right(90); t.forward(100)
    t.left(90); t.forward(100)
    t.right(90); t.forward(100)
    t.left(90); t.forward(100)
    t.right(90); t.forward(100)
    turtle.done()

# --- Fragmento 4 ---
def adelante(n): print("→ " * n)
def abajo(n):
    espacio = " " * (3 * n - 1)
    for _ in range(n): print(espacio + "↓")
def movimientos_simples():
    n = int(input("¿Cuántas unidades hacia adelante? "))
    m = int(input("¿Cuántas unidades hacia abajo? "))
    adelante(n)
    abajo(m)

# --- Fragmento 5 ---
def escalon(forward, down):
    print("→ " * forward)
    for _ in range(down):
        print(" " * (forward * 2 - 1) + "↓")
def programa_escalones():
    print("🐢 Simulación de tortuga bajando escalones")
    num_escalones = int(input("¿Cuántos escalones debe bajar la tortuga? "))
    for i in range(num_escalones):
        print(f"\n# Escalón {i + 1}")
        forward = int(input("  ¿Cuántas unidades hacia adelante? "))
        down = int(input("  ¿Cuántas unidades hacia abajo? "))
        escalon(forward, down)
    print("\n✅ La tortuga ha completado su recorrido en escalones.")

# --- Menú principal con diccionario ---
def menu():
    opciones = {
        "1": mover_tortuga,
        "2": tortuga_abajo,
        "3": tortuga_turtle,
        "4": movimientos_simples,
        "5": programa_escalones
    }

    while True:
        print("\n=== MENÚ PRINCIPAL ===")
        print("1. Mover tortuga hacia adelante")
        print("2. Tortuga bajando")
        print("3. Dibujo con turtle")
        print("4. Movimientos simples (→ y ↓)")
        print("5. Simulación de escalones")
        print("6. Salir")

        opcion = input("Selecciona una opción: ")

        if opcion == "6":
            print("👋 Saliendo del programa...")
            break
        elif opcion in opciones:
            opciones[opcion]()  # ejecuta la función correspondiente
        else:
            print("❌ Opción inválida, intenta de nuevo.")

# --- Ejecutar ---
menu()


## Referencias de IA

En cumplimiento del uso responsable de la inteligencia artificial en el curso, declaro que utilicé herramientas de IA para apoyar la elaboración de esta tarea.

- **ChatGPT**: usado para aclarar dudas sobre los retos, corregir el código de turtle y generar ejemplos de código en texto para la simulación de movimientos.  
- Fecha de uso: (agrega la fecha en que consultaste).  
- Conversación utilizada: (puedes pegar aquí el enlace a esta conversación si lo deseas).

No se utilizó ninguna otra herramienta adicional para la generación del código o el contenido de la entrada.
