# Servicios financieros

## Transferencias

Un banco quiere empezar a ofrecer nuevos servicios a sus clientes, por lo que nos contrató para extender su actual sistema.

Actualmente se cuenta con un modelo bancario simple, formado por cuentas bancarias y transacciones de depósito y retiro. El mismo se puede cargar haciendo file-in de ServiciosFinancieros-Ejercicio.st.

El primer servicio a implementar consiste en brindar la posibilidad de realizar transferencias entre los clientes. Para ello decidió agregar un nuevo tipo de transacción: la transferencia entre cuentas.

Una **transferencia** es una transacción entre cuentas, que tiene ”dos patas”. La **pata de la extracción**, de donde se saca la plata, y la **pata del depósito** a donde se deposita la plata.

Una transferencia se realiza entonces entre dos cuentas y por un valor.

Además de poder registrar una transferencia entre cuentas, deseamos poder saber el valor de la misma. Del mismo modo, queremos poder preguntarle a cada una de las patas de la transferencia cual es su contraparte: a la pata de extracción cual es el depósito por transferencia relacionado, y viceversa.

Antes de comenzar, notar que uno de los tests está fallando.. ¿qué sucede? Corregir este problema antes de comenzar con el modelado de las transferencias.

Una vez corregido el test, implementar el modelo mediante TDD.

## Portfolios

El segundo servicio a implementar es tener la posibilidad de poder administrar agrupaciones de cuentas. Las agrupaciones de cuentas se denominan **portfolios**. Se espera poder hacer con ellos lo mismo que con una cuenta convencional, excepto registrar transacciones. Por ejemplo, debemos podemos **obtener el balance** de un portfolio: Si un portfolio es la agrupación de Cuenta 1 (con balance de $100) y Cuenta 2 (con balance de $200), se espera que el balance del mismo sea $300. También se espera **poder preguntarle** a un portfolio por medio de un mensaje **si alguna de sus cuentas registró una transacción**. Por último, también se desea poder conocer todas las transacciones de una cuenta.

Notar que un portfolio puede estar conformado no sólo por cuentas convencionales sino por otros portfolios, y se espera que las 3 operaciones mencionadas funcionen correctamente para estos casos también.

Por el momento, no se desea poder quitar cuentas convencionales ni portfolios de un portfolio.

Implementar el modelo mediante TDD.

## Extra: Portfolios válidos

Dado que un portfolio puede estar compuesto por otros portfolios, lo correcto sería que asegurarse que las cuentas no se repitan porque sino habría duplicación de información. Es decir, debemos evitar cualquiera de los siguientes escenarios:

1. Un portfolio no puede agregar dos veces la misma cuenta.
2. Un portfolio no puede agregar una cuenta ya incluída en un portfolio previamente agregado.
3. Un portfolio no se puede incluir a sí mismo.
4. No puedo agregar una cuenta a un portfolio cuando este último ya es hijo de otro portfolio padre que tenía dicha cuenta.
5. No puedo agregar un portfolio a otro porfolio, si el primero incluye una cuenta que el segundo ya tiene.

Extender el modelo existente para contemplar estas restricciones.
