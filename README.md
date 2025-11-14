# Desafio_Santander_Explorando_IA_Generativa_em_um_pipeline_de_ETL_com_Python

Desafio de projeto para o Bootcamp Santander 2025 - Ciência de Dados com Python 2° Semestre/2025



# 🏦 Cenário de Negócio – Banco Do Ricardo

**Banco do Ricardo**, uma instituição financeira sólida, com uma vasta base de clientes espalhada por todo o país. 

Atualmente, muitos dos clientes do banco ainda não contrataram seguros. Alguns já têm seguro de vida, outros têm seguro automóvel, e há até quem tenha seguro do cartão de crédito. Mas a maioria nunca foi abordada com uma oferta verdadeiramente personalizada.

## 🎯 Objetivos

- Identificar o **seguro ideal** para cada cliente com base em idade, renda, saldo e comportamento.
- Enriquecer o dataset com **regras de negócio reais** do contexto bancário.
- Criar **prompts automáticos** para o Microsoft Copilot gerar mensagens personalizadas.
- Definir **prioridade comercial** das ofertas.
- Incluir instruções de **canal de envio** (App, WhatsApp, E-mail, Agência).
- Gerar automaticamente:
  - 📄 CSV detalhado  
  - 📄 CSV de resumo  
  - 🗂 Banco SQLite  
  - 📊 Excel (.xlsx)  
  - 🖼 Apresentação PPTX
 
## Deixa eu te explicar rapidinho como executar o projeto ▶️:

## ▶️ Como executar

Na raiz do projeto, rode:

python etl_banco_do_ricardo.py

O script vai:
- Ler data/raw/clientes_banco_ricardo.csv
- Gerar arquivos em data/processed/
- Criar (ou sobrescrever) o banco SQLite data/banco_do_ricardo_seguros.db
- Gerar um Excel .xlsx
- Gerar uma apresentação .pptx

📦 requirements

1. pandas
2. xlsxwriter
3. python-pptx


## 🧱 Arquitetura do Pipeline ETL

O pipeline segue o fluxo:

📁 CSV bruto → 🧼 Transformações → 🧠 Enriquecimento → 📤 Carga Final

### 🔵 **Extract**
- Leitura do CSV dos clientes.
- Conversão de tipos numéricos (idade, renda, saldo).

### 🟢 **Transform**
- Classificação da faixa de renda.
- Algoritmo de recomendação de seguros.
- Definição de prioridade comercial.
- Geração do `prompt_copilot` para criação automática de mensagens pelo MS Copilot.
- Criação do campo `instrucao_envio` simulando o envio do contato.

### 🟠 **Load**
Geração automática de:

- **CSV detalhado** com todas as colunas enriquecidas.
- **CSV resumo** com agregados.
- **SQLite** com tabelas normalizadas.
- **Excel (.xlsx)** com abas:
  - `Clientes`
  - `Resumo_Seguros`
- **Apresentação PPTX** contendo:
  - Slide de título  
  - Slide com visão geral do pipeline  
  - Slide com tabela resumo  

Todos os artefatos são armazenados em:

data/processed/

## 🤖 Personalização das Mensagens com Microsoft Copilot

Este projeto **não usa API externa de IA**.

Em vez disso, o pipeline cria automaticamente um prompt configurado para cada cliente:

- Dados pessoais
- Renda
- Faixa de renda
- Seguro recomendado
- Prioridade
- Canal preferido

O Copilot utiliza esses prompts para escrever **mensagens comerciais personalizadas** no Excel.

Outra sugestão não implementada por motivos didaticos foi o envio da mensagem personalizada para o canal favorito do cliente.

Este repositório contém:

- 🧠 Modelos de recomendação e segmentação;
- 🗃️ Dados de exemplo (anonimizados);
- ⚙️ Lógica de recomendação personalizada;
- 📄 Exemplos de textos prontos para envio.

🚀 Vamos transformar dados em confiança. E confiança em proteção.

##### Todos os dados, Nomes de empresa e Clientes são ficticios, houve uso de IA para formulação do material. 


