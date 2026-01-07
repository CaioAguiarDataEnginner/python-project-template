# Python Project Template

Template profissional para projetos Python com estrutura organizada e ferramentas de desenvolvimento configuradas.

## 📋 Sobre o Projeto

Este é um template base para novos projetos Python que inclui:
- Gerenciamento de dependências com Poetry
- Estrutura de pastas organizada
- Configurações para testes, cobertura de código e CI/CD
- Suporte a Docker
- Documentação estruturada

## 🚀 Pré-requisitos

- Python >= 3.12
- Poetry (gerenciador de dependências)
- Docker (opcional, para containerização)

## 📁 Estrutura do Projeto

```
python-project-template/
├── src/                    # Código-fonte principal do projeto
├── tests/                  # Testes automatizados
├── docs/                   # Documentação do projeto
├── notebooks/              # Jupyter notebooks para análise/experimentação
├── pyproject.toml          # Configuração do Poetry e do projeto
├── poetry.lock             # Lockfile do Poetry (versões exatas das dependências)
├── pytest.ini              # Configuração do pytest (framework de testes)
├── dockerfile              # Configuração para containerização Docker
├── codecov.yml             # Configuração do Codecov (cobertura de código)
├── workflows.yml           # Configuração de workflows CI/CD
├── task.yml                # Configuração de tarefas automatizadas
├── mlp-config.yaml         # Configuração MLP (Machine Learning Pipeline)
├── .pre-commit-config.yaml # Configuração do pre-commit (hooks Git)
├── .gitignore              # Arquivos e pastas ignorados pelo Git
├── changelog.md            # Registro de mudanças do projeto
└── README.md               # Este arquivo
```

## 📂 Descrição de Pastas e Arquivos

### 📁 Pastas

#### `src/`
Diretório principal onde deve estar todo o código-fonte do projeto. É aqui que você organizará seus módulos e pacotes Python. Esta estrutura ajuda a separar claramente o código da aplicação dos testes e outros arquivos auxiliares.

**Exemplo de estrutura:**
```
src/
├── seu_pacote/
│   ├── __init__.py
│   ├── modulo1.py
│   └── modulo2.py
```

#### `tests/`
Contém todos os testes automatizados do projeto. Recomenda-se usar `pytest` como framework de testes. Organize os testes para espelhar a estrutura do código em `src/`.

**Exemplo de estrutura:**
```
tests/
├── __init__.py
├── test_modulo1.py
└── test_modulo2.py
```

#### `docs/`
Documentação adicional do projeto. Pode incluir guias, tutoriais, diagramas, ou documentação gerada automaticamente com ferramentas como Sphinx.

#### `notebooks/`
Jupyter notebooks para análise de dados, experimentação, prototipagem ou documentação interativa. Útil para projetos de ciência de dados e machine learning.

### 📄 Arquivos de Configuração

#### `pyproject.toml`
Arquivo de configuração principal do Poetry que define:
- Metadados do projeto (nome, versão, descrição, autores)
- Dependências do projeto
- Versão mínima do Python requerida
- Configurações de build e publicação

**Como usar:**
```bash
# Instalar dependências
poetry install

# Adicionar uma nova dependência
poetry add nome-do-pacote

# Adicionar dependência de desenvolvimento
poetry add --group dev nome-do-pacote

# Atualizar dependências
poetry update
```

#### `poetry.lock`
Arquivo gerado automaticamente pelo Poetry que fixa as versões exatas de todas as dependências (incluindo dependências transitivas). Garante builds reproduzíveis. **Recomenda-se commitar este arquivo no controle de versão.**

#### `pytest.ini`
Configuração do pytest, framework de testes Python. Define:
- Diretórios de testes
- Padrões de nomenclatura de arquivos de teste
- Opções de cobertura
- Configurações de plugins

**Exemplo de uso:**
```bash
# Executar todos os testes
pytest

# Executar com cobertura
pytest --cov=src --cov-report=html

# Executar testes específicos
pytest tests/test_modulo1.py
```

#### `dockerfile`
Configuração Docker para containerizar a aplicação. Permite criar uma imagem Docker que pode ser executada em qualquer ambiente que suporte Docker, garantindo consistência entre desenvolvimento e produção.

