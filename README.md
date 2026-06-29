# VAE2 — Estatísticas Públicas

Trabalho avaliativo para a disciplina **Estatísticas Públicas** (ENCE/UERJ).

## Estrutura do trabalho

Este projeto é dividido em **três partes integradas**, que formam uma narrativa coerente sobre informação pública, poluição de dados e evidência oficial.

### Parte 1: Análise de Matéria Jornalística

**Arquivo:** `VAE2.docx` (seção inicial)

Análise crítica de uma reportagem do Intercept Brasil intitulada *"A grande mídia é cúmplice da desinformação sobre o clima"* (25 de novembro de 2025).

**Conteúdo:**
- Identificação da fonte, veículo e data da publicação
- Resumo da mensagem principal e tópicos abordados
- Análise das fontes de dados utilizadas na reportagem
- Reflexão sobre a "lacuna de percepção" entre dados científicos reais e narrativas corporativas

**Conceito central:** A reportagem ilustra como a **poluição da informação** (*malinformation*) afeta o ecossistema de dados público, quando empresas financiam "publieditoriais" que confundem fatos científicos com marketing, reforçando a "era da pós-verdade".

---

### Parte 2: A Jornada de Agapito no Ecossistema de Dados Ambientais

**Arquivo:** `VAE2.docx` (segunda seção)

Uma narrativa em estrutura de jornada do herói sobre um pesquisador/empresário que descobre a realidade da desinformação ambiental e muda sua abordagem.

**Personagem:** Agapito de Antunes, 33 anos
- Pesquisador focado em áreas ambientais
- Diretor de produto de uma startup de preservação oceânica (inspirada na Infinito Maré)
- Usuário crítico e assíduo de estatísticas públicas

**Estrutura narrativa:**
1. **Apresentação** — Agapito busca dados confiáveis sobre resíduos marinhos
2. **Desenvolvimento** — Esbarra em confusão informacional; descobre a reportagem sobre mídia e negacionismo climático
3. **Clímax** — Percebe que publieditoriais e campanhas corporativas inflam narrativas falsas de sustentabilidade
4. **Desfecho** — Em vez de sucumbir ao cinismo, mergulha em fontes primárias oficiais (IBGE, bancos de dados públicos)

**Moral da história:** A cadeia de valor do dado só atinge pleno potencial quando a informação é criticamente filtrada e transformada em ação prática. O letramento de dados é essencial não só para cidadãos, mas principalmente para profissionais de mídia, que devem ser guardiões da integridade informacional.

---

### Parte 3: Indo além da mídia — O que os dados oficiais do IBGE revelam sobre resíduos sólidos industriais

**Arquivo:** `VAE2_Parte3.Rmd`

Relatório técnico em R Markdown que reproduz, na prática, o movimento de Agapito: abandonar o ruído midiático e ir direto às fontes primárias oficiais.

**Dados utilizados:**
- **Tabela 2064 (IBGE/PNSB/SIDRA)** — Número de municípios que coletam resíduos sólidos industriais perigosos e/ou não-inertes; quantidade coletada (toneladas/dia). Referência: 2008.
- **Tabela 1241 (IBGE/PNSB/SIDRA)** — Total de municípios por Grande Região e UF (2000 e 2008). Usada como denominador para calcular taxa de cobertura.

**Análise:**
1. Importação e limpeza de dados do SIDRA (tratamento de cabeçalhos, códigos de valor ausente)
2. Classificação de linhas por hierarquia geográfica (Brasil → Região → UF → Município)
3. Construção de painel integrado com cálculo de cobertura (% de municípios com coleta)
4. Visualizações:
   - Cobertura por Grande Região
   - Cobertura por Unidade da Federação
   - Concentração de volume coletado
5. Discussão de achados: apenas 2,4% dos municípios brasileiros tinham algum serviço formal de coleta de resíduos perigosos em 2008; 8 UFs registraram zero municípios; São Paulo e Paraná concentram ~92,6% de todo o volume coletado

**Tecnologia:** R + tidyverse + ggplot2, seguindo o padrão de caminhos portáteis com `here::here()`.

---

## Como usar este trabalho

### Estrutura de arquivos

