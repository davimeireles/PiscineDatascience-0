## Sumário

- [Sumário](#sumário)
- [Introdução](#introdução)
- [Configuração do Ambiente](#configuração-do-ambiente)
  - [Pré-requisitos](#pré-requisitos)
  - [Passo 1: Clonando o Repositório](#passo-1-clonando-o-repositório)
  - [Passo 2: Configurando Variáveis de Ambiente](#passo-2-configurando-variáveis-de-ambiente)
  - [Passo 3: Construindo o Ambiente](#passo-3-construindo-o-ambiente)
  - [Passo 4: Iniciando o Ambiente](#passo-4-iniciando-o-ambiente)
  - [Passo 5: Acessando o Banco de Dados](#passo-5-acessando-o-banco-de-dados)
  - [Gerenciamento de Credenciais](#gerenciamento-de-credenciais)

## Introdução

O Piscine de Data Science é uma iniciativa da Escola 42 para fornecer treinamento intensivo e imersivo em ciência de dados. Este projeto utiliza o Docker para garantir que todos os participantes trabalhem em um ambiente consistente e bem configurado.

## Configuração do Ambiente

### Pré-requisitos

Antes de começar, certifique-se de ter o Docker e o Docker Compose instalados em sua máquina.

### Passo 1: Clonando o Repositório

Clone este repositório em sua máquina local utilizando o seguiente comando:

```bash
git clone https://github.com/davimeireles/PiscineDatascience-0.git
```

Navegue até o diretório do projeto:
```bash
cd PiscineDatascience-0/ex00
```

### Passo 2: Configurando Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto com as seguintes variáveis de ambiente:

`
DB_USER=user
`
`
DB_PASSWORD=password
`
`
DB_NAME=name
`

Certifique-se de substituir os valores pelos dados reais apropriados para o seu ambiente.

### Passo 3: Construindo o Ambiente

Construa o ambiente Docker executando o seguinte comando:

```bash
docker-compose build
```

Este comando irá compilar as imagens Docker necessárias para rodar o projeto.

### Passo 4: Iniciando o Ambiente

Inicie o ambiente com o comando:

```bash
docker-compose up -d
```

A flag `-d` permite que os containers sejam executados em segundo plano.

### Passo 5: Acessando o Banco de Dados

Para acessar o banco de dados PostgresSQL no container Docker, use o seguinte comando:

```bash
docker exec -it ex00_db_1 psql -U user -d name -W
```

- -U user: Especifica o usuáiro do banco de dados.
- -d name: Especifica o nome do banco de dados.
- -W: Solicita a senha do banco de dados, que foi definida no arquivo `.env`

### Gerenciamento de Credenciais

As credenciais do banco de dados são mantidas em um arquivo `.env` para garantir segurança. É importante que este arquivo não seja incluído no controle de versão (adicione `.env` ao seu `.gitignore`).