**Como usar:**
```bash
# Construir a imagem
docker build -t python-project-template .

# Executar o container
docker run python-project-template
```

#### `codecov.yml`
Configuração do Codecov, serviço que monitora a cobertura de código. Define limites mínimos de cobertura e regras para relatórios de cobertura de código.

#### `workflows.yml`
Configuração de workflows de CI/CD (Continuous Integration/Continuous Deployment). Define pipelines automatizados para:
- Executar testes em cada push/pull request
- Verificar qualidade de código
- Fazer deploy automático
- Gerar relatórios de cobertura

#### `task.yml`
Arquivo de configuração para automação de tarefas. Pode ser usado com ferramentas como `task` (Task Runner) ou similar para definir comandos comuns do projeto.

#### `mlp-config.yaml`
Configuração para Machine Learning Pipeline (MLP). Usado em projetos de ML para definir fluxos de trabalho, etapas de processamento e configurações de modelos.

#### `.pre-commit-config.yaml`
Configuração do pre-commit, framework de hooks Git. Permite executar verificações automáticas antes de cada commit:
- Formatação de código (black, ruff)
- Verificação de lint (flake8, pylint)
- Verificação de tipos (mypy)
- Outras verificações customizadas

**Como usar:**
```bash
# Instalar hooks
pre-commit install

# Executar manualmente em todos os arquivos
pre-commit run --all-files
```

#### `.gitignore`
Lista de arquivos e pastas que o Git deve ignorar. Inclui:
- Arquivos Python compilados (`__pycache__/`, `*.pyc`)
- Ambientes virtuais (`.venv/`, `venv/`)
- Arquivos de IDE (`.vscode/`, `.idea/`)
- Arquivos de cobertura de código (`.coverage`, `htmlcov/`)
- Arquivos de configuração local (`.env`)
- E muitos outros padrões comuns

#### `changelog.md`
Registro de todas as mudanças, correções e novas funcionalidades do projeto. Mantém um histórico organizado das versões do software. Segue geralmente o formato [Keep a Changelog](https://keepachangelog.com/).

## 🔧 Como Usar Este Template

### 1. Clonar o Template
```bash
git clone <url-do-repositorio>
cd python-project-template
```

### 2. Configurar o Projeto
```bash
# Instalar dependências
poetry install

# Ou criar um novo ambiente virtual
poetry env use python3.12
```

### 3. Personalizar
- Atualize `pyproject.toml` com informações do seu projeto
- Adicione suas dependências
- Escreva seu código em `src/`
- Crie testes em `tests/`

### 4. Executar Testes
```bash
pytest
```

### 5. Instalar Pre-commit Hooks
```bash
pre-commit install
```

## 📝 Comandos Úteis

```bash
# Instalar dependências
poetry install

# Adicionar dependência
poetry add nome-do-pacote

# Adicionar dependência de desenvolvimento
poetry add --group dev nome-do-pacote

# Executar testes
pytest

# Executar testes com cobertura
pytest --cov=src --cov-report=html

# Verificar formatação de código
black --check src tests

# Formatar código
black src tests

# Executar lint
ruff check src tests

# Executar todos os checks do pre-commit
pre-commit run --all-files

# Ativar ambiente virtual do Poetry
poetry shell

# Executar comando dentro do ambiente virtual
poetry run python seu_script.py
```

## 🧪 Testes

O projeto está configurado para usar `pytest`. Execute os testes com:

```bash
pytest
```

Para ver a cobertura de código:
```bash
pytest --cov=src --cov-report=html
```

Os relatórios de cobertura serão gerados em `htmlcov/index.html`.

## 📦 Publicação

Para publicar o pacote no PyPI:

```bash
# Build do pacote
poetry build

# Publicar no PyPI (requer configuração)
poetry publish
```

## 🤝 Contribuindo

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/MinhaFeature`)
3. Commit suas mudanças (`git commit -m 'Adiciona MinhaFeature'`)
4. Push para a branch (`git push origin feature/MinhaFeature`)
5. Abra um Pull Request

## 📄 Licença

[Especifique a licença do seu projeto aqui]

## 👤 Autor

[Seu Nome] - [seu-email@example.com]

## 🙏 Agradecimentos

- Poetry pela excelente ferramenta de gerenciamento de dependências
- Comunidade Python por todas as ferramentas e bibliotecas
