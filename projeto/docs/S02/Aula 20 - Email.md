# Email

## Explicação

Após o codigo realizar algumas ações, é importante sempre no final que ele envie os arquivos ou logs por email. Dentro do Python é possível se comunicar com servidores das provedoras de email (Gmail, Outlook e etc) utilizando o protocolo SMTP.

## SMTP

É o protocolo padrão de envio de emails atrávez da internet entre dois dispositivos.

- SMTP Gmail
    - Liberação do email para suportar a conexão via SMTP:
    [https://myaccount.google.com/lesssecureapps](https://myaccount.google.com/lesssecureapps)
    - Endereços e portas de acesso:
    [https://support.google.com/a/answer/176600?hl=pt#zippy=%2Cusar-o-servidor-smtp-do-gmail](https://support.google.com/a/answer/176600?hl=pt#zippy=%2Cusar-o-servidor-smtp-do-gmail)

- SMTP Outlook
    - Endereços e portas de acesso:
    [https://support.microsoft.com/pt-br/office/configurações-pop-imap-e-smtp-para-outlook-com-d088b986-291d-42b8-9564-9c414e2aa040](https://support.microsoft.com/pt-br/office/configurações-pop-imap-e-smtp-para-outlook-com-d088b986-291d-42b8-9564-9c414e2aa040)

## Comandos

1. Instalação da biblioteca
    ```bash
    pip install smtplib
    ```

2. Declaração das variáveis
    ```python
    email = const.USER_EMAIL
    senha = const.PASS_EMAIL
    ```

3. Importação das bibliotecas
    ```python
    from email.message import EmailMessage
    import constants as const
    import smtplib
    import os
    ```


4.  Geração do objeto de e-mail
    ```python
    msg = EmailMessage()
    ```

5. Geração do corpo do e-mail com texto
    ```python
    payload = """Olá! Tudo bem?

    Este é um e-mail automático para testar o disparo de e-mail ensinado pelo curso de RPA Python!

    Atenciosamente,

    RPA Pythonico
    """
    msg.set_content(payload)
    ```

6. Atribuição de dados para disparo do e-mail (De, Para e Assunto)
    ```python
    msg['From'] = email
    
    msg['To'] = 'seu_email@provedor.com'
    
    msg['Subject'] = 'Email Automatico - SMTPLIB'
    ```

7. Criação da conexão SMTP
    ```python
    smtp = smtplib.SMTP('smtp.gmail.com', 587)
    smtp.starttls()
    smtp.login(email, senha)
    ```

8. Inserção de anexo no e-mail
    ```python
    with open('foto_email.png', 'rb') as file:
        file_data = file.read()
    msg.add_attachment(file_data, maintype='image',  subtype='png')
    ```

9. Disparo do e-mail via SMTP
    ```python
    smtp.send_message(msg)
    ```

10. Finalização da conexão SMTP
    ```python
    smtp.quit()
    ```