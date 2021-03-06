---
layout: post
title: "Análisis para preprocesamiento de data COVID-19 de Perú"
date: 2020-05-22
---
<p align="justify">
Este post busca realizar un análisis parcial y básico para el preprocesamiento de los datos de acceso libre de los nuevos contagios en Perú del COVID-19. He dejado en este [repositorio](https://github.com/gissemari/covid19Peru) un notebook en jupyter para que se puedan apreciar mejor los pasos que seguí.
La calidad de la data es un tema importante. Y algunas instancias con datos ilegibles podrían no significar o impactar mucho en el análisis global. Sin embargo, cuando abrimos los datos por departamento estos podrían impactar más o menos:<br/>

<b>1. Fecha de Nacimiento</b><br/>
Es una variable que aporta la edad y por tanto el riesgo de las personas de contraer la enfermedad. Tiene mezcladas fechas con guiones y diagonales.<br/>

<b>2. Fecha de Prueba</b><br/>
también contiene los mismos problemas que la fecha de nacimiento, mezcla entre guiones y diagonales. Afortunadamente la función to_datetime() de pandas identifica ambas.<br/>
Ambas fechas cuentan con instancias donde mes y día se han intercalado. Es fácil confirmar esto porque hay registros de pruebas después de mayo del 2020, es decir que no han sucedido aún. La solución aquí es identificar estas instancias, pasarlas a string, intercambiar dia y mes y volverlas tipo de dato datetime de nuevo.<br/>
Hay algunos dias de enero y febrero con registros y no necesariamente por confusión en mes/dia, llegando incluso a valores alrededor de 500. Ejemplos en la siguiente tabla.<br/>


2020-01-02	  2<br/>
2020-01-04	444<br/>
2020-01-05	581<br/>
2020-01-06	  1<br/>
2020-01-07	  2<br/>
2020-01-27	  2<br/>

<!--
 <table style="width:30%">
  <tr>
    <th>FECHA_PRUEBA</th>
    <th>CONTADOR</th>
  </tr>
  <tr>
    <td>2020-01-02</td>
    <td>2</td>
  </tr>
  <tr>
    <td>2020-01-04</td>
    <td>444</td>
  </tr>
   <tr>
    <td>2020-01-05</td>
    <td>581</td>
  </tr>
  <tr>
    <td>...</td>
    <td>...</td>
  </tr>
   <tr>
    <td>2020-01-27</td>
    <td>2</td>
  </tr>
</table> 
<br/>
-->


<b>3. Provincia, Distritos</b><br/>
Algunas nombres están escritos con una ligera diferencia, acento u otra letra y esto hace que se conviertan en una nueva instancia. Ejemplo: 'BONGARA', 'BONGARÁ'<br/>

<b>4. Sexo</b><br/>
En minúsculas y mayúsculas hacen que se creen dos otras instancias a los dos valores que generalmente se usan.<br/>


<b>5. Disminuyen las pruebas los domingos</b><br/>
Debido a algunos valles, se puede concluir que en alguna departamento-provincia se hacen menos pruebas los días domingos (cada 7 dias)<br/>
<img src="../../../images/covid/valleysSundays.png" alt="Nuevos casos con valles cada 7 dias, los domingos">

<br/>
<b>6. Tipo de prueba</b><br/>
Hay menos pruebas PCR hechas, comparadas con el número de PR. Ambos tipos parecen tener un ligero patrón de acuerdo el día de la semana.<br/>
<img src="../../../images/covid/testType.png" alt="Nuevos casos por tipo de prueba">

</p>
