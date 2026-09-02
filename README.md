# 📱 Agenda de Contatos

Aplicação de **Agenda de Contatos desenvolvida em Java**, executada através do terminal. O sistema permite cadastrar, listar, pesquisar e excluir contatos.

> **Versão:** `0.2.0`
> **Status:** Em desenvolvimento

---

## 📖 Sobre o projeto

A **Agenda de Contatos** é uma aplicação de console desenvolvida em Java para realizar o gerenciamento básico de contatos.

Nesta versão, o projeto passou a utilizar as estruturas **`List`** e **`ArrayList`**, substituindo os arrays utilizados na versão anterior. Isso permite trabalhar com uma lista de contatos sem definir previamente uma capacidade fixa.

O sistema possui um menu interativo que permanece em execução até que o usuário escolha a opção **5 - Sair**.

---

## ✨ Funcionalidades

### ➕ Adicionar contato

Permite cadastrar um contato informando:

* Nome;
* Celular;
* E-mail.

Os dados são adicionados às respectivas listas através do método `add()`.

---

### 📋 Listar contatos

Exibe todos os contatos cadastrados.

Para cada contato são apresentados:

* Número do contato;
* Nome;
* Celular;
* E-mail.

A aplicação percorre a lista utilizando um laço `for` e recupera os dados através do método `get()`.

---

### 🔎 Procurar contato

Permite pesquisar um contato pelo nome.

A busca percorre todos os contatos cadastrados e utiliza `equalsIgnoreCase()`, fazendo com que a pesquisa não diferencie letras maiúsculas de minúsculas.

---

### 🗑️ Excluir contato

Permite excluir um contato através do nome.

Quando o contato é encontrado, seus dados são removidos das três listas utilizando o método `remove()` e o índice correspondente.

---

### 🚪 Sair

A opção **5 - Sair** altera a variável de controle `continuar` para `false`, encerrando o funcionamento do menu.

---

## 🖥️ Menu do sistema

Ao iniciar, a aplicação apresenta:

```text
==========================
    AGENDA DE CONTATOS
        V.0.2.0
==========================
Bem-vindo!

1-Adicionar contato
2-Listar contato
3-Procurar contato
4-Excluir contato
5-Sair
```

---

## 🛠️ Tecnologias utilizadas

* **Java**
* `Scanner`
* `List`
* `ArrayList`
* Estruturas de repetição
* Estruturas condicionais
* `switch`
* `equalsIgnoreCase()`

As listas utilizadas pelo sistema são declaradas como `List<String>` e instanciadas com `ArrayList<>`.

---

## 📂 Estrutura do projeto

```text
Agenda-de-Contatos/
│
└── Principal.java
```

Pacote:

```text
br.edu.principal
```

Classe principal:

```text
Principal
```

---

## ▶️ Como executar

### Pré-requisitos

É necessário possuir o **Java JDK** instalado.

Verifique a instalação:

```bash
java -version
```

Verifique também o compilador:

```bash
javac -version
```

### Compilação

Compile o arquivo:

```bash
javac Principal.java
```

### Execução

Execute o programa:

```bash
java Principal
```

> Caso o projeto esteja organizado de acordo com o pacote `br.edu.principal`, execute os comandos a partir da estrutura correta de diretórios.

---

## 🧠 Funcionamento interno

A versão `0.2.0` utiliza três listas para armazenar os dados:

```text
nomes
celulares
emails
```

Cada posição representa os dados de um mesmo contato.

Por exemplo:

```text
Índice 0
Nome: João
Celular: 88999999999
E-mail: joao@email.com

Índice 1
Nome: Maria
Celular: 88988888888
E-mail: maria@email.com
```

A quantidade de contatos é obtida diretamente através do método `size()` das listas.

---

## 🔄 Evolução da versão anterior

### Versão `0.1.0`

A aplicação utilizava arrays com uma capacidade definida previamente.

### Versão `0.2.0`

Os arrays foram substituídos por:

```java
List<String> nomes = new ArrayList<>();
List<String> celulares = new ArrayList<>();
List<String> emails = new ArrayList<>();
```

## Essa mudança permite adicionar e remover elementos utilizando diretamente os métodos da estrutura `ArrayList`, como `add()` e `remove()`.

## ⚠️ Limitações atuais

Apesar da evolução, a versão `0.2.0` ainda possui algumas limitações:

* Os dados são armazenados somente durante a execução;
* Ao fechar o programa, os contatos cadastrados são perdidos;
* Não existe edição de contatos;
* Não há armazenamento em arquivos;
* Não há banco de dados;
* Não existe validação específica para celular ou e-mail.

---

## 🚀 Melhorias futuras

Possíveis melhorias para as próximas versões:

* [ ] Editar contatos;
* [ ] Salvar contatos em arquivo;
* [ ] Implementar banco de dados;
* [ ] Validar e-mails;
* [ ] Validar números de telefone;
* [ ] Criar uma classe `Contato`;
* [ ] Utilizar orientação a objetos;
* [ ] Organizar o projeto em múltiplas classes;
* [ ] Adicionar ordenação dos contatos;
* [ ] Criar uma interface gráfica.

---

## 🎯 Objetivo

O projeto tem como objetivo praticar conceitos fundamentais da programação em **Java**, incluindo:

* Variáveis;
* Listas;
* `ArrayList`;
* Laços de repetição;
* Estruturas condicionais;
* `switch`;
* Entrada de dados;
* Manipulação de Strings;
* Busca de elementos;
* Adição e remoção de elementos.

---

## 📌 Versão

**Agenda de Contatos — v0.2.0**

Esta versão representa uma evolução do projeto, substituindo os arrays de tamanho fixo por **`List` e `ArrayList`**, tornando o gerenciamento dos contatos mais flexível.