```
.
├── README.md                          # Este arquivo
├── VAE2.docx                          # Partes 1 e 2 (documento Word)
├── VAE2_Parte3.Rmd                    # Parte 3 (relatório R Markdown)
├── tabela2064.xlsx                    # Dados: IBGE/PNSB — resíduos industriais
├── tabela1241.xlsx                    # Dados: IBGE/PNSB — total de municípios
└── .Rproj                             # Projeto RStudio (opcional)
```

### Rodar a Parte 3 em R

**Pré-requisitos:**
- R 4.0+ com RStudio
- Pacotes: `here`, `readxl`, `dplyr`, `stringr`, `tidyr`, `ggplot2`, `knitr`

**Instalação de pacotes:**
```r
install.packages(c("here", "readxl", "dplyr", "stringr", "tidyr", "ggplot2", "knitr"))
```

**Para rodar o arquivo:**

1. Abra `VAE2_Parte3.Rmd` no RStudio
2. Certifique-se de que `tabela2064.xlsx` e `tabela1241.xlsx` estão na mesma pasta do projeto
3. Clique em **Knit** (ou pressione `Ctrl + Shift + K` / `Cmd + Shift + K`)
4. O relatório será gerado em HTML com tabelas, gráficos e discussão integrados

**Saída esperada:**
- Arquivo HTML interativo com:
  - Tabelas de cobertura por Brasil/Região/UF
  - 3 gráficos (ggplot2)
  - Discussão textual ligando os dados às Partes 1 e 2
  - Referências bibliográficas

---

## Contexto acadêmico

**Disciplina:** Estatísticas Públicas  
**Instituição:** ENCE (Escola Nacional de Ciências Estatísticas)  
**Período:** 2026  

### Conceitos-chave abordados

1. **Poluição da Informação** (*malinformation*) — Informação que pode conter bases reais, mas é manipulada para causar danos ou distorcer fatos.

2. **Lacuna de Percepção** — A distância entre o que os dados realmente mostram e o que o público acredita que mostram, frequentemente amplificada por narrativas corporativas.

3. **Letramento de Dados** — Capacidade de compreender, interpretar, criar e comunicar dados como parte de leitura, escrita e aritmética. Essencial em profissionais de mídia e formuladores de política pública.

4. **Ecossistema de Dados Público** — O conjunto de instituições (IBGE, agências governamentais, imprensa, academia), plataformas (SIDRA, repositórios) e normas que governam a coleta, tratamento e disseminação de informação oficial.

5. **Fonte Primária vs. Secundária** — A importância de ir direto aos dados originais do IBGE/SIDRA, em vez de depender de interpretações jornalísticas.

---

## Dados utilizados

### Tabela 2064 — IBGE/PNSB (SIDRA)

**Título completo:** Número de municípios que coletam resíduos sólidos industriais perigosos e/ou não-inertes e quantidade coletada de resíduos sólidos industriais perigosos e/ou não-inertes

**Link no SIDRA:** https://sidra.ibge.gov.br/tabela/2064

**Ano de referência:** 2008

**Abas da planilha:**
- **Aba 1** — Número de municípios (unidades)
- **Aba 2** — Quantidade coletada (toneladas/dia)
- **Aba 3** — Notas e legenda de códigos (-, .., X, A-Z)

**Cobertura geográfica:** Brasil, Grandes Regiões, UFs, municípios e regiões metropolitanas

**Observações:** O caractere "-" significa "zero absoluto" (não existe coleta naquele lugar); ".." significa "não aplicável" ou "não disponível".

---

### Tabela 1241 — IBGE/PNSB (SIDRA)

**Título completo:** Número de municípios, total e os com manejo de resíduos sólidos, por situação da coleta seletiva no município

**Link no SIDRA:** https://sidra.ibge.gov.br/tabela/1241

**Anos de referência:** 2000 e 2008

**Abas da planilha:**
- **Aba "Tabela 1"** — Total geral de municípios
- **Aba "Tabela 2"** — Percentual de cobertura (%) — *não usada neste trabalho*
- **Aba "Notas"** — Legenda

**Uso neste trabalho:** Usada como denominador para calcular a taxa de cobertura (% de municípios com coleta formal de resíduos perigosos em relação ao total de municípios existentes).

---

## Principais achados

