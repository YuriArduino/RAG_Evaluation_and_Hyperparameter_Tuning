# RAG_Evaluation_and_Hyperparameter_Tuning - Optimization Framework
LLM Grounding Leads to More Accurate Contextual Responses -  studies and tests, searching for the best metrics


Um framework completo em Python para **avaliar, comparar e otimizar cientificamente** as estratégias de `Retrieval` em pipelines de RAG (Retrieval-Augmented Generation), utilizando o próprio LLM para gerar o "ground truth".

---

## A Jornada: De um Exercício de RAG a um Laboratório de MLOps

O que começou como um exercício da Aula 2 da Imersão Dev (Agentes de IA) da Alura, rapidamente se transformou em uma pergunta muito mais profunda: **como podemos medir, otimizar e, acima de tudo, confiar nos resultados de um sistema de RAG?**

Este repositório é a resposta a essa pergunta. Ele documenta a jornada de refatoração de um script simples para uma arquitetura de software modular e testável, culminando em um verdadeiro **laboratório de MLOps para RAG**.

## O Problema Resolvido

A performance de um sistema RAG é extremamente sensível a hiperparâmetros como `chunk_size` e `chunk_overlap`. Escolhas ruins podem levar a:
- **Fragmentação de Contexto:** Chunks pequenos que perdem o sentido.
- **Diluição de Informação:** Chunks grandes que escondem a resposta em meio a ruído.
- **Alucinações:** O LLM inventa respostas quando o retriever falha.

Este framework foi projetado para substituir a intuição por **dados**, permitindo uma tomada de decisão de engenharia baseada em evidências.

## ✨ Features

-   🧠 **`LLM-derived Ground Truth`:** Usa o Gemini para analisar todos os chunks e criar um "gabarito" objetivo de relevância, eliminando a necessidade de anotação manual.
-   🔬 **Benchmarking Automatizado:** Compara sistematicamente múltiplas estratégias de chunking contra um conjunto de perguntas de teste.
-   ⚖️ **Métricas Avançadas:** Calcula automaticamente `Precision`, `Recall`, `F1-Score` e `Precision@K` para cada estratégia, fornecendo uma visão completa da performance.
-   🏛️ **Arquitetura SOLID:** O código é dividido em 15 células modulares, com classes especialistas (`RelevanceEvaluator`, `MetricsCalculator`, etc.) que seguem o Princípio da Responsabilidade Única.
-   💾 **Cache Persistente:** Salva os resultados de experimentos caros em disco, permitindo a re-análise instantânea e economizando tempo e custos de API.
-   📊 **Visualização de Resultados:** Gera um `heatmap` e uma tabela de performance agregada para uma interpretação visual e clara dos resultados.

---

## 📸 Demonstração dos Resultados

O framework executa os experimentos e gera um dashboard visual para comparar a performance (medida pelo F1-Score) de cada estratégia em todo o conjunto de testes.

![Heatmap de Performance das Estratégias](https://github.com/YuriArduino/RAG_Evaluation_and_Hyperparameter_Tuning/blob/notebook(colab)/Resultado%20dos%20testes%203.png)

---

## 💻 Como Usar

O projeto está estruturado como um notebook Jupyter (`.ipynb`).

1.  Abra o arquivo `RAG_Evaluation_and_Hyperparameter_Tuning_v2.ipynb` no Google Colab, VS Code, ou Jupyter Lab.
2.  Adicione sua `GEMINI_API_KEY` aos segredos do ambiente (no Colab, clique no ícone de chave 🔑).
3.  Execute as células em ordem, de cima para baixo. A célula final (`main()`) orquestra todo o pipeline de análise.

Os parâmetros do experimento, como as estratégias de chunking e as perguntas de teste, podem ser facilmente modificados na célula de execução principal para se adequarem a novos documentos ou casos de uso.

---

## 📜 Licença
Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

```
