# Importar Bibliotecas
import pandas as pd

# Lendo arquivo CSV
df = pd.read_csv('datatran2020.csv', encoding = 'ISO-8859-1', sep = ';')

# Ajustando Coluna de latitude e longitude para usar na plataforma Keple.gl
df['latitude'] = df['latitude'].str.replace(',','.')
df['longitude'] = df['longitude'].str.replace(',','.')

# Criando coluna de data e hora concatenada 
df['data_hora'] = pd.to_datetime(df['data_inversa'] + ' ' + df['horario'])

# Salvando arquivo
df.to_csv('acidentesPRF2020.csv', sep = ',')

#Link da Platafaorma Keple.gl
https://kepler.gl/demo

