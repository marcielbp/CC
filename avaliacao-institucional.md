---
layout: page
title: Avaliação Institucional
description: Avaliação Institucional
hide_hero: true
show_sidebar: true
---


<script src="https://cdn.jsdelivr.net/npm/mermaid@8.4.0/dist/mermaid.min.js"></script>
<script>mermaid.initialize({  startOnLoad:true,  theme: 'neutral' });</script>





<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.3/Chart.min.js"></script>

# Como funciona o instrumento de Avaliação Institucional?

<div class="mermaid">
gantt
    title TImeline da Avaliação Institucional em 2019.2
    axisFormat  %b/%Y
    dateFormat  MM-YYYY
    section Discentes
       Avaliação Institucional   :done, a1,  11-2019, 21d
       Recebimento dos resultados: a2, after c3, 7d
    section Professores
        Avaliação Institucional       : done, b1, 11-2019  , 21d
        Reunião com a Coordenação: b2, after c2, 7d
    section Coordenação
        Divulgação         :crit, c1, 11-2019, 21d
        Discussão Interna: crit, c2, after d1, 7d
        Discussão nos Colegiado e NDE: c3, after c2, 21d
        Reunião com Professores: c3, after c2, 7d
        Apresentação aos Discentes: c4, after c3, 7d
        Viabilização de melhorias: crit, c5, after c3, 60d
    section STI
        Compilação dos resultados :done, d1, 12-2019, 60d
</div>

# Avaliação Instituicional da COORDENAÇÃO

1. A Coordenação do curso é acessível aos alunos.
1. A Coordenação do curso orienta os alunos (na matrícula, no aproveitamento de créditos, em atividades complementares, etc.), auxiliando-os quando necessário.
1. A Coordenação promove a divulgação do Projeto Pedagógico do Curso.
1. A Coordenação do curso estimula os alunos a participar dos encontros universitários da UFC ou de outros eventos acadêmicos (congressos científicos, reuniões tecnológicas, atividades esportivas, extensionistas e/ou artísticas, etc).
1. A Coordenação do curso esclarece os alunos sobre a importância em participar do Exame Nacional de Desempenho de Estudantes (ENADE).
1. A Coodenação do curso promove momentos de diálogos com os alunos sobre os resultados do ENADE.
1. A Coordenação do curso promove momentos de diálogos com os alunos sobre a formação acadêmica, curriculo e mercado de trabalho.
1. A Coordenação do curso incentiva os alunos a avaliarem os professores e as disciplinas (ou módulos).
1. A Coordenação do curso acompanha a execução e monitora a qualidade dos estágios.
1. O meu nível de satisfação com a coordenação do curso é muito elevado.



<div class="mermaid">
stateDiagram
state DISCENTES {
        Autoavaliação--> RESULTADOS
        Intraestrutura--> RESULTADOS
}
state PROFESSORES {
         Autoavaliação--> RESULTADOS
        Intraestrutura--> RESULTADOS
    }
state COORDENAÇÃO {
        [*] --> fir
        fir --> [*]
    }
state DIREÇÃO {
        [*] --> fir
        fir --> [*]
    }

    DISCENTES --> COORDENAÇÃO : Autoavaliação
    PROFESSORES --> COORDENAÇÃO : Autoavaliação


    DISCENTES --> DIREÇÃO : Infraestrutura
    PROFESSORES --> DIREÇÃO : Infraestrutura
</div>



<canvas id="myChart" width="400" height="250"></canvas>

Criado com [Chart.js](https://www.chartjs.org/).

<script>
var data = {
    labels: ['2015-1', '2015-2', '2016-1', '2016-2', '2017-1', '2017-2', '2018-1', '2018-2'],
    datasets: [
        {
            label: "Q1",
            fillColor: "rgba(220,220,220,0)",
            strokeColor: "#abc",
            pointColor: "#abc",
            pointColor: "#9ab",
            fill: false,
            data: [96.43, 91.43, 93.02, 97.06, 97.06, 98.46, 98.46, 100.00],
        }]
};

var ctx = document.getElementById("myChart").getContext("2d");
var myBarChart = new Chart(ctx).Line(data, {
    //Boolean - Whether the scale should start at zero, or an order of magnitude down from the lowest value
    scaleBeginAtZero : true,
    //Boolean - Whether grid lines are shown across the chart
    scaleShowGridLines : true,
    //String - Colour of the grid lines
    scaleGridLineColor : "rgba(0, 0, 0, .25)",
    //Number - Width of the grid lines
    scaleGridLineWidth : 1,
    //Boolean - Whether to show horizontal lines (except X axis)
    scaleShowHorizontalLines: true,

    //Boolean - Whether to show vertical lines (except Y axis)
    scaleShowVerticalLines: true,

    //Boolean - If there is a stroke on each bar
    lineShowStroke : true,

    //Number - Pixel width of the bar stroke
    lineStrokeWidth : 4,

    //String - A legend template
    legendTemplate : "<ul class=\"<%=name.toLowerCase()%>-legend\"><% for (var i=0; i<datasets.length; i++){%><li><span style=\"background-color:<%=datasets[i].fillColor%>\"></span><%if(datasets[i].label){%><%=datasets[i].label%><%}%></li><%}%></ul>"

});

</script>
