# Aula 5 - Selenium e BeautifulSoup

## Webdrivers:

- Chromedriver:
    - [https://chromedriver.chromium.org/downloads](https://chromedriver.chromium.org/downloads)

- Geckodriver:
    - [https://github.com/mozilla/geckodriver/releases](https://github.com/mozilla/geckodriver/releases)
- IEDriver:
    - [https://www.selenium.dev/downloads/](https://www.selenium.dev/downloads/)
        - x64: [https://github.com/SeleniumHQ/selenium/releases/download/selenium-3.150.0/IEDriverServer_x64_3.150.2.zip](https://github.com/SeleniumHQ/selenium/releases/download/selenium-3.150.0/IEDriverServer_x64_3.150.2.zip)
        - x32: [https://github.com/SeleniumHQ/selenium/releases/download/selenium-3.150.0/IEDriverServer_Win32_3.150.2.zip](https://github.com/SeleniumHQ/selenium/releases/download/selenium-3.150.0/IEDriverServer_Win32_3.150.2.zip)
- Operadriver:
    - [https://github.com/operasoftware/operachromiumdriver/releases](https://github.com/operasoftware/operachromiumdriver/releases)
- Edgedriver:
    - [https://developer.microsoft.com/en-us/microsoft-edge/tools/webdriver/](https://developer.microsoft.com/e../img/n-us/microsoft-edge/tools/webdriver/)

## Selenium:

- Instalação do Selenium:
    
    ```bash
    pip install selenium
    ```
    
- Importação da biblioteca:
    
    ```python
    from selenium import webdriver
    ```
    
- Chamar navegadores com o(s) webdriver(s):
    
    ```python
    #Google Chrome
    driver = webdriver.Chrome('chromedriver.exe')
    
    #Mozilla Firefox
    driver = webdriver.Firefox('geckodriver.exe')
    
    #Internet Explorer
    driver = webdriver.Ie('IEDriverServer.exe')
    ```
    
- Maximizar a janela do navegador:
    
    ```python
    driver.maximize_window()
    ```
    
- Colocar um tempo para carregamento - IMPLÍCITO:
    
    ```python
    driver.implicitly_wait(30)
    ```
    
- Colocar um tempo para carregamento - EXPLÍCITO:
    
    ```python
    from selenium.webdriver.common.by import By
    from selenium.webdriver.support.ui import WebDriverWait
    from selenium.webdriver.support import expected_conditions as EC
    
    WebDriverWait(driver, 30).until(EC.presence_of_element_located((By.ID, 'twotabsearchtextbox')))
    ```
    
- Acessar um site:
    
    ```python
    driver.get('https://www.amazon.com.br/')
    ```
    
- Buscar elementos na página:
    
    ```python
    #Buscar pela class do elemento
    driver.find_element_by_class_name('nav-input.nav-progressive-attribute')
    
    #Buscar pelo id do elemento
    driver.find_element_by_id('twotabsearchtextbox')
    
    #Buscar pela tag do elemento
    driver.find_element_by_tag_name('h1')
    
    #Buscar pelo xpath do elemento
    driver.find_element_by_xpath('//input[@id="twotabsearchtextbox"]')
    
    #Buscar pelo texto completo do elemento:
    driver.find_element_by_link_text('Todos')
    
    #Buscar pelo texto parcial do elemento:
    driver.find_element_by_partial_link_text('endereço').click()
    
    #Buscar pelo seletor CSS:
    driver.find_element_by_css_selector('#searchDropdownBox')
    driver.find_element_by_css_selector('[name=url]')
    driver.find_element_by_css_selector('.nav-search-dropdown.searchSelect.nav-progressive-attrubute.nav-progressive-search-dropdown')
    ```
    
- Digita um valor no site:
    
    ```python
    driver.find_element_by_id('twotabsearchtextbox').send_keys('Python')
    ```
    
- Apagar um campo escrito:
    
    ```python
    driver.find_element_by_id('twotabsearchtextbox').clear()
    ```
    
- Clicar em um elemento:
    
    ```python
    driver.find_element_by_id('nav-search-submit-button').click()
    ```
    
- Movimentar a tela para um elemento (scroll):
    
    ```python
    driver.find_element_by_class_name('navFooterBackToTopText').location_once_scrolled_into_view
    ```
    
- Extrair texto:
    
    ```python
    driver.find_element_by_id('glow-ingress-line2').text
    ```
    
- Coletar atributos do HTML:
    
    ```python
    driver.find_element_by_id('nav-logo-sprites').get_attribute('aria-label')
    ```
    
- Tirar print de um elemento ou do site:
    
    ```python
    #Print do elemento
    driver.find_element_by_id('navbar').screenshot('menu.png')
    
    #Print do site
    driver.save_screenshot("screenshot.png")
    ```
    
- Selecionar uma opção no Dropdown:
    
    ```python
    from selenium.webdriver.support.ui import Select
    
    dropdown = Select(driver.find_element_by_id('searchDropdownBox'))
    
    #Selecionar pelo texto presente
    dropdown.select_by_visible_text('Computadores e Informática')
    
    #Selecionar pelo atributo value do HTML
    dropdown.select_by_value('search-alias=computers')
    
    #Selecionar pelo número dele na lista
    dropdown.select_by_index(11)
    ```
    
- Fechar aba do navegador:
    
    ```python
    driver.close()
    ```
    
- Fechar navegador e seu webdriver:
    
    ```python
    driver.quit()
    ```
    

## BeautifulSoup:

- Importar biblioteca para "baixar" o HTML da página:
    
    ```python
    from urllib.request import urlopen
    ```
    
- Efetuar requisição da página HTML:
    
    ```python
    html = urlopen('https://quotes.toscrape.com/')
    ```
    
    - **Resolvendo problema de certificado SSL (se houver):**
        
        ```python
        import ssl
        
        ssl._create_default_https_context = ssl._create_unverified_context
        ```
        
        - Outras formas de resolver o erro de certificado SSL: [https://exerror.com/urlopen-error-ssl-certificate_verify_failed-certificate-verify-failed/](https://exerror.com/urlopen-error-ssl-certificate_verify_failed-certificate-verify-failed/)
- Instalar o “parser” do HTML:
    
    ```bash
    pip install beautifulsoup4
    ```
    
- Importar biblioteca do “parser” de HTML:
    
    ```python
    from bs4 import BeautifulSoup
    ```
    
- Formatar o código de HTML para “parsear”:
    
    ```python
    soup = BeautifulSoup(html.read(), 'html.parser')
    ```
    
- **ALTERNATIVA de biblioteca para "baixar" o html da página:**
    - Instalação da "lib":
        
        ```bash
        pip install requests
        ```
        
    - Importação da “lib”:
        
        ```python
        import requests
        ```
        
    - Efetuar requisição da página HTML:
        
        ```python
        html = requests.get('https://quotes.toscrape.com/')
        ```
        
    - Formatar o código de HTML para “parsear”:
        
        ```python
        soup = BeautifulSoup(html.text, 'html.parser')
        ```
        
- Acessar uma TAG diretamente:
    
    ```python
    soup.h1
    
    # output:
    # <h1>
    # <a href="/" style="text-decoration: none">Quotes to Scrape</a>
    # </h1>
    ```
    
- Acessar o **PRIMEIRO** elemento através dos seus atributos básicos (ID  ou CLASS):
    
    ```python
    soup.find(class_='text')
    
    # output:
    # <span class="text" itemprop="text">“The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.”</span>
    ```
    
- Buscar algum elemento através do seu texto (entre as TAGS):
    
    ```python
    soup.find(text="deep-thoughts")
    
    # output: 'deep-thoughts'
    ```
    
- Buscar mais de um elemento na página:
    
    ```python
    soup.find_all(class_='text')
    
    # ou
    
    soup.find_all('span', {'class': 'text'})
    
    # output: [<span class="text" itemprop="text">“The world as we have created it is a process of our thinking. It cannot be changed without changing our thinking.”</span>, <span class="text" itemprop="text">“It is our choices, Harry, that show what we truly are, far more than our abilities.”</span>, ... ]
    ```
    
- Ver atributos da TAG de HTML:
    
    ```python
    div = soup.find('div', {'class': 'quote'})
    div.attrs
    
    # output: {'class': ['quote'], 'itemscope': '', 'itemtype': 'http://schema.org/CreativeWork'}
    ```
    
- Pegar atributos da TAG de HTML:
    
    ```python
    soup.find('div', {'class': 'quote'}).get('itemtype')
    
    # output: 'http://schema.org/CreativeWork'
    ```
    

## Xpath:

![032816_0758_XPathinSele1.png](../img/xpath_syntax.png)

- Guia de criação de Xpath: [https://www.guru99.com/xpath-selenium.html](https://www.guru99.com/xpath-selenium.html)
- Extra: [https://devhints.io/xpath](https://devhints.io/xpath)

CSS Selector:

- Guia: [https://www.w3schools.com/cssref/css_selectors.asp](https://www.w3schools.com/cssref/css_selectors.asp)
- Cheat Sheet: [https://devhints.io/css](https://devhints.io/css)
- Extra: [https://www.freecodecamp.org/news/css-selectors-cheat-sheet/](https://www.freecodecamp.org/news/css-selectors-cheat-sheet/)

## Extras:

- [https://dunossauro.github.io/curso-python-selenium/](https://dunossauro.github.io/curso-python-selenium/)
- [https://scrapy.org/](https://scrapy.org/)
- [https://mechanicalsoup.readthedocs.io/en/stable/](https://mechanicalsoup.readthedocs.io/en/stable/)