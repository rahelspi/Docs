<div style="text-align:justify;">
![Logo Softplus](../images/ls.png)

# Cadastro e Emissão de Boletos

## O que é um Boleto
***
Basicamente, esse documento é um título de cobrança que pode ser pago em qualquer instituição ou estabelecimento conveniado, até a data de vencimento indicada. Alguns boletos, porém, trazem orientações para que o portador do título possa quitá-lo mesmo após a data preestabelecida como prazo, indicando acréscimos como juros, multas e demais condições (*que variam bastante de acordo com cada documento e com a empresa credora*).

## Onde é feito o pagamento
***
Antigamente, os boletos só podiam ser liquidados em agências bancárias. Hoje em dia, no entanto, com o grande avanço da tecnologia e o aumento dos convênios, esse pagamento pode ser efetuado em casas lotéricas, em postos dos Correios, em caixas eletrônicos e até mesmo por meio da internet (*acesso por home banking ou aplicativos de smartphones e tablets*).

## Utilização de boletos no sistema
***
Para geração correta de um boleto/remessa existem basicamente alguns passos a seguir:

### Cadastro de Bancos
Antes da emissão é necessário o cadastro do banco para qual o boleto será pago, por isso você deve entrar em contato com o banco no momento do cadastro para que o mesmo passe as devidas informações:
* APC > Financeiro > Cadastro de Bancos;
* Clique em Novo, para adicionar

    ![cadastro banco](../images/EmissaoBoletos/1.jpg)

* **Banco**: Adicione o número do banco (conforme passado pela agência);
*Note que o sistema já traz um pré cadastramento de banco e números.*
* **Nome Banco**: Descrição do banco para orientação no sistema;
* **Conta corrente**: Selecione a conta criada no sistema para que entre o valor e fique registrado em seus relatórios financeiro;
* **Conta Tarifas**: Selecione uma conta para despesa na geração desse boleto;
* **Site**: Se desejar pode informar o site do banco ou até mesmo do posto;
* **Local de pagamento**: Informe o local onde o seu cliente poderá efetuar o pagamento deste boleto (*a informação sairá impressa no boleto*);

    ![Informações do Banco](../images/EmissaoBoletos/2.jpg)

### Parâmetros Bancários
![Parâmetros do Banco](../images/EmissaoBoletos/3.jpg)
* **Empresa**: Selecione a empresa para qual deseja que vá a configuração realizada;
* **Cód. Compensação**: Informado pelo banco;
* **Agencia Cedente + Digito Verificador**: Informado pelo banco;
* **Cód. Cedente [C/C] + Digito Verificador**: Informado pelo banco;
* **Diretório de Cobrança**: Informe o local que será gravado o PDF ou qualquer outro arquivo gerado junto ao boleto;
* **Nome do Arquivo**: Para melhor orientação adicione o nome para geração do arquivo, como exemplo: *Banco_Brasil?*;
* **Último Lote de Cobrança**: Gerado automático; É o último boleto gerado para esta configuração de banco;
* **Último Cheque**: Gerado automático; É o último cheque deste banco;
* **Multa**: Aqui deve ser informado a porcentagem paga pela geração do boleto;
* **Situação**: Quando desejar inativar alguma configuração bancária poderá apenas desmarcar a opção “Ativo” de situação;

### Carteira de Cobrança
![Carteira](../images/EmissaoBoletos/4.jpg)
* **Carteira**: Informado pelo banco;
* **Convênio Líder**: Informado pelo banco;
* **Convênio**: Informado pelo banco;
* **Instrução 1**: Informado pelo banco;
* **Instrução 2**: Informado pelo banco;
* **Último boleto**: Gerado automaticamente, é o último boleto gerado para esta configuração de carteira;
* **Tarifa repassada**: Informado pelo banco, é o valor cobrado pela agência;
* **Situação**:  Se desejar inativar alguma configuração de carteira poderá apenas desmarcar a opção “Ativo” de situação;
* **Dias Protestar**: Após para reembolso do boleto;

#### Opções
![Opções](../images/EmissaoBoletos/5.jpg)
* **Gerar remessa**: Marque a opção para que essa configuração gere remessa para boleto;
* **Banco Emite boleto**: Marque a opção para que seja possível a geração de boleto através deste banco;
* **Banco numera boleto**: Marque a opção para que essa configuração de banco tenha uma numeração própria de boleto;
* **Layout CNAB**: Selecione o layout usado pelo seu banco;
* **Instrução codificada 1 e 2**: Informado pelo Banco (opcional);
* **Confirme as configurações feitas**.

## Teste de Boleto
***
Se desejar poderá retornar nas configurações da carteira de cobrança e testar a geração do boleto;

![Botão teste de boleto](../images/EmissaoBoletos/6.jpg)

![Configurações para teste de boleto](../images/EmissaoBoletos/7.jpg)
* **Cliente**: Selecione um cliente (não gera fatura, apenas para teste);
* **Número Boletos**: Informe a quantidade de boletos que deseja gerar;
* **Vencimento**: Data para vencimento do mesmo;
* **Incrementa Próximos**: Dias após o vencimento para pagar;
* **Valor Boleto**: Valor de exemplo para geração do boleto;
* **Incrementa Próximo**: Valor/Juros para geração do boleto;
* **Visualiza Antes**: Marque essa opção se desejar visualizar o boleto na tela;
* **Ao clicar em confirmar o boleto será gerado em “homologação”, ou seja no formato teste e não terá validade**;

![Emissão de Boleto](../images/EmissaoBoletos/8.jpg)
Após a configuração do banco, já é possível a geração e emissão de um boleto nas faturas de seus clientes.

## Geração e Emissão de Boletos
***
Para geração de um boleto é necessário que seu cliente tenha alguma fatura já gerada no estabelecimento, se já houve uma compra a prazo, siga os passos:

* **APC > Financeiro > Contas a Receber**;
* **Selecione o cliente e em seguida a fatura** que deseja gerar o boleto;
* **Clique com botão direito sobre a mesma e vá em “Emitir Boleto / Remessa”**;

    ![Emissão de Boleto](../images/EmissaoBoletos/9.jpg)

* **Em Boletos / Manutenção de Boletos**:
    * **Banco**: Selecione o banco (criado anteriormente);
    * **Carteira**: Selecione a carteira (criada anteriormente);
    * **Vencimento Fixo**: Informe a data para vencimento do boleto. *Normalmente, após a data de vencimento a lotérica não aceita o boleto*;
    * **Isentar taxa**: Se marcado a opção, os encargos do boletos não serão adicionado no valor final do mesmo;
    * **Instruções Adicionais**: Informe algumas observações no boleto para seu cliente;

* **Processamento**:
Informe aqui o que desejar gerar junto ao boleto, normalmente marcada as opções boleto (para geração da cobrança bancária) e visualizar (para mostrar na tela). Você pode ainda gerar um arquivo, [mandar por e-mail](/articles/CofigEnvioEmailNFe.html), gerar um novo número ou gerar etiquetas (para envio de carta na residência do cliente);

    ![Emissão de Boleto](../images/EmissaoBoletos/10.jpg)

* **Clicando em Confirmar o boleto** deve ser mostrado na tela (se marcado a opção visualizar);

    ![Emissão de Boleto](../images/EmissaoBoletos/11.jpg)

**ORIENTAÇÃO: Qualquer instrução, taxas ou adicionais criados na configuração de bancos ou na geração do boleto, serão mostrados no documento para o cliente.**