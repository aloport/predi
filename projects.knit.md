---
title: ¿Cómo funciona el mercado de predicción?
---

El mecanismo del mercado de predicción se asemeja mucho al de un mercado bursátil. Sin embargo, en lugar de comerciar con productos financieros, [los participantes](https://aloport.github.io/predi/participate.html) en el mercado comercian con acciones sobre eventos políticos futuros. En nuestro mercado para las elecciones generales del 28A, por ejemplo, los participantes tienen que predecir dos tipos de eventos. 

- _Gobierno resultante._ El primer evento que tienen que predecir los participantes es cuál va ser el gobierno resultante tras las elecciones, en el que cada uno de los escenarios más probables es un contrato en el mercado. 

En este submercado los participantes compran y venden, por ejemplo, un contrato llamado “un gobierno de coalición de izquierdas”, lo cual significa en nuestro mercado que PSOE y al menos otro partido distinto a Ciudadanos formarán el próximo gobierno de España. En cuanto el mercado se pone en marcha, el precio variante de este contrato refleja la probabilidad de que tenga lugar el evento descrito en él. Los participantes pueden comprar acciones si piensan que la probabilidad de que este evento tenga lugar es mayor que la sugerida por su precio y vender acciones si piensan que la probabilidad de dicho evento es menor. Así, conforme el precio de cada contrato refleja la probabilidad de que se consituya cada tipo de gobierno resultante.


- _Estimación de voto._ El segundo tipo de evento es el resultado electoral que va a obtener cada uno de los principales partidos en porcentaje de votos. Para ello, tenemos un submercado para cada uno de los cinco grandes partidos (PSOE, PP, Ciudadanos, Unidas Podemos y VOX). En cada uno de estos mercados, los participantes tienen que asignar probabilidades a los posibles resultados electorales de cada partido.

A modo de ejemplo, observa la siguiente tabla. La primera columna se corresponde con el submercado del PP en el que los participantes tienen que asignar probabilidades a estos márgenes de voto. La segunda columna presenta probabilidades ficticias asignadas por los participantes.

<!--html_preserve--><div id="htmlwidget-9bfe9cfb56314c123ebd" style="width:100%;height:auto;" class="datatables html-widget"></div>
<script type="application/json" data-for="htmlwidget-9bfe9cfb56314c123ebd">{"x":{"filter":"none","extensions":["FixedColumns"],"data":[["1","2","3","4","5"],["Contrato A","Contrato B","Contrato C","Contrato D","Contrato E"],["17% votos o menos","17%-19'99% votos","20%-22'99% votos","23%-25'99% votos","26% votos o más"],["10%","20%","40%","20%","10%"]],"container":"<table class=\"display\">\n  <thead>\n    <tr>\n      <th> <\/th>\n      <th>Contratos de voto al PP<\/th>\n      <th>Margen de estimación de voto al PP<\/th>\n      <th>Probabilidad de cada contrato (ejemplo)<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"dom":"t","scrollX":false,"fixedColumns":true,"scrollCollapse":true,"pageLength":10,"order":[],"autoWidth":false,"orderClasses":false,"columnDefs":[{"orderable":false,"targets":0}]}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

Posteriormente, calculamos las probabilidades acumuladas de estas estimaciones e interpolamos cuál es la estimación que se correspondería con el 50% de probabilidades acumuladas. Es decir, estimamos el resultado más probable para este partido.

<!--html_preserve--><div id="htmlwidget-ce4f7f0078246ef9ad47" style="width:100%;height:auto;" class="datatables html-widget"></div>
<script type="application/json" data-for="htmlwidget-ce4f7f0078246ef9ad47">{"x":{"filter":"none","extensions":["FixedColumns"],"data":[["1","2","3","4","5","6","7"],["100% de votos","&gt; 26% de votos","&gt; 23% de votos","21% de votos","&gt; 20% de votos","&gt; 17% de votos","&gt; 0% de votos"],["0%","10%","30%","50%","70%","90%","100%"],["Ninguno","Contrato E","Contrato D + Contrato E","Resultado de la interpolación","Contrato C + Contrato D + Contrato E","Contrato B + Contrato C +  Contrato D + Contrato E","Contrato A + Contrato B + Contrato C + Contrato D + Contrato E"]],"container":"<table class=\"display\">\n  <thead>\n    <tr>\n      <th> <\/th>\n      <th>Estimación de voto al PP<\/th>\n      <th>Probabilidad acumulada<\/th>\n      <th>Agregación<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"dom":"r","scrollX":false,"fixedColumns":true,"scrollCollapse":true,"pageLength":10,"order":[],"autoWidth":false,"orderClasses":false,"columnDefs":[{"orderable":false,"targets":0}],"rowCallback":"function(row, data) {\nvar value=data[0]; $(row).css({'font-weight':value == 4.000000 ? 'bold' : ''});\n}"}},"evals":["options.rowCallback"],"jsHooks":[]}</script><!--/html_preserve-->


En este caso, el porcentaje de voto estimado para el PP por nuestro modelo sería un 21%. Esta misma operación la repetimos en los submercados de los otros partidos. Como último paso, corregimos el resultado de acuerdo a la cantidad estimada de "Otros" cuando la probabilidad acumulada de los cinco partidos supera la media de las encuestas. Nuestras estimaciones de voto diarias son el resultado de la agregación de estas operaciones.

## Ventajas

El mercado de predicción conlleva algunas ventajas sustanciales sobre otros modelos de predicción como las encuestas. En este sentido, la predicción de los resultados cambia en vivo. Es decir, el mercado tiene el potencial de mostrar el efecto directo que tiene un evento, por ejemplo, sobre las expectativas de voto de un partido. Otra ventaja importante es que permite predecir eventos complejos como cuál va a ser el gobierno que conforme tras las próximas elecciones. En este mercado, los participantes tienen que agregar la participación electoral, los resultados esperados de cada partido y la política de pactos que estos pueden seguir. Por último, el mercado tiene una ventaja estratégica y es que, al no ser una encuesta, no está sujeto a prohibiciones de publicación durante la última semana antes de las elecciones.

A diferencia de las encuestas donde las muestra de los participantes debe ser representativa de la población, en nuestro mercado reclutamos participantes interesados por la política (la mayoría de ellos profesores y alumnos de ciencias sociales de universidades españolas). Esto es importante porque su labor consiste en traducir en probabilidades la información a su alcance (encuestas, de elecciones precedentes, noticias, eventos). Como el objetivo es puramente científico, en nuestro mercado los participantes no pueden endeudarse o invertir su propio dinero. En cambio, les entregamos diez euros. Este montante, que puede subir o bajar en función del buen rendimiento del participante mientras transcurre el juego, sirve de incentivo económico para motivar el acierto y bloquear posibles sesgos.

_________________

Contacto: Alberto López Ortega _alberto.lopezortega@uzh.ch_ , [bertous](https://twitter.com/bertous)

