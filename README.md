# 🚀 Tech Challenge - Fine-Tuning de Foundation Model

**Aluno:** Vinícius Oliveira Litran Andrade  
**Instituição:** FIAP - Pós-graduação em Inteligência Artificial  (IA para Devs)

---

## 📜 Descrição do Projeto

Este projeto consiste na aplicação de **fine-tuning de um modelo de linguagem** utilizando o dataset **AmazonTitles-1.3MM**, que contém títulos e descrições de produtos da Amazon.

O objetivo é treinar o modelo para que, ao receber uma pergunta baseada no título de um produto, ele consiga gerar uma resposta coerente com base na descrição aprendida durante o treinamento.

---

## 🔥 Justificativa do Modelo

O desafio sugere o uso de foundation models como **Llama**, **Mistral** ou **BERT**.  
Contudo, devido a limitações de hardware local, o modelo utilizado foi o **DistilGPT-2**, uma versão leve e otimizada do GPT-2.

Essa escolha permite realizar o fine-tuning e a geração de respostas de forma eficiente, sem comprometer a demonstração dos conceitos e práticas fundamentais do desafio.

---

## 🗂️ Estrutura do Projeto

├── LF-Amazon-1.3M/ # Dataset (trn.json) 🔗 [LF-Amazon-1.3M](https://drive.google.com/file/d/12zH4mL2RX8iSvH0VCNnd3QxO4DzuHWnK/view) 

├── fine_tune_data.csv # Dados preparados para o treino

├── fine_tuned_model/ # Modelo treinado

├── tech_challenge.ipynb # Notebook com todo o código

├── README.md # Documentação do projeto

---

## ⚙️ Pipeline do Projeto

### 🔹 1. Pré-processamento dos Dados
- Leitura do arquivo `trn.json`
- Limpeza dos textos (remoção de caracteres inválidos e espaços desnecessários)
- Criação dos prompts no formato:  
Pergunta: {title}
Resposta: {content}

- Limitação dos textos para até **256 tokens**

### 🔹 2. Fine-Tuning (Treinamento)
- Modelo utilizado: **DistilGPT-2**
- Parâmetros principais:
- Épocas: 1
- Batch Size: 8
- Learning Rate: 0.0003
- Máximo de tokens: 256
- Processo:
- Treinamento com os prompts gerados
- Avaliação do modelo antes e depois do fine-tuning

### 🔹 3. Geração de Respostas
- O usuário fornece uma pergunta baseada no **título de um produto**
- O modelo retorna uma **resposta coerente com base na descrição aprendida**

---

## 💻 Tecnologias Utilizadas

- 🐍 Python
- 🤗 Hugging Face Transformers
- 🤗 Hugging Face Datasets
- 🐼 Pandas
- 🔥 PyTorch

---

## ▶️ Demonstração em Vídeo

🎥 Link para o vídeo no YouTube:  
👉 [Assista aqui](https://www.youtube.com/SEU_VIDEO_AQUI) *(substituir pelo link real)*

---

## 📂 Link do Repositório

🔗 [Acesse o projeto no GitHub](https://github.com/UnB-EngEnerg-180028863/Terceiro-Tech-Challenge)
