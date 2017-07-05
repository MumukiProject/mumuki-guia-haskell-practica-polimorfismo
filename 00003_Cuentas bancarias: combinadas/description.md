Juan y Pepe se pusieron de acuerdo para que en ciertas épocas, afronten los gastos juntos. Para eso es necesario generar una cuenta combinada, que une otras dos. Tiene una cuenta primaria y una secundaria. La cuenta combinada se comporta de la siguiente manera:

* `saldo`: devuelve la suma de los saldos de las cuentas primaria y secundaria;
* `depositar!(cantidad_de_pesos)`: si el saldo de la cuenta secundaria es menor a $1000 deposita en dicha cuenta. En cualquier otro caso deposita en la primaria;
* `extraer!(cantidad_de_pesos)`: extrae todo lo que puede de la cuenta primaria y el resto de la secundaria.

> Creá la cuenta combinada, con la posibilidad de cambiarle las cuentas primaria y secundaria.