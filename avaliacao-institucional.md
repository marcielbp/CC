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
var ctx = document.getElementById('myChart').getContext('2d');
var myChart = new Chart(ctx, {
    type: 'bar',
    data: {
        labels: ['Red', 'Blue', 'Yellow', 'Green', 'Purple', 'Orange'],
        datasets: [{
            label: '# of Votes',
            data: [12, 19, 3, 5, 2, 3],
            backgroundColor: [
                'rgba(255, 99, 132, 0.2)',
                'rgba(54, 162, 235, 0.2)',
                'rgba(255, 206, 86, 0.2)',
                'rgba(75, 192, 192, 0.2)',
                'rgba(153, 102, 255, 0.2)',
                'rgba(255, 159, 64, 0.2)'
            ],
            borderColor: [
                'rgba(255, 99, 132, 1)',
                'rgba(54, 162, 235, 1)',
                'rgba(255, 206, 86, 1)',
                'rgba(75, 192, 192, 1)',
                'rgba(153, 102, 255, 1)',
                'rgba(255, 159, 64, 1)'
            ],
            borderWidth: 1
        }]
    },
    options: {
        scales: {
            yAxes: [{
                ticks: {
                    beginAtZero: true
                }
            }]
        }
    }
});
</script>
