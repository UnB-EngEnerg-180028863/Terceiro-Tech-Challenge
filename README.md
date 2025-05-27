# 🚀 Tech Challenge - Fine-Tuning de Foundation Model

**Aluno:** Vinícius Oliveira Litran Andrade
**Instituição:** FIAP - Pós-graduação em Inteligência Artificial (IA para Devs)

---

## 📜 Descrição do Projeto

Este projeto consiste na aplicação de **fine-tuning de um modelo de linguagem** utilizando o dataset **AmazonTitles-1.3MM**, que contém títulos e descrições de produtos da Amazon.

O objetivo é treinar o modelo para que, ao receber uma pergunta baseada no título de um produto, ele consiga gerar uma resposta coerente com base na descrição aprendida durante o treinamento.

---

## 🔥 Justificativa do Modelo

O desafio sugere o uso de foundation models como **Llama**, **Mistral** ou **BERT**. Contudo, devido a limitações de hardware local (como RTX 4070, RTX 3060 ou RTX 2060), o modelo utilizado foi o **DistilGPT-2**, uma versão leve e otimizada do GPT-2, com aproximadamente **82 milhões de parâmetros** (em comparação com os 124 milhões do GPT-2 original).

Essa escolha permite realizar o fine-tuning e a geração de respostas de forma eficiente, sendo leve e rápido de treinar, menos demandante em termos de recursos computacionais e viável para execução local, sem custos adicionais com infraestrutura em nuvem. Embora o desempenho não seja comparável a modelos maiores, ele é plenamente suficiente para validar o pipeline completo de fine-tuning aplicado ao dataset _AmazonTitles-1.3MM_.

---

## 🗂️ Estrutura do Projeto

├── LF-Amazon-1.3M/ # Dataset (trn.json) 🔗 [LF-Amazon-1.3M](https://drive.google.com/file/d/12zH4mL2RX8iSvH0VCNnd3QxO4DzuHWnK/view)

├── fine_tune_data.jsonl # Dados preparados para o treino 

├── fine_tuned_model/ # Modelo treinado

├── tech_challenge.ipynb # Notebook com todo o código 

├── README.md # Documentação do projeto

---

## ⚙️ Pipeline do Projeto

### 🔹 1. Pré-processamento dos Dados
- Leitura do arquivo `trn.json` 
- Limpeza e normalização dos textos, removendo HTML, caracteres especiais e espaços desnecessários
- Criação dos prompts no formato:
You are an assistant that answers questions based on the product description.
Question: {title}
Answer: {content}

- Limitação dos textos para um máximo de **256 tokens**

### 🔹 2. Fine-Tuning (Treinamento)
- Modelo utilizado: **DistilGPT-2** 
- Parâmetros principais:
  - Épocas (`num_train_epochs`): `3` 
  - Batch Size (`per_device_train_batch_size`): `16` 
  - Learning Rate (`learning_rate`): `5e-5` 
  - Máximo de tokens (`max_length`): `256`
  - `fp16`: `True` (se GPU com CUDA disponível)
  - Otimizador (`optim`): `adamw_torch_fused`
  - `save_steps`: `500`
  - `save_total_limit`: `1`
  - `logging_steps`: `100`
  - `weight_decay`: `0.01`
- Processo:
  - Treinamento com os prompts gerados.
  - Avaliação do modelo antes e depois do fine-tuning para analisar a diferença do resultado gerado.

### 🔹 3. Geração de Respostas
- O usuário fornece uma pergunta baseada no **título de um produto**.
- O modelo retorna uma **resposta coerente com base na descrição aprendida** durante o fine-tuning.

---

## 💻 Tecnologias Utilizadas

- 🐍 Python
- 🤗 Hugging Face Transformers
- 🤗 Hugging Face Datasets
- 🐼 Pandas
- 🔥 PyTorch
- `tqdm` (para barras de progresso)
- `pathlib` (para manipulação de caminhos)
- `json` (para manipulação de JSON)
- `os` (para interações com o sistema operacional)
- `re` (para expressões regulares)
- `unicodedata` (para normalização Unicode)
- `html` (para unescape de HTML)

---

## ▶️ Demonstração em Vídeo

🎥 Link para o vídeo no YouTube:
👉 [Assista aqui](https://www.youtube.com/SEU_VIDEO_AQUI) *(substituir pelo link real)* 
---

## 📂 Link do Repositório

🔗 [Acesse o projeto no GitHub](https://github.com/UnB-EngEnerg-180028863/Terceiro-Tech-Challenge) 
