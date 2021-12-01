# Floating WhatsApp Button

Você pode ler este documento em: [Português Brasileiro](https://github.com/mvmcloud/floating-whatsapp-button/blob/master/README.pt-br.md)

This is a floating WhatsApp button library plugin for jQuery.

It adds a floating button to your website that calls the [WhatsApp Click to Chat API](https://faq.whatsapp.com/en/26000030/).

Besides to allow chat via WhatsApp, it can capture visitors details like, first name, last name, email. This behaviour is optional and you can activate it or not.

If you activate the capture of visitors details you will receive them in the email you chose when you create the button.

## Creating the button

You can use an online tool to create the button. Please, visit [Create Free WhatsApp Button](https://www.mvmcloud.net/en/whatsapp/new). After create the button you'll see a complete instruction to install the code in your website.

## Installing

Link the files to your html in the tag head of your website (make sure you load the files after jQuery)

```html
<script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.0/jquery.min.js"></script>
<script type="text/javascript" src="https://cdn.mvmcloud.net/mvm-wapp-3.1.1.min.js"></script>
```

## How to use button

The code generated by the MVMCloud tool must be inserted in each page where you want to show the button. If you want to show it on all pages you must insert it in the footer of your website.

```html
<body>
  ...The html code of your website is here...
  <!-- Insert the below code just before closing body  -->
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
### Form to capture visitors' details

The capture of visitor details, first name, last name, email and WhatsApp number are enabled by default. When visitors click on the button, a small form opens to request these details before starting the conversation through WhastApp. This information is sent to the email address you chose when creating the button.


![Form Chat Window](create-whatsapp-button.jpg)

### Customization

You can customize the appearance and behavior of the button by modifying the parameters used when calling the function jQuery('#WAButton').mvmWhatsApp in your website.

### Options

You can have a complete description about the below options and how to use them at [How to Configure Free WhatsApp Button](https://www.mvmcloud.net/en/configure-free-whatsapp-button).

| option              | type                                          | default                  | required | description |
|---------------------|-----------------------------------------------|--------------------------|----------|-------------|
| autoOpenTimeout     | `integer`                                     | `0`                      |    N     | Set a time period in milliseconds for the form to open automatically.
| backgroundColor     | `string`                                      | `'#25D366'`              |    N     | Button background color. 
| btnSendColor        | `string`                                      | `'#128C7E'`              |    N     | Form send button color.
| btnSendColorHover   | `string`                                      | `'#16b7a4'`              |    N     | Form send button hover color.
| btnSendText         | `string`                                      | `'Send Your Message'`    |    N     | Form send button text.
| buttonImage         | `string`                                      | [this one](whatsapp.svg) |    N     | Button background image to substitute the embeded image. Must be an `img` or `svg` in order to be displayed properly.
| buttonOffset        | `string`                                      | `''`                     |    N     | Overrides the button's css right or left, e.g. '30px'.
| cid                 | `string`                                      | `''`                     |    Y     | Client id. This string identifies your button to our server.
| embedResources      | `boolean`                                     | `true`                   |    N     | Embed css required for this library.
| emailLabel          | `string`                                      | `'Enter Your Email'`     |    N     | Label for email field.
| errorMsg            | `string`                                      | `'Please, fill the required fields'`   |    N     | Error message to be shown if visitor doesn't enter the form fields.
| firstNameLabel      | `string`                                      | `'Enter Your First Name'` |    N     | Label for first name field.
| lastNameLabel       | `string`                                      | `'Enter Your Last Name'` |    N     | Label for last name field.
| headerColor         | `string`                                      | `'#128C7E'`              |          | Background color of the form title bar.
| headerTitle         | `string`                                      | `'WhatsApp Chat'`        |    N     | Text to be displayed at the form title bar.
| message             | `string`                                      | `''`                     |    N     | Message to be sent. If `showPopup` is `true`, the input will be populated with this message.
| messageLabel        | `string`                                      | `'Enter Your Message Here'`  |    N     | Label for message field.
| nameLabel           | `string`                                      | `'Enter Your Name'`      |    N     | Label for name field.
| phone               | `string`                                      | `''`                     |    Y     | WhatsApp [international number](https://faq.whatsapp.com/en/general/21016748) which will receive the message.   
| phoneHint           | `string`                                      | `'phone number like: 14081234567'`     |    N     | Phone number hint message.
| phoneLabel          | `string`                                      | `'Enter Your phone number'`     |    N     | Label for phone field.
| position            | `string`                                      | `'left'`                 |    N     | Button position on screen. `'left'` &#124; `'right'`
| popupMessage        | `string`                                      | `'Please, enter your details'` |    N     | Welcome message to your website visitor.
| requiredData        | `boolean`                                     | `true`                   |    N     | True to force data (name, first_name, last_name, email and phone) to be required.
| showOnIE            | `boolean`                                     | `true`                   |    N     | Whether to show or not the button on IE (recommended true).
| showPopup           | `boolean`                                     | `true`                   |    N     | Show the form when the user hovers (on desktop) or clicks the button (on mobile).
| size                | `string`                                      | `'60px'`                 |    N     | The size of the button. Any css option is valid for width and height properties.
| useFirstLastName    | `boolean`                                     | `true`                   |    N     | True to display first and last name field. False to display name field instead.
| zIndex              | `integer` &#124; `string`                      | `10`                     |    N     | Overrides button div z-index. Use a z-index css property value.



