# Selenium - Interações

## Apagando e escrevendo em um campo

Durante a navegação em um site, existem formulátios ou campos de busca que precisam ser preenchidos. Com isso, o primeiro passo para evitar problemas, é apagar o campo utilizando o seguinte comando:
```python
driver.find_element_by_id('twotabsearchtextbox').clear()
```

Após o campo estar limpo e pronto para receber o texto, a escrita será realizada com o código:
```python
driver.find_element_by_id('twotabsearchtextbox').send_keys('Python')
``` 
    
## Movimentar a tela para um elemento (scroll):

Alguns elementos acabam não carregando até que a tela seja movimenta para próximo do mesmo. Para fazer isso, basta utilizar o código a seguir:
```python
driver.find_element_by_class_name('navFooterBackToTopText').location_once_scrolled_into_view
```
    
## Clicar em um elemento:

Para acessar objetos na página, se faz necessário dar cliques e isso é permitido usando o comando:
```python
driver.find_element_by_id('nav-search-submit-button').click()
```
    
## Extrair textos

Quando uma tag possui texto entre a abertura e o fechamento, o mesmo poderá ser coletado através da seguinte funcionalidade:    
```python
driver.find_element_by_id('glow-ingress-line2').text
```
    
Caso não exista texto entre as tags, o mesmo poderá estar em algum atributo dela. Logo, para coletar direto de um atributo HTML, basta usar a seguinte função:
```python
driver.find_element_by_id('nav-logo-sprites').get_attribute('aria-label')
```
    

## Printscreens

- Para tirar um print de algum elemento específico do HTML, existe o seguinte código:    
```python
driver.find_element_by_id('navbar').screenshot('menu.png')
```
Caso deseje tirar um print da página inteira conforme está sendo visto no navegador, basta utilizar a função a seguir:
```python
driver.save_screenshot("screenshot.png")
```

## Dropdowns

Dentro do HTML, existe o conceito de dropdown, cujo botão permite ao usuário abrir uma lista de opções e escolher uma delas. Para que isso fique bem assertivo no Selenium, a função "Select" deverá ser importada e instanciada durante a execução. O uso dela pode ser visto melhor no código abaixo:
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