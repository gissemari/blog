---
layout: post
title: "Análisis para preprocesamiento de data COVID-19 de Perú"
date: 2020-05-22
---
<p align="justify">
Este post busca realizar un análisis parcial y básico para el preprocesamiento de los datos de acceso libre de los nuevos contagios en Perú del COVID-19. He dejado en este [repositorio](https://github.com/gissemari/covid19Peru) un notebook en jupyter para que se puedan apreciar mejor los pasos que seguí.
La calidad de la data es un tema importante. Y algunas instancias con datos ilegibles podrían no significar o impactar mucho en el análisis global. Sin embargo, cuando abrimos los datos por departamento estos podrían impactar más o menos:<br/>

<b>1. Fecha de Nacimiento</b><br/>
Ces una variable que aporta la edad y por tanto el riesgo de las personas de contraer la enfermedad. Tiene mezcladas fechas con guiones y diagonales.<br/>

<b>2. Fecha de Prueba</b><br/>
también contiene los mismos problemas que la fecha de nacimiento, mezcla entre guiones y diagonales. Afortunadamente la función to_datetime() de pandas identifica ambas.<br/>
Ambas fechas cuentan con instancias donde mes y día se han intercalado. Es fácil confirmar esto porque hay registros de pruebas después de mayo del 2020, es decir que no han sucedido aún. La solución aquí es identificar estas instancias, pasarlas a string, intercambiar dia y mes y volverlas tipo de dato datetime de nuevo.<br/>
Hay algunos dias de enero y febrero con registros y no necesariamente por confusi[on en mes/dia, llegando incluso a valores alrededor de 500. Tabla 1.<br/>

2020-01-02	  2<br/>
2020-01-04	444<br/>
2020-01-05	581<br/>
2020-01-06	  1<br/>
2020-01-07	  2<br/>
2020-01-27	  2<br/>

<b>3. Provincia, Distritos</b><br/>
Algunas nombres están escritos con una ligera diferencia, acento u otra letra y esto hace que se conviertan en una nueva instancia. Ejemplo: 'BONGARA', 'BONGARÁ'<br/>

<b>4. Sexo</b><br/>
En minúsculas y mayúsculas hacen que se creen dos otras instancias a los dos valores que generalmente se usan.<br/>


![this screenshot](https://github.com/gissemari/blog/blob/master/images/covid/valleysSundays.png)
![this screenshot2](/images/covid/valleysSundays.png)

![this screenshot3](../../../images/covid/valleysSundays.png)
![this screenshot3](../../../images/covid/testType.png)



<b>5. Disminuyen las pruebas los domingos</b><br/>
Debido a algunos valles. Se puede concluir que en alguna departamento-provincia se hacen menos pruebas los días domingos (cada 7 dias)<br/>
<img src="../../../images/covid/valleysSundays.png" alt="Nuevos casos con valles cada 7 dias, los domingos">

<br/>
<b>6. Tipo de prueba</b><br/>
Hay menos pruebas PCR hechas, comparadas con el número de PR. Las PCR parecen tener un ciclo bastente predecible. En cambio las PR parece<br/>
<img src="../../../images/covid/testType.png" alt="Nuevos casos por tipo de prueba">

</p>
