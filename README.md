# 📱 Agenda de Contatos

Aplicação de **Agenda de Contatos desenvolvida em Java**, executada através do terminal. O sistema permite cadastrar, listar, pesquisar, alterar e excluir contatos de forma simples e interativa.

> **Versão:** `0.3.0`
> **Status:** Em desenvolvimento

---

## 📖 Sobre o projeto

A **Agenda de Contatos** é uma aplicação de console desenvolvida em Java com o objetivo de realizar o gerenciamento básico de contatos.

Nesta versão, o projeto utiliza **`List` e `ArrayList`** para armazenar os nomes, números de celular e e-mails dos contatos. Além das funcionalidades já existentes, a versão `0.3.0` adiciona a possibilidade de **alterar os dados de um contato cadastrado**.

O programa utiliza um menu interativo que permanece em execução até que o usuário escolha a opção **6 - Sair**.

---

## ✨ Funcionalidades

### ➕ Adicionar contato

Permite cadastrar um novo contato informando:

* Nome;
* Celular;
* E-mail.

Os dados são armazenados nas respectivas listas utilizando o método `add()`.

---

### 📋 Listar contatos

Exibe todos os contatos cadastrados.

Para cada contato são apresentados:

* Nome;
* Celular;
* E-mail.

Caso não existam contatos cadastrados, o sistema informa que nenhum contato foi encontrado.

---

### 🔎 Procurar contato

Permite pesquisar um contato através do nome.

A pesquisa utiliza `equalsIgnoreCase()`, permitindo encontrar o contato independentemente de o nome ter sido digitado com letras maiúsculas ou minúsculas.

Exemplo:

```text
Digite o nome do contato: joao
```

Também será possível encontrar um contato cadastrado como:

```text
Joao
```

---

### ✏️ Alterar contato

A versão `0.3.0` adiciona a funcionalidade de **alteração de contatos**.

Primeiro, o usuário informa o nome do contato que deseja alterar. Depois de localizado, o sistema solicita os novos dados:

* Novo nome;
* Novo celular;
* Novo e-mail.

Os dados são atualizados utilizando o método `set()`.

---

### 🗑️ Excluir contato

Permite excluir um contato através do nome.

Quando o contato é encontrado, seus dados são removidos das três listas utilizando o método `remove()`.

Após a exclusão, o sistema informa:

```text
Contato excluído com sucesso!
```

Caso o contato não seja encontrado, uma mensagem informativa é exibida.

---

### 🚪 Sair

A opção **6 - Sair** encerra a execução da agenda.

Ao selecionar essa opção, o sistema apresenta:

```text
Saindo da Agenda de Contatos...
```

---

## 🖥️ Menu do sistema

A versão `0.3.0` possui o seguinte menu:

```text
==========================
    AGENDA DE CONTATOS
        V.0.3.0
==========================
Bem-vindo!

1-Adicionar contato
2-Listar contatos
3-Procurar contato
4-Alterar contato
5-Excluir contato
6-Sair
```

---

## 🛠️ Tecnologias utilizadas

* **Java**
* `Scanner`
* `List`
* `ArrayList`
* Estruturas condicionais
* Estruturas de repetição
* `switch`
* `equalsIgnoreCase()`
* `add()`
* `get()`
* `set()`
* `remove()`

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

Verifique a instalação do Java:

```bash
java -version
```

Verifique o compilador:

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

> Caso esteja utilizando a estrutura de pacotes do projeto, a compilação e execução devem respeitar a organização de diretórios correspondente ao pacote `br.edu.principal`.

---

## 🧠 Funcionamento interno

O sistema utiliza três listas principais:

```java
List<String> nomes = new ArrayList<>();
List<String> celulares = new ArrayList<>();
List<String> emails = new ArrayList<>();
```

Cada índice representa um contato.

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

Dessa forma, os dados relacionados ao mesmo contato permanecem na mesma posição das três listas.

---

## 🔄 Alteração de contatos

Para alterar um contato, o programa primeiro procura a posição correspondente ao nome informado.

Quando encontra o contato, a posição é armazenada na variável `posicao`.

Depois, os métodos `set()` são utilizados para substituir os dados antigos:

```text
nomes.set(posicao, novoNome)
celulares.set(posicao, novoCelular)
emails.set(posicao, novoEmail)
```

Assim, os dados do contato são atualizados sem precisar criar um novo registro.

---

## 🗑️ Processo de exclusão

A exclusão funciona procurando o contato pelo nome.

Quando o contato é encontrado, o sistema remove o mesmo índice das três listas:

```text
nomes.remove(i)
celulares.remove(i)
emails.remove(i)
```

Isso mantém os dados dos contatos sincronizados.

---

## ⚠️ Limitações atuais

A versão `0.3.0` ainda possui algumas limitações:

* Os dados ficam armazenados somente durante a execução;
* Ao fechar o programa, os contatos são perdidos;
* Não existe armazenamento em arquivos;
* Não existe banco de dados;
* Não há validação específica de e-mail;
* Não há validação específica de número de celular;
* O sistema utiliza três listas separadas para armazenar os dados de cada contato.

---

## 🚀 Melhorias futuras

Possíveis funcionalidades para próximas versões:

* [ ] Salvar contatos em arquivo;
* [ ] Implementar banco de dados;
* [ ] Criar uma classe `Contato`;
* [ ] Utilizar orientação a objetos;
* [ ] Unificar os dados em uma estrutura de contato;
* [ ] Validar e-mails;
* [ ] Validar números de telefone;
* [ ] Ordenar contatos alfabeticamente;
* [ ] Criar uma interface gráfica;
* [ ] Adicionar confirmação antes de excluir;
* [ ] Permitir busca por celular ou e-mail.

---

## 🎯 Objetivo do projeto

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
* Adição de elementos;
* Alteração de elementos;
* Remoção de elementos.

---

## 📌 Histórico de versões

### `v0.3.0` — Atual

**Novidades:**

* ✏️ Adicionada alteração de contatos;
* 📋 Menu atualizado;
* 🔢 Menu passou a possuir 6 opções;
* 🗑️ Exclusão de contatos mantida;
* 🔎 Pesquisa de contatos mantida;
* 📱 Cadastro e listagem de contatos mantidos.

### `v0.2.0`

* Utilização de `List` e `ArrayList`;
* Cadastro de múltiplos contatos;
* Listagem de contatos;
* Pesquisa de contatos;
* Exclusão de contatos.

### `v0.1.0`

* Primeira versão com suporte a múltiplos contatos utilizando arrays.

---

## 📄 Licença

Este projeto foi desenvolvido para fins **educacionais e de aprendizado em programação Java**.
