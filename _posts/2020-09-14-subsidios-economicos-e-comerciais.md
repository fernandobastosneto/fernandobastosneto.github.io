---
title: Subsídios Econômicos e Comerciais
projects: true
layout: post
---

A área econômica do Itamaraty costuma formular relatórios econômicos e comerciais para subsidiar reuniões e negociações bilaterais (ou até mesmo pluri ou multilaterais) de autoridades brasileiras dos mais variados níveis. Nestes relatórios, procura-se estimar minimamente os interesses estratégicos econômicos do Brasil com cada país específico: principais produtos comercializados, eventuais concorrentes, tendências e movimentos de longo prazo, entre outros aspectos.

Este projeto tem por objetivo automatizar estes relatórios, atualmente feitos pela área de Promoção Comercial do Itamaraty, reduzindo o tempo perdido pela construção mecânica dos relatórios - permitindo que a maior parte do tempo, cada vez mais escasso, possa ser dedicado à análise qualitativa da relação bilateral.

A aplicação toma por base bancos de dados públicos do Ministério da Economia, do COMTRADE-ONU e do Banco Mundial. Além disso, este programa não seria possível sem o (incrível) conjunto de pacotes do Tidyverse, construído pela comunidade da linguagem R.

O código do programa pode ser encontrado aqui.

Os relatórios estão disponíveis abaixo.
# Relatórios por país
<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1">
</head>
 <div class="dropdown">
  <button onclick="myFunction()" class="dropbtn">Balanças Comerciais</button>
  <div id="myDropdown" class="dropdown-content">
    <input type="text" placeholder="Procurar.." id="myInput" onkeyup="filterFunction()">
	{% assign pdf_files = site.static_files | where: "pdf", true %}
	{% for mypdf in pdf_files %}
	<a href="{{mypdf.path}}"> {{mypdf.basename}}</a>
	{% endfor %}
  </div>
</div> 
<script>
/* When the user clicks on the button,
toggle between hiding and showing the dropdown content */
function myFunction() {
    document.getElementById("myDropdown").classList.toggle("show");
  }
  
  function filterFunction() {
    var input, filter, ul, li, a, i;
    input = document.getElementById("myInput");
    filter = input.value.toUpperCase();
    div = document.getElementById("myDropdown");
    a = div.getElementsByTagName("a");
    for (i = 0; i < a.length; i++) {
      txtValue = a[i].textContent || a[i].innerText;
      if (txtValue.toUpperCase().indexOf(filter) > -1) {
        a[i].style.display = "";
      } else {
        a[i].style.display = "none";
      }
    }
  }
</script>
</html>
