project:
  name: "Tech Challenge - Fine-Tuning de Foundation Model"
  student: "Vinícius Oliveira Litran Andrade"
  institution: "FIAP - Pós-graduação em Inteligência Artificial"
  description: |
    Este projeto consiste na aplicação de fine-tuning de um modelo de linguagem utilizando o dataset AmazonTitles-1.3MM,
    que contém títulos e descrições de produtos da Amazon.

    O objetivo é treinar o modelo para que, ao receber uma pergunta baseada no título de um produto,
    ele consiga gerar uma resposta coerente com base na descrição aprendida durante o treinamento.

  model_justification: |
    O desafio sugere o uso de foundation models robustos como Llama, Mistral ou BERT.
    Contudo, devido a limitações de hardware local, o modelo utilizado foi o DistilGPT-2,
    uma versão leve e otimizada do GPT-2.

    Essa escolha permite realizar o fine-tuning e a geração de respostas de forma eficiente,
    sem comprometer a demonstração dos conceitos e práticas fundamentais do desafio.

structure:
  - "LF-Amazon-1.3M/ : Dataset (trn.json)"
  - "fine_tune_data.csv : Dados preparados para o treino"
  - "fine_tuned_model/ : Modelo treinado"
  - "tech_challenge.ipynb : Notebook com todo o código"
  - "README.md : Documentação do projeto"

pipeline:
  preprocessing:
    description: "Preparação dos dados para treinamento."
    steps:
      - "Leitura do arquivo trn.json"
      - "Limpeza dos textos (remoção de caracteres inválidos e espaços desnecessários)"
      - "Criação dos prompts no formato: 'Pergunta: {title}\\nResposta: {content}'"
      - "Limitação dos textos para até 256 tokens"
  training:
    description: "Execução do fine-tuning no modelo DistilGPT-2."
    model: "distilgpt2"
    parameters:
      epochs: 1
      batch_size: 8
      learning_rate: 0.0003
      max_tokens: 256
    process:
      - "Treinamento com prompts criados"
      - "Avaliação do modelo antes e depois do fine-tuning"
  generation:
    description: "Geração de respostas com base nos títulos dos produtos."
    process:
      - "O usuário fornece uma pergunta baseada no título de um produto"
      - "O modelo gera uma resposta coerente com base nas descrições aprendidas"

technologies:
  - "Python"
  - "Hugging Face Transformers"
  - "Hugging Face Datasets"
  - "Pandas"
  - "PyTorch"

video_demo:
  youtube_link: "https://www.youtube.com/SEU_VIDEO_AQUI"

repository:
  github_link: "https://github.com/SEU_REPOSITORIO_AQUI"

execution:
  steps:
    - "Clone o repositório: git clone https://github.com/seu-usuario/seu-repositorio.git"
    - "Instale as dependências: pip install -r requirements.txt"
    - "Execute o notebook tech_challenge.ipynb para preparar os dados, treinar o modelo e gerar respostas"

improvements:
  - "Migração para foundation models mais robustos (ex.: Llama 2, Mistral)"
  - "Criação de uma interface web com Streamlit ou Gradio"
  - "Otimização do pipeline para rodar em ambientes com GPU na nuvem"

conclusion: |
  Este projeto demonstra, na prática, como realizar o fine-tuning de um modelo de linguagem com dados customizados.
  Mesmo utilizando um modelo leve, os resultados mostram que é possível personalizar modelos de linguagem
  para tarefas específicas.

acknowledgements: "Agradecimentos à equipe da FIAP e aos instrutores pela orientação e suporte técnico durante o desenvolvimento deste desafio."
