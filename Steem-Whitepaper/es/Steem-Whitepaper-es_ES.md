# Steem
## Una plataforma de "social media", basada en blockchain, con incentivos.

Daniel Larimer, Ned Scott, Valentine Zavgorodnev, Benjamin Johnson, James Calfee, Michael Vandeberg

Marzo 2016

---

# Abstract
Steem es una base de datos blockchain que permite la contrucción comunitaria e interacción social con premios en criptomoneda. Steem combina conceptos de *social media* con los aprendizajes provenientes de la construcción de criptomonedas y sus comunidades. Una clave importante para inspirar participación de cualquier comunidad, moneda o economía de libre mercado es un sistema de contabilidad justa que refleje consistentemente la contribución de cada persona. Steem es la primer criptomoneda que intenta recompenzar de forma acertada y transparente una cantidad indeterminada de individuos que realizan *contribuciones subjetivas* a su comunidad.

---

# Tabla de contenidos
1. Abstract
2. Tabla de contenidos
3. Introducción
	3.1 Reconociendo las contribuciones
4. Formas de contribuir
	- 4.1 Contribuciones de capital
	- 4.2 Steem (STEEM)
	- 4.3 Steem Power (SP)
	- 4.4 Steem Dollars (SBD)
      - 4.4.1 Minimizando comisiones fraudulentas
      - 4.4.2 Mitigando ataques de cadencia
      - 4.4.3 Minimizando el abuso de conversiones
      - 4.4.4 Liquidez
      - 4.4.5 Deuda sostenible a relaciones de propiedad
      - 4.4.6 Intereses
      - 4.4.7 Definiendo fuentes de precios
	- 4.5 Contribuciones subjetivas
		- 4.5.1 Distribuyendo la moneda
		- 4.5.2 Votando sobre la distribución de la moneda
			- a. Complicidad en la votación
			- b. La historia del *Crab Bucket*
		- 4.5.3 Tasa limitada de voto
		- 4.5.4 Pagos retrazados
		- 4.5.5 Distribución de pagos
			- a. Recompensas para posts padres.
        - 4.5.6 Pagos
    - 4.6 Algoritmo de consenso
    	- 4.6.1 Consenso en Steem
    	- 4.6.2 Minando en Steem
    		- a. Premios de minado requieren Steem Power
            - b. Algoritmo de minado
            - c. Resistencia a Botnets
            - d. Resistencia de Pools de minado
        - 4.6.3 Eliminando comisiones de transacción
        	- a. El problema de las comisiones
            	- a.a Los micropagos no funcionan
                - a.b Las comisiones son barreras para el acceso.
              	- a.c Cambiando las comisiones
                - a.d Ataques de identidad (Sybil attacks)
                - a.e Reserva completa vs. reserva fraccionada
            - b. Iterando mas allá de los micropagos
            	- b.a Ejemplo de implementación
                - b.b Caso de estudio: Bitcoin
                	- b.b.a Impacto de capacidad
                    - b.b.b Numero máximo de usuarios únicos
                    - b.b.c Comparación a comisiones
                - b.c Creación de cuenta
                - b.d Justificando balances mínimos
                - b.c Ajustando relación de reserva
                - b.d Efectividad relativa a comisiones
                - b.e Renta vs. Compra vs. Tiempo compartido
            - c. Performance y Escalabilidad
            	- c.a Escala Reddit
            - d. Asignación y suministro
            	- d.a Impacto de Tasa de creacion de tokens
                	- d.a.a Impacto de tasa de cración de tokens mayor al noventa porciento
                    - d.a.b Sistema contable
            - e. El poder de Steem
            	- e.a Sin micropagos, Propina opcional
                - e.b El valor está en los enlaces
                - e.c Resolviendo el problema de abordaje de las criptomonedas
                - e.d Resolviendo el problema de liquidación de las criptomonedas
                - e.e Censura
                - e.f Resolviendo el descubrimiento orgánico a través de optimización en motores de búsqueda
                - e.g Viraje hacia la atribución basada en Blockchain
                - e.h Reemplazando la publicadad con recompenzas de contenido basado en Blockchain
            - f. Conclusión
            

---

# Introducción

