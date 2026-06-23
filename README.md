# Trabalho 2 – Estatística Computacional I

## Descrição

Análise estatística completa de dados da PNAD Contínua (4º trimestre de 2025) focando em rendimento, escolaridade, gênero e faixa etária, com regressão linear simples e múltipla, diagnóstico de resíduos e previsões de séries temporais.

## Estrutura

- **Parte 1:** Análise descritiva — estatísticas por gênero e faixa etária, visualizações com boxplots
- **Parte 2:** Inferência — teste qui-quadrado, regressão linear simples (rendimento × escolaridade), diagnóstico de resíduos
- **Parte 3:** Modelos log-nível e regressão múltipla — transformação para contornar heterocedasticidade, inclusão de gênero e idade
- **Parte 4:** Séries temporais — decomposição (aditiva/multiplicativa) de três séries e previsão de 12 meses para PMC

## Arquivos

```
analise_pnad_corrigido.Rmd      # Relatório R Markdown consolidado (Partes 1–4)
serie_co2.csv                   # CO2 mensal, Mauna Loa (1959–1997)
Tabela_8880.xlsx                # PMC - Índice de Volume de Vendas (2000–2026)
Venda_Semanal_One_Piece.xlsx    # Vendas semanais do mangá One Piece (2009–2025)
README.md                        # Este arquivo
```

## Como rodar

1. Abra `analise_pnad_corrigido.Rmd` no RStudio
2. Certifique-se de que os três arquivos de dados estão na **mesma pasta** do projeto (onde está o `.Rmd`)
3. Instale os pacotes (se necessário):
   ```r
   install.packages(c("PNADcIBGE", "srvyr", "dplyr", "summarytools", 
                      "stargazer", "lmtest", "ggplot2", "readxl", 
                      "here", "forecast"))
   ```
4. Rode cada chunk ou clique **Knit** para gerar o relatório HTML completo

## Prazos e Entregas

- **Parte 1:** 4 de junho (parcial: 2 de junho)
- **Parte 2:** 11 de junho (parcial: 9 de junho)
- **Parte 3:** 18 de junho
- **Parte 4:** 2 de julho (impressa, presencial)

**Entrega final consolidada:** Relatório impresso em papel, em aula no dia 2 de julho.

## Principais Descobertas

- **Gênero:** disparidade salarial estrutural — mediana e 3º quartil da população masculina acima da feminina
- **Faixa etária:** renda aumenta das faixas mais jovens para 36–50 anos, estabilizando depois
- **Escolaridade:** relação significativa com rendimento (p < 0,01); cada ano adicional de estudo impacta positivamente
- **Log-Nível:** transformação logarítmica melhora ajuste e reduz heterocedasticidade
- **Séries temporais:** CO2 (aditiva), PMC (multiplicativa), One Piece (multiplicativa com ciclo de ~13 semanas, não anual)

## Contato/Notas

Trabalho realizado para a disciplina **Estatística Computacional I**, Professor Eduardo Campos, UERJ/ENCE.

Entrega: julho de 2026.
