---
title: Mostrando Funcionalidades 2
layout: post
youtubelink: https://www.youtube.com/embed/7YJMgbYbKO8
questions: questions_test
options: options_test
author: Projeto Aprender Economia
categories: [explicação, demonstração, início, bolsa]
---

Olá professor, bem vindo à plataforma de aprendizado **Aprender Economia**. Esta página deve te ensinar a utilizar as estruturas internas do site para fazer upload de posts e arquivos necessários para ensinar dados em funcionalidade, bem como mostrar essas funcionalidades que te ajudam a manejar e a ensinar na plataforma. É tudo muito simples e podem ser feitos com poucos clicks dentro do repositório do GitHub.

Temos diversas funcionalidades que podemos adcionar em cada "post" da plataforma. Cada arquivo deste, de post, com a extensão ".md" que fica dentro da pasta "_posts", começa com um cabeçalho, como o abaixo:

    ---
    title: Mostrando Funcionalidades
    layout: post
    youtubelink: https://www.youtube.com/embed/7YJMgbYbKO8
    questions: questions_test
    options: options_test
    author: Projeto Aprender Economia
    ---

A explicação de cada campo é a seguinte:

+ **title**: O título que será exibido da página em vários lugares do site, como na barra de navegação e nome da aba no navegador.
+ **layout**: O estilo de página a ser exibido, para posts esse campo deve ser sempre "post" e outros detalhes são omitidos para implementação.
+ **youtubelink**: Link da vídeo aula no youtube a ser inserido logo ao topo de texto como forma de complemento à explicação. Links de vídeos podem ser também insiridos no meio do texto, mas este link em especial serve para facilitar o formato da página. **OBS:** formato da URL deve ser no tipo mostrado, não podendo ser o formato abreviado como em **https://youtu.be/7YJMgbYbKO8** e sim o formato completo como em **https://www.youtube.com/embed/7YJMgbYbKO8**
+ **questions**: Nome do arquivo a ser guardado na pasta "_data" contendo as questões a serem respondidas sobre o conteúdo. Caso não hajam questões, esse campo deve ser desconsiderado ou deixado em branco.
+ **options**: Opções de cada questão a ser inserida no questionário. Caso não hajam questões esse arquivo não há também o porquê de existir e deve ser desconsiderado ou deixado em branco
+ **author**: Nome do autor do post.
+ **categories**: Aqui devem ficar as categorias de cada post na plataforma, facilitando a busca por tópicos relacionados como "juros", "moeda", "inflação", "criptomoedas" e assim por diante. **OBS:** Essa funcionalidade infelizmente ainda não se encontra disponível, mas estou trabalhando para fazê-la real. A dificuldade se encontra no manejo do *framework* que suport a aplicação.

