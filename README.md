# Analisando_Risco_Clientes
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/LombaAnderson/Analisando_Risco_Clientes/blob/main/LICENSE)


# Sobre o projeto
Análise de alguns dados sobre clientes tais como idade, número de membros da família, renda familiar, dentre outros retirados do site https://data.mendeley.com/datasets/27cndjvfbx/1. Foram deletados algumas colunas que não foram aproveitadas. A visualização com a biblioteca plotly demonstrou análises cruzadas de vários atributos do conjunto de dados.

 # Importando Bibliotecas 
import numpy as np 
import pandas as pd 
import matplotlib.pyplot as plt
import seaborn as sns
import plotly as py
from sklearn.cluster import KMeans
import warnings
import os
warnings.filterwarnings("ignore")
py.offline.init_notebook_mode(connected=True)


 # Importando Base de dados

dados_clientes =pd.read_excel('dataset.xlsx', index_col=0)

# Renomeando as colunas do conjunto de dados

dados_clientes.rename({'age':'Idade','average':'Media','job':'Trabalho','marital status':\
                       'Estado civil','family income':'Renda fam','family member':'Membros fam','lost family':'Perda fam','special disease':\
                      'Doença espec','belive in abilities':'Crença em Hab','plenty friends':\
                       'Muitos amigos',},axis=1, inplace=True)
                       
 # Renomeando atributos do conjunto de dados
dados_clientes.rename({'number':'ID','bankrupcy':'Falencia','political concern':'Preocupação politica',\
                       'smoke':'Fumante','religion':'Religião','lonely':'Solitario','sport':'Esporte','parents relationship':'Relac pais','worring about job':'Preocupação com emprego',\
                       'depression':'Depressão'},axis=1, inplace=True)
 
 # Colunas deletadas

dados_clientes.drop('enterance',axis=1,inplace=True)
#dados_clientes.drop('art',axis=1,inplace=True)
#dados_clientes.drop('break in love',axis=1, inplace=True)
#dados_clientes.drop('activity',axis=1,inplace=True)
#dados_clientes.drop('Media',axis=1,inplace=True)
#dados_clientes.drop('interested in major',axis=1,inplace=True)

# Renomeando todos os atributos das colunas

dados_clientes['Estado civil'].replace(['single','married'],['Solteiro(a)','Casado(a)'],inplace=True)
dados_clientes['Perda fam'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Doença espec'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Religião'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Relac pais'].replace(['Divorce','kind','bad'],['divorciados','bom','ruim'],inplace=True)
dados_clientes['Esporte'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Crença em Hab'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Muitos amigos'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Falencia'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Preocupação politica'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Fumante'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Preocupação com emprego'].replace(['no','yes'],['Não','Sim'],inplace=True)
dados_clientes['Depressão'].replace(['no','yes','a little'],['Não','Sim','Um pouco'],inplace=True)
dados_clientes['Trabalho'].replace(['no','yes'],['Não','Sim'],inplace=True)

# Autor

Anderson Lomba de Oliveira

Linkedin

https://www.linkedin.com/in/anderson-lomba-140279142/

Portfólio

https://www.lombanderson.epizy.com

# Agradecimentos

Agradeço sobretudo a Deus e a minha esposa Liciane.
