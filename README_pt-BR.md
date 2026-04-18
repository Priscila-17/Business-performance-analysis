# Performance de negócio – E-commerce
## 1. Objetivo
O objetivo deste projeto é analisar o comportamento de vendas de um e-commerce ao longo do tempo, buscando identificar:
- padrões de consumo
- concentração de receita
- nível de recorrência dos clientes
- possíveis riscos operacionais (dependência de mercado ou clientes)
- oportunidades de melhoria em retenção e estratégia comercial
A análise tem caráter exploratório, mas orientado à geração de insights aplicáveis ao negócio.

**Fonte de dados:**
Dataset público disponível em:
https://archive.ics.uci.edu/ml/machine-learning-databases/00352/Online%20Retail.xlsx

O conjunto contém dados transacionais, incluindo:
InvoiceNo (pedido)
StockCode (produto)
Description (descrição)
Quantity (quantidade)
InvoiceDate (data)
UnitPrice (preço unitário)
CustomerID (cliente)
Country (país)
Sales (valor total da operação)

## 2. Arquivos do projeto
Este repositório contém os seguintes materiais:

- **Notebook (Jupyter):** apresenta as etapas de limpeza, tratamento e análise exploratória dos dados, com maior nível de detalhamento técnico.
- **Dashboard (Power BI):** reúne as principais visões de negócio, destacando padrões de receita, comportamento dos clientes e indicadores relevantes.
- **Imagem do Dashboard:** visualização demonstrativa do resultado final (mostrado abaixo).
- **README (PT-BR e EN):** documentação do projeto em português e inglês, permitindo melhor acessibilidade conforme a preferência do leitor.

![Dashboard](Dashboard_ecommerce.png)

## 3. Etapas do projeto
1. Extração
Os dados foram carregados diretamente do arquivo original e estruturados para análise em ambiente Python.
2. Transformação (Data Cleaning)
a) Valores ausentes
	- Description: removidos (baixa proporção)
	- CustomerID: mantidos (~25% ausentes), para evitar perda de volume relevante
b) Valores negativos
	- Mantidos, pois representam devoluções ou ajustes financeiros, afetando o resultado financeiro
c) Valores nulos (UnitPrice = 0)
	- Removidos por não representarem transações reais de venda
d) Padronização e filtragem
	- Remoção de descrições genéricas ou ambíguas
	- Exclusão de registros não relacionados diretamente a vendas (ex.: taxas operacionais)

## 4. Principais análises
a) Qualidade e estrutura dos dados
	- Separação entre vendas reais e registros administrativos
b) Receita e distribuição
	- Forte concentração de receita em poucos países
	- Reino Unido representa a maior parcela do faturamento
	- Indício de dependência geográfica relevante
c) Comportamento dos clientes
	- Grande parte dos clientes realiza apenas uma compra
	- Pequena parcela concentra a maior parte da receita
d) Recorrência vs Receita
	- Clientes recorrentes (alta frequência) representam pequena fração da base
	- Porém, geram mais de 50% da receita total
	- A retenção é mais valiosa do que aquisição massiva de novos clientes
e) Impacto de devoluções e ajustes
	- Segmentação de categoria de produto com maior taxa de devolução 
	- Devoluções e ajustes financeiros representam redução de 9,43% no faturamento líquido
	- Indica necessidade de monitoramento de perdas operacionais

## 5. Insights de negócio e contribuições
- Estratégias de retenção tendem a gerar mais retorno do que aquisição
- Clientes frequentes devem ser tratados como segmento estratégico
- Diversificação geográfica pode reduzir riscos
- Monitoramento de devoluções pode melhorar margem operacional

## 6. Tecnologias utilizadas
Python; Pandas; Matplotlib; DAX; Power BI; Power Query; ETL; Statistic; Data cleaning.

## 7. Próximos passos
- Modelagem de churn mais robusta (considerando maior período de tempo e perfis de compra)
- Segmentação de clientes (clusterização)
- Integração com dados de estoque/logística

## 8. Autor
Este projeto foi desenvolvido integralmente por mim, incluindo as etapas de limpeza, análise exploratória, interpretação dos dados e construção das visualizações.
