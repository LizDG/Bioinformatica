#**Uso de FastQC para visualizar y evaluar la  calidad de secuencias**#

######FastQC tiene como objetivo proporcionar una rápida impresión y un primer control de calidad de los datos de secuencias sin procesar para asegurar que no tienen problemas o sesgos que puedan afectar los estudios que se realizarán.######

Para realizar esta práctica, se sugiere crear un directorio de trabajo para mantener ordenados los archivos obtenidos. Como primer paso moveremos nuestras 6 secuencias a esta carpeta.
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/01-directorio.png)

###Abriendo la secuencia con FastQC###
#####*Opción 1.*#####
En la terminal tecleamos **fastqc &**, lo que nos abrirá la interfaz gráfica del programa. Para seleccionar nuestra secuencia, vamos a la esquina superior izquierda  **file, open** y seleccionamos nuestro archivo.
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/02-grafica.png)
Al terminar el proceso veremos en pantalla algo como lo siguiente:
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/04-infor-secuencia.png)

#####*Opción 2.*#####
En la terminal tecleamos **fastqc [y el nombre de nuestro archivo]**, tomando como ejemplo el primer archivo con el que trabajaremos, llamado HP_91M_1.fastq, tecleamos **fastqc HP_91M_1.fastq &** y veremos en la terminal como el proceso se esta llevando a cabo.
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/03-fastqc.png)

Cuando el proceso termine, veremos un archivo .zip (que deberemos descomprimir) y un archivo .html. Por lo tanto, tenemos dos opciones para visualizar los resultados:
* a) Descomprimiendo los archivos del zip, entrando a la carpeta **Images** y utilizando el visualizador de imágenes, con el siguiente comando **eog [nombre de la imagen.png] &**
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/05-eog-use.png)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/06-eog-view.png)

* b) Utilizando el archivo .html, tecleando **firefox [nombre del archivo.html]**
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/07-firefox.png)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/08-firefox2.png)

###Visualizando la secuencia###
Sea cual sea la opción que se elija, FastQC tiene diferentes "pestañas" que nos dan la siguiente información:
* Basic stadistics (Datos básicos) podemos ver:
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/08-firefox2.png)
Nombre del archivo: HP_91_M_1.fastqc
Formato de archivo: convencional
Sistema usado: Sanger / Illumina 1.9
Total de secuencias analizadas: 91069 (es el número de lecturas analizadas)
Secuencias marcadas con mala calidad: 0 (esto debes decidirlo en base a los gráficos que vienen más adelante)
Longitud de cada lectura: 100 bases
% GC: 64%

* Per base sequence quality (Calidad (Q) de las secuencias por base)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/09-per-base.png)
En amarillo están representados los cuartiles, la línea azul es la mediana y en rojo, la media de la calidad. En el eje X, se representa las bases de las lecturas y cada lectura tiene 97 bases. Mientras que en el Y, se representan las calidades de 0 a 40.
La zona verde: corresponde lecturas de muy buena calidad.
La zona naranja: es la zona de calidad intermedia.
La zona roja: es la zona de mala calidad.
* Per tile sequence quality (Calidad de la secuencia por "baldosa")
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/10.png)
Aquí solo aparece un gráfico si se usa una biblioteca de Illumina, que nos muestra las células de flujo (flow cell), canales donde se pone la secuencia. Este gráfico permite buscar en las puntuaciones de calidad de cada pieza a través de todas sus bases para ver si hubo una pérdida de calidad asociada con sólo una parte de la célula de flujo.
Podemos inferir que no hubo problemas en el flow cell, ya que no nos aparece ningún gráfico.
* Per sequence quality scores (Niveles de calidad por secuencia)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/11.png)
En el eje X se representa la media de la calidad de las secuencias. Mientras que en el eje Y, se representa el numero se secuencias o lecturas al que corresponde esa media. Nos da una idea de cuantas lecturas es necesario retirar ya que tienen valores con baja calidad.
* Per base sequence content (Contenido de la secuencia por base)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/12.png)
Nos indica la proporción de cada una de las bases que hay en la secuencia. En una biblioteca aleatoria, no debería de haber apenas diferencias entre las bases de una secuencia de ejecución, por lo que las líneas deberían correr paralelas entre sí.
* Per sequence GC content (Contenido en guanina y citosina (GC) por secuencia)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/13.png)
Este módulo mide el contenido de GC de toda nuestra secuencia (línea roja) y lo compara con una distribución normal teórica del contenido de GC (línea azul). En el eje X se muestra el porcentaje medio del contenido de G y C. Mientras que en el Y se muestra el número de lecturas.
* Per base N content (Contenido de N por base)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/14.png)
Este apartado nos indica el contenido de bases que tienen una N (base no asignada).
*Sequence Length Distribution (Distribución de la longitud de las secuencias)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/15.png)
Este módulo genera un gráfico que muestra la distribución de tamaños de los fragmentos en el archivo que se analizó.
* Sequence Duplication Levels (Niveles de secuencias duplicadas)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/16.png)
Este módulo cuenta el grado de duplicación para cada secuencia en una biblioteca y crea un gráfico que muestra el número relativo de secuencias con diferentes grados de duplicación.
* Overrepresented sequences (Secuencias sobrerepresentadas)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/17.png)
muestra la valoración del número de secuencias que me salen a la hora de mapear (uso un transcriptoma de referencia y busco alineamiento por homología) que me pueden dar problemas cuando intento hacer un ensamblado.
* Adapter Content (Contenido de adaptadores)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/18.png)
Una clase obvia de secuencias que es posible que se desee analizar son las secuencias adaptadoras. Es útil saber si la biblioteca contiene una cantidad significativa de adaptadores para poder evaluar si necesita adaptador de ajuste o no. Por lo tanto, este módulo se hace una búsqueda específica para un conjunto de Kmers definidos por separado y le dará una vista de la proporción total de su biblioteca que contiene estos Kmers.
* Kmer Content
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/Fastqc/19.png)
Este apartado nos indica subfragmentos de ADN de un tamaño determinado.


Información obtenida de: 
[Control de calidad de la secuenciación](https://sites.google.com/site/b22aggoabms1516/home/analisis-de-la-calidad-de-la-secuenciacion-de-un-archivo-de-secuencias-fastq-obtenido-con-la-plataforma-illumina)