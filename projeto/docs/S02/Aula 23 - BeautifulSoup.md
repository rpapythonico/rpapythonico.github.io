# BeautifulSoup

## O que é?

BeautifulSoup é uma ferramente que permite extrair dados de arquivos HTML e XML.

## Como ela irá funcionar?

Para usá-la, será necessário "baixar" a página web (o código dela) e ai sim, ela poderá ser acessada através da BeautifulSoup para efetuar as devidas extrações.

A biblioteca é excelente para extrações rápidas de dados, visto que não precisa abrir navegador e interagir com o mesmo para conseguir coletar informações.

## Baixando a página HTML

### Biblioteca Embarcada - urllib

1. Importar biblioteca para "baixar" o HTML da página:  
    ```python
    from urllib.request import urlopen
    ```
    
2. Efetuar requisição da página HTML:
    ```python
    html = urlopen('https://quotes.toscrape.com/')
    ```

    - **Resolvendo problema de certificado SSL (se houver):**
        
        ```python
        import ssl
        
        ssl._create_default_https_context = ssl._create_unverified_context
        ```
        
        - Outras formas de resolver o erro de certificado SSL: [https://exerror.com/urlopen-error-ssl-certificate_verify_failed-certificate-verify-failed/](https://exerror.com/urlopen-error-ssl-certificate_verify_failed-certificate-verify-failed/)

### Biblioteca Externa - requests

1. Instalação da "lib" usando o gerenciador de pacotes "pip":
    ```bash
    pip install requests
    ```
    

2. Importação da “lib”:
    ```python
    import requests
    ```
    
3. Download da página HTML:   
    ```python
    html = requests.get('https://quotes.toscrape.com/')
    ```
## Efetuando "parse" no HTML

### Instalação do “parser” do HTML utilizando o gerenciador de pacotes "pip":
```bash
pip install beautifulsoup4
```
    
### Importação do “parser” de HTML:
```python
from bs4 import BeautifulSoup
```
    
### Formatar o código de HTML para “parsear”:
```python
# Formato para quem usou urllib
soup = BeautifulSoup(html.read(), 'html.parser')

# Formato para quem usou requests
soup = BeautifulSoup(html.text, 'html.parser')
```

### Acessar uma TAG diretamente: 
```python
soup.h1

# output:
# <h1>
# <a href="/" style="text-decoration: none">Quotes to Scrape</a>
# </h1>
```


### Acessar o **PRIMEIRO** elemento através dos seus atributos básicos (ID  ou CLASS): 
```python
soup.find(class_='text')

# output:
# <span class="text" itemprop="text">“The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.”</span>
```
    
### Buscar algum elemento através do seu texto (entre TAGs):
```python
soup.find(text="deep-thoughts")

# output: 'deep-thoughts'
```
    
### Buscar mais de um elemento na página:
```python
soup.find_all(class_='text')

# ou

soup.find_all('span', {'class': 'text'})

# output: [<span class="text" itemprop="text">“The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.”</span>, <span class="text" itemprop="text">“It is our choices, Harry, that show what we truly are, far more than our abilities.”</span>, ... ]
```
    
### Ver atributos da TAG de HTML: 
```python
div = soup.find('div', {'class': 'quote'})
div.attrs

# output: {'class': ['quote'], 'itemscope': '', 'itemtype': 'http://schema.org/CreativeWork'}
```
    
### Pegar atributos da TAG de HTML:  
```python
soup.find('div', {'class': 'quote'}).get('itemtype')

# output: 'http://schema.org/CreativeWork'
```