El contenido generado colectivamente por usuarios ha creado billones de dólares en valor para los accionista de compañias de *social media* como Reddit, Facebook y Twitter. En 2014, Reddit hipotetizó que su plataforma podría ser mejorada si todos los que contribuyen en reddit.com posteando historias, agregando comentarios o votando fuesen premiados con una cantidad justa de participación en Reddit, Inc[[1]](#1). Steem apunta a apoyar comunidades online y de *social media* devolviendo gran parte de su valor a la gente que provee valiosas contribuciones, premiándolos con criptomoneda, y a través de este proceso crear una moneda que puede alcanzar un mercado masivo, incluyendo gente que aún no ha participado en alguna economía de criptomoneda.

Hay algunos principios clave que han sido utilizados para guiar el diseño de Steem. El más importante es que todos los que contribuyen a una empresa deben recibir una participación prorrateada, pago o débito de la empresa.
Este principio es el mismo que se aplica en casi todas las *Startups*, estas colocan acciones durante la fundación y durante rondas de inversión subsecuentes.

El segundo principio es que todas las formas de capital son igualmente valiosas. Esto significa que aquellos que contribuyen su escaso tiempo y atención en producir y curar contenido para otros, son tan valiosos como quienes contribuyen con su capital. Este es el principio de equidad de sudor[[2]](#2) y es un concepto que previo a las criptomonedas ha tenido problemas para proveer a no más de algunas docenas de individuos.

El tercer principio es que la comunidad produce productos para servir a sus miembors. Esto se ejemplifica con las uniones de crédito, coperativas de alimentos, planes de salud compartidos, que sirven a los miembros de sus comunidades mas que vender productos o servicios a la gente fuera de la comunidad.

La comunidad de Steem provee los siguientes servicios a sus miembros:
1. Una fuente de noticias y comentarios curada.
2. Medios para obtener respuestas de alta calidad a preguntas personalizadas.
3. Una criptomoneda estable vinculada al Dólar Estadounidense.
4. Pagos libres.
5. Trabajos que proveen los servicios antes mencionados a otros miembros.


El útil realineamiento de incentivos económicos de Steem tiene el potencial de producir resultados justos y mas inclusivos para todos los involucrados que las plataformas de *social media* y criptomonedas que la preceden.

Este documento explorará los incentivos económicos existentes y demostrará cómo Steem y sus incentivos podrán resultar mejor para la mayoría de los participantes.

---

[1] Reddit’s Cryptocurrency, Forbes, Erika Morphy, Octubre 2014,
http://www.forbes.com/sites/erikamorphy/2014/10/01/reddits-cryptocurrency-could-have-many-uses/#4e07b05332b9
[2] Sweat Equity, Investopedia,
http://www.investopedia.com/terms/s/sweatequity.asp


---

## 3.1 - Reconociendo las contribuciones

Steem está diseñado desde cero para resolver las mayores barreras para su adopción y monetizaciones de una economías basada en *social media*.
Nuestra tésis es que las mismas técnicas usadas para hacer crecer las mas grandes plataformas de *social media* pueden ser utilizadas para iniciar una criptomoneda existosa.
Incentivos económicos habilitados por criptomoneda pueden facilitar dramáticamente el crecimientod de una nueva plataforma de *social media*. Es la sinergía entre criptomoneda y *social media* lo que creemos que puede dar a Steem una poderosa ventaja en el mercado.

El reto afrontado por Steem es derivar un algoritmo para tasar contribuciones individuales que la mayor parte de los miembros de la comunidad consideren una evaluación justa del valor subjetivo de cada contribución.
En un mundo perfecto, los miembros de la comunidad coperarían para valuar la contribución de cada par y devolver una justa compensación. En el mundo real, deben diseñarse algoritmos de tal forma que sean resistentes a manipulación intencional con fines de lucro. Cualquier abuso del sistema de tasación podría causar la pérdida de fe en la percepción de justicia del sistema económico por parte de sus miembros.

Las plataformas existentes operan en un principio de un usuario, un voto. Esto crea un ambiente donde los rankings pueden ser manipulados por ataques de profeta y los proveedores de servicio deben proactivamente identificar y bloquar abusadores. La gente actualmente intenta manipular los sistemas de tasacipon de Reddit, Twitter y Facebook siendo la única ganancia el tráfico web o la censura.

La unidad fundamental de contabilidad en la plataforma de Steem es STEEM, un token de criptomoneda.
Steem opera en la base de un STEEM, un voto. Bajo este modelo, los individuos que mas hayan contribuido a la plataforma, segun lo corroborado por el balance de su cuenta, tienen mayor influencia sobre cómo se valúan las contribuciones. Además, Steem solo permite a los miembros votar con STEEM cuando este es sujeto a un esquema multi-anual de adquisición.
Los miembros tienen un incentivo financiero para votar en el sentido que ésto maximiza el valor a largo plazo de sus propios STEEM.

Steem está diseñado alrededor de un concepto relativamente simple: toda contribución significativa a la comunidad debería ser reconocida por el valor que añade. Cuando la gente es reconocida por sus contribuciones, continúan contribuyendo y la comunidad crece.
Cualquier desbalance en el ida y vuelta dentro de una comunidad es insustentable. Eventualmente los dadores se cansan de soportar a los miembros que restan y atentan contra la comunidad.

El reto es crear un sistema capaz de identificar qué contribuciones son necesarias y su valor relativo de manera que pueda escalar a un numero indeterminado de gente.
Un sistema comprobado para evaluar y premiar contribuciones es el libre mercado. El libre mercado puede ser visto como una comunidad única donde todos intercambian con otros y las recompenzas son asignadas por pérdidas y ganancias. El sistema de mercado premia aquellos que proveen valor a otros y castiga a quienes consumen más valor del que producen. El mercado libre soporta muchas monedas diferentes y el dinero es simplemente una *commodity* que todos encuentran fácil de intercambiar.

Desde que el libre mercado es un sistema comprobado, es tentador intentar crear un sistema de igual característica donde los consumidores de contenido pagan directamente a los productores del mismo. De todas formas, el pago directo es ineficiente y realmente inviable para la creación y curado de contenido. El valor de la mayoría del contenido es muy bajo en relación con el costo cognitivo, financiero y de oportunidad asociado con hacer un pago que algunos pocos lectores eligen beneficiar. La abundancia de alternativas libres siginifica que la aplicación de un *muro de pago* derivará a los lectores a otro lado. Han habido gran cantidad de intentos de implementar micro pagos por artículo de parte de los lectores hacia los autores, pero ninguno se ha alcanzado una amplitud considerable.

Steem está diseñado para permitir micropagos efectivos por cualquier tipo de contribución al cambiar la ecuación económica. Los lectores ya no tienen que decidir si pagar o no a alguien desde su propio bolsillo, en cambio votan  o restan votos y Steem usa estos votos para determinar premios individuales. Esto significa que se le otorga a la gente una interfaz familiar y ampliamente utilizada y ya no enfrentan los costos de oportunidad, cognitivos y financieros asociados tradicionalmente a los micropagos y plataformas de propinas.

El voto de los miembros de la comunidad es crítico para que Steem acomode los pagos a los contribuyentes de forma precisa.
El voto puede por lo tanto ser visto como una contribución crucial y digno de ser recompenzado en sí mismo. Algunas plataformas, como Slashdot, usan meta-moderación[[3]](#3) como una forma de rankear y premiar a los moderadores honestos. Steem entonces premia a quienes mas contribuyen al total de la promoción de una pieza de contenido pagando a los votantes proporcionalmente al pago principal del creador del contenido votado.

Hay otras formas de contribución que Steem reconoce y premia usando métricas objetivas. Entre ellas están: validación de transacciones, minado de prueba de trabajo, premios de liquidez, y reportado de productores de bloque malitencionados.

[3] Meta-moderacion es un segundo nivel de moderación de comentarios. Los usuarios son invitados a valuar las decisiones de los moderadores para mejorar la moderación.
https://en.wikipedia.org/wiki/Meta-moderation_system


---

# 4. Formas de contribuír
Esta sección delínea las ideas detrás de Steem y sus recompenzas para la gente que provee contribuciones significativas y mesurables a la comunidad de Steem.

## 4.1 - Contribuciones de capital
Hay dos items que una comunidad puede ofrecer para atraer capital: deuda y propiedad.
Quienes compran propiedad ganan cuando la comunidad crece pero pierden si la misma decrece.
Quienes compran deuda obtienen la garantia de un cierto monto de interpes pero no llegan a participar de las ganancias realizadas por el crecimiento de la comunidad. Ambos tipos de contribuciones de capital son valiosas para el crecimiento de la comunidad y la valuación de su moneda.
Adicionalmente hay dos formas en que la propiedad puede conservarse: liquidez y colocación.
La colocación de propiedad genera un compromiso de largo plazo y no puede ser vendida por un determinado período de tiempo.

La red Steem denomina a estas diferentes clases de *assets* Steem (STEEM), Steem Power (SP), y Steem Dollars (SMD)

## 4.2 - Steem (STEEM)

Steem es la unidad fundamental contable en el blockchain de Steem. Los demás tokes derivan su valor del de STEEM. Generalmente STEEM deberia ser mantenido por cortos períodos de tiempo cuando se necesita liquidez. Alguien que busque entrar o salir de la plataforma de Steem tendrá que comprar o vender STEEM. Una vez comprado debería ser convertido a SP o SMD para mitigar el impacto de la dilución en el largo plazo.
STEEM crece constantemente en oferta por un 100% anual debido a incentivos no SMD. Quien tenga STEEM sin convertirlos a SP, se diluirán aproximadamente en un 0.19% diario. Mientras el ritmo puede parecer alto, para transacciones que toman menos de 10 dias, sigue siendo mas barato que las comisiones de proceso de tarjetas de crédito. Ademas, la creación diaria de *tokens* es insignificante al lado de la volatilidad diaria.

Quien compre Bitcoin o cualquier otra criptomoneda y la venda 10 dias después podría perder fácilmente 3% o mas debido a las fluctuaciones de precio. Quien compre Bitcoin y luego lo venda en el mismo dia usualmente pagará mas del 0.4% sólo en comisiones del mercado de intercambio.
En otras palabras, el ritmo de inflacipon es efectivamente insignificante durante el período de tiempo que un individuo típico sostendrá STEEM.

La mayoría de la inflación es de hecho un artefacto de contabilidad en lugar de un verdadero reacomodamiento de riqueza. El 90% de la inflación no SMD es redistribuída a los poseedores existentes de STEEM proporcionalmente al valor de STEEM de su balance de SP, convirtiendo la inflación en mas bien una repartición. Solo alrrededor del 10% de la inflación no SMD redistribuye propiedad en la red.

## 4.3 Steem Power (SP)

Las Startups o los emprendimientos requieren un compromiso de capital a largo plazo. Aquellos que invierten su dinero en estas companías calculan esperar años antes de poder vender sus acciones y efectivizar su ganancia.
Sin compromiso a largo plazo, una *startup* buscando recolectar capital adicionar a través de la venta de acciones adicionales estaría compitiendo con accionistas existentes queriendo retirarse. Los inversores compresivos quieren que sus contribuciones de capital hagan crecer la compañía, pero el crecimiento no puede suceder si el nuevo capital es entregado a los que buscan retirarse.

Hay un valor significativo en tener compromiso a largo plazo porque habilita a las comunidades a hacer planes a largo plazo. El compromiso a largo plazo de los *stakeholders* también causa que estos voten por el crecimiento a largo plazo en lugar de bombeos de corto plazo.

En el espacio de las criptomonedas, los especuladores saltan de criptomoneda en criptomoneda basados mayormente en las expectativas de crecimiento a corto plazo. Steem busca armar una comunidad que sea propiedad y controlada enteramente por aquellos con perspectivas a largo plazo.
Debido a que Steem busca alentar el crecimiento a largo plazo, está fijado en su lógica la acomodación de 9 STEEM a los poseedores de Steem Power (SP) por cada STEEM que crea para financiar el crecimiento a través de incentivos a la contribución. En el tiempo, esto lleva a que la relación entre el total de valor en STEEM de Steem Power (SP) se balacee al total de los balances STEEM hacia un 9:1. (Al parecer, esta relación probablemente supere el 9:1 debido al contínuo empoderamiento de la red de los nuevos STEEM emitidos)
Esto también significa que los poseedores a largo plazo son protegidos casi por completo de la dilución utilizada en la financiación del crecimiento.

Los SP sólo pueden ser convertidos a STEEM luego de 2 años a través de 104 pagos semanales equitativos. *1 SP* puede ser visto como una acción en un *pool* de STEEM. La red automáticamente agrega STEEM al *pool* en cada bloque. En cualquier momento, los usuarios pueden convertir sus STEEM en SP en la misma relación en que el STEEM en el *pool* de plazos fijos al total de SP. Convertir STEEM a SP no diluye a los poseedores existentes de SP.
Mas bien, cada vez que se convierte de SP a STEEM, se hace con la relación del momento. Los individuos tienen garantizado poseer mas STEEM en el futuro de lo que tienen cuando convierten por primera vez desde STEEM a SP.

Los balances de SP son no-transferibles y no-divisibles excepto a través de las solicitudes recurrentes automáticas de conversión. Esto significa que el SP no puede ser intercambiado en *exchanges* de criptomonedas.

Poseer SP es requerido para votar a favor o denunciar contenido. Esto quiere decir que el SP es el *token* de acceso que otorga a sus poseedores poderes exclusivos dentro de la plataforma de Steem.

La acción de transferir desde STEEM a SP es llamada *Powering Up* mientras que la transferencia de SP a STEEM es *Powering Down*. Por ejemplo, uno puede hacer *Power Down* de sus STEEM sobre un período de 2 años, pero se puede hacer *Power Up* con sus STEEM inmediatamente.

## 4.4 - Steem Dollars (SMD)

La estabilidad es un componente importante en las economías globales exitosas. Sin estabilidad, los individuos en distintas partes del mundo no podrían tener costos cognitivos bajos al participar en el comercio y ahorro. Por este motivo, los *Steem Dollars* fueron diseñados como un intento de traer estabilidad al mundo de las criptomonedas y a los individuos que usen la red Steem.

Los Steem Dollars (SMD) son creados por un mecanismo similar a las notas convertibles, que son usualmente utilizadas para financias *startups*. En el mundo de las *startups*, las notas convertibles son instrumentos de deuda a corto plazo que pueden ser convertidos a propiedad a un ritmo determinado en el futuro, típicamente durante una futura ronda de inversión. Un *token* basado en blockchain puede ser visto como propiedad mientras una nota convertible puede ser vista como deuda con denominación en otra *commodity* o moneda. Los términos de la nota convertible permiten a su dueño convertirla al *token* que la respalda con una antelación mínima al precio justo del mercado del *token*. Crear dólares convertibles a *tokens* habilita a los blockchains a aumentar su efecto de red mientras se maximiza el retorno a los poseedores de *tokens*.

Los *Steem Dollars* son nomenclados con el símbolo SMD, su acrónimo. Para crear los SMD se requiere una combinación entre un indicador de precio confiable, reglas para prevenir el abuso, y liquidez.
Proveer un indicador de precio confiable implica tres factores: minimizar el impacto de un indicador incorrecto, maximizar el costo de producir un indicador incorrecto, y minimazar la importancia de la cadencia.

### 4.4.1 - Minimizando comisiones fraudulentas

Los poseedores de SP eligen individuos para publicar indicadores de precio. Estos individuos seleccionados son presumiblemente poseen la confianza de aquellos que tienen un interés personal en la calidad del indicador. Al pagarle a quienes son elegidos, Steem crea un mercado competitivo para obtener el derecho de producir indicadores. Mientras mas productores de indicadores reciben pagos menos les conviene a éstos publicar información falsa. 

Habiendo varios productores electos y confiables, el precio determinado para conversiones puede ser derivado entonces del promedio de los indicadores. De esta forma si alguna minoría de productores de indicadores publican valores atípicos, éstos tienen entonces un impacto mínimo en el promedio pero de todas formas se afecta su reputación.

Aún si todos los productores son honestos, existe la posibilidad que la mayoría de éstos sean afectados por eventos que estén más allá de su control. La red de Steem está diseñada para tolerar corrupciones de corto plazo en el indicador promediado mientras la comunidad trabaja activamente en la corrección del problema. Un ejemplo de un problema que puede tomar cierto tiempo para corregir es la manipulación de mercado a corto plazo. La manipulación de mercado es dificultosa y costosa de mantener por períodos largos. Otro ejemplo sería la falla de un servicio de intercambio centralizado o la corrupción de los datos publicados por el mismo.

Steem elimina el factor de las fluctuaciones de precio de corto plazo usando el promedio del período de una semana. El indicador de promedio publicado es generado cada una hora.

Siempre que una corrupción en el indicador de precios dure menos que la ventana de tiempo del promedio móvil, habrá un impacto mínimo en el precio de conversión. Si eventualmente el indicador es corrompido, los participantes de la red tendrán una oportunidad para votar la expulsión de los productores de indicadores corrompidos antes que impacten en el precio efectivo de conversión.

Tal vez lo mas importante es que le da a los productores una oportunidad para detectar y corregir los problemas antes que sus indicadores comiencen a afectar el precio promediado.
Con una ventana de tiempo de una semana, los miembros de la comunidad tienen tres dias y medio para responder y mitigar los problemas que puedan surgir.

### 4.4.2 - Mitigando ataques de cadencia

Los participantes del mercado tienen acceso a información antes de lo que el promedio móvil semanal de precio de conversión pueda reaccionar. Esta información puede ser utilizada para beneficio de los operadores a expensas de la comunidad. Si hay un incremento repentino en el valor de STEEM, los operadores podrían solicitar la conversión de sus SMD al precio anterior, más bajo, y luego vender los STEEM recibidos a un nuevo precio mayor con muy bajo riesgo.

Steem nivela el juego al imponer a todos los pedidos de conversión un retardo de una semana. Esto significa que ni los operadores ni el blockchain tienen ventaja con respecto al precio cuando la conversión se ejecuta.

### 4.4.3 - Minimizando el abuso de conversiones

Si los usuarios puediesen convertir libremente en ambas direcciones, los operadores podrían tomar ventaja de las medidas de conversión del blockchain al intercambiar grandes volúmenes sin modificar el precio. Los operadores que ven un aumento masivo en el precio podrían convertir a SMD al mayor precio (cuando hay mas riesgo) y luego reconvertir luego de la correción. El protocolo de Steem proteje a la comunidad de este tipo de abusos al permitir únicamente la conversión de SMD a STEEM y no al revés.

El blockchain decide cómo y cuándo crear SMD y quién debe recibirlos. Esto mantiene estable el ritmo de creación de SMD y elimina formas de abuso.

### 4.4.4 - Liquidez

El hecho que SMD pueda ser convertido a dólares de STEEM a un precio justo en un tiempo razonable no implica que sea considerado como reemplazo confiable al dólar. Estos *assets* requieren liquidez en un mercado que habilite conversión instantánea entre STEEM y SMD. Las medidas a las que el blockchain se ver forzado a tomar para prevenir abusos derivan en la baja calidad de los dólares convertibles. Para compensar ésta pérdida de calidad el blockchain puede ofrecer un preio de costo fijo a los proveedores de liquidez. Considerando que las potenciales pérdidas por la manipulación y el abuso son ilimitadas, el costo de fomentar la liquidez puede ser fijo.

Un proveedor de liquidez compra y vende SMD y STEEM. Ellos se encargan de la mayoría del riesgo de precio de corto plazo y el indicador de largo plazo, otorgando al resto de los participantes un mercado de alta calidad y extremadamente líquido donde comerciar.

Steem posee un mercado incluído en el blockchain para intercambiar entre SMD y STEEM. Los usuarios pueden ganar premios al proveer liquidez en ambas partes de dicho mercado. El blockchain utiliza un algoritmo simple para clasificar la provisión y consumo de liquidez de cada usuario.

Se considera a un usuario proveedor de liquidez si éste deja una orden abierta en los libres por al menos 1 minuto y la orden eventualmente se ejecuta. Si la orden es cancelada antes de su ejecución el usuario no recibe acreditación por proveer liquidez. 

Los usuarios deben proveer liquidez en ambos lados del libro para calificar para los premios y deben proveer liquidez consistentemente en el tiempo. El algoritmo de puntuación es:

	PuntosDeLiquidez = VolumenNetoDeOfertas x VolumenNetoDeDemanda

Cada hora, la cuenta con más *PuntosDeLiquidez* recibe 1200 STEEM y luego dichos puntos son vueltos a 0. Una cuenta que no recibe *PuntosDeLiquidez* durante una semana también queda con sus puntos de liquidez en 0. Esto significa que proveer un monto grande o pequeño durante un período largo otorga a todos un monto proporcional de premios. Si tanto el *VolumenNetoDeOfertas* o el *VolumenNetoDeDemanda* son negativos, los *PuntosDeLiquidez* se consideran 0.

### 4.4.5 - Deuda sostenible a relaciones de propiedad

Si un *token* es considerado propiedad en el total de provisión de *tokens*, entonces un *token* convertible a dólar puede ser considerado como deuda. Si la deuda de propiedad tiene una relación muy alta, la moneda entera puede volverse inestable. Las conversiones de deuda pueden incrementar dramaticamente la provisión de *tokens*, los cuales por su parte pueden ser vendidos en el mercado suprimiendo el precio. Las conversiones subseuentes requieren la emisión de aún más *tokens*. Si no se comprueba el sistema puede colapsar dejando una montaña de deuda respaldada por propiedad sin valor. A mayor relación entre deuda a propiedad, menos inversores nuevos desearán aportar capital a la mesa.

Por cada SMD que Steem crea, $19.00 en STEEM son también creados y convertidos a SP. Esto implica que la máxima relación posible de deuda/propiedad en un mercado estable es de 1:19 o alrrededor del 5%. Si el  precio de Steem cae un 50% entonces la relación podría crecer un 10%. Un 88% de caída del valor de STEEM podría causar que la relación deuda/propiedad alcance el 40%. Asumiendo que el valor de STEEM eventualmente se estabilice, la relación deuda/propiedad se moverá naturalmente de vuelta hacia el 5%.

La idea detrás de tener una deuda conservativo de 5% en relación a la propiedad es que incluso si toda la deuda fuese convertida y vendida, debería haber bastos compradores y la dilución efectiva de los poseedores de *tokens* se mantiene relativamente baja.

Un cambio repentino en el valor de STEEM puede cambiar dramáticamente la relación deuda/propiedad. El piso de porcentajes usado paa computar la creación de STEEM se basa en la provisión incluyendo el valor de STEEM de todo el SMD y SP existente (tal como lo determine la relación / indicador del momento).

### 4.4.6 - Intereses

SMD retribuye intereses a los poseedores. La relación de interés es definida por la misma gente que publica el indicador de precio de forma que se puede adaptar a las condiciones cambiantes del mercado. Toda deuda acarrea riesgo para el prestador. Quien posee SMD sin redimirlo está efectivamente prestando a la comunidad el valor de un dólar. Ellos están confiando que en cierto punto en el futuro alguien estará dispuesto a comprarles los SMD por un dólar o que habrán especuladores e inversores dispuestos a comprar el STEEM al que lo conviertan.

Los poseedores de STEEM y SP ganan apalancamiento cuando los miembros de la comunidad se dispongan a sostener sus SMD. Este apalancamiento amplifica las ganancias por la crecida mientras también contribuyen a la misma. Quienes poseen STEEM sufren incremento de dilución si el precio cae. Los proyectos de Criptomonedas han demostrado que las ganancias de incrementar la base de usuarios dispuestos a confiar en la red con capital, terminan por sumar mas valor a la red que cualquier dilución que pueda ocurrir durante una baja.

### 4.4.7 - Definiendo fuentes de precios

Lectores astutos reconocerán que los activos de provisión limitada que generan intereses pueden ser intercambiados mayor o menos que el activo subyacente dependiendo de otras oportunidades para ganar interés sobre el mismo activo. Con una relación mas alta de interés sobre un activo vinculado al USD (dólar estadounidense) muchas personas intentarán ofertar sobre esta oferta limitada de Steem Dollars hasta que ya no valgan $1. En economía hay un principio conocido como "La Trinidad Imposible"[4] que sugiere que resulta imposible tener todas las siguientes condiciones al mismo tiempo:

1. Relación de intercambio estable
2. Movimiento libre de capital
3. Una política monetaria independiente


	[4] The Impossible Trinity, teoría económica
	https://en.wikipedia.org/wiki/Impossible_trinity


Si los productores de indicadores apuntan a tener una política monetaria independiente para permitirles crear y destruír Steem Dollars y simultáneamente tener control total sobre la tasa de interés, entonces encontrarán problemas. La trinidad imposible dice que los Steem Dollars necesitan restringir el movimiento de capital, tener una tasa de intercambio inestable o tener control limitado sobre la tasa de interés.

La principal preocupación de los productores de indicadores de Steem es mantener una relación 1 a 1 estable entre SMD y el USD (Dólar estadounidense). Cuando el SMD sea consistentemente intercambiado por sobre $1 USD los pagos de interés deben ser detenidos. En un mercado donde el 0% de interés aún exige una prima, es seguro afirmar que el mercado está dispuesto a extender mas crédito del que la comunidad está dispuesta a tomar como deuda. Si ésto sucede el SMD será valuado a mas de $1.00 y poco podrá hacer la comunidad sin cobrar tasas de interés negativas.

Si la relación deuda/propiedad se encuentra debajo del 10% y el SMD está siendo intercambiado por menos de $1.00 entonces la tasa de interés debería incrementarse. Esto estimula a mas gente a sostener sus SMD y apoyar el precio.

Si el SMD se intercambia por menos de $1.00 USD y la relación deuda/propiedad está por sobre el 10%, el indicador debería ajustarse en subida para pagar mas STEEM por SMD. Esto incrementa la demanda de SMD mientras reduce la tasa de deuda/propiedad y la paridad entre SMD y USD.

Asumiendo que el valor de STEEM crece mas rápido de lo que Steem crea nuevos SMD, la relación deuda/propiedad debería permanecer debajo de la tasa necesaria y el interés ofrecido beneficia a todos. Si el valor de la red es plano o en caída, entonces cualquier interés ofrecido sólo hará peor la relación deuda/propiedad.

En efecto, los productores de indicadores son confiados con la responsabilidad de aplicar una política monetaria con el propósito de mantener un vínculo estable al USD. Abusar de este poder puede dañar el valor del STEEM de forma que los poseedores de SP deben ser listos al votar a los testigos (*witnesses*) con quienes contar para ajustar el indicador de precio y tasas de interés de acuerdo a las reglas recién especificadas.

Si la relación deuda/propiedad se posiciona peligrosamente alta y los participantes del mercado eligen evitar los pedidos de conversión, se debería ajustar el indicador para incrementar la tasa a la que se paga STEEM al convertir desde SMD.

Los cambios en la política de tasa de interés y/o cualquier prima/descuento en la relación de conversión de STEEM/SMD deberían ser una respuesta lenta y mesurada a la desviación promedio en el largo plazo en lugar de intentar responder a las condiciones de corto plazo del mercado. El blockchain paga a los proveedores de liquidez por su servicio de absorber la demandas de corto plazo.

Es nuestra creencia que estas reglas darán a los participantes del mercado la confianza de que la probabilidad de perder dinero por mantener SMD comprados al precio de $1.00 será poco probable. Esperamos completamente que habrá un rango de intercambio acotado entre $0.99 y $1.01 para el SMD bajo la mayoria de condiciones del mercado.

## 4.5 - Contribuciones subjetivas

La Prueba Subjetiva de Trabajo (*Subjective Proof of Work*) presenta un enfoque alternativo de distribución de moneda que "mejora" el PoW (*Proof of Work*) completamente objetivo tal como es el minado. Las aplicaciones de una moneda que implementa una prueba de trabajo subjetiva son mucho mas amplias que cualquier sistema de prueba de trabajo porque puede ser aplicada para construir una comunidad en torno a cualquier concepto que tenga un prósito lo suficientemente definido. Cuando los individuos acceden a una comunidad éstos compran acceso a un conjunto particular de creencias y pueden votar para reforzar los valores o propósito de la comunidad.

En efecto, el criterio por el cual se evalúa un trabajo es completamente subjetivo y su definición radica fuera del código de fuente en sí. Una comunidad puede desear premiar a artistas, poetas, comediantes. Otras podrían preferir premiar causas de caridad o apoyar agendas políticas.

El valor que cada moneda alcance depende de la demanda de influencia dentro de una comunidad en particular y de cuán grande el mercado crea que cada comunidad pueda ser. A diferencia de otros sistemas existentes, la prueba de trabajo subjetiva permite a una comunidad financiar colectivamente el desarrollo o lo que considere valioso y habilida la monetización de su tiempo otrora no monetizable.

### 4.5.1 - Distribuyendo la moneda

Hay dos formas en las que la gente puede involucrarse en una comunidad de criptomoneda: pueden comprar su acceso, o trabajarlo. En ambos casos, los usuarios agregan valor a la moneda, sin embargo, la basta mayoría de personas tienen mas tiempo libre que efectivo a disposición. Imagine el objetivo de fundar una moneda en una comunidad de escasos recursos y sin efectivo pero con suficiente tiempo disponible. Si la gente puede ganar dinero trabajando el uno por el otro, podrán crear valor a través del intercambio mutuo facilitado por un sistema justo de contabilidad/moneda.

Distribuír una moneda a la mayor cantidad de gente posible de una forma que sea generalmente percibida como justa es una tarea desafiante. Las tareas que pueden ser enteramente evaluadas por un algoritmo computacional objetivo son limitadas en su naturaleza y generalmente hablando, tienen limitados beneficios externos. En el caso del minado al estilo *Bitcoin*, puede resultar en una producción de hardware especializado y causar problemas para invertir tiempo desarrollando algoritmos mas eficientes para tal fin. Incluso puede servir encontrar números primos, pero ninguna de estas cosas provee valor con sentido a la sociedad o a la entera comunidad poseedora de la moneda. Aún mas importante, las economías fuerza de mercado y escala terminan excluyendo de la participación a todos salvo a los expertos con éste tipo de distribución. Finalmente, el minado basado en cómputos es sólo otra forma de comprarse acceso porque requiere dinero para pagar los costos de electricidad o el desarrollo del hardware necesario para realizar el trabajo.

Para otorgar a cada uno una oportunidad equitativa de involucrarse y recibir moneda, las personas deben tener la oportunidad de trabajar. El desafío es cómo juzgar la calidad relativa y cantidad de trabajo que los individuos proveen y de qué forma lograr que se que repartan eficientemente los premios a millones de usuarios. Esto requiere la introducción de un proceso de votación escalable. En particular se requiere que la autoridad que reparta los fondos sea tan distribuída y descentralizad como sea posible.

El primer paso para premiar millones de usuarios es encomendarse a la distribución de un monto fijo de moneda mas allá de cuánto trabajo sea realizado o cómo votan los usuarios. Esto cambia la pregunta de "¿Debemos pagar?" a "¿A quién pagar?" y señalar al mercado que la moneda está siendo distribuída y subastada a quien "oferte" mas trabajo.
Esto es similar al *Bitcoin* encomendado premios de 50 BTC a quien encuentre los hashes mas difíciles. Como en *Bitcoin*, todo el trabajo debe ser realizado previo al pago y nada debe ser pagado especulativamente bajo la promesa de realización del trabajo a futuro.

El próximo paso es premiar con algo a cada uno que haga algo aunque sea remotamente positivo. Esto se logra clasificando todo el trabajo hecho y distribuyendo proporcionalmente a su valor. Mientras más competitivo se vuelva el mercado (mayor calidad o cantidad), más difícil se torna recibir el mismo pago.

### 4.5.2 - Votando sobre la distribución de la moneda

Asumiendo que hay un monto fijo de dinero para distribuir, y que aquéllos que tienen intereses creados a largo plazo en el valor a futuro y utilidad de la moneda son quienes deben decidir como distribuirlo. Todos los usuarios con inversión emiten sus votos a quien haya hecho el mejor trabajo y al final del dia el dinero disponible para ese día es dividido proporcionalmente a los votos de manera que todos los que tengan al menos un voto positivo neto, obtiene algo.

El proceso de voto inocente genera un Dilema del Prisionero, donde cada votante individualmente tiene incentivo para votarse a si mismo a expensa del objetivo del resto de la comunidad. Si cada votante se votara a si mismo entonces no habría dinero distribuído y la moneda entera fallaría en ganar efecto de red. Por otro lado, si sólo un votate se autovota, entonces él obtendría ganancias no merecidas mientras el efecto en el valor total de la moneda sería mínimo.

Para realinear lso incentivos y desalentar a los individuos de simplemente autovotarse, el dinero debe ser distribuído de manera no linear. Por ejemplo una función cuadrática en los votos, ej.: alguien con el doble de votos que otro debería recibir cuatro veces el valor del pago y alguien con tres veces mas de votos debería recibir nueve veces el pago. En otras palabras, el premio es proporcional a los *votos^2* (al cuadrado), en lugar de a la cantidad de votos. Esto espeja el valor del efecto de red, que crece con *n^2* el número de participantes, de acuerdo al Ley de Metcalfe[5].

Asumiendo que todos los usuarios poseen la misma cantidad de fondos, alguien que sólo se autovota recibirá menos que alguien que recibe votos de 100 usuarios distintos. Esto alienta a los usuarios a coooperar para votar las mismas cosas para maximizar el pago. El sistema también crea incentivos financieros para los usuarios *confabularse* en donde votar y luego dividirse el premio equitativamente entre ellos.

	[5] Metcalfe’s Law https://en.wikipedia.org/wiki/Metcalfe%27s_law
    
#### 4.5.2.a - Complicidad en la votación

Mientras la cooperación para distribuír fondos al mejor trabajo es el objetivo deseado, la confabulación que socabe éste objetivo debería ser minimizada. Hay dos tipos de complicidad o confabulación, la más directa es cuando un usuario simplemente compra un mayor monto que otros, y los otros se involucran coordinando un largo número de partes interesadas para trabajar juntos. Un conjunto mas grande de partes interesadas puede tener una influencia de voto de 100 o incluso 1000 interesados mas pequeños lo que significa que éstos tienen un incentivo aún mas grande para autovotarse que si estuvieran en una distribución linear.

Independiente de cuánto dinero tenga cualquier individuo, siempre hay varios otros individuos con riquezas similares. Incluso el individuo más enriquecido raramente tiene mucho mas que la combinación de los que le siguen en cantidad de riquezas. Incluso, aquéllos que tienen una gran inversión en una comunidad también tienen más riesgo de perder al intentar jugarle al sistema de votos para su beneficio. Sería como si el CEO de una compañía decidiese dejar de pagar salarios para guardarse las ganancias en su bolsillo. Todos dejaría de trabajar y se irían a otras compañías y su empresa quedaría vacía y sin valor, dejando al CEO en bancarrota en lugar de rico.

Afortunadamente, cualquier trabajo que esté obteniendo una gran concentración de votos también gana más escrutiño (publicidad). A través de la adición de votación negativa es posible para participantes de menor talla nulificar el poder de voto de grupos confabulado o contrarrestar a los grandes poseedores. Tambipen, los grandes poseedores tienen mas para perder si la oneda falla en su valor debido a abusos de lo que pueden ganar por autovotarse. De hecho, los grandes poseedores honestos son usualmente mas efectivos en castigar el abuso y usando votos negativos de lo que serían al votar contribuciones mas pequeñas.

El uso de votos negativos para evitar que la gente abuse el sistema apalanca la mentalidad "cangrejo" que muchas personas poseen cuando se percibe que un individuo está obteniendo ganancias a expensas de los demás. Mientras la mentalidad de "cangrejo" normalmente se refiere a personas de corta visión detrimentando a las buenas personas, también permite a las buenas personas mantener a las malas abajo.

El único "problema" con la mentalidad de cangrejo es cuando la gente cree equivocadamente que alguien está beneficiándose a expensas del resto.

###### La Historia de la cubeta de cangrejos [6]

*Un hombre se encontraba caminando por la playa y vió a otro hombre pescando en el muelle con una cubeta a su lado. A medida que se acercaba, vió que la misma estaba destapada y tenía cangrejos vivos en su interior.
"¿Por qué no tapa su cubeta para que no escapen los cangrejos?", preguntó.
"No entiendes.", respondió el pescador, "Si hay sólo un cangrejo en la cubeta, éste trepará y escapará rápidamente, sin embargo, cuando hay muchos cangrejos en ésta, si uno trata de trepar por un lado, los demás lo tomarán y lo devolverán adentro para que sufra el mismo destino que el resto."*

También sucede con las personas. Si uno intenta hacer algo diferente, obtener mejores notas, mejorarse, escapar a su entorno, soñar en grande, otras personas intentarán arrastrarlo abajo y compartir su destino.

Eliminar el "abuso" no es posible y tampoco debería ser el objetivo. Incluso aquellos quienes intentan "abusar" del sistema también están trabajando. Cualquier compsensación que obtengan por sus intentos satisfactorios de abusar o confabularse es cuando menos valioso para el propósito de de distribuír la moneda como en el sistema de trabajo empleado por la minería tradicional de *Bitcoin* o de minería confabulada a través de *pools* de minado. Todo eso es necesario para asegurar que el abuso no sea tan rampante como para socabar el incentivo para realizar verdadero trabajo de soporte de la comunidad y su moneda.

La meta de desarrollar una moneda comunitaria es obtener mas "cangrejos en la cubeta". Tomar medidas extremas para eliminar todo abuso es como intentar poner una tapa en la cubeta para prevenir que se escapen algunos cangrejos y viene a expensas de hacerlo mas difícil de agregar nuevos integrantes. Alcanza con hacer las paredes resbaladizas y dar a otros "cangrejos" el suficiente poder para prevenir que otros "escapen".

	[6] The Story of the Crab Bucket, http://guidezone.e-guiding.com/jmstory_crabs.htm

### 4.5.3 - Tasa limitada de voto

Una mayor parte de minimizar el abuso es limitar la tasa de voto. Los usuarios individuales sólo pueden leer y evaluar tántos items de trabajo diarios. Cualquier intento de votar mas frecuentemente que ésto es una señal de automatización y potencial abuso. A través del límite de tasa de voto, los participantes que voten más frecuentemente tienen su voto menos valioso que los participantes que votan con menos frecuencia. Los intentos de dividir *tokens* entre múltiples cuentas también divide la influencia y por ende no resulta en un incremento neto en influencia ni saltea el límite de tasa impuesto en el voto.

![](fig/fig1.png)

El gráfico de arriba muestra cómo el poder de voto de un usuario decrece cada vez que vota y luego se regenera a medida que pasa el tiempo sin votar. Estos gráficos usan una unidad nominal de tiempo y podría ser hecho a escala de cualquier tasa de voto. Nótese que el poder de voto cae rapidamente durante períodos de votación contínua, y luego se recupera lentamente.
El poder de voto es multiplicado por los *tokens* invertidos de un usuario para determinar la parte que debería ser colocada en el *pool* de pagos para determinado ítem.

### 4.5.4 - Pagos retrazados

Para prevenir abusos a futuro, todos los pagos son retrasados por un promedio ponderado de 24 horas a partir del momento en que cada voto fue emitido. Esto asegura que grandes poseedores no puede atinar pagos votando al menos un segundo antes que otros votantes (también conocidos como "cangrejos") tengan la oportunidad de rechazar potenciales abusos. Una vez que se realiza el pago al usuario, el conteo de votos es restaurado a 0. Si vienen votos luego del pago, el proceso vuelve a comenzar. 

![](fig/fig2.png)

Este gráfico muestra cómo el período de expiración de voto cambia en respuesta a nuevos votos positivos y negativos siendo aplicados. Nuevos votos extienden el período de pago en proporción a cuán grande son relativos a todos los votos que se han sucedido anteriormente. Se puede ver cerca de la línea de tiempo con valor *40* un gran numero de nuevos votos que extienden el período de votación por 12 horas, los votos menores subsecuentes tienen mucho menos impacto en el período de votación.


### 4.5.5 - Distribución de pagos

Una de las metas primordiales del sistema de premios de Steem es producir las mejores discusiones on internet. Cada año el 10% de la capitalización de mercado de Steem es distribuída a los usuarios que envían, votan y discuten contenido. Como el tamaño de *Bitcoin* ésto podría ser tanto como $1.75 millones de dólares por día siendo entregados a los contribuyentes.

![](fig/fig3.png)

La distribución efectiva dependerá del patrón de votación de los usuarios, pero sospechamos que la amplia mayoría de los premios será distribuída entre el contenido mas popular. Steem prepara los pagos proporcional a *n^2* veces el monto de Steem Power votando en un post. En otras palabras, el post *p* recibirá un pago proporcional a:

	( votos[p]^2) / suma(votos[0...n]^2)

La Ley de Zipf[7] es una de esas reglas empíricas que caracterizan muy bien un sorprendente rango de fenómenos del mundo real. Ésta dice que si ordenamos determinada colección grande por tamaño o popularidad, el segundo elemento en la colección medirá aproximadamente la mitad del primero, el tercero un tercio del primero y así sucesivamente. En general, el item en la posición X medirá aproximadamente 1/X del primero.

Tomando la popularidad como una medida de valor tosca, entonces el valor de cada item individual es dado por la Ley de Zipf. Esto es, si tenemos un millón de items, entonces los 100 mas populares contribuirán un tercio del valor total, los próximos 10.000 otro tercio, y los restantes 989.900 el tercio restante. El valor de la coleccion de *n* items es proporcional a *log(n)*.

El impacto de esta distribución de votos y pagos ofrece grandes recompenzas al buen contenido mientras se mantiene el premiado a los pequeños jugadores por el *long-tail* de su contribución.

El efecto económico de ésto es similar a la lotería donde la gente sobreestima su probabilidad de obtener votos y por ende trabaja mas del valor esperado de su premio y por lo tanto maximizan el monto total de trabajo realizado en servicio de la comunidad.
El hecho de que todos "ganen algo" juega sobre la misma psicología que suelen usar los casinos para mantener a la gente apostando. Dicho de otra forma, los pequeños premios ayudan a reforzar la idea de que es posible ganar premios mayores.

	 [7] Zipf’s Law https://en.wikipedia.org/wiki/Zipf%27s_law

#### 4.5.5.a - Recompensas para posts padres

Una buena discusión requiere posteos hacia adelante y hacia atrás. Cuando usted responde a otro, ellos obtienen un 50% de cualquier pago que usted obtenga en ese hilo. Esta regla aplica hasta 6 niveles de profundidad. Empezando una gran discusión premia ampliamente al posteador inicial.

Fallar en anidar propiamente sus posts en la discusión es una buena forma de ser votado para abajo.

Esta estructura de incentivo motiva a la gente a contribuír de forma que motiva a otros a involucrarse. Alienta a las personas a hacer buenas preguntas para que otros puedan proveer respuestas valiosas.

### 4.5.6 - Pagos

Cuando un post recibe un pago, éste toma la forma de 50% de SMD y 50% de SP. El Steem Power da al usuario un poder aumentado de voto y transacción mientras que el SMD da al usuario un beneficio inmediato en una moneda estable. Como ya hemos analizado en profundidad, tanto el SP como el SMD están diseñados para alentar la posesión a largo plazo en lugar de la venta a corto plazo.

## 4.6 - Algoritmo de consenso

El consenso es el proceso por el cual una comunidad llega a un acuerdo no ambiguo y universalmente reconocido sobre una pieza de información. Hay muchos algoritmos desarrollados por la sociedad para alcanzar consenso sobre quién es dueño de qué. Cada gobierno en la tierra es un algoritmo de consenso primitivo con el cual la población acuerda atenerse a cierto conjunto de reglas encapsuladas en una Constitución. los gobiernos establecen cortes, jueces y jurados para interpretar hechos subjetivos y emitir una decisión final. La mayoría de las veces la gente se atiene a estas decisiones incluso si son erróneas.

Los algoritmos utilizados por las criptomonedas proveen una mejor forma para alcanzar consenso. Testimonios criptográficamente firmados por individuos son registrados en un registro público que establece un orden global absoluto de eventos. Una algoritmo computacional determinístico puede procesar este registro para derivar una conclusión universalmente aceptada. En tanto los miembros de una comunidad estén de acuerdo en el algoritmo de proceso, el resultado de dicho algoritmo es autoritario.

La consideración primaria es determinar qué testimonio es permitido para entrear el registro público. Los sistemas deberían ser diseñados para minimizar el potencial para su censura. La censura en el registro público es similar a prevenir que alguien vote en una elección. En ambos casos un individuo tiene su impacto en el consenso global imposibilitado.

### 4.6.1 - Consenso en Steem

Conceptualmente, el algoritmo de consenso adoptado por Steem es similar al algoritmo de consenso adoptado por compañías de todo el mundo. Gente con interés invertido en el valor futuro de Steem, vota para elegir individuos responsables de incluír testimonios en el registro público. El peso del voto es determinado proporcionalmente al interés invertido de cada individuo.

En el mundo de las criptomonedas, se refiere comunmente al registro público como *blockchain*. Un *block* o bloque es un grupo de transacciones firmadas (testimonios).

En Steem, la producción de bloques es realizada en rondas. En cada ronda se seleccionan 21 testigos para crear y firmar bloques de transacciones. Diecinueve (19) de éstos testigos son seleccionados para aprobar las votaciones, uno es seleccionado por una prueba-de-trabajo computacional (*Proof of work*), y un puesto es compartido por tiempo por cada testigo que no logró entrar en el *top* 19 proporcional de mas votados. Los 21 testigos activos son mezclados en cada ronda para prevenir que cualquiera de los testigos ignore constantemente bloques producidos por el mismo testigo ubicado anteriormente en ese puesto.

Este proceso está diseñado para proveer la mejor confiabilidad mientras se asegura que todos tengan potencial para participar en la producción de bloques independientemente de si son suficientemente populares para ser votados dentro de la lista de los 19 testigos principales elegidos: pacientemente esperan en línea con todos los demás que no estén entre los 19 principales, compran suficiente poder computacional para resolver una prueba de trabajo (*proof of work*) mas rápido que otros, o compran mas SP para mejorar su poder de voto. Generalmente hablando, aplicar censura es una buena forma de elegir testigos para perder su trabajo y por lo tanto, es improbable que sea un problema real en la red de Steem.

Debido a que los testigos activos son conocidos de antemano, Steem puede acomodar los testigos para producir bloques cada 3 segundos. Los testigos sincronizan sus producción de bloques a través del protocolo NTP. Una variante de este algoritmo ha sido utilizada por la red BitShares por alrrededor de una año donde ha demostrado ser confiable.

### 4.6.2 - Minando en Steem

Los blockchains de prueba de trabajo (*PoW* ó *Proof of work*) tradicionales combinan la producción de bloques con la solución de una prueba de trabajo. Debido a que el proceso de resolver una prueba de trabajo toma una cantidad impredecible de tiempo, el tiempo de producción de bloques resulta también indeterminado. Steem apunta a tener una producción confiable y consistente cada 3 segundos casi sin potencial de *forks* o desvíos.

Para lograr ésto, Steem separa la producción de bloques de la solución de pruebas de trabajo. Cuando un minero resuelve una prueba de trabajo para Steem, éste emite una transacción que contiene el trabajo o resultado. El próximo testigo programado lo incluye entonces en el blockchain. Cuando la transacción es efectivamente incluída el minero es añadido a la cola de mineros programados para producir bloques. Cada ronda un minero salta de la cola y es incluído en el conjuto activo de testigos. El minero obtiene el pago cuando éstos producen un bloque en el tiempo que tienen programado. 

La dificultad de la prueba de trabajo se duplica cada vez que el largo de la cola crece por 4. Debido a que un minero sale de la cola a cada ronda, y cada ronda toma 21 * 3 = 63 segundos, la dificultad automáticamente se divide si no se resuelve una prueba de trabajo en no más de 21 * 3 * 4 = 252 segundos.

#### 4.6.2.a - Premios de minado requieren Steem Power

Luego del primer mes, a los minadores de Steem se les paga en Steem Power (SP). El Steem Power es liquidado a través de un proceso de dos años de "powering down". Esto significa que los mineros deben esperar un buen tiempo, seguramente varios meses, antes de que suficientes premios de minado hayan sido desactivados ("powered down") para permitirles recuperar el costo de electricidad y recursos computacionales. El proceso de *powering down* desalienta la creación de *pool* de minado porque el operador del *pool* debería tener que repartir los pagos entre años.

El efecto de pagar los premios de minado en SP es la prevención de la utilización del precio diario por parte de los mineros para determinar la ganancia del proceso de minado. Pocos estarán de acuerdo en cuál será el precio en el futuro.
Esto quiere decir que la dificultad será determinada por aquellos que depositen mayor estima en el valor a futuro. Los mineros sin un interés en la plataforma a largo plazo serán desalentados de competir. Finalmente se logra que las procedencias de minar sean menos tendientes a ser extraídas del mercado debido a que éstas serán acumuladas por los creyentes de la plataforma a largo plazo.

#### 4.6.2.b - Algoritmo de minado

El algoritmo de minado adoptado por Steem requiere que el minero tenga acceso a la clave privada de la cuenta que recibirá los premios. Este requerimiento tiene varias consecuencias importandes. Primero alienta la optimización de los algoritmos de verificación de la firma de curva elíptica requerida por Steem. Segundo, hace más desafiante la instalación de *pools* de minado porque el operador del mismo debería compartir el control de la ganancia con mineros "anónimos". Tercero, dificulta el uso de botnets al hacer que operador necesite distribuír su llave privada a todas las máquinas comprometidas.

El siguiente pseudocódigo describe cómo se calcula el valor del hash de la prueba de trabajo (*proof of work*):

```
Let H = Head Block ID
Let H2 = SHA256(H+NONCE)
Let PRI = Producer Private Key
Let PUB = Producer Public Key
Let S = SIGN(PRI, SHA256( H ) )
Let K = RECOVER_PUBLIC_KEY( H2, S )
Let POW = SHA256( K )
```

#### 4.6.2.c - Resistencia a Botnets

Muchas monedas basadas en prueba de trabajo terminan siendo minadas por *botnets*. Una *botnet* es una colección de miles o millones de máquinas que han sido comprometidas por intrusos informáticos. Estos intrusos roban los recursos computacionales y eléctricos de dichas máquinas comprometidas para minar *tokens* de criptomoneda.

Steem posee varias propiedades que previenen que éstos ladrones computacionales obtengan beneficios. Los operadores de las *botnets* son "empresas" que buscan lucro y típicamente venden sus recursos robados al mayor postor. Esto significa que aquellos que utilizan una *botnet* pagan el poder computacional de la misma forma que lo hace alguien usando el servicio EC2 de Amazon. El requerimiento para impulsar Steem significa que el capital gastado en comprar recursos de la *botnet* estarán atados por un período durante el cual el operador se expone a la volatilidad de los precios.

Otra forma en que se previene que los operadores de las *botnets* obtengan ganancias es la necesidad de que el mismo deba distribuír la llave privada a todas las máquinas comprometidas. Si al menos una de éstas computadoras es descubierta, el operador podría perder las monedas ganadas por toda la *botnet*.

La última mitigación es la dependencia en la latencia. La mayoría de las *botnets* comprometen computadoras con una conexión a internet pobre, éstas conexiones lentas reducen drásticamente la efectividad del recurso computacional.

Debería ser mas conveniente y menos riesgoso para los operadores de *botnets* usar estos recursos para otras actividades que no sean minar STEEM.

#### 4.6.2.d - Resistencia a grupos o *pools* de minado

Los minadores tienen un total de 3 segundos para recibir un bloque, resolver la prueba de trabajo, y obtener la transacción al siguiente productor de bloque. Gran parte de este tiempo se irá en la latencia de la red, lo que implica que es crítico para los mineros poseer buena conexión a la red para lograr un uso efectivo de sus recursos computacionales.

Debido al constante cambio del bloque de cabecera y la latencia de la red, reenviar una plantilla para minar un bloque específico a los participantes del *pool* o grupo de minado agrega latencia adicional y reduce significativamente la eficiencia del minado en grupo (*pool mining*).

### 4.6.3 - Eliminando comisiones de transacción

Steem va más allá para beneficiar a quienes contribuyen a la red. Sería contraproducente dar la espalda y cobrar a los usuarios cada vez que intentan interactuar con la comunidad.

La tecnología blockchain actualmente depende de comisiones de transacción para prevenir spam. Estas comisiones sufren de todos los problemas conocidos con las microtransacciones y previenen que los blockchains sean usados para transacciones de bajo costo. Las aplicaciones verdaderamente descentralizadas deben ofrecer a los usuarios el atractivo de transacciones gratuitas si se desea competir ante sus alternativas centralizadas. Este documento explica el método utilizado por Steem para eliminar la necesidad de comisiones y por ende habilitar un amplio rango de aplicaciones anteriormente inviables de manera descentralizada.

#### 4.6.3.a - El problema de las comisiones

Los blockchains son redes descentralizadas donde todas las transacciones son emitidas a todos los pares (*peers*). Cada tanto se produce un bloque que incluye alguna o todas las transacciones pendientes. Todos los blockchains deben encontrar una solución para prevenir que usuarios maliciosos consuman todo o gran parte de la capacidad disponible de la red con transacciones sin valor o inútiles. Estas transacciones sin valor evitan que transacciones valiosas y útiles sean procesadas en detrimento de la red.

La solución adoptada por la mayoría de los blockchains hasta ahora es cargar una comisión mínima de transacción. Una comisión con un costo de unos pocos centavos es suficiente para lograr que atacar la red no sea redituable e incluso costoso. Mientras ésta solución resuelve el problema del *spam*, introduce nuevos problemas. Imagine resolver el problema del *spam* en emails introduciendo una pequeña comisión en cada correo enviado; la gente no usaría el correo electrónico.




