![Logo Softplus](./images/ls.png)

# Configuração para envio de E-mail NFe
55555
## Para que serve esta configuração?
Muitas vezes clientes solicitam que sua DANFE ou [boleto](https://docs.google.com/document/d/1gl5oQnL5VVrrbfEymGZhFXnY9UvW0JA20DF6acUDt0I) sejam enviados por e-mail, ou seja, além da impressão no ato da emissão, o sistema ainda permite que seja enviado o documento para o cliente em PDF. 

## O que é preciso para envio de e-mail via NFe?
Para envio dos mesmos temos alguns pré requisitos:
* **Dados do provedor**: Antes de iniciar as configurações o cliente deve ter em mãos os dados passados pelo provedor, tais como servidor SMTP e POP, porta SMTP e POP, login e senha.
* **Provedor liberado**: É importante lembrar que o provedor do cliente deve estar liberado para uso e envio destes e-mails, ou seja, não podemos simplesmente fazer a configuração se o provedor não autorizar o uso das portas e dos dados;
* **Firewall ou programa de bloqueio**: Como todo o uso do sistema, o envio de e-mail necessita de permissões especiais, com isso é importante que estejam desativados o firewall, programas de bloqueio e também devemos cuidar com alguns anti vírus;
Configuração prévia para envio: Configuração correta de E-mail no NFe;
* **Cliente com e-mail cadastrado**: No cadastro de cliente deve conter um e-mail válido para envio;

## Existe algum parâmetro?
Sim, por default (padrão) o envio de e-mail é automático, o cliente só precisa ter um e-mail cadastrado em seu cadastro, na aba Contato/Cobrança;
![Parâmetro para emissão](http://i.imgur.com/YTxSHuk.jpg)

Se necessário poderá configurar se será enviado ou não este e-mail na emissão de notas, para isso vá até o cadastro de clientes, na aba Propriedades, haverá o parâmetro “Não envia e-mail automático NFE”, se desmarcado, não será enviado o e-mail para o cliente.
Na [geração/emissão de boleto](https://docs.google.com/document/d/1gl5oQnL5VVrrbfEymGZhFXnY9UvW0JA20DF6acUDt0I), basta marcar a opção “E-mail” no momento da geração.

## Configuração para envio de E-mail NFe
Lembrando que o usuário deve ter em mãos os dados que ele irá utilizar para configuração.

1. Via **APC > Sistema > Empresa > Cadastro de E-mails**;
2. ou **Via NFe > menu Contas de E-mails**;
![Configuração de Email](http://i.imgur.com/tmVyFhb.jpg)
3. Na seleção de e-mails, clique em “**Novo**” para criar uma nova configuração;
4. **Adicione as informações passadas pelo provedor**;
* Abaixo colocaremos informações que **podem ser usadas por técnicos da Softplus**, para teste interno ou no cliente, lembrando que **não devemos manter essas informações na máquina do cliente**.
    * **Empresa**: Selecione a empresa para configuração;
    * **Finalidade**: Escolha entre NFe ou Boleto;
    * **Servidor SMTP**: smtps.bol.com.br;
    * **Servidor POP**: pop.bol.com.br;
    * **Porta SMTP**: 587;
    * **Porta POP**: 993;
    * **Autenticação**: Sim;
    * **Conta de login**: testenfee@bol.com.br;
    * **Senha**: suporte1;
    * **E-mail**: testenfee@bol.com.br (Opcional:é para onde vai o envio do teste);
    ![Cadastro de e-mail](http://i.imgur.com/Nl5NuGF.jpg)

    * **Empresa**: Selecione a empresa para configuração;
    * **Finalidade**: Escolha entre NFe ou Boleto;
    * **Servidor SMTP**: smtp.gmail.com;
    * **Servidor POP**: deixe em branco;
    * **Porta SMTP**: 587;
    * **Porta POP**: deixe em branco;
    * **Autenticação**: Sim;
    * **Conta de login**: suportesoftplus05@gmail.com;
    * **Senha**: spi12345678;
    * **E-mail**: suportesoftplus05@gmail.com (Opcional:é para onde vai o envio do teste);
5. Ao finalizar a configuração de e-mail clique em “**Testar**”, se tudo estiver correto ele deve retornar a mensagem de “**E-mail enviado com sucesso**”;
6. Confirme as informações (lembrando em deixar as configurações do provedor do usuário, e não os de exemplo passados pela Softplus);

Pronto, se a configuração foi feita corretamente, o sistema já estará apto para enviar e-mail na emissão de NFe ou para boletos.
