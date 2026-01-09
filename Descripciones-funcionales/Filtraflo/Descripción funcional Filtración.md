# Descripción funcional Filtración



## Documentos que acompañan esta descripción

- P&ID: PID-2201BI01A0-BR7, págs: X-046 (filtros, 52), X-045-H2 (bombeo de efluente, 51),X-044-H2 (bombeo de efluente, 49), X-049 (lavado, 55), X-042 (soplantes)
- Esquemas eléctricos Filtraflo: [DOECFF332676_24000488](https://drive.google.com/file/d/1K2Yv-mfcGx6m4tJrQsQVkdPnMApLxXDo/view)
- P&ID Equipo Filtraflo: [DOPFFF313233-2400488](https://drive.google.com/file/d/1ARp57utd1WaAGZpv6rWfaLGWUFM--wTF/view)
- Tabla de intercambio Modbus TCP/IP: [DOLIFF332530_2400488](https://drive.google.com/file/d/1FPEaikLZlxMeexy2XMuhmehHPNNVOxxp/view)
- Tabla de secuencia del Filtraflo [DOLIFF332529_24000488](https://drive.google.com/drive/folders/1xHWoJttHsTa8Bp7czAxyN-ZE2TWyheXZ)
- Lista de E/S con equipos paquete de VWT: [1750217102-VWT-I-LI-006 - I/O List from package skids Rev-3](https://docs.google.com/spreadsheets/d/1TABNGFEBWYtetfe_67veyGEzDdMUs3IFMZzejPBs_fU/edit?gid=96208323#gid=96208323)


## Equipos e instrumentos involucrados

- DAF 2A, BR7-UP-0304A.
- DAF 2B, BR7-UP-0304B.
- Bomba de efluente del DAF 2A, BR7-P-0304A.
- Válvula de regulación de la salida del DAF 2A, BR7-LV-0037A.
- Bomba de efluente del DAF 2B, BR7-P-0304B.
- Válvula de regulación de la salida del DAF 2B, BR7-LV-0037B.
- Bomba de reserva de efluente de los DAF 2A/B, BR7-P-0304C.
- Válvulas de asignación de la regulación de caudal para la bomba de reserva, BR7-UV-0320/21.
- Bomba de dosificación de coagulante, BR7-0168B. En el skid de dosificación existe una bomba de reserva, BR7-0168C que se puede asignar al filtro, abriendo la válvula BR7-MV-0348. Si se asigna a este servicio, no se puede asignar a la unidad del DAF 3, y viceversa, si está asignada al DAF 3, no se puede asignar a la filtración.
- Tanque de coagulante, BR7-T-0131, con los siguientes instrumentos asociados:
  - Nivel analógico, BR7-LT-0095.
  - Nivel alto, BR7-LSH-0096A, y nivel bajo, BR7-LSL-0096B.
- Bombas de lavado, BR7-P-0406A/B.
- Válvula de regulación del caudal de agua de lavado, BR7-FV-0079.
- Caudalímetro de agua de lavado, BR7-FT-0079.
- Tanque de agua filtrada, BR7-T-0405, con los siguientes instrumentos asociados:
  - BR7-LT-0039 y BR7-0040.Caudalímetro de entrada de caudal a los filtros, BR7-FT-0034.

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

Cuando alguno de los DAFs vaya a ponerse en marcha, tiene que tener la señal del skid de filtración para confirmar que está disponible (`BR7YS   0054`, "*healthy*"). Cuando se vaya a poner en marcha el bombeo de efluente de cualquiera de los DAFs, hay que dar la señal de demanda al skid de filtración (`BR7YL   0046`, U-DO1, "*water demand*") y esperar la señal de marcha del bombeo de efluente (`BR7YS   0052`, "*supply pump - Run Cmd*".



