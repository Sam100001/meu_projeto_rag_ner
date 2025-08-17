# 🏛️ Projeto NER Jurídico com LLMs

Este repositório implementa a **extração de entidades nomeadas (NER)** em textos jurídicos utilizando **Large Language Models (LLMs)** em conjunto com **LangChain** e FAISS.  

Foram aplicadas três técnicas de *prompt engineering*:
- **Zero-shot**  
- **One-shot**  
- **Few-shot**  

---

## 📂 Estrutura do Código

- **`main.py`**  
  Script principal que coordena os experimentos.  
  - Carrega os dados de entrada.  
  - Executa as três abordagens (Zero-shot, One-shot, Few-shot).  
  - Salva os resultados em `results/`.

- **`mistral_ner.py`**  
  Responsável por chamar a API da **Mistral AI** para realizar a extração de entidades.  
  - Implementa funções específicas para cada técnica (zero, one e few-shot).  

- **`retriever.py`**  
  Implementa a recuperação de contexto com **FAISS + LangChain**.  
  - Divide documentos longos em chunks.  
  - Cria embeddings vetoriais.  
  - Recupera trechos relevantes para apoiar a extração de entidades.

- **`data/`**  
  Pasta de dados de entrada.  
  - `acordao.txt`: exemplo de decisão judicial usada para teste.  
  - `gabarito_entidades.json`: conjunto anotado manualmente (gabarito para avaliação).  

- **`results/`**  
  Resultados gerados pelo código.  
  - `avaliador.py`: métricas (precisão, recall e F1-score).  

---

## ▶️ Como Executar

1. Configure as dependências (via `requirements.txt` ou `poetry install`).  
2. Adicione sua chave de API da Mistral em um arquivo `.env`:  
