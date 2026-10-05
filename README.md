# 📱 Agenda de Contatos

Projeto didático de **Agenda de Contatos desenvolvido em Java** na disciplina de **Programação Orientada a Objetos (POO)**. Criado para praticar conceitos fundamentais de programação e acompanhar a evolução da organização, estruturação e persistência de dados de um projeto.

O projeto começou como uma aplicação simples e evoluiu gradualmente, passando por variáveis, arrays, listas, métodos e, atualmente, uma estrutura dividida em diferentes classes com gravação de dados em arquivo.

---

## 📌 Versão atual

### `V.2.1.0`

Nesta versão, foi introduzida a classe **`Persistencia`** para salvar e carregar os contatos em um arquivo de texto (`contatos.txt`).

* **Carregamento automático:** Os dados são lidos do arquivo ao iniciar a aplicação.
* **Salvamento automático:** Os dados são gravados no arquivo ao optar por sair do sistema.

A estrutura modular foi expandida e agora divide o projeto em quatro classes principais:

```text
Principal.java
Agenda.java
Uteis.java
Persistencia.java
```

---

# 🚀 Funcionalidades

O sistema possui atualmente um CRUD básico e persistência:

| Opção | Funcionalidade                |
| ----: | ----------------------------- |
|     1 | ➕ Adicionar contato            |
|     2 | 📋 Listar contatos             |
|     3 | 🔎 Procurar contato            |
|     4 | ✏️ Alterar contato             |
|     5 | 🗑️ Excluir contato            |
|     6 | 🚪 Sair (com salvamento)      |
|     7 | ℹ️ Informações sobre a Agenda  |
|   --- | 💾 Persistência em arquivo     |

---

# 🛠️ Tecnologias utilizadas

* ☕ **Java**
* `List` e `ArrayList`
* I/O (Entrada e Saída): `FileWriter`, `PrintWriter`, `BufferedReader`
* `Scanner` e `JOptionPane`
* Estruturas de controle: `while`, `switch`, `for`, `if-else`
* Métodos `static`
* Tipos primitivos: `boolean`
* Métodos de String: `equalsIgnoreCase()`
* Métodos de Lista: `add()`, `get()`, `set()`, `remove()`, `size()`
* Pacotes Java

---

# 📂 Estrutura do projeto

O projeto utiliza o pacote:

```java
package br.edu.principal;
```

Estrutura atual:

```text
Agenda-Contatos/
├── .gitignore
├── README.md
└── src/
    └── br/
        └── edu/
            └── principal/
                ├── Principal.java
                ├── Agenda.java
                ├── Uteis.java
                └── Persistencia.java
```

---

# 🧩 Organização das classes

## `Principal.java`

Responsável pelo **fluxo principal da aplicação**. Suas responsabilidades são:

* Criar as listas de contatos;
* Acionar o carregamento inicial dos dados via classe `Persistencia`;
* Inicializar o programa e o `Scanner`;
* Controlar o loop `while`;
* Receber a opção do usuário e encaminhar cada opção para a classe responsável;
* Acionar o salvamento dos dados ao encerrar.

---

## `Agenda.java`

A classe `Agenda` concentra as funcionalidades diretamente relacionadas ao CRUD dos contatos.

| Método        | Responsabilidade              |
| ------------- | ----------------------------- |
| `adicionar()` | Cadastra um novo contato      |
| `listar()`    | Exibe os contatos cadastrados |
| `pesquisar()` | Procura um contato pelo nome  |
| `atualizar()` | Altera os dados de um contato |
| `excluir()`   | Remove um contato             |

Essa separação deixa a classe `Principal` mais limpa e facilita a manutenção do sistema.

---

## `Persistencia.java`

Nova classe responsável pela gravação e leitura física dos dados, garantindo que os contatos não sejam perdidos ao fechar o programa.

| Método       | Responsabilidade                                    |
| ------------ | --------------------------------------------------- |
| `carregar()` | Lê `contatos.txt` e preenche as listas na inicialização |
| `salvar()`   | Grava as listas no `contatos.txt` ao encerrar o sistema |

---

## `Uteis.java`

A classe `Uteis` concentra funcionalidades auxiliares do programa e interface.

| Método                  | Responsabilidade                  |
| ----------------------- | --------------------------------- |
| `mostraInicializacao()` | Exibe o título e a versão         |
| `mostraMenu()`          | Exibe o menu                      |
| `selecionaOpcao()`      | Recebe a opção escolhida          |
| `sair()`                | Controla o encerramento           |
| `sobre()`               | Exibe informações usando `JOptionPane` |

---

# 🔄 Arquitetura atual

A organização do projeto pode ser representada da seguinte forma:

```text
                 ┌─────────────────┐
                 │    Principal    │
                 │                 │
                 │ Fluxo principal │
                 └────┬───────┬────┘
                      │       │
     ┌────────────────┴───────┴────────────────┐
     │                │                        │
     ▼                ▼                        ▼
┌───────────────┐ ┌────────────────┐ ┌────────────────┐
│    Agenda     │ │  Persistencia  │ │     Uteis      │
│               │ │                │ │                │
│ Adicionar     │ │ Carregar dados │ │ Inicialização  │
│ Listar        │ │ Salvar dados   │ │ Menu           │
│ Pesquisar     │ │                │ │ Selecionar     │
│ Atualizar     │ │                │ │ Sair           │
│ Excluir       │ │                │ │ Sobre          │
└───────────────┘ └────────────────┘ └────────────────┘
```

---

# 📈 Evolução do projeto

| Versão | Estrutura | Principais conceitos |
|---|---|---|
| **V.0.0.0** | Variáveis simples | `String`, `Scanner`, `if-else`, `switch`, `while` |
| **V.0.1.0** | Arrays | Vetores, índices, `for` e capacidade fixa |
| **V.0.2.0** | `List` + `ArrayList` | Coleções, tamanho dinâmico, `add()`, `get()`, `remove()`, `size()` |
| **V.0.3.0** | `List` + `ArrayList` | Alteração de contatos com `set()` e CRUD |
| **V.1.0.0** | Métodos | Organização do código em métodos |
| **V.1.1.0** | Classes `Agenda` e `Uteis` | Separação de responsabilidades e organização do código |
| **V.1.1.1** | Classes `Agenda` e `Uteis` | Correção do encerramento do sistema e opção "Sobre" |
| **V.2.1.0** | Classe `Persistencia` | Persistência de dados em arquivos (`FileWriter`, `PrintWriter`, `BufferedReader`) |

### Detalhes das Versões Anteriores

* **V.0.0.0 — Primeiro protótipo:** Cadastro de apenas um contato usando variáveis
