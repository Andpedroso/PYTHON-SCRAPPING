## Scrapping da loja virtual x
#### Foram consultados os principais valores dos produtos oferecidos na loja.
---
## Comandos
---
> imports
```bash
import requests
import re
import json
from bs4 import BeautifulSoup
!pip install gtts
from gtts import gTTS
import os
```
---
> Carregar página e retornar status
#### verifica a disponibilidade para o scrapping
```bash
result = requests.get('url')
print(result.status_code)
```
---
> Conteúdo da página
```bash
result.content
```
---
> Armazena o conteúdo e organiza a sopa com html
```bash
src = result.content
soup=BeautifulSoup(src,'lxml')
soup
```
---
> Localizar a informação que precisa através das tags e dos nomes de classes
```bash
soup.find_all('span',{'x-bestPrice'})
```
---
> Coloca as informações em uma lista
```bash
prices=soup.find_all('span',{'x-bestPrice'})
prices_list=[]
for x in prices:
  prices_list.append(x.text)
prices_list
```
---
---
## Ferramentas
#### Para este projeto foi utilizado o GoogleColaboratory.
---
## Problemas
#### Nem todas as páginas permitem scrapping podendo haver tratamentos de Back-end para isso.