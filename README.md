# METEO

Painel responsivo para consultar as condições meteorológicas atuais e a previsão de cinco dias de cidades do mundo todo.

## Executar

Abra um terminal nesta pasta e inicie um servidor estático:

```powershell
python -m http.server 5500
```

Depois, acesse `http://localhost:5500`. O aplicativo não requer instalação de dependências ou chave de API; precisa de conexão com a internet para consultar os serviços da Open-Meteo.

## Funcionalidades

- Busca de cidades e seleção entre localidades com nomes iguais.
- Temperatura atual, sensação térmica, umidade, vento, UV, precipitação e coordenadas.
- Previsão de cinco dias com ícones, mínimas, máximas, UV e gráfico de temperaturas.
- Atualização do clima, histórico das cinco cidades mais recentes e comparação de previsões.
- Mensagens de erro para entradas inválidas, localidades não encontradas, falhas de rede e tempo limite.

## Serviços e arquitetura

A versão atual consulta diretamente os serviços públicos da Open-Meteo:

- Geocoding: `https://geocoding-api.open-meteo.com/v1/search`
- Meteorologia: `https://api.open-meteo.com/v1/forecast`

As localidades consultadas são guardadas no armazenamento local do navegador. Um API Gateway e microsserviços de localização e meteorologia são uma possível evolução da arquitetura, mas não fazem parte deste protótipo.
