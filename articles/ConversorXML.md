<div style="text-align:justify;">
![Logo Softplus](../images/ls.png)

# Conversor XML Sefaz para SPI

## O que é e para que serve
***
Devido a muitas situações com divergência de valores entre SEFAZ e SPI, onde era identificado que diversas vendas existiam na SEFAZ, mas não eram encontradas no banco de dados, desenvolvemos um software que converte XML da Sefaz para arquivos de vendas da Softplus (Registrar_Venda.xml), que tem a função de fazer o procedimento de conversão dos arquivos e a importação para base;

![Conversor XML](../images/ConversorXML/1.png)

## Procedimento Técnico
***
O procedimento que passaremos a seguir só deve ser realizado por técnicos ou representantes autorizados da Softplus Informática;
* **Faça <a href="https://mega.nz/#!kkRUQQbD!fgdHi8uv8cHu0Sqc8aREThmzO9vS4OxfH5B2Cfc5YmM" target="_new">Download do Aplicativo</a> e execute o mesmo**;

* **Local dos Arquivos do Sefaz**: Nesta área deve ser informado o local onde estão gravados os arquivos enviados para sefaz, que são os arquivos de validação que normalmente estão no Disco C:\NFe, porém essa localização poderá ser alterada conforme configuração dentro do SPINFE > Configurações. 
Você pode informar dois caminhos diferentes, NFCe-Enviados ou Diretórios com Data na descrição (ex: 201607);

    ![Conversor XML](../images/ConversorXML/2.png)

* **Tipo Emissão**: Informe o tipo de xml, se a mesma é de ECF ou NFCe, alterando também o local onde o sistema deve localizar os arquivos para importação ao banco de dados;

    ![Conversor XML](../images/ConversorXML/3.png)

* **Tipo de Arquivo (tag Raiz)**: Nesta parte é possível a seleção do tipo de arquivo para leitura, onde as opções são;
    * **Retorno de Processamento (tag NFeProc)**: Selecione para informar o local dos arquivos que foram enviados para sefaz e validados (sem rejeição);
    * **Envio de Dados (tag NFe)**: São todos os arquivos gerados para envio a sefaz com e sem prévia validação e retorno;
    * **Sistema Autenticador e Transmissor (SAT)**: Selecione para buscar arquivos gerados para o SAT;

    ![Conversor XML](../images/ConversorXML/4.png)

* **Mover Arquivos Processados (check box)**: Quando marcado a opção, os arquivos são movidos para novas pastas, onde documentos que forem importados corretamente irão para a pasta “XML_Conversao_Ok”, já as xmls que estiver com erro na importação, serão movidas para “XML_Erro_Conversao”. Estas pastas são criadas automaticamente na raiz do aplicativo Conversor XML Sefaz para SPI. 

    **Os arquivos serão removidos da pasta de configuração do SpiNFe (Ex: NFE/NFCe-Enviados)*;

    ![Conversor XML](../images/ConversorXML/5.png)

* **Processar**: No final da configuração, clique em “processar” para iniciar a conversão e importação dos arquivos;

    ![Conversor XML](../images/ConversorXML/6.png)

## Retornos
***
É importante identificar os retornos do aplicativo, onde eles são:
* **Ok**: São os arquivos importados corretamente para a base de dados;
* **Venda já esta no banco de dados (NFSEQ)**: São arquivos que já estavam na base de dados (estes arquivos serão movidos para XML_Erro_Conversao);
* **Erro na field SERALTERNUMERO**: Este retorno pode ser apresentado em versões 1.29 ou inferiores, neste caso deve ser criada esta coluna com as configurações:

    Field Name = SERALTERNUMERO,    
    Field Type = CHAR    
    Domain = SIMNAO    
    Size = 1