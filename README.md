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

	`wget https://www.dropbox.com/s/cmq4saduh9gozi9/RFMix_v1.5.4.zip`

 2. Descomprimir archivo RFMix:

	`unzip RFMix_v1.5.4.zip`

 3. Ingresa a directorio con script de analisis poblacional:

	`cd RFMix_v1.5.4/PopPhased/`

 4. Compila el script de analisis poblacional:

	`g++ -Wall -O3 -ftree-vectorize -fopenmp main.cpp getdata.cpp randomforest.cpp crfviterbi.cpp windowtosnp.cpp -o RFMix_PopPhased`

 5. Regresa a directorio principal de RFMix:

	`cd ..`

 6. Prueba si RFMix se ejecuta correctamente:

	`python RunRFMix.py PopPhased ./TestData/alleles1.txt ./TestData/classes.txt ./TestData/markerLocationsChr1.txt - o outputPopPhased`

    

    
    Giddyup
    Reading files
    Number of processors available: 2
    Minimum node size: 1
    Number of SNPs Read: 51231
    Number of SNPs to Exclude: 0
    Number left after pruning: 51231
    Number of windows: 1183
    Creating phasings
    Done creating phasings
    Growing forests
    Applying Conditional Random Fields
    CRF on individual: 0
    CRF on individual: 1
    CRF on individual: 2
    CRF on individual: 3
    CRF on individual: 4
    CRF on individual: 5
    CRF on individual: 6
    CRF on individual: 7
    CRF on individual: 8
    CRF on individual: 9
    Converting Window Calls to SNP Calls and Writing to File
    Cleaning up

