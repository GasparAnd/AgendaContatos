# 📱 Agenda de Contatos

Sistema de **Agenda de Contatos desenvolvido em Java**, criado para praticar conceitos fundamentais de programação e evoluir gradualmente a organização, estrutura e manutenção do código.

O projeto passou por diversas versões, começando com um cadastro simples e evoluindo para uma aplicação organizada em **três classes**, cada uma com uma responsabilidade específica.

---

## 📌 Versão atual

### `v1.1.0`

Nesta versão, o projeto foi reorganizado em **três classes principais**:

```text
Principal.java
Agenda.java
Uteis.java
```

Essa divisão permite separar melhor as responsabilidades do programa, deixando o código mais organizado e preparado para futuras funcionalidades.

Também foi adicionada a opção **7 — Informações Sobre a Agenda de Contatos**.

---

# 🚀 Funcionalidades

O sistema possui atualmente:

| Opção | Funcionalidade                |
| ----: | ----------------------------- |
|     1 | ➕ Adicionar contato           |
|     2 | 📋 Listar contatos            |
|     3 | 🔎 Procurar contato           |
|     4 | ✏️ Alterar contato            |
|     5 | 🗑️ Excluir contato           |
|     6 | 🚪 Sair                       |
|     7 | ℹ️ Informações sobre a agenda |

---

# 🛠️ Tecnologias utilizadas

* ☕ **Java**
* `ArrayList`
* `List`
* `Scanner`
* `JOptionPane`
* `while`
* `switch`
* Métodos `static`
* `boolean`
* `equalsIgnoreCase()`
* `add()`
* `get()`
* `set()`
* `remove()`
* Pacotes Java

---

# 📂 Estrutura do projeto

O projeto está organizado dentro do pacote:

```java
package br.edu.principal;
```

Estrutura:

```text
src/
└── br/
    └── edu/
        └── principal/
            ├── Principal.java
            ├── Agenda.java
            └── Uteis.java
```

---

# 🧩 Organização das classes

## `Principal.java`

É a classe responsável pelo **fluxo principal da aplicação**.

Suas responsabilidades incluem:

* Criar as listas de contatos;
* Criar o `Scanner`;
* Iniciar o programa;
* Controlar o `while`;
* Receber a opção escolhida;
* Direcionar cada opção para o método correspondente.

Exemplo:

```java
switch (opcao) {
    case 1 -> Agenda.adicionar(sc, nomes, celulares, emails);
    case 2 -> Agenda.listar(nomes, celulares, emails);
    case 3 -> Agenda.pesquisar(sc, nomes, celulares, emails);
    case 4 -> Agenda.atualizar(sc, nomes, celulares, emails);
    case 5 -> Agenda.excluir(sc, nomes, celulares, emails);
    case 6 -> Uteis.sair(continuar);
    case 7 -> Uteis.sobre();
}
```

---

## `Agenda.java`

A classe `Agenda` concentra as operações relacionadas diretamente aos contatos.

### Métodos:

| Método        | Responsabilidade    |
| ------------- | ------------------- |
| `adicionar()` | Cadastra um contato |
| `listar()`    | Exibe os contatos   |
| `pesquisar()` | Procura um contato  |
| `atualizar()` | Altera um contato   |
| `excluir()`   | Remove um contato   |

Essa separação evita colocar toda a lógica de gerenciamento dentro da classe `Principal`.

---

## `Uteis.java`

A classe `Uteis` reúne funcionalidades auxiliares do programa.

### Métodos:

| Método                  | Responsabilidade                  |
| ----------------------- | --------------------------------- |
| `mostraInicializacao()` | Exibe o título e a versão         |
| `mostraMenu()`          | Exibe o menu                      |
| `selecionaOpcao()`      | Recebe a opção do usuário         |
| `sair()`                | Exibe a mensagem de saída         |
| `sobre()`               | Exibe informações sobre o projeto |

A classe também utiliza:

```java
import javax.swing.JOptionPane;
```

para apresentar as informações da opção **Sobre** através de uma janela.

---

# 💾 Armazenamento dos contatos

Os contatos são armazenados utilizando três listas:

```java
List<String> nomes = new ArrayList<>();
List<String> celula
```