O arquivo dos posts é feito no formato *kramdown* e uma documentação extensa para qualquer tipo necessidade com o mesmo pode ser encontrado neste site oficial que pode ser acessado [clickando aqui](https://kramdown.gettalong.org/quickref.html){:target="_blank"} ou pelo link ao lado: [https://kramdown.gettalong.org/quickref.html](https://kramdown.gettalong.org/quickref.html){:target="_blank"}.

### Sobre os arquivos de questões e opções

Os arquivos de questões e opções seguem o formato de planilha onde campos são separados por vírgula, o chamado CSV. São arquivos simples e de fácil manejo, onde cada coluna têm nome auto explicativo e relacionado ao assunto.

O arquivo de questões segue o seguinte padrão em suas colunas:

+ **id**: O número da questão de fato, seu identificador. É indicado que este número siga o padrão de 1 até o número máximo de questões de maneira contínua.
+ **question**: O texto da questão de fato, por exemplo caso eu queria perguntar as alternativas que têm valor igual à soma de 1 com 1, o campo "question" seria: "Quais alternativas abaixo contém o valor da soma de 1 com 1? Selecione todas as alternativas corretas.". Observe que a questão deve estar sempre entre aspas duplas (") para que pontuações que confundam o arquivo, como vírgulas e caracteres especiais, sejam ignorados e mantidos na questão sem erros.
+ **type**: Define o número de alternativas corretas a serem marcadas. Todas as questões são de múltipla escolha, mas este campo indica por exemplo se há 1, 2, 3 ou mais alternativas a serem escolhidas para responder a pergunta. Por exemplo, para a questão anterior imagine que teremos 3 respostas que devem ser marcadas e portanto este campo tem valor type igual a 3, poderíamos ter alternativas como:
    + 1 + 1 (esta alternativa deve ser marcada)
    + 2 - 1
    + 3 - 1 (esta alternativa deve ser marcada)
    + 10 - 8 (esta alternativa deve ser marcada)
    + 7 - 4

Já o arquivo de opções segue o seguinte padrão para suas colunas:

+ **question_id**: Número do id que relaciona a questão a qual essa opção faz parte. Por exemplo, para a questão 6, teríamos para todas as opções dessa questão o campo question_id com o valor igual a 6.
+ **option**: O texto da opção.
+ **right**: Indicador de valor 1 ou 0, indicando se a opção é correta quando marcada, ou deve ser deixada em branco - respectivamente. Assim sendo, quando a questão deve ser assinalada, este valor é 1; quando a opções é correta quando não assinalada, este valor é 0.

Após respondidas, as questões são enviadas e "corrigidas", retornando um *feedback* ao usuário sobre erros e acertos do mesmo e marcando no questionários suas tentativas de resposta corretas e erradas. A opção de refazer o teste é também sempre oferecida.

É importante lembrar que dá para se colocar diversos recursos nesta página, como imagens:
![projeto]({{ site.url }}{{ site.baseurl }}//assets/images/index.jpeg){:class="img-fluid"}


Gráficos em forma de script, utilizando por exemplo do Google Charts:

<script type="text/javascript">
      google.charts.load('current', {'packages':['line']});
      google.charts.setOnLoadCallback(drawChart);

    function drawChart() {

      var data = new google.visualization.DataTable();
      data.addColumn('number', 'Day');
      data.addColumn('number', 'Guardians of the Galaxy');
      data.addColumn('number', 'The Avengers');
      data.addColumn('number', 'Transformers: Age of Extinction');

      data.addRows([
        [1,  37.8, 80.8, 41.8],
        [2,  30.9, 69.5, 32.4],
        [3,  25.4,   57, 25.7],
        [4,  11.7, 18.8, 10.5],
        [5,  11.9, 17.6, 10.4],
        [6,   8.8, 13.6,  7.7],
        [7,   7.6, 12.3,  9.6],
        [8,  12.3, 29.2, 10.6],
        [9,  16.9, 42.9, 14.8],
        [10, 12.8, 30.9, 11.6],
        [11,  5.3,  7.9,  4.7],
        [12,  6.6,  8.4,  5.2],
        [13,  4.8,  6.3,  3.6],
        [14,  4.2,  6.2,  3.4]
      ]);

      var options = {
        chart: {
          title: 'Box Office Earnings in First Two Weeks of Opening',
          subtitle: 'in millions of dollars (USD) \n Exemplo Utilizado no Site do projeto Aprender Economia'
        },
        // width: 900,
        // height: 500,
        axes: {
          x: {
            0: {side: 'top'}
          }
        }
      };

      var chart = new google.charts.Line(document.getElementById('line_top_x'));

      chart.draw(data, google.charts.Line.convertOptions(options));
    }
</script>
<div class="chart" id="line_top_x"></div>
<script>$(window).resize(() => drawChart());</script>
Bem como qualquer outra tecnologia utilizada na Web para gerar interações, animações e demonstrações na página.

Abaixo segue um exemplo de questionário utilizando questões exemplo que demonstram a funcionalidade da ferramenta.