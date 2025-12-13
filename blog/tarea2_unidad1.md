# Tarea 2 - Ejercicios Unidad 1

El objetivo de esta actividad es resolver una serie de desafíos de programación, centrados en la recursión y en simular la lógica de la biblioteca gráfica `turtle`utilizando texto (`print()` e `input()`).

---


## 🐢 Reto 1: Simula el comportamiento de la tortuga

**Enunciado:** Simula el comportamiento de la tortuga usando solo `print()` e `input()`.

### Solución:

```
def simular_avance_tortuga():
    """
    Simula el movimiento de la tortuga hacia adelante usando 
    caracteres de texto. Si la entrada del usuario no es un número válido, 
    usa 50 pasos por defecto.
    """
    
    # Definimos el valor por defecto
    PASOS_POR_DEFECTO = 50
    
    # 1. Pedir al usuario la cantidad de pasos
    entrada = input("¿Cuántos pasos debe dar la tortuga? (Presiona Enter para usar 50 por defecto): ")
    
    # 2. Intentar convertir la entrada a número
    pasos = PASOS_POR_DEFECTO  # Inicialmente, usamos el valor por defecto
    
    if entrada.strip() != "":  # Solo si el usuario escribió algo
        try:
            # Intentamos convertir la entrada a un número entero
            pasos_ingresados = int(entrada)
            
            # Verificamos que sea positivo, si no, se queda con el valor por defecto
            if pasos_ingresados > 0:
                pasos = pasos_ingresados
            else:
                print(f"Número no válido. Usando el valor por defecto de {PASOS_POR_DEFECTO} pasos.")
                
        except ValueError:
            # Si la conversión falla (no es un número), usamos el valor por defecto
            print(f"Entrada no válida. Usando el valor por defecto de {PASOS_POR_DEFECTO} pasos.")
            
    # 3. Construir la representación de texto del avance
    # Se repite el carácter '-' la cantidad de 'pasos'
    simulacion_pasos = '-' * pasos
    
    # 4. Imprimir el mensaje y la simulación
    print(f"\nCreando una tortuga simulada... que da {pasos} pasos.")
    
    # Imprimir la línea de pasos con el indicador de dirección '->' al final
    print(f"{simulacion_pasos}->")

# 5. Llamar a la función para ejecutar la simulación
simular_avance_tortuga()

```

<img width="1283" height="837" alt="image" src="https://github.com/user-attachments/assets/36beca10-980a-42a2-99cf-78d4128bc3c9" />

**Explicacion:** El objetivo es simular el movimiento de una tortuga sin usar gráficos ni la librería turtle, únicamente usando texto en la terminal con print() e interacción con el usuario mediante input().
La tortuga “avanza” mostrando guiones (-) y una flecha (->) que indican la dirección del movimiento.


## 🐢 Reto 2: Crea el rastro de una tortuga moviéndose hacia abajo usando únicamente print() e input().

**Enunciado:** tortuga bajando
     
    def simular_avance_vertical(): 
    print("🐢 La tortuga está lista para moverse hacia abajo.")
    pasos = int(input("¿Cuántos pasos hacia abajo debe dar la tortuga? "))

    print("tortuga bajando...")
    for i in range(pasos):
    print("|")
    print("🐢")

<img width="1327" height="929" alt="image" src="https://github.com/user-attachments/assets/a6280fd7-0897-47cc-b6b3-4d2c79c4817d" />

**Explicacion:** El objetivo de este ejercicio es simular el movimiento vertical de una tortuga hacia abajo usando únicamente print() para mostrar el rastro y input() para recibir la cantidad de pasos desde el usuario.
No se usan gráficos, solo texto en la terminal.

## 🐢 Reto 3: Girar y dibujar usando solo print() e input()

**Enunciado:** Ahora la tortuga no solo avanza: también gira.

    def simular_giro_y_dibujo():
    import turtle

    t = turtle.Turtle()   # Crea una tortuga

    t.forward(100)        # Avanza 100 unidades
    t.right(90)           # Gira 90 grados a la derecha
    t.forward(100)
    turtle.done()


<img width="1476" height="988" alt="image" src="https://github.com/user-attachments/assets/5edae41d-6684-44a1-8a8d-8985c9a4f66a" />

**Explicacion:** El objetivo de este ejercicio es mostrar que la tortuga no solo puede avanzar, sino también girar, permitiendo dibujar trayectorias más complejas combinando movimientos rectos y giros.
En este caso, el movimiento forma una “L” gracias a un giro de 90 grados.


## 🐢 Reto 4: Encapsula los comportamientos anteriores usando funciones

**Enunciado:** representen los movimientos de la tortuga solo con texto.

    def simular_encapsula_tortuga():
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

<img width="1252" height="842" alt="image" src="https://github.com/user-attachments/assets/54c84113-9b74-4ed1-886a-777fc1d5755c" />

**Explicacion:** El objetivo de este reto es encapsular los movimientos de la tortuga en funciones, representando su comportamiento únicamente con texto en la terminal, sin usar gráficos.
Se reutilizan los comportamientos aprendidos en retos anteriores: avanzar y bajar.


## 🐢 Reto 5: La tortuga baja las escalas

**Enunciado:** Cada escalón debe conservar la posición horizontal acumulada y dibujar correctamente tanto el tramo horizontal como el vertical.

    def adelante(espacios):
    print(" " * espacios + "----->")

    def abajo(espacios):
    # La flecha vertical empieza donde termina la horizontal
    print(" " * (espacios + 5) + "|")
    print(" " * (espacios + 5) + "|")
    print(" " * (espacios + 5) + "v")

    escalones = 3
    espacios = 0

    for i in range(escalones):
    adelante(espacios)
    abajo(espacios)
    espacios += 5


<img width="1144" height="895" alt="image" src="https://github.com/user-attachments/assets/2e4c7206-bf4c-4be8-8535-2137f3da5456" />

**Explicacion:** El objetivo de este reto es simular una escalera descendente usando únicamente texto en la terminal, asegurando que cada escalón conserve la posición horizontal acumulada y que se dibujen correctamente los tramos horizontales y verticales.


**Referencia IA**
OpenAI. (2025). ChatGPT [Modelo de lenguaje de gran escala]. OpenAI. https://chat.openai.com/
