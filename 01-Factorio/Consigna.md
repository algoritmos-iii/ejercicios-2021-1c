# Factorio

Vamos a continuar trabajando con las máquinas del mundo Factorio. En esta ocasión vamos a modelar extractores de carbón, hierro, cintas transportadoras y cajas contenedoras. Los extractores extraen menas, las cintas transportan lo que le pongas encima y las cajas simplemente contienen lo que le depositan.

El objetivo es tener un modelo que soporte los siguientes tres escenarios.


**Primer escenario - Extractor-Caja**: 

![EscenarioExtractorCaja](https://github.com/algoritmos-iii/ejercicios-2021-1c/blob/main/01-Factorio/imagenes/ExtractorCaja.jpg)


En este escenario queremos conectar un extractor de carbón a una caja, extraer una mena y que la misma sea depositada en la caja. Para lograr esto el extractor debe tener energía suficiente (en este caso para la única mena que queremos extraer necesitamos 5 joules) y debe estar conectado a la caja. 
Una vez armado el circuito debemos indicarle al extractor que extraiga.
Finalmente debemos asegurarnos que efectivamente haya quedado una mena en la caja. 


**Segundo escenario - Extractor-Cinta-Caja**: 

![EscenarioExtractorCintaCaja](https://github.com/algoritmos-iii/ejercicios-2021-1c/blob/main/01-Factorio/imagenes/ExtractorCintaCaja.jpg)

Ahora queremos conectar el extractor y la caja a través de una cinta. Para lograrlo debemos conectar el extractor (con energía suficiente) a la cinta y la cinta a la caja.
Una vez que esté todo conectado y preparado deberemos indicarle al extractor que extraiga y a la cinta que transporte lo extraído.
Finalmente debemos asegurarnos nuevamente que efectivamente haya quedado una mena en la caja y que la cinta esté vacía.


**Tercer escenario - Extractor-Extractor-Cinta-Cinta-Caja**:

![EscenarioExtractorExtractorCintaCintaCaja](https://github.com/algoritmos-iii/ejercicios-2021-1c/blob/main/01-Factorio/imagenes/ExtractorExtractorCintaCintaCaja.jpg)

Para este último escenario, queremos agregar un nuevo extractor, pero esta vez de hierro, conectado al circuito anterior a través de una nueva cinta. Para lograrlo debemos conectar el extractor de carbón a la cinta A, el de hierro a la cinta B, la cinta B a la cinta A y la cinta A a la caja.
Luego de conectar todo el sistema, le indicaremos a cada extractor que extraiga y a ambas cintas que transporten su contenido.
Finalmente, debemos asegurarnos que la caja contenga una mena de hierro y una de carbón y que ambas cintas estén vacías.


## Tips de colecciones

**¿Cómo crear una colección ordenada?**

```smalltalk
unaColeccion := OrderedCollection new.
```

**¿Cómo agregarle un objeto a una colección?**

```smalltalk
unaColeccion add: 'Hola'
```

**¿Cómo agregar todos los elementos de una colección a otra colección?**

```smalltalk
otraColeccion := OrderedCollection new.
otraColeccion addAll: unaColeccion
```

**¿Cómo contar la cantidad de elementos que cumplen con cierta condición? Por ejemplo la cantidad de unos que tenemos.**

```smalltalk
unaColeccion count: [ :cadaElemento | cadaElemento = 1 ]
```
