# Servicios financieros 2

## Reportes

Por nuestro gran trabajo, el CEO del banco decidió extender el contrato y seguir agregando funcionalidades. Esta vez, quiere poder agregar la funcionalidad de brindar reportes para las cuentas y portfolios de clientes.

Se espera tener dos reportes inicialmente:

1. El resumen de cuentas (Account Summary).
2. El neto de transferencias (Transfer Net).

El **resumen de cuenta** debe generar una línea por cada transacción realizada en una cuenta con el siguiente formato:

```
Depósito por 100 pesos
Extracción por 50 pesos
Salida por transferencia de 20 pesos
Entrada por transferencia de 30 pesos
Balance = 60 pesos
```

Este sería el resumen de cuenta esperado de una cuenta a la cual se le realizó un depósito por 100, una extracción por 50, se le sacó 20 por una transferencia y recibió 30 por otra transferencia.

El **reporte de neto de transferencias** debe devolver el resultado de sumar todos los depósitos por transferencias y restarle todas las extracciones por transferencias. Para el ejemplo anterior, el neto de transferencias seria 10.

El banco prevé agregar muchos reportes nuevos en un tiempo inmediato, por lo tanto el modelo final para sacar reportes debe cumplir con los siguientes requerimientos de extensibilidad:

1. Poder agregar futuros reportes sin tener que modificar la jerarquía de cuentas.
2. Poder agregar futuros reportes sin tener que modificar la jerarquía de transacciones.
3. Crear nuevos reportes debe implicar crear clases nuevas únicamente y no modificar ninguna existente.

Implementar la solución haciendo TDD. Deben partir del código de la solución del ejercicio anterior, ya sea el realizado por ustedes o a partir de la solución provista por la cátedra.

## Extra: Reportes especiales

El CEO del banco nos premiará si logramos tener 2 nuevos reportes para portfolios. El primero (PortfolioTreePrinter) deberá mostrar la estructura de árbol completa del portfolio. El segundo, un reporte más detallado (PortfolioDetailedTreePrinter) que muestre las transacciones indentadas de acuerdo a la profundidad de cada cuenta del portfolio.

Dado un portfolio como se muestra a continuación: 
```
johnsAccount := ReceptiveAccount named: 'Cuenta de Juan'. 
angiesAccount := ReceptiveAccount named: 'Cuenta de Angeles'. 
childrenPortfolio := Portfolio named: 'Portfolio de hijos' with: johnsAccount with: angiesAccount. 
myAccount := ReceptiveAccount named: 'Cuenta mia'. 
familyPortfolio := Portfolio named: 'Portfolio de la familia' with: myAccount with: childrenPortfolio.
```

El reporte de la estructura de árbol de dicho portfolio debería ser:
```
Portfolio de la familia
   Cuenta mia
   Portfolio de hijos
      Cuenta de Juan
      Cuenta de Angeles
```

Se espera que el reporte detallado se muestre de la siguiente manera:
```
Portfolio de la familia
   Cuenta Mia
      Depósito por xxx
      Extracción por yyy
      Balance = bbb
   Portfolio de hijos
      Cuenta de Juan
         Depósito por zzz
         Extracción por nnn
         Balance = bbb
      Cuenta de Angeles
         Salida por transferencia de qqq
         Balance = bbb
      Balance = bbb
   Balance = bbb
```

Al igual que los reportes anteriores, el diseño final para resolverlos debe permitir agregar reportes sobre portfolios sin tener que modificar nada.

