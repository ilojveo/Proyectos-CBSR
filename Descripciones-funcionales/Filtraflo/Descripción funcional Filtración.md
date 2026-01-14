# Descripción funcional Filtración



## Documentos que acompañan esta descripción

- P&ID: PID-2201BI01A0-BR7, págs: X-046 (filtros, 52), X-045-H2 (bombeo de efluente, 51),X-044-H2 (bombeo de efluente, 49), X-049 (lavado, 55), X-042 (soplantes, 46), X-083 (depósito de coagulante, 97) y X-085 (skid de coagulante para los filtros, 99).
- Esquemas eléctricos Filtraflo: [DOECFF332676_24000488](https://drive.google.com/file/d/1K2Yv-mfcGx6m4tJrQsQVkdPnMApLxXDo/view)
- P&ID Equipo Filtraflo: [DOPFFF313233-2400488](https://drive.google.com/file/d/1ARp57utd1WaAGZpv6rWfaLGWUFM--wTF/view)
- Tabla de intercambio Modbus TCP/IP: [DOLIFF332530_2400488](https://drive.google.com/file/d/1FPEaikLZlxMeexy2XMuhmehHPNNVOxxp/view)
- Tabla de secuencia del Filtraflo [DOLIFF332529_24000488](https://drive.google.com/drive/folders/1xHWoJttHsTa8Bp7czAxyN-ZE2TWyheXZ)
- Lista de E/S con equipos paquete de VWT: [1750217102-VWT-I-LI-006 - I/O List from package skids Rev-3](https://docs.google.com/spreadsheets/d/1TABNGFEBWYtetfe_67veyGEzDdMUs3IFMZzejPBs_fU/edit?gid=96208323#gid=96208323)
- documentos de descripción funcional, [12008579136 CEPSA REV 1.2 20250714 DAF-2A](https://docs.google.com/document/d/1dtHX2HVR9yPwOXtGPGPKXaAwt1ePq4ftFygHJclpNC0/edit?tab=t.0) y [12008579136 CEPSA REV 1.2 20250714 DAF-2B](https://docs.google.com/document/d/1hd1AylWZS2a2C147NFqOwWQYSqX2F5eOXERQes9vPkM/edit?tab=t.0)


## Equipos e instrumentos involucrados

- DAF 2A, BR7-UP-0304A.
- DAF 2B, BR7-UP-0304B.
- Bomba de efluente del DAF 2A, BR7-P-0304A.
- Válvula de regulación de la salida del DAF 2A, BR7-LV-0037A.
- Bomba de efluente del DAF 2B, BR7-P-0304B.
- Válvula de regulación de la salida del DAF 2B, BR7-LV-0037B.
- Bomba de reserva de efluente de los DAF 2A/B, BR7-P-0304C.
- Válvulas de asignación de la regulación de caudal para la bomba de reserva, BR7-UV-0320/21.
- Bomba de dosificación de coagulante, BR7-P-0168B. En el skid de dosificación existe una bomba de reserva, BR7-P-0168C que se puede asignar al filtro, abriendo la válvula BR7-MV-0348. Si se asigna a este servicio, no se puede asignar a la unidad del DAF 3, y viceversa, si está asignada al DAF 3, no se puede asignar a la filtración.
- Tanque de coagulante, BR7-T-0131, con los siguientes instrumentos asociados:
  - Nivel analógico, BR7-LT-0095.
  - Nivel alto, BR7-LSH-0096A, y nivel bajo, BR7-LSL-0096B.
- Bombas de lavado, BR7-P-0406A/B.
- Válvula de regulación del caudal de agua de lavado, BR7-FV-0079.
- Caudalímetro de agua de lavado, BR7-FT-0079.
- Tanque de agua filtrada, BR7-T-0405, con los siguientes instrumentos asociados:
  - BR7-LT-0039 y BR7-LT-0040.Caudalímetro de entrada de caudal a los filtros, BR7-FT-0034.

- Caudalímetro de aire de lavado, BR7-FT-0112.
- Válvula de regulación de aire de lavado, BR7-FV-0112.
- Válvula de alivio de aire de lavado del skid de filtración, BR7-UV-0353.
- Skid de filtración, BR7-UP-0403A/B/C.



### Señales a intercambiar con los skids involucrados

#### Señales del Skid de los filtros

| TAG              | Tipo | Descripción                                                  |
| ---------------- | ---- | ------------------------------------------------------------ |
| BR7YL   0027     | DO   | MULTIMEDIA FILTERS  - SUPPLY PUMP - / HEALTHY                |
| BR7YL   0046     | DO   | MULTIMEDIA FILTERS  - UNIVERSAL DIGITAL INPUT 1 / WATER DEMAND |
| BR7YL   0047     | DO   | MULTIMEDIA FILTERS  - UNIVERSAL DIGITAL INPUT 2 / ONLINE COMMAND |
| BR7YL   0033     | DO   | MULTIMEDIA FILTERS  - UNIVERSAL DIGITAL INPUT 3 / RESET      |
| BR7YL   0034     | DO   | MULTIMEDIA FILTERS  - UNIVERSAL DIGITAL INPUT 4 / WASHING INHIBIT |
| BR7YS   0050     | DI   | MULTIMEDIA FILTERS - Backwash Pump - / Run Cmd               |
| BR7YS   0052     | DI   | MULTIMEDIA FILTERS - Supply pump - / Run Cmd                 |
| BR7YS   0054     | DI   | MULTIMEDIA FILTERS - Universal Digital Output 1 / HEALTHY    |
| BR7YS   0055     | DI   | MULTIMEDIA FILTERS - Universal Digital Output 2 / PRODUCCIÓN |
| BR7YS   0056     | DI   | MULTIMEDIA FILTERS - Universal Digital Output 3 / ALGÚN FILTRO LAVANDO |
| BR7YS   0057     | DI   | MULTIMEDIA FILTERS - Universal Digital Output 4 / ALTO CAUDAL DE LAVADO |
| BR7YS   0053     | DI   | MULTIMEDIA FILTERS - Raw Water Aeration Inlet Valve Open Cmd |
| **A DETERMINAR** | DI   | MULTIMEDIA FILTERS - Raw Water Aeration Outlet Valve Open Cmd |
| **A DETERMINAR** | AI   | MULTIMEDIA FILTERS - BACKWASHING PUMP *FLOW* SETPOINT        |



#### Señales del skid de dosificación de coagulante para los filtros



| TAG           | Tipo | Descripción                                              |
| ------------- | ---- | -------------------------------------------------------- |
| BR7YA   0168B | DI   | POSTCOAGULATION COAGULANT dosing pump - Alarm relay      |
| BR7YL   0168B | DI   | POSTCOAGULATION COAGULANT dosing pump - Pacing relay     |
| BR7XSL  0168B | DO   | POSTCOAGULATION COAGULANT dosing pump - Pause            |
| BR7SC   0168B | AO   | POSTCOAGULATION COAGULANT dosing pump - Reference        |
| BR7YA   0168C | DI   | POSTCOAGULATION DAF COAGULANT dosing pump - Alarm relay  |
| BR7YL   0168C | DI   | POSTCOAGULATION DAF COAGULANT dosing pump - Pacing relay |
| BR7XSL  0168C | DO   | POSTCOAGULATION DAF COAGULANT dosing pump - Pause        |
| BR7SC   0168C | AO   | POSTCOAGULATION DAF COAGULANT dosing pump - Reference    |
| BR7HSH 0034   | DO   | COAGULANT SPARE PUMP TO FILTERS VALVE - OPEN COMMAND     |
| BR7SV 0034    | DO   | COAGULANT SPARE PUMP TO FILTERS VALVE - CLOSE COMMAND    |
| BR7ZSL 0034   | DI   | COAGULANT SPARE PUMP TO FILTERS VALVE - FEEDBACK CLOSE   |
| BR7ZSH 0034   | DI   | COAGULANT SPARE PUMP TO FILTERS VALVE - FEEDBACK OPEN    |



## Descripción somera del proceso y la secuencia

El propósito de esta descripción funcional es facilitar la programación en el sistema DCS de los equipos que tienen que trabajar con los filtros.

El efluente viene las unidades DAF 2 A/B, BR7-UP-0304 A/B, a través de sus válvulas de regulación, BR7-LV-0037A/B. Existe una bomba de reserva para las dos unidades DAF, BR7-P-0304C que tiene asociadas un par de válvulas BR7-UV-0320/21 para que la salida de dicha bomba vaya a la entrada de las válvulas reguladoras BR7-LV-0037 A/B, respectivamente.

### Servicio

Cuando alguno de los DAFs vaya a ponerse en marcha, tiene que tener la señal del skid de filtración para confirmar que está disponible (`BR7YS   0054`, "*healthy*"). Cuando se vaya a poner en marcha el bombeo de efluente de cualquiera de los DAFs, hay que dar la señal de demanda al skid de filtración (`BR7YL   0046`, U-DO1, "*water demand*") y esperar la señal de marcha del bombeo de efluente (`BR7YS   0052`, "*supply pump - Run Cmd*"). En caso de que la señal `BR7YS   0052` se deje de recibir, se tiene que parar el bombeo de efluente de los DAFs. Si, por el proceso de los DAFs, se tiene que parar el bombeo, se deja de enviar la señal de demanda de agua (`BR7YL   0046`, U-DO1, "*water demand*") para que sea el filtro el que retire la señal de marcha del bombeo de efluente (`BR7YS   0052`, "*supply pump - Run Cmd*") para parar el bombeo.

#### Dosificación de coagulante

Durante la fase de servicio se realiza una dosificación de coagulante. Puede ser habilitada o deshabilitada por el operador desde el SCADA.

Cuando arranca el bombeo de efluente (se tienen las señales `BR7YS   0052` y la señal de  confirmación de marcha de alguna de las dos bombas de BR7-P-304A/B/C) se arranca el bombeo de dosificación de coagulante, normalmente la BR7-P-0168B (señal de marcha `BR7XSL  0168B`).

La dosificación será proporcional al caudal de entrada a los filtros:

$$
Q_{coag} = Q_{ent} \cdot  \frac{D_c}{W \cdot M \cdot 10}
$$

Donde:	
- Q<sub>coag</sub>: Caudal de coagulante en l/h
- Q<sub>ent</sub>: Caudal de entrada en m<sup>3</sup>/h `BR7FT  0034`
- D<sub>c</sub>: Dosis de coagulante requerida en mg de metal (Fe/Al) por litro (a introducir por el operador). 
- W: Concentración del metal en el producto comercial en % (a introducir por el operador).
- M: Densidad del coagulante en kg/l (a introducir por el operador).

Como no existe un caudalímetro para el coagulante, se tiene que calibrar la dosificadora, v<sub>1</sub> y v<sub>2</sub> que darán dos caudales q<sub>1</sub> y q<sub>2</sub>, quedando la siguiente ecuación:

$$
V_{dosif} = \frac{v_2 - v_1}{q_2 - q_1} \cdot Q_{coag} + v_1
$$

Donde:
- v<sub>1</sub> y v<sub>2</sub> son los puntos de referencia de velocidad de la dosificadora, en % (a introducir por el operador).
- q<sub>1</sub> y q<sub>2</sub> los caudales a dichos puntos de referencia, en l/h (a introducir por el operador).
- Q<sub>coag</sub>: Caudal de coagulante en l/h, que viene de la ecuación anterior.
- V<sub>dosif</sub>: Velocidad de referencia de la dosificadora.

### Lavado

El lavado de los filtros se gestiona desde su propio PLC, sin embargo el DCS tiene que manejar los equipos exteriores al filtro para que lave. Hay que señalar que como es una batería de 3 filtros (2 en funcionamiento y uno en espera, con rotación automática), aunque un filtro esté lavando, uno o los otros dos están en marcha.

Para que el lavado sea efectivo, ha de garantizarse que se dispone de la suficiente agua para que se complete. Existe una señal de inhibición de lavado, `BR7YL   0034`, que se activa en los siguientes casos:

- No existe el suficiente nivel en el tanque de agua filtrada antes del inicio del lavado (según los niveles BR7-LT-0039 y BR7-LT-0040, habrá una consigna para determinar el nivel inicial del tanque de agua filtrada para permitir el lavado).
- No se tiene disponible (en automático) ninguna de las bombas de lavado, BR7-P-0406A/B.
- No se tiene disponible (en automático) la válvula de regulación del caudal de agua de lavado, BR7-FV-0079 o el caudalímetro de agua de lavado, BR7-FT-0079. El operador podrá "puentear" esta condición, desde el SCADA, pero deberá estar pendiente de posicionar la válvula manualmente para que el lavado se realice correctamente.
- No se tiene disponible (en automático) la válvula de regulación de aire de lavado, BR7-FV-0112 o el caudalímetro de aire de lavado, BR7-FT-0112. El operador podrá "puentear" esta condición, desde el SCADA, pero deberá estar pendiente de posicionar la válvula manualmente para que el lavado se realice correctamente.
- No se tiene disponible (en automático) la válvula de alivio de aire de lavado del skid de filtración, BR7-UV-0353.
- No se tiene en marcha (en automático) ninguna de las soplantes de los MBBR (BR7-SO-0301 A/B/C).

Durante el lavado, desde el skid de filtración se dará la orden de la marcha del bombeo de lavado (`BR7YS   0050`, "*Backwash pump - Run Cmd*") y la consigna de caudal de lavado a través de una señal 4-20 mA (**tag a determinar** *BACKWASHING PUMP FLOW SETPOINT*). 

Por otra parte, una de las etapas de lavado consiste en lavar con aire o con agua y aire. Cuando el filtro demande la entrada de aire (`BR7YS   0053`, "*Raw Water Aeration Inlet Valve - Open Cmd*") se deberá abrir la válvula BR7-FV-0112. 

El filtro también va a solicitar la apertura de la válvula de liberación de aire BR7-UV-0353 mediante la señal (`BR7YS   0053`, "*Raw Water Aeration Inlet Valve - Open Cmd*")



## Equipos

### Bombeo de alimentación (BR7-P-0304A/B/C)

Las condiciones y regulación de estos equipos se pueden encontrar en los documentos de descripción funcional, *12008579136 CEPSA REV 1.2 20250714 DAF-2A* y *12008579136 CEPSA REV 1.2 20250714 DAF-2B*

Cuando se den las condiciones para el bombeo del DAF 2A, BR7-UP-0304A, o del DAF 2B, BR7-UP-0304B, arrancará la bomba correspondiente, BR7-P-0304A o BR7-P-0304B. 

#### Condiciones de marcha automática


Según las especificaciones arriba mencionadas, al alcanzar el nivel de consigna *BR7-LT0037A_REL1* se dan las condiciones de arranque de la bomba (marcha/paro por nivel) para  el efluente del DAF 2A y *BR7-LT0037B_REL1* para el efluente del DAF 2B.

Si se dan estas condiciones y el filtro está disponible (`BR7YS   0054` "*Universal Digital Output 1 / HEALTHY*" activa), se activa la señal de demanda de agua (`BR7YL   0046` "*UNIVERSAL DIGITAL INPUT 1 / WATER DEMAND*")

Cuando se cumplen estas condiciones, al recibir la señal de marcha del bombeo (`BR7YS   0052`, "*supply pump - Run Cmd*") se arranca la bomba correspondiente cuando la válvula correspondiente se ha posicionado para la apertura inicial. 


#### Regulación 

Como se indica en los documentos de descripción funcional, se realiza un PID para mantener el nivel constante. Este PID se realiza con la válvula de regulación de nivel correspondiente, BR7-LV-0037A/B.

Antes de arrancar la bomba la válvula se pondrá en una posición inicial (*BR7-LV-0037A/B_pos_ini*). 

El PID permanece en "*manual*" (fijando la posición de la válvula) y la válvula permanece en esta posición hasta que se recibe la señal de que el filtro ha pasado al estado de "*Producción*" (`BR7YS   0055` *Universal Digital Output 2 / PRODUCCIÓN*), donde el PID pasa a "*automático*" para mantener el nivel constante.

Las posiciones de apertura máximas y mínimas estarán limitadas. 

#### Bomba de reserva

En caso de que la bomba principal de uno de los dos DAFs entre en fallo, arrancará la bomba de reserva. 

Dado que la bomba de reserva se puede asignar a los dos DAFs, existirán unas variables internas para que el sistema identifique a cuál de ellos está asignada la bomba de reserva. Esta asignación puede ser automática (hasta que no falla una de las bombas no se asigna la bomba de reserva y la primera que falla "coge" dicha bomba de reserva) o manual, de forma que se preasigna la bomba de reserva a una de las dos bombas y si la otra falla se queda sin poder bombear el efluente.

En caso de que una bomba entre en fallo, y se pueda asignar o tuviese asignada la bomba de reserva y ésta esté disponible y en automático, así como las válvulas BR7-UV-0320 y BR7-UV-0321 en automático y sin fallo.

En ese caso, se abrirá la válvula correspondiente BR7-UV-0320/BR7-UV-0321, y se arranca la bomba de reserva. 

Mientras que se abre la válvula y arranca la bomba, el PID se queda "congelado" quedándose la válvula de regulación de nivel en su última posición.

#### Enclavamiento

- Alarma de nivel bajo del nivel correspondiente BR7-LT-0037A/B.

### Bombas de lavado (BR7-P-0406A/B)

Durante las etapas de filtración, la bomba arranca según la demanda del skid de filtración.

#### Condiciones de marcha automática

Al recibir la señal de marcha del bombeo de lavado (`BR7YS   0050`, "*Backwash pump - Run Cmd*") se arranca la bomba principal. 

#### Regulación

El filtro envía una salida analógica (4-20 mA) para indicar el caudal requerido en cada etapa (**tag a determinar** *BACKWASHING PUMP FLOW SETPOINT*). Habrá que escalar esta entrada analógica para que coincida con la señal que envía el filtro. La regulación del caudal se realiza con el lazo `BR7FC  0079`. El controlador (PID) tomará la señal de dicho SetPoint que envía el filtro para ajustar el caudal con la válvula de regulación.

Antes de poner en marcha la bomba de lavado correspondiente, la válvula de regulación BR7-FV-0079 se pondrá en una posición inicial (*BR7-FV-0079_pos_ini*) (PID en *manual*) y transcurridos unos segundos el PID pasa a *automático* para coger la referencia de caudal. 

#### Gestión de la alternancia

La alternancia de las bombas se realizará según se haga en el resto del proyecto.

#### Enclavamiento

Alarma LL de los niveles BR7-LT-0039/40. 

### Soplantes (BR7-SO-0301A/B/C)

El control de las soplantes está definido en la descripción de control *1750217102-P-DP-002 Control description MBBR* y siempre están en marcha.

### Válvula de alivio de presión BR7-UV-0353

En automático, esta válvula abre y cierra según el estado de la señal **`TAG A DETERMINAR`** - *Raw Water Aeration Outlet Valve Open Cmd*, pero tendrá cierto retardo a la desconexión (de pocos segundos).


### Válvula de control de caudal de aire de lavado BR7-FV-0112 

Durante algunas etapas de la fase de lavado, es necesario aportar aire al filtro. Esto se hace abriendo la válvula de caudal de aire de lavado, BR7-FV-0112 al recibir la señal de apertura de aire de lavado, `BR7YS   0053` - *Raw Water Aeration Inlet Valve Open Cmd*. 

Al recibir esta señal, la válvula realizará una rampa de unos segundos para alcanzar el caudal de aire de lavado 

#### Variables a establecer

**Nota: los tags son a confirmar, no están en el Hardware Freeze**

- Setpoint de aire de lavado a conseguir `BR7FC  0112 SP-Fin`. 
- Tiempo de duración de la rampa `Tim_SP_BR7FC  0112`, inicialmente 15 seg.
- Tiempo de intervalo `Tim_Int_SP_BR7FC  0112`, inicialmente 3 seg.
- Contador de tiempo de rampa `Tim_Cta_BR7FC  0112`.
- Contador de tiempo de intervalo `Tim_Int_Cta_BR7FC  0112`.
- Setpoint de rampa para el caudal de aire de lavado `BR7FC  0112 SP_Rampa`. 

#### Rampa

Al flanco de la señal de apertura de aire de lavado `BR7YS   0053` - *Raw Water Aeration Inlet Valve Open Cmd* y con alguna soplante en marcha, se inicia la rampa. 

Se realiza la siguiente ecuación
$$
Q_{SP-Rampa} = \frac{Q_{SP-fin}}{Tim_{rampa} } \cdot Tim_{Cta-Rampa}
$$
Siendo Q<sub>SP-Rampa</sub> `BR7FC  0112 SP_Rampa`, Q<sub>SP-fin</sub> `BR7FC  0112 SP-Fin`, Tim<sub>rampa</sub> `Tim_SP_BR7FC  0112` y Tim<sub>Cta-Rampa</sub> `Tim_Cta_BR7FC  0112`.

Al inicio de la rampa se inicia el temporizador para `Tim_Int_Cta_BR7FC  0112`, muy inferior a  `Tim_SP_BR7FC  0112`. Al finalizar, se reinicia, y en cada reinicio, se carga en el SP del PID del controlador `BR7FC  0112` la variable `BR7FC  0112 SP_Rampa`. 

Una vez finaliza la rampa, se deja el controlador con el valor del setpoint deseado.

Para el cierre de la válvula, se hace lo mismo, cuando se deja de recibir la señal  `BR7YS   0053` - *Raw Water Aeration Inlet Valve Open Cmd* se realiza una rampa, por lo que tendrán que existir las variables adecuadas para la rampa de cierre; ya que además los tiempos no tienen por qué ser iguales.


### Dosificadora de coagulante BR7-P-0168B (BR7-P-0168C)

#### Condiciones de marcha automática

Será necesario cumplir las siguientes condiciones:

- El skid de filtración envía la señal de marcha de bombeo de baja (`BR7YS   0052`, "*supply pump - Run Cmd*") .
- Existe confirmación de marcha de las bombas de baja (alguna de las señales `BR7YL   0304A`, `BR7YL   0304B`, `BR7YL   0304C`).
- No existe fallo de la dosificadora (`BR7YA   0168B`). Normalmente, la señal de fallo será a "0" (contacto NC, es decir, si no hay fallo se recibe un "1"), pero se confirmará en la PEM, según la configuración de la dosificadora.
- La bomba está en automático y disponible y no tiene alarma de fallo de confirmación de marcha.
- El skid (BR7-PL-0168) está alimentado. 

#### Monitorización de la dosificación

Lo que viene a continuación es válido para los siguientes skids de dosificación y todas sus bombas:

| SKID | BOMBAS      | EQUIPO |
| :---------: | :---------------: | :---------------: |
| BR7-PL-0122 | BR7-P-122A/B      | CAUSTIC SODA DOSING SKID UF CIP |
| BR7-PL-0121 | BR7-P-121A/B/C    | CAUSTIC SODA DOSING SKID Anaerobic reactors |
| BR7-PL-0123 | BR7-P-0123A/B/C   | CAUSTIC SODA DOSING SKID DAF 1 |
| BR7-PL-0198 | BR7-P-0198A/B/C/D | Caustic Soda dosing skid DAF2 and HVO DAF |
| BR7-PL-0129 | BR7-P-129A/B      | Micronutrients dosing skid Anaerobic Reactors |
| BR7-PL-0120 | BR7-P-120A/B      | Sodium Hypochlorite dosing skid UF CIP |
| BR7-PL-0125 | BR7-P-125A/B      | Citric Acid dosing skid UF CIP |
| BR7-PL-0163 | BR7-P-163A/B/C    | Antifoam dosing skid MBBR |
| BR7-PL-0126 | BR7-P-126A/B/C    | Antifoam dosing skid Anaerobic Reactors |
| BR7-PL-0127 | BR7-P-127A/B/C    | UREA DOSING SKID MBBR |
| BR7-PL-0164 | BR7-P-164A/B      | Urea dosing skid Anaerobic reactors |
| BR7-PL-0128 | BR7-P-128A/B/C    | PHOSPHORIC ACID DOSING SKID MBBR |
| BR7-PL-0161 | BR7-P-151A/B/C    | POLYMER DOSING SKID DAF2 |
| BR7-PL-0162 | BR7-P-152A/B/C    | POLYMER DOSING SKID MULTIFLO |
| BR7-PL-0165 | BR7-P-153A/B      | POLYMER DOSING SKID DAF HVO |
| BR7-PL-0167 | BR7-P-154A/B      | POLYMER DOSING SKID CENTRATES DAF |
| BR7-PL-0166 | BR7-P-166A/B/C    | COAGULANT DOSING SKID DAF2 |
| BR7-PL-0131 | BR7-P-0131A/B/C/D | COAGULANT DOSING SKID DAF1 AND HVO DAF |
| **BR7-PL-0168** | **BR7-P-168A/B/C** | **COAGULANT DOSING SKID CENTRATES DAF AND FILTERS** |
| BR7-PL-0169 | BR7-P-169A/B/C    | COAGULANT DOSING SKID MULTIFLO |
| BR7-PL-0134 | BR7-P-134A/B      | H2SO4 DOSING SKID HVO DAF |
| BR7-PL-0133 | BR7-P-133A/B/C/D  | H2SO4 DOSING SKID DAF1 AND TREATED WATER TANK |
| BR7-PL-0135 | BR7-P-135A/B/C    | H2SO4 DOSING SKID UF CIP AND MBBR |
| BR7-PL-0199 | BR7-P-0199A/B/C/D | H2SO4 DOSING SKID DAF2 AND MULTIFLO EFFLUENT |
| BR7-PL-0137 | BR7-P-137A/B/C    | CACL2 DOSING SKID MULTIFLO |

Las bombas dosificadoras tienen una señal de marcha `BR7XSL` y una señal de monitorización `BR7YL`. Durante la puesta en marcha se verá si el contacto para la señal de marcha es NC (un "0" arranca la bomba y un "1" la para) o NO (un "1" arranca la bomba y un "0" la para, como ocurre normalmente con todos los motores). 

La señal de monitorización de la bomba (`BR7YL`) se activa ("1") cuando el impulsor de ésta llega al final, por lo que está dando parpadeos con más tiempo desactivado que activado. Para monitorizar correctamente, habrá que tener en cuenta esto, con un temporizador que se active cuando se dé la señal de marcha `BR7XSL` y se reinicie cada vez que se active la señal de monitorización (`BR7YL`). Si el temporizador llega a su fin, será cuando se active la alarma de fallo de dosificadora por confirmación de marcha. Esta alarma detiene la marcha de la dosificadora, aunque la monitorización puede ser deshabilitada por lo que esta alarma no saltaría nunca. 

Se establecerán dos tiempos, mínimo y máximo, para escalar el tiempo de temporizador en función de la velocidad de la dosificadora (0% -> tiempo máximo, 100% -> tiempo mínimo), que se asignarán al temporizador cada vez que se reinicie el temporizador (activación de la señal de monitorización `BR7YL`). Estos parámetros se asignarán para cada dosificadora durante la puesta en marcha.

Al arranque de la dosificadora siempre estará asignado el tiempo máximo para monitorización. Se tendrá una variable de número de "*golpes de bomba (pump strokes)*" de forma que mientras no se llegue a este número de impulsiones (recogidas con la señal de monitorización `BR7YL`) se mantenga el tiempo máximo de monitorización.

#### Regulación

Como se vio más arriba, se hace una dosificación proporcional al caudal de entrada a los filtros, calculando la velocidad de referencia en porcentaje que saldrá como señal 4-20 mA (`BR7SC   0168B`) limitando la velocidad de la dosificadora (V<sub>dosif</sub>) entre 0 y 100%.

#### Dosificadora de reserva

Al fallo de la dosificadora BR7-P-0168B, se podrá arrancar la dosificadora BR7-P-0168C que da servicio tanto al skid de filtración (BR7-UP-0403A/B/C) como al DAF-3 (BR7-UP-0509).

Existirán unas variables internas para que el sistema identifique a qué sistema está asignada la bomba de reserva. Esta asignación puede ser automática (hasta que no falla uno de los sistemas no se asigna la bomba de reserva y el primero que falla "coge" dicha bomba de reserva) o manual, de forma que se preasigna la bomba de reserva a uno de los dos sistemas y si el otro falla se queda sin dosificación.

En caso de que esté preasignado a la filtración o esté en automático y no se haya asignado la bomba de reserva al DAF-3 y la dosificadora BR7-P-0168B entre en fallo, bien por el relé (`BR7YA   0168B`) o por fallo de monitorización, como se describe más arriba, se asigne la dosificadora de reserva, siempre y cuando ésta esté disponible (sin fallo de monitorización, ni fallo por su relé `BR7YA   0168B`) y esté en automático, así como las válvulas BR7-MV-0348 y BR7-MV-0349 en automático y sin fallo.

En ese caso, se abrirá la válvula BR7-MV-0348 (se activa la señal `BR7HSH  0348`) y al recibir la confirmación de apertura (`BR7ZSH  0348`), se activa la marcha de la dosificadora (`BR7XSL  0168C`).

 ## Instrumentos

### Caudal de aire de lavado BR7-FT-0112

Se monitoriza los valores de aviso cuando está en operación la válvula (rampa finalizada).

### Caudal de alimentación BR7-FT-0034

Se monitorizan los valores de aviso cuando el filtro está en producción (`BR7YS   0055` *Universal Digital Output 2 / PRODUCCIÓN*). 

### Caudal de agua de lavado BR7-FT-0079

Se monitorizan los valores de aviso transcurrido un tiempo tras la activación de la confirmación de marcha de las bombas BR7-P-0406A/B y el PID `BR7FC  0079` está en automático.

