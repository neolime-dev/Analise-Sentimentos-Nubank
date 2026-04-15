# Análise de Sentimentos — Avaliações do Nubank no Google Play Store

> **Atividade Avaliativa 03 — Análise de Sentimentos Baseada em Regras** 
> **Disciplina:** Tópicos Avançados em Ciência de Dados e Inteligência Artificial 
> **Professor:** Alexandre Vaz Roriz 
> **Instituto:** IESB — Instituto de Educação Superior de Brasília

---

## Objetivo

Análise de sentimentos baseada em regras sobre **3.000 avaliações do Nubank** extraídas do Google Play Store, utilizando as bibliotecas **VADER** e **TextBlob**.

## O que está no notebook

| Seção | Descrição |
|-------|-----------|
| Imports & Config | Bibliotecas, paleta de cores, estilos |
| Extração de Dados | `google-play-scraper` — 3.000 avaliações |
| Pré-processamento | Limpeza, features de texto, extração de versão |
| VADER + TextBlob | Cálculo de scores e classificação |
| Requisito Mínimo | Contagem de sentimentos positivo/neutro/negativo |
| Distribuição de Notas | Histograma e pizza das 1–5 estrelas |
| Análise por Versão | Notas da versão atual vs versões anteriores |
| Curtidas × Nota | Violin plot e médias — engajamento por sentimento |
| Tamanho × Nota | Quem escreve mais? Usuários satisfeitos ou não? |
| Sentimento × Nota | Matriz de concordância + correlação de Pearson |
| WordClouds | Palavras mais usadas em avaliações positivas e negativas |
| Série Temporal | Evolução mensal do sentimento vs nota média |
| Subjetividade | Análise TextBlob: polaridade × subjetividade |
| Conclusões | Síntese e tabela comparativa VADER vs TextBlob |

## Como executar

```bash
# Instalar dependências
pip install google-play-scraper vaderSentiment textblob wordcloud langdetect jupyter

# Executar o notebook
jupyter notebook analise_sentimentos_nubank.ipynb
```

## Dependências

```
google-play-scraper
vaderSentiment
textblob
wordcloud
langdetect
pandas
numpy
matplotlib
seaborn
scikit-learn
nltk
```

## Principais Resultados

- **VADER**: classifica avaliações em positivo/neutro/negativo com **correlação de Pearson** significativa com as notas dos usuários
- **Avaliações negativas** recebem mais curtidas (validação coletiva de insatisfação)
- **Usuários insatisfeitos** escrevem textos mais longos (mais caracteres em média nas notas 1)
- **Versão atual vs anteriores**: análise comparativa de nota média e sentimento por versão

## Limitação

VADER e TextBlob foram treinados primariamente em inglês. Para textos em português, a acurácia é reduzida (~40–60% de concordância com a nota). Para análise em produção, recomenda-se **BERT-pt** ou modelos multilíngues.

---
*Análise realizada com dados públicos do Google Play Store via `google-play-scraper`*
