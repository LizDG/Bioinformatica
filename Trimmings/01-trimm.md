#Uso de trimmings (recortadores) para eliminar secuencias de mala calidad y adaptadores

**Trim galore**
Es un recortador que utiliza una secuencia de comandos para automatizar la calidad de los datos sin procesar.
Para realizar esta práctica, se sugiere crear un directorio de trabajo con el nombre **Trim_galore** y los archivos a editar, para mantener ordenados los archivos que se obtendrán.
Para utilizarlo, en la línea de comandos colocamos: **trim_galore --fastqc --paired --retain_unpaired ../FASTQS/HP_15M_1.fastq ../[nombre de la carpeta con los archivos originales]/[nombre del archivo]**
Las opciones que utilizamos significan:
**- -paired** significa que el programa realizará el recorte de longitud de las lecturas para el par de archivos (ambos archivos están obligados a tener una cierta longitud mínima). Si alguno no cumple, solo se rescata la otra lectura (para eso es la siguiente parte **--retain_unpaired**). Con esta opción se descartan pares de lectura demasiado cortos sin alterar el orden de las secuencias.
Al igual que con FastQC, tenemos las opciones de visualizar los resultados con firefox o con el visor de imágenes (descomprimiendo el archivo .zip).

****

**Trimmomatic**
Dado que es un recortador que funciona con java, debemos tener un directorio con el archivo previamente descargado [de la página oficial, la opción "source"](http://www.usadellab.org/cms/?page=trimmomatic) y nuestros archivos que se editarán. Tomando como ejemplo nuestros archivos 91M_1 y 2, el comando que se pondrá en la terminal queda como sigue:
**java -jar trimmomatic-0.36.jar PE -phread33 HP_91M_1.fastq HP_91M_2.fastq HP_91M_1.Tp.fastq HP_91M_1.Tu.fastq HP_91M_2.Tp.fastq HP_91M_2.Tu.fastq ILLUMINACLIP:TruSeq3-PE.fa:2:30:10 LEADING:3 TRAILING:3 SLIDINGWINDOW:4:15 MINLEN:36**
Las opciones que agregamos significan:
ILLUMINACLIP: Corta el adaptador y otras secuencias específicas de illumina.
LEADING: Corta las bases del comienzo de la lectura, si están por debajo de un umbral de calidad.
TRAILING: Corta las bases del final de la lectura, si están por debajo de un umbral de calidad.
SLIDINGWINDOW: Realiza un corte de "sliding window" cortando una vez que la calidad media cae por debajo del umbral.
MINLEN: Deja la lectura si está por debajo de una longitud especificada.

****
**Dynamictrim**
Este recortador viene como parte del paquete de programas de SOLEXA, por lo que es necesario descargarlo [de la siguiente página](http://solexaqa.sourceforge.net/) y al igual que con el programa anterior, copiar el archivo compatible con el sistema operativo (linux) al directorio con los archivos que se desea editar.
Las instrucciones que debemos colocar en la terminal son:
**./SolexaQA++ dynamictrim [nombre del archivo]**
Lo cual nos dará como resultado la siguiente ventana:
[Dynamictrim resultados](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/20-dynamictrim.png)
