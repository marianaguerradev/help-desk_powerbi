# Projeto de Análise de Atendimentos Helpdesk com Power BI

## Visão Geral

Este projeto consiste na criação de um dashboard de Business Intelligence (BI) para a análise de dados de um Helpdesk. O objetivo principal é transformar dados brutos de ocorrências e informações de suporte em métricas de desempenho e visualizações acionáveis.

O relatório final permite o monitoramento do desempenho da equipe de suporte, a identificação de padrões e a detecção de tendências no volume e no tempo de resolução dos problemas (TMA - Tempo Médio de Atendimento). O desenvolvimento seguiu as etapas de análise, modelagem e visualização de dados.

## 📊 Estrutura e Tecnologia

* **Ferramenta Principal:** Power BI Desktop (`Relatorio_HelpDesk_SI.pbix`).
* **Modelo de Dados:** Utiliza um modelo dimensional (Schema Estrela) para relacionar as tabelas de dimensões (`dUsuario`, `dSuporte`, `dProblema`) com a tabela Fato (`fOcorrencias`).
* **Linguagem de Fórmulas:** DAX (Data Analysis Expressions) para a criação de métricas e indicadores.

## 📂 Fontes de Dados (Data Dictionary)

O projeto é alimentado por quatro arquivos CSV que simulam as bases de dados do Helpdesk:

| Tabela | Descrição | Colunas Chave (Exemplos) |
| :--- | :--- | :--- |
| **`fOcorrencias.csv`** | Registros detalhados de atendimentos (Tabela Fato principal). | `Data Chamado`, `ID Usuario`, `ID Suporte`, `ID Problema`, `Status`. |
| **`dUsuario.csv`** | Informações demográficas dos usuários que abriram os chamados (Dimensão). | `ID Usuario`, `Nome Usuario`, `Sexo`, `Data de inscrição`. |
| **`dSuporte.csv`** | Dados sobre os atendentes ou equipe de suporte (Dimensão). | `ID Suporte`, `Nome Cliente`, `Data de Nascimento`. |
| **`dProblema.csv`** | Categorias e tipos de problemas atendidos (Dimensão). | `ID problema`, `Problema` (e.g., "Conexão lenta", "Problema com login"). |

## 📐 Métricas Chave (Implementação em DAX)

O relatório calcula e exibe as seguintes métricas de desempenho:

* **Total de Ocorrências:** Contagem total de chamados na base.
* **Tempo Médio de Atendimento (TMA):** Média do tempo de atendimento (calculado entre a abertura e o encerramento do chamado).
* **Tempo Total de Atendimento por Atendente:** Soma do tempo de atendimento para avaliação da carga de trabalho e eficiência da equipe.

## 🖼️ Visualizações e Relatórios Principais

O dashboard está organizado em seções para facilitar a análise:

1.  **Dashboard de Atendimentos:** Contém cartões de resumo (KPIs) e gráficos de barras para visualizar a distribuição das **Ocorrências por Categoria de Problema**.
2.  **Desempenho por Atendente:** Tabela detalhada e gráficos comparativos do **Tempo Médio de Atendimento** e **Satisfação Média** (se aplicável nos dados) entre os membros da equipe de suporte.
3.  **Análise Temporal:** Gráfico de linha do tempo que permite verificar o **Volume de Atendimentos por Mês ou Semana**, sendo essencial para identificar sazonalidades e tendências.

## 🚀 Como Executar o Projeto

1.  **Clone o Repositório:** Baixe todos os arquivos para sua máquina local.
2.  **Instale o Power BI:** Certifique-se de ter o [Power BI Desktop](https://powerbi.microsoft.com/pt-br/desktop/) instalado.
3.  **Abra o Relatório:** Abra o arquivo `Relatorio_HelpDesk_SI (1).pbix`. O Power BI carregará automaticamente as fontes de dados CSV que devem estar na mesma pasta ou em um caminho configurado.
4.  **Explore:** Utilize os filtros e segmentações de dados para interagir com as visualizações.
