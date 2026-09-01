# 📱 Agenda de Contatos

Aplicação de **Agenda de Contatos desenvolvida em Java**, executada através do terminal. O sistema permite cadastrar, listar, pesquisar e excluir múltiplos contatos.

> **Versão:** `v0.1.0`
> **Status:** Em desenvolvimento

---

## 📖 Sobre o projeto

A **Agenda de Contatos** é uma aplicação de console desenvolvida em Java para gerenciamento básico de contatos.

Nesta versão, o sistema evoluiu para trabalhar com **múltiplos contatos**, utilizando arrays para armazenar os nomes, números de celular e endereços de e-mail.

O programa possui um menu interativo que permanece em execução até que o usuário escolha a opção **Sair**.

---

## ✨ Funcionalidades

### ➕ Adicionar contato

Permite cadastrar um novo contato informando:

* Nome;
* Número de celular;
* E-mail.

Cada novo contato é armazenado nos respectivos arrays e o contador de contatos é incrementado.

---

### 📋 Listar contatos

Exibe todos os contatos cadastrados.

Para cada contato são apresentados:

* Número do contato;
* Nome;
* Celular;
* E-mail.

A listagem é realizada percorrendo os contatos armazenados através de um laço `for`.

---

### 🔎 Procurar contato

Permite pesquisar um contato pelo nome.

A busca percorre todos os contatos cadastrados e utiliza `equalsIgnoreCase()`, permitindo encontrar o nome independentemente de letras maiúsculas ou minúsculas.

---

### 🗑️ Excluir contato

Permite excluir um contato informando seu nome.

Quando o contato é encontrado, os elementos seguintes são deslocados uma posição para preencher o espaço deixado pelo contato removido. Depois disso, a última posição utilizada é definida como `null` e o contador é decrementado.

---

### 🚪 Sair

A opção **5 - Sair** encerra o loop principal e finaliza a execução da aplicação.

---

## 🖥️ Menu

Ao iniciar, o programa apresenta:

```text
==========================
     AGENDA DE CONTATOS
          v0.1.0
==========================

Bem-vindo!

1 - Adicionar contato
2 - Listar contato
3 - Procurar contato
4 - Excluir contato
5 - Sair
```

---

## 🛠️ Tecnologias

* **Java**
* **Scanner**
* Arrays (`String[]`)
* Estruturas de repetição
* Estruturas condicionais
* `switch`
* `equalsIgnoreCase()`

O projeto utiliza a classe `Scanner` para receber as informações digitadas pelo usuário no terminal.

---

## 📂 Estrutura do projeto

```text
Agenda-de-Contatos/
│
└── Principal.java
```

Pacote utilizado:

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

Verifique a instalação com:

```bash
java -version
```

E:

```bash
javac -version
```

### Compilação

Compile o arquivo Java:

```bash
javac Principal.java
```

### Execução

Execute o programa:

```bash
java Principal
```

> Caso esteja utilizando a estrutura de pacotes do projeto, a compilação e execução devem ser feitas respeitando a estrutura de diretórios correspondente ao pacote `br.edu.principal`.

---

## 🧠 Funcionamento interno

Os contatos são armazenados em três arrays:

```text
nomes[]
celulares[]
emails[]
```

Cada posição dos arrays representa um contato.

Por exemplo:

```text
Posição 0 → João | 88999999999 | joao@email.com
Posição 1 → Maria | 88988888888 | maria@email.com
```

A variável `cont` controla quantos contatos estão atualmente cadastrados.

---

## 🗑️ Processo de exclusão

Quando um contato é excluído, o sistema:

1. Procura o nome informado;
2. Identifica o índice do contato;
3. Desloca os contatos seguintes uma posição para trás;
4. Limpa a última posição;
5. Diminui o contador de contatos.

Esse processo evita deixar um espaço vazio no meio dos contatos cadastrados.

---

## ⚠️ Limitações atuais

A versão `v0.1.0` ainda possui algumas limitações:

* A capacidade inicial dos arrays é de **2 contatos**.
* Não há expansão automática dos arrays quando a capacidade é atingida.
* Os dados são mantidos apenas enquanto o programa está em execução.
* Os contatos não são salvos em arquivos ou banco de dados.
* Não existe funcionalidade para editar um contato.
* Não há validação específica de celular ou e-mail.

---

## 🚀 Melhorias futuras

Possíveis evoluções do projeto:

* [ ] Permitir mais contatos;
* [ ] Implementar expansão automática da capacidade;
* [ ] Editar contatos;
* [ ] Salvar contatos em arquivo;
* [ ] Utilizar banco de dados;
* [ ] Validar e-mails;
* [ ] Validar números de telefone;
* [ ] Criar uma classe `Contato`;
* [ ] Utilizar `ArrayList`;
* [ ] Criar uma interface gráfica;
* [ ] Implementar ordenação dos contatos.

---

## 🎯 Objetivo

O projeto tem como objetivo praticar conceitos fundamentais de **programação em Java**, especialmente:

* Arrays;
* Variáveis;
* Loops;
* Condicionais;
* `switch`;
* Entrada de dados;
* Manipulação de Strings;
* Busca de elementos;
* Remoção e reorganização de elementos.

---

## 📌 Versão

**v0.1.0**

Esta versão representa uma evolução da aplicação inicial, passando de um único contato para o gerenciamento de múltiplos contatos.

