# 📱 Agenda de Contatos

Uma aplicação simples de **Agenda de Contatos desenvolvida em Java**, executada via terminal. O projeto permite cadastrar, visualizar, pesquisar e excluir um contato através de um menu interativo.

> **Versão atual:** `v0.0.0`

---

## 📋 Sobre o projeto

O projeto foi desenvolvido com o objetivo de praticar conceitos fundamentais da linguagem **Java**, como:

- Entrada de dados pelo terminal;
- Estruturas condicionais;
- Estruturas de repetição;
- `switch`;
- Variáveis e tipos de dados;
- Comparação de Strings;
- Organização de um menu interativo;
- Utilização da classe `Scanner`.

A aplicação apresenta um menu que permanece disponível até que o usuário escolha a opção **Sair**.

---

## ⚙️ Funcionalidades

Atualmente, o sistema possui as seguintes funcionalidades:

### ➕ Adicionar contato

Permite cadastrar:

- Nome;
- Número de celular;
- E-mail.

Após o preenchimento dos dados, o sistema informa que o contato foi salvo com sucesso.

### 📋 Listar contato

Exibe os dados do contato cadastrado:

- Nome;
- Celular;
- E-mail.

Caso nenhum contato esteja cadastrado, o sistema informa que não há contatos disponíveis.

### 🔎 Procurar contato

Permite pesquisar um contato pelo nome.

A pesquisa não diferencia letras maiúsculas de minúsculas, utilizando `equalsIgnoreCase()`.

### 🗑️ Excluir contato

Remove os dados do contato atualmente cadastrado.

Caso não exista um contato, o sistema informa que nenhum contato está cadastrado.

### 🚪 Sair

Encerra a execução do programa através da opção **5 - Sair**.

---

## 🖥️ Menu do sistema

Ao iniciar, o programa apresenta o seguinte menu:

```text
==========================
     AGENDA DE CONTATOS
          v0.0.0
==========================

Bem-vindo!

1 - Adicionar contato
2 - Listar contato
3 - Procurar contato
4 - Excluir contato
5 - Sair
```

---

## 🛠️ Tecnologias utilizadas

- **Java**
- `java.util.Scanner`
- Aplicação executada via **terminal/console**

A classe principal pertence ao pacote `br.edu.principal` e utiliza `Scanner` para receber os dados informados pelo usuário.

---

## 📁 Estrutura atual

```text
projeto/
└── Principal.java
```

Classe principal:

```text
br.edu.principal.Principal
```

---

## ▶️ Como executar

### 1. Instale o Java

Verifique se o Java está instalado:

```bash
java -version
```

E o compilador:

```bash
javac -version
```

### 2. Compile o projeto

Dentro da pasta correspondente ao projeto, compile o arquivo:

```bash
javac Principal.java
```

### 3. Execute

```bash
java Principal
```

> Dependendo da estrutura de pastas e do pacote utilizado, pode ser necessário executar o programa a partir do diretório raiz do projeto.

---

## 📌 Limitações da versão atual

A versão `v0.0.0` possui uma implementação inicial e algumas limitações:

- O sistema trabalha com **apenas um contato por vez**.
- Os dados são armazenados somente durante a execução do programa.
- Não existe banco de dados ou arquivo para persistência.
- Ao encerrar o programa, os dados cadastrados são perdidos.
- Ainda não há validação específica para telefone ou e-mail.
- Não existem funcionalidades de edição de contatos.

---

## 🚀 Possíveis melhorias futuras

Algumas funcionalidades que podem ser adicionadas em versões futuras:

- [ ] Cadastro de múltiplos contatos;
- [ ] Edição de contatos;
- [ ] Armazenamento em arquivo;
- [ ] Integração com banco de dados;
- [ ] Validação de e-mail;
- [ ] Formatação do número de telefone;
- [ ] Ordenação dos contatos;
- [ ] Busca por diferentes informações;
- [ ] Interface gráfica;
- [ ] Separação do projeto em diferentes classes;
- [ ] Implementação de orientação a objetos mais completa.

---

## 🎯 Objetivo acadêmico

Este projeto serve como uma aplicação prática para o aprendizado dos fundamentos da programação em **Java**, especialmente entrada de dados, estruturas de controle e desenvolvimento de aplicações interativas no terminal.

---

## 👨‍💻 Status

**Em desenvolvimento**

Versão atual: **v0.0.0**

Novas funcionalidades poderão ser adicionadas conforme a evolução do projeto.