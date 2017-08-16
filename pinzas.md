# Artículo a comentar:<h1>

## 1) Pinzas termoforéticas para la manipulación de bajo consumo y versátil de células biológicas <h2>
###### Thermophoretic Tweezers for Low-Power and Versatile Manipulation of Biological Cells <h6>

###### [Artículo] (https://www.ncbi.nlm.nih.gov/pubmed/28230355)

Los autores aseguran que:
> "han desarrollado una herramienta termofóretica que permite la manipulación de células biológicas con un poder óptico 100-1000 veces menor que la utilizada en las pinzas ópticas existentes"

__Concepto importante:__ 
**Termoforesis**: *Movimimiento de moléculas (o células) en un gradiente de temperatura (Reichl and Braun, 2014).*

__Ventajas__
* Permiten la manipulación versátil de células para conocer la comunicación o interacciones célula-célula, realizar ensambles celulares, controlar la orientacion de células individuales, etc.
* Dependen del gradiente de temperatura lo que permite crear una trampa estable y segura para la manipulacion de células sin un gran incremento de temperatura.
* Pueden utilizarse tanto en biología celular como en biomedicina.

__Explicación del fénomeno__
![alt text](http://www.usadellab.org/cms/uploads/supplementary/Trimmomatic/TrimmomaticManual_V0.32.pdf)

__Método__
1. Desarrollo del dispositivo de termoforesis (no se podria replicar fácilmente)
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/optical-setup.png)

	* Consiste en una placa de cristal con una capa de 4 nm de nanopartículas de oro donde se coloca una película de agua que contiene las células o partículas a estudiarse.
	* El láser se enfoca a un semiconductor óptico llamado Dispositivo digital de microespejos (DMD) que dirige el láser por un objetivo a la placa de oro.
2. Exclusión del efecto de otros fenómenos físicos sobre su dispositivo
	* Comprobaron que la convección termal no influía:
		* 1) midiendo el movimiento browniano de beads de poliestireno (PS) de diferentes tamaños en función de la temperatura ambiente. Lo cual les arrojo que posicionando el bead a una distancia de 20 micrometros del láser, el gradiente de temperatura era débil y se podía ignorar la termoforesis.
		* 2) reducieron el tamaño de la camára a 20 micrometros para evitar el flujo termal convectivo. Ya que entre más pequeña es, se reduce la brecha entre la partícula atrapada y el sustrato.
		* 3) Suspendieron beads de poliestireno en H2O y D2O para verificar que la convección termal no era la que conducia el atrapamiento.
	* Exclusión de la fuerza óptica relacionada con los plasmones.
		* Calcularon que el gradiente de fuerza óptica que actúa en beads de 500 nm era 4 fN.
		* Experimentalmente obtuvieron que es necesario un gradiente de 170 fN para atrapar los mismos beads. Concluyeron que la fuerza óptica es una contribución ignorable en estás pinzas.
3. Manipulación de células vivas
	* 1) **Manipulacion de levadura** (*no especifícan cual*)
		* formaron la palabra NANO
		* convierten una Y en T
	 ![alt text](https://github.com/LizDG/Bioinformatica/blob/master/nano.png)
		* forman casi un cuadrado de 4 x 4
	![alt text](https://github.com/LizDG/Bioinformatica/blob/master/cua.png)
		* estudiaron la interacción entre dos levaduras
		* controlaron arbitrariamente un ensamble celular
		* manipularon 3 células en una dimensión
		* lograron rotar una levadura
		* lograron rotar un par de levaduras
	![alt text](https://github.com/LizDG/Bioinformatica/blob/master/leva.png)
	* 2) **_Escherichia coli_**
		* Atrapamiento, alineamiento y control de la orientacion
![alt text](https://github.com/LizDG/Bioinformatica/blob/master/coli.png)
4. Simulaciones computacionales
	*En COMSOL solo mencionan las propiedades fisicas que consideraron 

Formas de manipulacion de levadura| **E. coli**
------------ | -------------
palabra nano | no hay más información
Y en T  |
cuadrado de 4 x4 |