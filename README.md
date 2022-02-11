"Bucle while"
#Trozo de codigo que se repite n-veces, el bucle While no sepamos la cantidad de interaciones que vayamos a implementar
#El bucle while se apoyará de una condición al igual que el if,por lo que podemos agregar else
import math

numero=int(input("Digite un número: "))

while numero<0: #condición
    print("Error -> Deberia ser un numero positivo")
    numero = int(input("Digite un número: "))
print(f"Su raíz cuadrada es : {(math.sqrt(numero)):.2f}")


#mostrar cierto mensaje n-veces
i= 0
while i<10:
    print("Hola mundo")
    i+=1

#Mostrar los números del 0 al 9

j=1
while j<=10:
    print(j)
    j+=1


"Bucle for"
#sabemos cuantas veces se va a repetir
#recorre la coleccion elemento por elemento
#Iteramos sobre cada uno de los elementos de la colección
for i in [1,2,3,4,"Alejandro"]: #necesitamos un interador (variable), 'in' y una colección
    print(f"Elemento {i}")

#se pude trabajar con listas, tuplas, conjuntos
coleccion1={"Lalo":22, "Maria":23, "Luis":30}
for i in coleccion1:
    print(f"Elemento: {i}") #muestra solo la clave

coleccion2={"Lalo":22, "Maria":23, "Luis":30}
for i in coleccion2:
    print(f"{coleccion2[i]}") #mostrar el valor
    print(f"{i}->{coleccion2[i]}")#mostrar clave y valor en una misma muestra

#Otra forma de utilizar for
coleccion3={"Lalo":22, "Maria":23, "Luis":30}
for clave, valor in coleccion3.items():
    print(f"{clave}-> {valor}")

#Recorrer cadenas
col="Alejandro"
for i in col:
    print(f"Hola")
    print(f"{i}") #imprime elemento por elemento
#Imprimir mi nombre letra por letra pero sin saltos de linea, que cada letra este separado pero e una misma linea
col1= "Patricia"
for i in col1:
    print(f"{i}",end=" ")

#Bucle for tipo range
#range nos ayuda a hacer la cantidad de repeticiones que queremos sin necesidad e hacer una colección
for i in range(50):
    print(i)

#Mostrar numeros del 5 al 10
for i in range(5,11):
    print(i)

#Mostrar numeros pares del 2 al 20
for r in range(2,21,2): #rango , y de cuanto en cuanto va
    print(r)

for r in range(20,1,-2): #rango , y de cuanto en cuanto va
    print(r)


#Instrucción continue y break (Se utliza en cualquier bucle)
#continue: va obviar ese elemnto cuando la instrución es vedadera y sigue con el programa
for i in range(10):
    if i==5:
        continue
    print(i)
#break: rompe el bucle for, para el programa
for i in range(10):
    if i==5:
        break #rompe o termina la condicion de nuestra condicion if
    print(i)

"EJERCICIOS"

#1)Llenar una lista con los números del 1 al 50, luego mostrar la lista con un bucle for los elemenos deben mostrarse de la siguiente forma:-2,-3,-4,...-50
r=list(range(1,51))
for r in r:
    print(f"{r}", end="-")


#2 Llenar una lista del 1 al 10, luego modificar los elementos de la lista multiplicandolos por un valor que el usuario digite
j=list(range(1,11))
for i in j:
    print(i, end=" ")

n=int(input("\n Digite un número: "))
indice=0
for i in j:
    j[indice]*=n
    indice+=1

print(f"Nueva lista de elementos modificados por {n}")
for i in j:
    print(i, end=" ")

#3) Pide un número y metelos en una lista, cuando el usuario digite un 0 dejaremos de insetar, por ultimo mostrar los elementos de menor a mayor
lista =[]
salir= False
while not salir:
    n = int(input("\n Digite un número: "))
    if n==0:
        salir= True
    else:
        lista.append(n)
lista.sort()
print(f"La lista ordenada: \n {lista}")


#4) Hacer un programa para sumar numeros pares dentro de un rango
a=int(input("Digite de donde va empezar a sumar"))
b=int(input("Digite donde va terminar de sumar"))
suma=0
for i in range(a,b+1):
    if i%2==0: # si el numero es par
        suma+=i

print(f"\n la suma es : {suma}")


#5) Hacer un programa del factorial de un número
a=int(input("Digite un número positivo"))
multiplicacion=1
for i in range(1, a+1): #ya está recorriendo todos los valores de 1 hasta a+1
    multiplicacion*=i

print(f"El factorial de {a} es : {multiplicacion}")


