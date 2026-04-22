# EJERCICIO-1def validar_jerarquia(cadena):
    pila = []
    pares = {')': '(', ']': '[', '}': '{'}

    for simbolo in cadena:
        if simbolo in "([{":
            pila.append(simbolo)
        elif simbolo in ")]}":
            if not pila:
                return False

            ultimo = pila.pop()
            if ultimo != pares[simbolo]:
                return False

    return len(pila) == 0


# Pruebas
print(validar_jerarquia("[()]"))     # True
print(validar_jerarquia("[(])"))     # False
print(validar_jerarquia(""))         # True
