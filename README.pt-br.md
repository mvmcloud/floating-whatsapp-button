# Botão de WhatsApp Flutuante

You can read this document in: [English](https://github.com/mvmcloud/floating-whatsapp-button/blob/master/README.md)

Este é um plugin de Botão de WhatsApp Flutuante para jQuery.

Ele adiciona um botão flutuante ao seu site que chama a [API do WhatsApp Web](https://faq.whatsapp.com/pt-br/26000030/).

Além de permitir o bate-papo via WhatsApp, ele pode capturar detalhes dos visitantes como nome, sobrenome, e-mail. Este comportamento é opcional e você pode ativá-lo ou não.

Se você ativar a captura de dados dos visitantes irá recebê-los no e-mail que escolheu ao criar o botão.

## Criando o botão

Você pode usar nossa ferramenta online para criar o botão. Por favor visite [Criar Botão de WhatsApp Gratuito](https://www.mvmcloud.net/whatsapp/new). ADepois de criar o botão, você verá uma instrução completa para instalar o código em seu site.

## Instalando

Vincule os arquivos ao seu html na tag head do seu site (certifique-se de carregar os arquivos após o jQuery).

```html
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script type="text/javascript" src="https://cdn.mvmcloud.net/mvm-wapp-3.1.1.min.js"></script>
```

## Como usar o botão

O código gerado pela ferramenta MVMCloud deve ser inserido em cada página onde você deseja mostrar o botão. Se você deseja exibí-lo em todas as páginas, deve inserí-lo no rodapé do seu site.

```html
<body>
  ...O código html do seu site está aqui...
  <!-- Insira o código abaixo imediatamente antes do fechamento da tag body  -->
  <div id="WAButton"></div>
  <script type="text/javascript">
      jQuery('#WAButton').mvmWhatsApp({
          cid: "Ade2aec28855422a9ec7b789723fcba2",
          phone: "5511991234567",
          headerTitle: "Talk to us by WhatsApp",
          popupMessage: "Hi, tell me who you are so we can talk.",
          showPopup: true,
          headerColor: "#128C7E",
          backgroundColor: "#25D366",
          position: "right",
          size: "60px",
          useFirstLastName: true,
          firstNameLabel: "First name",
          lastNameLabel: "Last name",
          emailLabel: "Email",
          phoneLabel: "What is your WhatsApp number?",
          phoneHint: "Enter the number with country and area code. E.g.: 5511991234567",
          messageLabel: "Type your message to us",
          errorMsg: "Please fill in the required fields",
          btnSendText: "Start WhatsApp",
          btnSendColor: "#128C7E",
          requiredData: true,
          buttonOffset: '70px',
      });
  </script>
</body>
```
### Formulário para capturar os detalhes dos visitantes

A captura de detalhes do visitante, nome, sobrenome, e-mail e número do WhatsApp estão ativados por padrão. Quando o visitante clica no botão, um pequeno formulário é aberto para solicitar esses detalhes antes de iniciar a conversa pelo WhastApp. Essas informações são enviadas para o endereço de e-mail que você escolheu ao criar o botão.


![Janela do Formulário](criar-botao-whatsapp.jpg)

### Personalização

Você pode personalizar a aparência e o comportamento do botão modificando os parâmetros usados ao chamar a função jQuery('#WAButton').mvmWhatsApp no seu site.

### Opções

Você pode ter uma descrição completa sobre as opções abaixo e como usá-las em [Como Configurar o Botão WhatsApp Gratuito](https://www.mvmcloud.net/configurar-botao-whatsapp-gratuito).

| opção              | tipo                                           | valor padrão             | obrigatório | descrição |
|---------------------|-----------------------------------------------|--------------------------|----------|-------------|
| autoOpenTimeout     | `integer`                                     | `0`                      |    N     | Define um tempo em milissegundos para abrir o formulário automaticamente.
| backgroundColor     | `string`                                      | `'#25D366'`              |    N     | Cor de fundo do botão. 
| btnSendColor        | `string`                                      | `'#128C7E'`              |    N     | Cor do botão enviar do formulário.
| btnSendColorHover   | `string`                                      | `'#16b7a4'`              |    N     | Cor do botão enviar do formulário quando o visitante passa o mouse sobre ele.
| btnSendText         | `string`                                      | `'Send Your Message'`    |    N     | Texto do botão enviar do formulário.
| buttonImage         | `string`                                      | [esta aqui](whatsapp.svg) |    N     | Imagem externa para substituir a imagem incorporada do botão. Deve ser `img` ou `svg` para que seja mostrada sem problema.
| buttonOffset        | `string`                                      | `''`                     |    N     | Substitui o css do botão direito ou esquerdo, por exemplo, '30px'.
| cid                 | `string`                                      | `''`                     |    Y     | ID do Cliente. Este texto identifica o seu botão em nosso servidor.
| embedResources      | `boolean`                                     | `true`                   |    N     | Incorpora o arquivo de estilo css necessário para esta biblioteca.
| emailLabel          | `string`                                      | `'Enter Your Email'`     |    N     | Rótulo para campo de e-mail.
| errorMsg            | `string`                                      | `'Please, fill the required fields'`   |    N     | Mensagem de erro a ser mostrada caso o visitante deixe em branco os campos do formulário.
| firstNameLabel      | `string`                                      | `'Enter Your First Name'` |    N     | Rótulo para o campo de primeiro nome.
| lastNameLabel       | `string`                                      | `'Enter Your Last Name'` |    N     | Rótulo para o campo de sobrenome.
| headerColor         | `string`                                      | `'#128C7E'`              |          | Cor de fundo da barra de título do formulário.
| headerTitle         | `string`                                      | `'WhatsApp Chat'`        |    N     | Texto que será mostrado na barra de título do formulário.
| message             | `string`                                      | `''`                     |    N     | Mensagem a ser enviada. Se `showPopup` for `true`, o campo de mensagem será preenchido com este texto.
| messageLabel        | `string`                                      | `'Enter Your Message Here'`  |    N     | Rótulo para o campo de mensagem.
| nameLabel           | `string`                                      | `'Enter Your Name'`      |    N     | Rótulo para o campo nome.
| phone               | `string`                                      | `''`                     |    Y     | Número de WhatsApp que receberá a mensagem [número no formato internacional](https://faq.whatsapp.com/pt-br/general/21016748).   
| phoneHint           | `string`                                      | `'phone number like: 14081234567'`     |    N     | Dica para o campo Phone.
| phoneLabel          | `string`                                      | `'Enter Your phone number'`     |    N     | Rótulo para o campo phone.
| position            | `string`                                      | `'left'`                 |    N     | Posição do botão na tela. `'left'` &#124; `'right'`
| popupMessage        | `string`                                      | `'Please, enter your details'` |    N     | Mensagem de boas-vindas para o visitante do seu site.
| requiredData        | `boolean`                                     | `true`                   |    N     | True para tornar obrigatório o preenchimento dos detalhes do visitante (name, first_name, last_name, email e phone).
| showOnIE            | `boolean`                                     | `true`                   |    N     | Mostra ou não o botao no browser IE (recommendado true).
| showPopup           | `boolean`                                     | `true`                   |    N     | Se TRUE, mostra o formulário quando o visitante passa o mouse sobre o botão (em desktop) ou clica no botão (em aparelhos móveis).
| size                | `string`                                      | `'60px'`                 |    N     | Tamanhoo do botão. Qualquer opção css é válida largura e altura. properties.
| useFirstLastName    | `boolean`                                     | `true`                   |    N     | True para mostrar o campo nome e sobrenome. False para mostrar apenas o campo nome.
| zIndex              | `integer` &#124; `string`                      | `10`                     |    N     | Substitui o z-index da tag div do botão. Esta opção pode trazer o botão para frente, ou enviar para trás, de outro elemento na página html. 