#6) Hacer un programa que pida numero por teclado y guarde en una lista su tabla de multiplicar hasta 10
a=int(input("Digite un número positivo"))

lista=[]
for i in range(1,11):
    lista.append(i*a)

print(f" La tabla del {a} es \n {lista}")

#7)Generar un numero aleatorio entre 0 y 100, luego ir pidiendo numeros indicando es mayor o menor segun sea mayor o menor respecto a 'n' , el proceso termia cuando el usuario acierta y mostrar el numero de intentos
aleatorio= random.randint(0,100) #nos genera un numero aleatorio entero

contador=0
while True: #bucle indeterminadi de iteraciones
    c = int(input("Digite un número"))
    contador+=1
    if c>aleatorio:
        print(f"\t No es el número, digite número menor")
    elif c < aleatorio:
        print(f"\t No es el número, digita un número mayor")
    else:
        print(f"\t Felicidades, acabas de adivinar el número {aleatorio}")
        break
print(f"\t Numero de intentos: {contador}")

#8) Hacer un programa que simule un cajero automático con saldo inicial de 1000 y tendrá el siguiente menú de opciones:
#a) ingresar dinero a la cuenta
#b retirar dinero de la cuenta
#c) mostrar dinero disponible
#d) salir

saldo=1000
while True:
    print("\t.:MENU:.")  # Decoracion
    print("1. Ingresar dinero en la cuenta ")
    print("2. Retirar dinero de la cueta ")
    print("3. Mostrar saldo disponible")
    print("4. Salir")
    opcion = int(input("Digite una opcion deñ menu"))

    print()  # salto de linea

    if opcion == 1:
        extra = float(input("Cuanto dinero desea ingresar ->"))
        saldo += extra
        print(f"Dinero en la cuenta: {saldo}")
    elif opcion == 2:
        retirar = float(input("Cuanto dinero desea rertirar ->"))
        if retirar > saldo:
            print("No tiene esa cantidad de dinero")
        else:
            saldo -= retirar
            print(f"Dinero en la cuenta :{saldo}")
    elif opcion == 3:
        print(f"Dinero en la cuenta: {saldo}")
    elif opcion == 4:
        print("Gracias por utilizar su cajero automatico")
        break
    else:
        print("Error, se equivocó de opción de menú")

#9)Hacer un programa donde el usuario ingrese una frase, se le devolverá la misma frase pero sin espacios en blanco ademas de un contador de cuantos caracteres tiene la frase
frase = input("Ingrese una frase:")
frase2= "" #Variable que almacena la frase origina pero quitandole los espacios

for i in frase: #Este ciclo nos ayuda a recorrer la frase, es decir, quitarle los espacios. el interador 'i' recorrer caracter por caracter
    if i!= " ": #Si el iterador 'i' es diferente de un espacios lo concatenamos con frase2
        frase2+=i

frase=frase2
print(f"La frase final es :{frase}")
print(f"Numero de caracteres es : {len(frase)}")

#10) Hacer un programa que pida una cadena por teclado,luego meta los caracteres en una lista sin repetir caracteres
frase0 = input("Ingrese una cadena:")
lista= []

for i in frase0: #'i' recorre caracter por caracter
    if i not in lista: #caracteres que aun no estan en la lista y
        lista.append(i) #agrega los caracteres a la lista

print(f"\n La lista sin repeticón de caracteres es :{lista}")


#11) Hacer un programa que simule una agenda de contactos. Crear un diccionario donde la clave sea el nombre y el valor el teléfono. Programa con el siguiente menú
#1)nuevo contacto
#2) Borrar contacto
#3) Ver contactos existentes
#4) salir

Agenda= {}
while True:
    print("\t.:MENU:.")  # Decoracion
    print("1. Nuevo cntacto ")
    print("2. Borrar contacto ")
    print("3. Ver contactos existentes")
    print("4 Salir")
    opcion = int(input("Digite una opción del menu"))

    print()

    if opcion==1:
        nombre=input("Nombre del contacto:")
        telefono=input("Número del telefono")

        if nombre not in Agenda:
            Agenda[nombre]=telefono
            print("Contacto agregado!")
        else:
            print("Ese nombre ya existe ")

    elif opcion==2:
        nombre = input("Nombre del contacto:")

        if nombre in Agenda:
            del(Agenda[nombre])
            print("Contacto eliminado!")
        else:
            print("Ese contacto no existe ")

    elif opcion==3:
        print("Agenda de contactos ")
        for clave, valor in Agenda.items():
            print(f"Nombre: {clave}, Telefono:{valor}")
    elif opcion==4:
        print("Gracias por utilizar su agenda de contactos")
        break
    else:
        print("Se equivoco de opción de menu")
