# Astra

Um framework aberto para refinamento de SLMs (Small Language Models) com técnicas modernas (LoRA/QLoRA, SFT, distilação e avaliação), focado em simplicidade, reprodutibilidade e performance em hardware acessível.

## Sobre o Projeto

Ainda pensando nas noites da floresta, temos a luz das estrelas que tornam a noite ainda mais calma e tranquila. Então nada melhor que complementar o framework Luna com um framework de refinamento de SLMs usando técnicas bem conhecidas e funcionais. O Astra nasce para facilitar o fine‑tuning e a adaptação leve de modelos de linguagem pequenos, oferecendo um caminho direto para especializar modelos em domínios específicos, alinhar instruções e publicar artefatos prontos para uso.

Na prática, o Astra propõe:
- Refinamento de SLMs via LoRA/QLoRA (PEFT), SFT e técnicas de alinhamento
- Suporte ao ecossistema Transformers/Hugging Face com PyTorch
- Pipeline de preparo de dados (limpeza, formatação de prompts, amostragem e split reprodutível)
- Treino eficiente em GPU única ou múltipla; execução em CPU para protótipos
- Avaliação automática (perplexidade, métricas baseadas em instruções e suites customizáveis)
- Exportação e empacotamento de modelos/adapters, com publicação local ou remota
- Configuração declarativa (YAML) e controle de experimentos com seeds e logs
- Integração opcional com provedores de LLM para avaliação comparativa e validação baseada em RAG

O objetivo é oferecer uma base simples e pragmática para quem precisa adaptar modelos de linguagem de forma confiável, com boas práticas de MLOps aplicadas ao ciclo de fine‑tuning, avaliação e versionamento.

## Recursos e Tecnologias

Astra é desenhado com tecnologias e conceitos amplamente utilizados:

- Linguagem principal e SDKs: Python
- Treinamento e inferência: PyTorch, Hugging Face Transformers, Accelerate
- Adaptação leve: PEFT (LoRA/QLoRA), bitsandbytes (quantização 4/8‑bit)
- Datasets: Hugging Face Datasets e conectores simples (CSV/JSONL/Parquet)
- Métricas e avaliação: ferramentas baseadas em prompts e benchmarks customizáveis
- Gerenciamento de dependências e tarefas: uv (package manager) e Make (alvos para setup, build, testes e validações)
- Configuração: arquivos YAML e variáveis de ambiente para credenciais e parâmetros
- Compatibilidade: CPU, GPU única ou múltipla; suporte opcional a CUDA

Observação: o conjunto exato de integrações é flexível, permitindo escolher bibliotecas, datasets e provedores que melhor se adaptem ao seu ambiente.

## Configurações e uso

### Pré-requisitos:
- Python 3.12+
- Git
- uv (gerenciador de pacotes/ambientes). Instalação e docs: https://docs.astral.sh/uv/
- Windows Subsystem for Linux (WSL) - Windows 10,11
- GPU com CUDA (opcional) para treino acelerado; CPU é suficiente para protótipos
- Credenciais de provedores (opcional) para avaliação comparativa ou integrações externas

### Passos:
1) Clonar o repositório
   - git clone https://github.com/florestaencantada/astra.git
   - cd astra

2) Sincronizar dependências e preparar o ambiente virtual automaticamente com o uv
   - make setup

3) Executar testes e validações automatizadas
   - make test

4) Rodar a CLI
   - uv run astra --version

5) Atualizar dependências
   - make sync

