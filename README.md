# analisador_sentencas_2 (Google Colab)

Este projeto utiliza um notebook do Google Colab para automatizar a coleta, a extração de informações e a análise com LLM de sentenças judiciais sobre tráfico de drogas em Piracicaba, extraídas do e-SAJ do TJSP.

## Fluxo de Trabalho

**Coleta de Dados:** O script realiza web scraping com ```requests``` para baixar páginas com julgados de interesse.

**Extração de Informações:** O conteúdo HTML é processado com ```BeautifulSoup4``` para extrair, por exemplo, número do processo, magistrado e texto completo da sentença e os organiza em dataframe, usando ```pandas```.

**Análise com IA:** O texto de cada sentença é analisado por um modelo de linguagem (LLM), que extrai informações-chave como modus operandi, alegações da defesa, resultado do processo e um resumo da decisão. Usamos o ```LiteLLM``` para facilitar a alternância dos modelos.

**Armazenamento:** Os dados obtidos com a extração e com a análise são salvos no Google Drive como arquivos CSV.

---

## Como Executar no Google Colab

- Abra o Google Colab.

- Configure as Chaves de API (no menu à esquerda, clique no ícone de "chave" e adicione as API_KEY necessárias.

- Conecte ao Google Drive.

- Execute todas as células do notebook em ordem, do início ao fim. As dependências serão instaladas e o processo será iniciado.

- Ao final da execução, você encontrará os arquivos CSV resultantes da análise no seu Google Drive, na pasta especificada na variável PROCESSED_DATA_PATH.

## Dicas

- Altere PARAMS_TJSP para analisar outros tipos de sentenças. Inspecione a página https://esaj.tjsp.jus.br/cjpg/pesquisar.do para entender como funcionam os parâmetros.

- Modifique o prompt para obter novos resultados. Faça as alterações correspondentes no JSON de saída. 
  
