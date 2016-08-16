<div style="text-align:justify;">
![Logo Softplus](../images/ls.png)

# Abastecimentos Remanescentes

## O que é abastecimento remanescente
***
Antes de saber o que é abastecimento remanescente tenha em mente que, atualmente existem duas maneiras de realizar um abastecimento no sistema, onde a primeira operação seria através do “abastecimento manual”, que são abastecimentos realizados diretamente via tela de vendas, este tipo de abastecimento só é feito para bombas que não utilizam integração com módulo concentrador e o usuário pode informar qualquer valor no momento da venda, porém este método já está proibido em muitos estados, também desta forma não é gerado abastecimentos remanescentes. O outro método é o “abastecimento automático”, que são os valores recebidos pelo módulo concentrador, onde a bomba faz o abastecimento e envia ao módulo, o mesmo então ao identificar, envia para a tela de vendas com valor correto do que foi abastecido;

**Abastecimento remanescente** é uma quantidade abastecida que não foi para o módulo ou este não conseguiu realizar a leitura e enviar para o sistema, o próximo abastecimento recebido deverá estar com uma quantidade de encerrante diferente do previsto, que deveria ser o correto. O sistema então gera estes abastecimentos remanescentes conforme legislação do <a href="https://www.confaz.fazenda.gov.br/legislacao/atos/2015/ac023_15" target="_new">PAF ECF REQUISITO XXXVII</a>; Ou seja: abastecimento remanescente é uma litragem gerada a partir da identificação de quebra de encerrantes dos abastecimentos que foram capturados com sucesso;

### Observe a imagem
***
![Funcionamento dos Abastecimentos](../images/AbastecimentoRemanescente/1.jpg)

### Na Prática
***
O último abastecimento recebido pelo sistema tinha o encerrante com valor 100, em seguida houve um abastecimento com quantidade de 50lts que não foi enviado para o módulo ou para o sistema, onde seu encerrante deveria estar com valor de 150, na sequencia um terceiro abastecimento foi feito com uma quantidade de 10lts e encerrante final de 160. Este ultimo foi capturado e gravado com sucesso, e durante o processo foi feito um cálculo onde o encerrante do terceiro abastecimento (160) subtraído da quantidade (10lts) deve bater com encerrante do último abastecimento gerado (150), porém como este abastecimento não está no banco de dados, a importação identifica o último abastecimento com valor de encerrante 100, ao identificar uma diferença de 50lts, o terceiro abastecimento grava uma coluna informativa com essa diferença para que seja criado um abastecimento remanescente automático pelo sistema no final do turno;

## Observações
***
* Conforme citado acima, os abastecimentos só serão gerados efetivamente no fechamento de turno ou emissão da redução Z;
* A falha de muitos abastecimentos seguidos pode causar um acumulo de diferenças e gerar apenas um abastecimento no fechamento de turno com valor total da quebra;
* Tenha cuidado ao implantar algum abastecimento diretamente via ibexpert, sempre faça o ajuste nas colunas ABAQUEBRA  e ABADIF_ENC para evitar a criação destes abastecimentos e a duplicidade nos valores (conforme veremos mais abaixo);

## O que causa estes Abastecimentos
***
Sabendo que os abastecimentos remanescentes são gerados após a falta de algum valor durante o turno, descrevemos aqui os principais motivos da falta destes abastecimentos no sistema:
* Bomba no modo manual, onde a mesma não envia informações para o módulo;
* Falha na comunicação entre módulo e bombas;
* Defeito no concentrador;
* Falha na leitura/captura do abastecimento pelo sistema;

## Visualizando Abastecimentos Remanescentes
***
O usuário poderá identificar / visualizar os abastecimentos remanescentes que serão criados no próximo fechamento de caixa ou retirada de redução z, é possível fazer a consulta de duas maneiras:

![Abastecimentos Remanescentes](../images/AbastecimentoRemanescente/2.png)

### Via Tela de vendas
O usuário poderá utilizar o menu Consultas > Consulta de Abastecimentos Remanescentes;

![Abastecimentos Remanescentes](../images/AbastecimentoRemanescente/3.jpg)

### Via Tela Principal
O usuário poderá utilizar o menu Consultas > Lista de Abastecimentos Remanescentes;

![Abastecimentos Remanescentes](../images/AbastecimentoRemanescente/4.jpg)

### Nota
A tela para visualização dos abastecimentos remanescentes é mesma, independente se ela é aberta via tela de vendas ou tela principal. Os abastecimentos mostrados nesta tela ainda não existem, por isso os mesmos não podem ser quitados. A quitação destes abastecimentos é feita no fechamento de turno ou retirada da redução Z;

## Entendendo o banco de dados
***
Recomendamos também que o técnico / representante tenha em mente como identificar tais valores no banco de dados;

### ABAORIGEM
Para identificar o tipo de abastecimento, basta listar os mesmos na tabela A02AABA e localizar a coluna “ABAORIGEM”, os itens que tiverem o valor “R” nesta coluna, são de fato abastecimentos remanescentes;

![Abastecimentos Remanescentes](../images/AbastecimentoRemanescente/5.jpg)

### ABAQUEBRA e ABADIF_ENC
É possível também identificar as diferenças de valores entre os abastecimentos, onde as mesmas, serão utilizadas juntamente do parâmetro da coluna “ABAQUEBRA” para criação dos abastecimentos remanescentes;

![Abastecimentos Remanescentes](../images/AbastecimentoRemanescente/6.png)

Ou seja, quando o valor da coluna “ABADIF_ENC” estiver diferente de zero e a coluna “ABAQUEBRA” for igual a “S”, deverá ser criado um abastecimento remanescente;

![Abastecimentos Remanescentes](../images/AbastecimentoRemanescente/7.jpg)

### Nota
Os abastecimentos com diferença são de origem “A”, vieram da automação, onde seu cálculo de encerrante subtraído da litragem foi identificado uma diferença e lançado na coluna ABADIF_ENC este valor e ABAQUEBRA com “S” para que seja criado uma abastecimento remanescente;