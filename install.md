
# Guia de Instalação do Projeto

Este documento fornece instruções detalhadas sobre como configurar o ambiente de desenvolvimento necessário para executar o projeto, incluindo a criação de um ambiente virtual e a instalação das dependências utilizando o `requirements.txt`.

## Pré-requisitos

Antes de iniciar, certifique-se de que ferramentas como `git`, `curl`, e um compilador C (como `gcc` ou `clang`) estão instaladas, pois são necessárias para a instalação do `pyenv`.

## Atualização do pip

- Atualize o pip dentro do ambiente virtual:
  ```bash
  pip install --upgrade pip
  ```

## Configuração Inicial

### Instalação do pyenv

#### Para macOS e Linux:

1. **Instalar o Homebrew**
   - Abra um terminal e execute:
     ```bash
     /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
     ```

2. **Instalar o pyenv**
   - Com o Homebrew instalado, execute:
     ```bash
     brew install pyenv
     ```

3. **Configurar Variáveis de Ambiente**
   - Abra o arquivo de configuração do seu shell usando o nano (`nano ~/.zshrc`) e adicione:
     ```bash
     export PYENV_ROOT="$HOME/.pyenv"
     export PATH="$PYENV_ROOT/bin:$PATH"
     if command -v pyenv 1>/dev/null 2>&1; then
       eval "$(pyenv init --path)"
     fi
     if which pyenv > /dev/null; then eval "$(pyenv init -)"; fi
     ```
   - Salve com `CTRL+O`, confirme com `Enter`, e saia com `CTRL+X`.

4. **Reiniciar o Shell**
   - Execute: `source ~/.zshrc`

5. **Verificar a Instalação**
   - Confirme a instalação do pyenv com: `pyenv --version`

#### Para Windows:

1. **Instalar o pyenv-win**
   - Instale via pip ou Chocolatey:
     ```cmd
     # Via pip
     pip install pyenv-win
     # Via Chocolatey
     choco install pyenv-win
     ```

2. **Configurar Variáveis de Ambiente**
   - Acesse "Variáveis de Ambiente" através do menu Iniciar e edite as variáveis do sistema adicionando:
     ```cmd
     C:\Users\SEU_USUARIO\.pyenv\pyenv-win\bin
     C:\Users\SEU_USUARIO\.pyenv\pyenv-win\shims
     ```
   - Defina a variável `PYENV` para o caminho de instalação do `pyenv-win`.

3. **Verificar Instalação**
   - Abra um novo prompt de comando e digite: `pyenv --version`

### Configurar a Versão do Python

- Instale e defina a versão do Python com:
  ```bash
  pyenv install 3.11  
  pyenv global 3.11
  ```

### Preparar o Diretório do Projeto

- Navegue até o diretório do projeto:
  ```bash
  cd caminho/para/seu/projeto/root/src
  ```

### Configurar Arquivo .env

- Renomeie `.env.example` para `.env` e ajuste as variáveis de ambiente conforme necessário.

## Criação e Ativação do Ambiente Virtual

1. **Criar o Ambiente Virtual**
   - Execute: `python -m venv venv`

2. **Ativar o Ambiente Virtual**
   - Para macOS e Linux:
     ```bash
     source venv/bin/activate
     ```
   - Para Windows:
     ```cmd
     .\venv\Scripts\activate
     ```


## Instalação de Dependências

- Instale as dependências do projeto:
  ```bash
  pip install -r requirements.txt
  ```

## Verificação do Ambiente

- Verifique se o ambiente virtual está configurado corretamente:
  - Para macOS e Linux: `which python`
  - Para Windows: `where python`

## Preparação do Dataset

1. **Download dos Dados**
   - Acesse [Google Drive](https://drive.google.com/drive/folders/1Dm0DBTIhttI-C1STf250cSYMcTTDYH3r) e baixe as pastas zipadas.

2. **Organização dos Arquivos**
   - Mova as pastas zipadas para `./src/data` no seu projeto.

## Execução do Projeto

- Siga as instruções detalhadas sobre como executar o projeto após a configuração do ambiente.

## Desativação do Ambiente Virtual

- Desative o ambiente virtual ao concluir:
  ```bash
  deactivate
  ```

## Dicas Adicionais

- Sempre ative o ambiente virtual antes de iniciar o trabalho no projeto.
- Mantenha o `pip` atualizado para garantir a segurança e eficiência das instalações de pacotes.




