# Actividad-6.1

1
´´´ bash
read -p "Introduce un número entero: " num
if [ $num -gt 0 ]; then
  echo "El número es positivo"
fi
´´´
2
´´´bash
read -p "Introduce un número entero: " num
if [ $num -lt 0 ]; then
  echo "El número es negativo"
fi
´´´
3 
´´´ bash
read -p "Introduce un número entero: " num
if [ $num -eq 0 ]; then
  echo "El número es igual a cero"
fi
´´´
4
´´´ bash
read -p "Introduce un número entero: " num
if [ $num -gt 0 ]; then
  echo "El número es positivo"
elif [ $num -lt 0 ]; then
  echo "El número es negativo"
else
  echo "El número es igual a cero"
fi
´´´
5
´´´
if [ "$#" -ne 3 ]; then
  echo "Error: el número de parámetros introducidos es incorrecto"
  fi
  ´´´
  6 
  ´´´ bash
  if [ $# -eq 2 ]
then
	echo "La suma de los dos números es $(($1 + $2))"
else
	echo "Error: deben haber exactamente dos parámetros"
fi
´´´
7
´´´ bash
if [ $# -eq 3 ]
then
	if [ $3 == "+" ]
	then
		echo "La suma de los dos números es $(($1 + $2))"
	elif [ $3 == "-" ]
	then
		echo "La resta de los dos números es $(($1 - $2))"
	elif [ $3 == "x" ]
	then
		echo "La multiplicación de los dos números es $(($1 * $2))"
	elif [ $3 == "/" ]
	then
		echo "La división de los dos números es $(($1 / $2))"
	else
		echo "Error: el tercer parámetro debe ser uno de los siguientes símbolos: + - x /"
	fi
else
	echo "Error: deben haber exactamente tres parámetros"
fi
´´´
8
´´´ bash
if [ -f $1 ]; then
    echo "El fichero existe"
else
    echo "El fichero no existe"
fi
´´´
9
´´´ bash
if [ -d $1 ]; then
    echo "Es un directorio"
else
    echo "Es un fichero"
fi
´´´
11
´´´ bash
or i in {1..50}; do
    echo "Hola"
done
´´´
12
´´´ bash
for i in {1..10}; do
    read -p "Introduce una palabra: " palabra
    echo $palabra
done
´´´
13
´´´ bash
if [ -z "$1" ]; then
    echo "No se ha especificado un número"
else
    for i in $(seq 1 $1); do
        echo "Hola"
    done
fi
´´´
14
´´´bash
if [ -z "$1" ]; then
    echo "No se ha especificado un número"
else
    for i in $(seq 0 $1); do
        echo $i
    done
fi
´´´
15
´´´bash
if [ -z "$1" ]; then
    echo "No se ha especificado un número"
else
    suma=0
    for i in $(seq 1 $1); do
        suma=$(($suma + $i))
    done
    echo "La suma es: $suma"
fi
´´´
16
´´´bash
if [ $# -ne 2 ]
then 
	echo "Error, necesita dos parametros"
	exit 1
fi
´´´
17
´´´ bash
echo "Introduzca palabras o ':q' para salir"

while read palabra
do
    if [ "$palabra" == ":q" ]
    then
        break
    fi
    echo "$palabra"
done
18
´´´bash
echo "Escribe una palabra (:q para salir):"
read palabra

while [ $palabra != ":q" ]
do
    echo $palabra >> palabras.txt
    echo "Escribe una palabra (:q para salir):"
    read palabra
done
´´´
19
´´´bash
echo "Escriba las palabras que desee, para terminar escriba ':q'"

read palabra

while [ "$palabra" != ":q" ]
do
    echo "$palabra" >> palabras.txt
    sort palabras.txt -o palabras.txt
    read palabra
done
echo "¡Se ha guardado la lista de palabras!"
´´´
20
´´´bash
echo "Introduce un número: "
read numero
if grep -q "$numero" números.txt; then
    echo "El número $numero se encuentra en el archivo números.txt"
else
    echo "El número $numero no se encuentra en el archivo números.txt"
fi
´´´
