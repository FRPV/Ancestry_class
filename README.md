# Clase de ancestria

## Descripcion

Material de apoyo para la clase de ancestria en la LCG/CCG en Noviembre de 2018

## Pre-requisitos

- OS Linux/UNIX
- Python v.2.7

## Programas a usar

### RFMix

Usa las siguientes lineas de comando para instalar RFMix.
 1. Descarga RFMix:

	wget https://www.dropbox.com/s/cmq4saduh9gozi9/RFMix_v1.5.4.zip

 2. Descomprimir archivo RFMix:

	unzip RFMix_v1.5.4.zip

 3. Ingresa a directorio con script de analisis poblacional:

	cd RFMix_v1.5.4/PopPhased/

 4. Compila el script de analisis poblacional:

	g++ -Wall -O3 -ftree-vectorize -fopenmp main.cpp getdata.cpp randomforest.cpp crfviterbi.cpp windowtosnp.cpp -o RFMix_PopPhased

 5. Regresa a directorio principal de RFMix:

	cd ..

 6. Prueba si RFMix se ejecuta correctamente:

	python RunRFMix.py PopPhased ./TestData/alleles1.txt ./TestData/classes.txt ./TestData/markerLocationsChr1.txt - o outputPopPhased

 


	

