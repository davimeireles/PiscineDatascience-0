# 🌊 Piscine de Data Science - 42 Porto 🐬

Bem-vindo ao guia de configuração e uso do PostgreSQL e pgAdmin! Este documento irá guiá-lo através dos passos necessários para configurar seu ambiente, criar a base de dados e acessar o pgAdmin.

## 📋 Sumário

- [🌊 Piscine de Data Science - 42 Porto 🐬](#-piscine-de-data-science---42-porto-)
  - [📋 Sumário](#-sumário)
  - [🛠️ Pré-requisitos](#️-pré-requisitos)
  - [📥 Passo 1: Clonando o Repositório](#-passo-1-clonando-o-repositório)
    - [⚙️ Passo 2: Configurando Variáveis de Ambiente](#️-passo-2-configurando-variáveis-de-ambiente)
    - [🏗️ Passo 3: Construindo o Ambiente](#️-passo-3-construindo-o-ambiente)
    - [🚀 Passo 4: Iniciando o Ambiente](#-passo-4-iniciando-o-ambiente)
    - [🌐 Passo 5: Acessando o pgAdmin](#-passo-5-acessando-o-pgadmin)
    - [🔌Passo 6: Configurando a Conexão no pgAdmin](#passo-6-configurando-a-conexão-no-pgadmin)
    - [🔒 Gerencimanento de Credenciais](#-gerencimanento-de-credenciais)

## 🛠️ Pré-requisitos

Antes de começar, certifique-se de ter o Docker e o Docker Compose instalados em sua máquina.

## 📥 Passo 1: Clonando o Repositório

Clone este repositório em sua máquina local utilizando o seguinte comando:

```bash
git clone https://github.com/davimeireles/datascience-00.git
```

Navegue até o diretório do projeto:

```bash
cd datascience-00/ex01
```

### ⚙️ Passo 2: Configurando Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis de ambiente:

```
POSTGRES_USER=user
POSTGRES_PASSWORD=db_password
POSTGRES_DB=db_name
PGADMIN_DEFAULT_EMAIL=pg_email
PGADMIN_DEFAULT_PASSWORD=pg_password
```

### 🏗️ Passo 3: Construindo o Ambiente

Construa o ambiente Docker executando o seguinte comando:

```bash
docker-compose build
```

Este comando irá compilar as imagens Docker necessárias para rodar o projeto.

### 🚀 Passo 4: Iniciando o Ambiente

Inicie o ambiente com o comando:

```bash
docker-compose up -d
```

A flag `-d` permite que os containers sejam executados em segundo plano.

### 🌐 Passo 5: Acessando o pgAdmin

Abra o navegador e acesse `http://localhost:8080`. Faça login com o email senha definidos no arquivo `.env`.

### 🔌Passo 6: Configurando a Conexão no pgAdmin

Após fazer login no pgAdmin, adicione um novo servidor com as seguintes configurações:

- Name: PostgreSQL
- Host: db
- Port: 5432
- Username: `.env`
- Password: `.env`

Clise em "Save" para salvar a configuração.

### 🔒 Gerencimanento de Credenciais

As credenciais do banco de dados são mantidas em um arquivo `.env` para garantir segurança. É importante que este arquivo não seja incluído no controle de versão (adicione `.env` ao seu `.gitignore`).