| Indicador | Valor |
|-----------|-------|
| **Municípios com coleta (2008)** | 136 de 5.564 (2,4%) |
| **Cobertura por Grande Região** | Sudeste lidera com ~3,9%; Centro-Oeste tem menor com ~1,5% |
| **UFs com zero municípios** | 8 (Rondônia, Acre, Amazonas, Roraima, Amapá, RN, MS, DF) |
| **Concentração SP + PR** | ~92,6% de toda a tonelagem coletada no país |
| **Quantidade coletada (Brasil)** | 3.444 ton/dia |

---

## Interpretação integrada

As três partes trabalham juntas para illustrar um argumento coerente:

1. **Parte 1** identifica um problema real: a mídia corporativa amplifica narrativas enganosas sobre sustentabilidade.

2. **Parte 2** personifica a resposta: quando alguém descobre esse problema, a solução não é imobilismo ou cinismo, mas **ir direto às fontes primárias** de dado oficial.

3. **Parte 3** materializa essa solução: usando R e dados do IBGE, revelamos que a infraestrutura formal de tratamento de resíduos perigosos no Brasil é mínima (2,4%) e geograficamente extremamente concentrada — exatamente o tipo de assimetria que os publieditoriais corporativos não mencionam, mas que fica óbvia quando se trabalha com dados públicos confiáveis.

**Conclusão:** Letramento de dados não é luxo — é essencial para qualquer pessoa que queira entender o Brasil além de narrativas corporativas.

---

## Referências

### Fontes do trabalho

- **IBGE.** Pesquisa Nacional de Saneamento Básico (PNSB) — 2008. Sistema IBGE de Recuperação Automática (SIDRA).
  - Tabela 2064: https://sidra.ibge.gov.br/tabela/2064
  - Tabela 1241: https://sidra.ibge.gov.br/tabela/1241

- **Intercept Brasil.** "A grande mídia é cúmplice da desinformação sobre o clima." 25 de novembro de 2025.
  - https://www.intercept.com.br/2025/11/25/grande-midia-clima-negacionismo/

### Leitura recomendada (contexto)

- **Kitchin, R.; Lauriault, T. P.** (2014). Small data in the era of big data. *GeoJournal*, 80(4), 463-475.
  - Sobre a importância de dados pequenos, contextualizados e criticamente interpretados.

- **D'Ignazio, C.; Klein, L. F.** (2020). *Data Feminism*. MIT Press.
  - Capítulos sobre poder, representação e responsabilidade na comunicação de dados.

- **Kitchin, R.** (2017). *The Data Revolution: Big Data, Open Data, Data Infrastructures and Their Consequences*. SAGE Publications.
  - Sobre ecossistemas de dados e governança de informação pública.

---

## Autor

**Cadu**  
Estudante de Estatística (ENCE/UERJ) — 5º semestre  
Complementação em Tecnologia de Banco de Dados  
Rio de Janeiro, 2026

---

## Notas de implementação

### Por que R Markdown para a Parte 3?

A escolha de R Markdown (em vez de, por exemplo, uma apresentação em Powerpoint ou um arquivo Word) reflete um princípio central do trabalho: **reprodutibilidade e transparência**. Um `.Rmd` permite que qualquer pessoa:

- Veja exatamente como os dados foram importados, limpos e analisados
- Rode os chunks de novo e obtenha os mesmos resultados
- Modifique os parâmetros (ex.: usar dados de um ano diferente) sem refazer a análise toda

Isso é o oposto da opacidade dos publieditoriais corporativos criticados na Parte 1.

### Convenções técnicas

- **Caminhos de arquivo portáteis:** Usamos `here::here()` para garantir que o código funcione em qualquer máquina, independente de estrutura de pastas.
- **Nomenclatura de variáveis em português:** Mantém coerência com o texto do trabalho e respeita a língua de trabalho da disciplina.
- **Sem hardcodes:** Todos os números mostrados são calculados por fórmulas do R, nunca digitados manualmente, evitando erros de transcription.

---

## Contato e feedback

Dúvidas sobre o código ou a análise? Considere:

1. Consultar a documentação de cada pacote R:
   - `?readxl::read_excel`
   - `?dplyr::left_join`
   - `?ggplot2::ggplot`

2. Acessar a documentação do SIDRA/IBGE diretamente: https://sidra.ibge.gov.br

3. Revisar as "Notas" nas abas das planilhas SIDRA, que explicam os códigos de valor ausente e outras legendas.

---

**Última atualização:** 29 de junho de 2026
