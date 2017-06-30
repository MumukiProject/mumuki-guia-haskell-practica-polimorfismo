Pepe y Julián son hermanos que se mudaron de la casa de sus padres buscando su independencia económica. Ahora viven juntos. Para controlar los gastos que realizan quieren un sistema programado en objetos. 

Hay distintas cuentas en el sistema. Lo que se le pide a cada una de ellas son las mismas 3 cosas: saber el saldo, extraer y depositar. Para eso, las cuentas entienden los mensajes: 

* `saldo` devuelve un número que es el saldo en pesos de la cuenta;
* `depositar!(cantidad_de_pesos)` incrementa el saldo;
* `extraer!(cantidad_de_pesos)` disminuye el saldo.

Vamos a asumir que nunca se le pide a una cuenta extraer una cantidad de pesos superior al saldo disponible.

Si bien todas las cuentas cumplen con esas responsabilidades, cada cuenta lo realiza de una manera particular.

**La cuenta de Pepe** es una cuenta en pesos normal: el saldo incrementa con los depósitos y disminuye con las extracciones en exactamente la misma cantidad de pesos que indican los parámetros.

**La cuenta de Julián** está embargada, esto significa que de cada depósito solo el 80% incrementa el saldo, el 20% restante se descarta. Por ejemplo, si Julián tiene $100 de saldo, y deposita otros $100, el saldo es $180. Además, cada vez vez que extrae
se le descuenta al saldo $5 adicionales en concepto de gastos administrativos. Este gasto es aplicado solo en aquellos casos en que el gasto no deje la cuenta con saldo negativo.

**La cuenta de la mamá** de ambos está dolarizada: mantiene internamente un saldo en dólares. Se usa igual que una cuenta en pesos (se extrae y se depositan pesos), pero en cada operación hay que convertir la moneda usando los precios de compra y de venta según corresponda. Los valores iniciales son $15.10 para la venta y $14.70 para la compra. Obviamente, estos valores pueden cambiar con el tiempo.

* `saldo`: devuelve `saldo_en_dolares * precio_de_compra`;
* `depositar!(cantidad_de_pesos)`: incrementa el saldo dolarizado en `cantidad_de_pesos / precio_de_venta`;
* `extraer!(cantidad_de_pesos)`: decrementa el saldo dolarizado en `cantidad_de_pesos / precio_de_compra`.

> Creá los objetos necesarios para representar a las tres cuentas, respetando la interfaz pedida (las tres tienen que entender `saldo`, `depositar!` y `extraer!`).
