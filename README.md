# Projeto de Análise de Atendimentos Helpdesk com Power BI

## Visão Geral

Este projeto consiste na criação de um dashboard de Business Intelligence (BI) para a análise de dados de um Helpdesk. [cite_start]O objetivo principal é transformar dados brutos de ocorrências e informações de usuários, suporte e problemas em métricas de desempenho e visualizações acionáveis, conforme proposto pela **Fatec Guaratinguetá**[cite: 46903, 46904].

O relatório final permite monitorar o desempenho da equipe de suporte e identificar padrões e tendências no volume e no tempo de resolução dos problemas.

## 📊 Estrutura e Tecnologia

* [cite_start]**Ferramenta Principal:** Power BI[cite: 46913].
* [cite_start]**Modelo de Dados:** Utiliza um modelo dimensional (Schema Estrela) para relacionar as tabelas de dimensões (`dUsuario`, `dSuporte`, `dProblema`) com a tabela Fato (`fOcorrencias`)[cite: 46910, 46925].
* [cite_start]**Linguagem de Fórmulas:** DAX (Data Analysis Expressions)[cite: 46935].

## 📂 Fontes de Dados (Data Dictionary)

[cite_start]O projeto é alimentado por quatro arquivos CSV (simulando um Data Warehouse ou Data Mart)[cite: 46906]:

| Tabela | Descrição | Colunas Chave (Exemplos) |
| :--- | :--- | :--- |
| **`fOcorrencias`** | [cite_start]Registros de atendimentos e eventos (Tabela Fato)[cite: 46910, 46922]. | [cite_start]`Data Chamado`, `ID Usuario`, `ID Suporte`, `ID Problema`, `Status`[cite: 46978, 46980, 46981]. |
| **`dUsuario`** | [cite_start]Dimensão de informações dos usuários[cite: 46907]. | [cite_start]`ID Usuario`, `Nome Usuario`, `Sexo`, `Data de Nascimento`, `Data de inscrição`[cite: 50358]. |
| **`dSuporte`** | [cite_start]Dimensão de dados sobre os atendentes[cite: 46908]. | [cite_start]`ID Suporte`, `Nome Cliente`, `Sexo`, `Data de Nascimento`[cite: 50367]. |
| **`dProblema`** | [cite_start]Dimensão de categorias de problemas[cite: 46909]. | [cite_start]`ID problema`, `Problema` (e.g., "Conexão lenta", "Problema com login", "Tempo de resposta")[cite: 50368]. |

## 📐 Métricas Chave (DAX)

[cite_start]As seguintes métricas de negócios foram implementadas em DAX para a análise de desempenho[cite: 46935]:

* [cite_start]**Total de Ocorrências:** Contagem total de atendimentos na base[cite: 46944, 46958].
* [cite_start]**Tempo Médio de Atendimento (TMA):** Cálculo da média da diferença entre `Data_Abertura` e `Data_Encerramento`[cite: 46936, 46940].
* [cite_start]**Total de Ocorrências por Categoria:** Distribuição do volume de chamados por tipo de problema[cite: 46941].
* [cite_start]**Satisfação Média dos Atendimentos:** Média ponderada ou simples da coluna `Satisfacao` (se implementada)[cite: 46945, 46947, 46963].
* [cite_start]**Tempo Total de Atendimento por Atendente:** Soma do tempo de atendimento para avaliação da carga de trabalho e eficiência individual[cite: 46949, 46951].

## 🖼️ Visualizações e Relatórios

O projeto inclui relatórios que permitem uma navegação completa sobre os dados de Helpdesk:

1.  **Dashboard de Atendimentos:**
    * [cite_start]Cartões de resumo (KPIs) para o Tempo Médio de Atendimento e Número Total de Ocorrências[cite: 46956, 46957, 46958].
    * [cite_start]Gráfico de barras detalhando as **Ocorrências por Categoria de Problema**[cite: 46954].
2.  **Desempenho por Atendente:**
    * [cite_start]Tabela com o detalhe do número de atendimentos e o Tempo Médio de Atendimento por `ID Suporte`[cite: 46966].
    * [cite_start]Gráfico de barras para comparação da **Satisfação Média** entre os atendentes[cite: 46967].
3.  **Análise Temporal:**
    * [cite_start]Visualização de linha do tempo para identificar o **Volume de Atendimentos por Mês ou Semana**, fundamental para a detecção de sazonalidades ou picos atípicos[cite: 46969].

---

**Como Contribuir:**

Sinta-se à vontade para clonar o repositório e sugerir melhorias no modelo de dados, métricas DAX ou novas visualizações!
