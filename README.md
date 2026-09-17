# 📊 Simulador de Investimentos em Fundos Imobiliários (FIIs) - Versão Pro 🥤

> **Projeto desenvolvido para o Desafio de Laboratório de Excel do Bootcamp DIO (Digital Innovation One) em parceria com o Grupo HEINEKEN.**

---

## 🏛️ Origem do Conteúdo e Contexto do Desafio

Este repositório é fruto da jornada de aprendizado no **Bootcamp Inteligência Artificial Aplicada a Vendas**, realizado pela [Digital Innovation One (DIO)](https://dio.me) em parceria com o **Grupo HEINEKEN**.

### 1. 🎯 O Desafio de Negócio (Grupo HEINEKEN / Marca FYS)
Durante o bootcamp, os especialistas do Grupo HEINEKEN compartilharam os desafios reais de Trade Marketing para a marca de refrigerantes **FYS** (*"Menos marketing, mais sabor"*). A marca busca otimizar a presença no subcanal de **padarias**, onde o volume de vendas tem alto potencial, mas enfrenta desafios logísticos e de visibilidade nos pontos de venda (PDV).

### 2. 🧮 O Desafio Prático de Excel (Simulador de Investimentos em FIIs)
Para fortalecer a capacidade analítica e o domínio de planilhas financeiras dos participantes, a DIO propôs o desenvolvimento de uma ferramenta prática de simulação de investimentos em **Fundos Imobiliários (FIIs)**. 

O objetivo do laboratório é responder às dúvidas centrais de qualquer investidor:
- *Quanto investir por mês?*
- *Por quanto tempo manter os aportes?*
- *Qual o retorno acumulado e a renda mensal de dividendos?*
- *Como distribuir o capital entre diferentes tipos de FIIs de acordo com o perfil de risco?*

### 3. 🚀 Da Planilha Base à Versão Pro
- **Planilha Base (`Desafio Excel.xlsx`)**: Arquivo de partida fornecido no curso com a estrutura inicial de simulação de juros compostos.
- **Especificações (`Desafio Excel.docx`)**: Diretrizes da DIO exigindo a criação de um repositório público no GitHub com documentação detalhada.
- **Evolução Pro (`Simulador_Investimentos_FIIs_Pro.xlsx`)**: Versão avançada desenvolvida com o auxílio do agente de IA em **Dark Mode Azul/Grafite**, adicionando a variável de **correção da inflação (IPCA) ano a ano**, métricas de **efeito bola de neve** e **painel interativo de alocação por perfil**.

---

## 🎨 Destaques Visuais e de Design (Dark Mode Fintech)

- **Tema Dark Mode Azul / Grafite**: Interface escura elegante baseada nos tons `#0F172A` (Slate Dark), `#1E293B` (Card Slate) e destaques visuais em Ciano (`#38BDF8`), Verde Esmeralda (`#4ADE80`) e Dourado (`#FACC15`).
- **Cartões de KPI (Key Performance Indicators)**: 4 cartões no topo da planilha para visualização instantânea de:
  1. *Aporte Mensal Inicial*
  2. *Patrimônio Estimado (5 Anos)*
  3. *Lucro de Juros Compostos (Ganho em R$)*
  4. *Renda Mensal Passiva (Dividendos em R$/mês)*
- **Gráficos Dinâmicos Integrados**:
  - **Evolução Patrimonial**: Comparativo de *Total Investido vs. Patrimônio Final com Juros*.
  - **Alocação por Perfil**: Rosca (*Donut Chart*) com a distribuição percentual por categoria de FII.

---

## ⚙️ Funcionalidades e Fórmulas Financeiras

### 1. 🧮 Simulação de Juros Compostos e Renda Passiva
- **Patrimônio Acumulado (VF)**: Utiliza a fórmula de Valor Futuro `=VF(taxa; nper; -pgto)` para prever a evolução do capital no tempo.
- **Renda Mensal Estimada**: Calcula os dividendos gerados com base no *Dividend Yield (DY)* médio mensal da carteira selecionada:
  $$\text{Dividendo Mensal} = \text{Patrimônio Acumulado} \times \text{DY Mensal}$$
- **Efeito Bola de Neve (Snowball Effect)**: Exibe a quantidade de novas cotas de FIIs (considerando valor médio de R$ 100/cota) que os próprios dividendos conseguem comprar mensalmente sem necessidade de novos aportes do bolso.

### 2. 📈 Reajuste de Inflação Ano a Ano (IPCA)
Diferente dos simuladores tradicionais com aportes fixos, a versão Pro considera que o investidor reajustará seu aporte mensal anualmente para acompanhar a inflação estimada (ex: IPCA 4,5% a.a.):
$$\text{Aporte}_{\text{Ano } t} = \text{Aporte Inicial} \times (1 + \text{IPCA})^t$$

### 3. 🧱 Alocação Inteligente por Perfil de Investidor
Matriz de alocação de carteira dividida em **6 segmentos imobiliários**:
1. **PAPEL**: Certificados de Recebíveis Imobiliários (CRI).
2. **TIJOLO**: Shopping Centers, Galpões Logísticos, Lajes Corporativas.
3. **HÍBRIDOS**: Combinação de ativos de Tijolo e Papel.
4. **FOFs**: Fundos de Fundos Imobiliários.
5. **DESENVOLVIMENTO**: Empreendimentos de Construção e Incorporação.
6. **HOTELARIAS**: Empreendimentos Hoteleiros e Flats.

- **Fórmula de Busca Dinâmica**: Utiliza `=PROCV` tratada com `=SEERRO` apontando para a aba `Matriz_Alocacao`, ajustando os percentuais automaticamente conforme o perfil selecionado (`Conservador`, `Moderado` ou `Agressivo`).

---

## 📊 Matriz Comparativa de Projeção Temporal

| Prazo | Meses | Aporte Mensal Reajustado | Total Investido (Do Bolso) | Total Investido (Com Inflação) | Patrimônio Acumulado (VF) | Lucro dos Juros (R$) | Dividendo Mensal (R$/mês) | Cotas Novas Geradas/mês |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **2 Anos** | 24 | R$ 218,41 | R$ 4.800,00 | R$ 5.021,53 | **R$ 5.445,53** | R$ 645,53 | R$ 32,67 | 0 cotas |
| **5 Anos** | 60 | R$ 249,24 | R$ 12.000,00 | R$ 13.129,74 | **R$ 16.755,38** | R$ 4.755,38 | R$ 100,53 | **1 cota/mês** *(Bola de Neve)* |
| **10 Anos**| 120 | R$ 310,59 | R$ 24.000,00 | R$ 29.491,48 | **R$ 48.656,84** | R$ 24.656,84 | R$ 291,94 | **2 cotas/mês** |
| **20 Anos**| 240 | R$ 482,34 | R$ 48.000,00 | R$ 75.302,28 | **R$ 225.039,68** | R$ 177.039,68 | R$ 1.350,24 | **13 cotas/mês** |
| **30 Anos**| 360 | R$ 748,97 | R$ 72.000,00 | R$ 146.643,51 | **R$ 864.433,93** | R$ 792.433,93 | R$ 5.186,60 | **51 cotas/mês** |

---

## 📂 Estrutura do Repositório

```text
.
├── Simulador_Investimentos_FIIs_Pro.xlsx   # Planilha final otimizada em Dark Mode com Inflação
├── Desafio Excel.xlsx                      # Planilha original fornecida como base pela DIO
├── Desafio Excel.docx                      # Especificação técnica do laboratório DIO
└── README.md                               # Documentação completa do projeto e origem dos dados
```

---

## 🚀 Como Utilizar o Simulador

1. Abra o arquivo **`Simulador_Investimentos_FIIs_Pro.xlsx`** no Microsoft Excel (2016 ou superior).
2. Na aba **`Simulador FIIs`**, navegue até a seção **`1. PARÂMETROS DA SIMULAÇÃO`**:
   - Ajuste o seu **Salário Mensal** e o **Aporte Mensal Praticado** (célula destacada em Azul Ciano).
   - Defina a **Taxa de Inflação Estimada (IPCA)** e a **Taxa de Rendimento Mensal dos FIIs**.
3. Na seção **`3. ESTRATÉGIA DE ALOCAÇÃO`**:
   - Clique na célula **C34** (Perfil Selecionado) e escolha entre `Conservador`, `Moderado` ou `Agressivo` na **Lista Suspensa**.
   - A tabela recalculará instantaneamente o valor em R$ alocado para cada segmento de FII.

---

## 👨‍💻 Autor & Agradecimentos

- **Autor**: Enrico
- **Plataforma**: [Digital Innovation One (DIO)](https://dio.me)
- **Parceiro Institucional**: Grupo HEINEKEN / Marca FYS

---
*Fim da Documentação.*
