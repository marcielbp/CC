---
layout: page
title: Avaliação Institucional
description: Avaliação Institucional
hide_hero: true
show_sidebar: false
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
var ctx = document.getElementById('myChart').getContext('2d');

var myLineChart = new Chart(ctx, {
    type: 'line',
    data: {
        labels: ['2015-1', '2015-2', '2016-1', '2016-2', '2017-1', '2017-2', '2018-1', '2018-2'],
        datasets: [{
            label: 'Q1',
            data: [96.43, 91.43, 93.02, 97.06, 97.06, 98.46, 98.46, 100.00],
            borderWidth: 2,
            cubicInterpolationMode: 'monotone',
            borderColor: 'red',
            fill: false
          },
          {
            label: 'Q2',
            data: [92.86, 85.72, 93.02, 91.18, 91.18, 98.46, 98.46, 97.14],
            borderWidth: 2,
            cubicInterpolationMode: 'monotone',
            borderColor: 'green',
            fill: false
          },
          {
            label: 'Q3',
            data: [76.78, 77.14, 86.05, 88.24, 88.24, 90.77, 90.77, 97.14],
            borderWidth: 2,
            cubicInterpolationMode: 'monotone',
            borderColor: 'orange',
            fill: false
          },
          {
            label: 'Q4',
            data: [67.86, 77.14, 81.40, 100.00, 100.00, 95.38, 95.38, 97.14],
            borderWidth: 2,
            cubicInterpolationMode: 'monotone',
            borderColor: 'blue',
            fill: false
          },
          {
            label: 'Q5',
            data: [46.43, 48.57, 65.85, 75.86, 75.86, 88.24, 88.24, 84.49],
            borderWidth: 2,
            cubicInterpolationMode: 'monotone',
            borderColor: 'yellow',
            fill: false
          }
        ]
    },
    options: {
    				responsive: true,
    				title: {
    					display: true,
    					text: 'Evolução da Avaliação da coordenação'
    				},
    				tooltips: {
    					mode: 'index',
    					intersect: false,
    				},
    				hover: {
    					mode: 'nearest',
    					intersect: true
    				},
    				scales: {
    					x: {
    						display: true,
    						scaleLabel: {
    							display: true,
    							labelString: 'Semestre'
    						}
    					},
    					y: {
    						display: true,
    						scaleLabel: {
    							display: true,
    							labelString: 'Value'
    						},
                ticks: {
                  beginAtZero: true,
                  steps: 10,
                  stepValue: 10,
                  min: 0,
                  max: 100
                }
    					}
    				}
    			}
});

</script>
