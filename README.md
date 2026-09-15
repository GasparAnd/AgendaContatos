# 📱 Agenda de Contatos

Sistema de **Agenda de Contatos desenvolvido em Java**, criado para praticar conceitos fundamentais de programação e acompanhar a evolução da organização e estruturação de um projeto.

O projeto começou como uma aplicação simples e evoluiu gradualmente, passando por arrays, listas, métodos e, atualmente, uma estrutura dividida em diferentes classes.

---

## 📌 Versão atual

### `v1.1.1`

Nesta versão, foi realizada uma **correção no funcionamento da opção de saída do programa**.

Também foi mantida a estrutura modular introduzida na `v1.1.0`, dividindo o projeto em três classes:

```text
Principal.java
Agenda.java
Uteis.java
```

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
|     7 | ℹ️ Informações sobre a Agenda |

---

# 🛠️ Tecnologias utilizadas

* ☕ **Java**
* `List`
* `ArrayList`
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

O projeto utiliza o pacote:

```java
package br.edu.principal;
```

Estrutura atual:

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

Responsável pelo **fluxo principal da aplicação**.

Suas responsabilidades são:

* Criar as listas de contatos;
* Criar o `Scanner`;
* Inicializar o programa;
* Controlar o `while`;
* Receber a opção do usuário;
* Encaminhar cada opção para a classe responsável.

O menu utiliza um `switch` para direcionar as operações:

```java
switch (opcao) {
    case 1 -> Agenda.adicionar(sc, nomes, celulares, emails);
    case 2 -> Agenda.listar(nomes, celulares, emails);
    case 3 -> Agenda.pesquisar(sc, nomes, celulares, emails);
    case 4 -> Agenda.atualizar(sc, nomes, celulares, emails);
    case 5 -> Agenda.excluir(sc, nomes, celulares, emails);
    case 6 -> continuar = Uteis.sair();
    case 7 -> Uteis.sobre();
    default -> System.out.println("Opção inválida!");
}
```

---

## `Agenda.java`

A classe `Agenda` concentra as funcionalidades diretamente relacionadas aos contatos.

### Métodos

| Método        | Responsabilidade              |
| ------------- | ----------------------------- |
| `adicionar()` | Cadastra um novo contato      |
| `listar()`    | Exibe os contatos cadastrados |
| `pesquisar()` | Procura um contato pelo nome  |
| `atualizar()` | Altera os dados de um contato |
| `excluir()`   | Remove um contato             |

Essa separação deixa a classe `Principal` mais limpa e facilita a manutenção do sistema.

---

## `Uteis.java`

A classe `Uteis` concentra funcionalidades auxiliares do programa.

### Métodos

| Método                  | Responsabilidade                  |
| ----------------------- | --------------------------------- |
| `mostraInicializacao()` | Exibe o título e a versão         |
| `mostraMenu()`          | Exibe o menu                      |
| `selecionaOpcao()`      | Recebe a opção escolhida          |
| `sair()`                | Encerra o programa                |
| `sobre()`               | Exibe informações sobre o projeto |

A classe utiliza `JOptionPane` na funcionalidade **Sobre**.

---

# ➕ Adicionar contato

A opção **Adicionar contato** solicita:

```text
Digite o nome:
Digite o celular:
Digite o email:
```

Os dados são armazenados nas listas através do método:

```java
add()
```

Após o cadastro, o programa informa:

```text
Contato adicionado com sucesso!
```

---

# 📋 Listar contatos

A opção **Listar contatos** verifica se existem contatos cadastrados.

Caso a agenda esteja vazia:

```text
Nenhum contato cadastrado!
```

Caso existam contatos, o programa percorre as listas utilizando um `for` e exibe:

* Nome;
* Celular;
* Email.

---

# 🔎 Procurar contato

A pesquisa é realizada através do nome.

O método utiliza:

```java
equalsIgnoreCase()
```

Assim, a pesquisa não diferencia letras maiúsculas e minúsculas.

Exemplo:

```text
João
joão
JOÃO
```

podem ser encontrados durante a pesquisa.

A variável `boolean encontrado` controla se o contato foi localizado.

---

# ✏️ Alterar contato

A opção **Alterar contato** procura um contato pelo nome.

Após encontrar sua posição, o programa solicita:

* Novo nome;
* Novo celular;
* Novo email.

Os valores são atualizados utilizando:

```java
set()
```

---

# 🗑️ Excluir contato

A opção **Excluir contato** procura o contato pelo nome.

Quando encontrado, os dados são removidos das três listas:

```java
nomes.remove(i);
celulares.remove(i);
emails.remove(i);
```

O `break` interrompe a busca após a exclusão.

---

# 🚪 Encerramento do programa

Na versão `v1.1.0`, existia um problema no método `sair()`.

O método recebia `continuar` como parâmetro:

```java
Uteis.sair(continuar);
```

Porém, alterações feitas em um `boolean` recebido como parâmetro não modificavam a variável original da classe `Principal`.

Na versão `v1.1.1`, o funcionamento foi corrigido.

Agora:

```java
case 6 -> continuar = Uteis.sair();
```

E o método:

```java
public static boolean sair() {
    System.out.println("Saindo da Agenda de Contatos...");
    return false;
}
```

Quando `false` é retornado, a variável `continuar` também recebe `false`:

```text
continuar = false
       ↓
while (continuar)
       ↓
   encerra
```

Dessa forma, a opção **Sair** passa a encerrar corretamente o programa.

---

# ℹ️ Sobre

A opção **7 — Informações Sobre a Agenda de Contatos** utiliza `JOptionPane` para exibir uma mensagem em uma janela.

Atualmente:

```text
Desenvolvido por Roger M. Sarmento!
```

---

# 💾 Armazenamento dos contatos

Os contatos são armazenados utilizando três listas:

```java
List<String> nomes = new ArrayList<>();
List<String> celulares = new ArrayList<>();
List<String> emails = new ArrayList<>();
```

Cada posição representa um contato.

Exemplo:

```text
Índice 0

nomes[0]      → João
celulares[0]  → 99999-9999
emails[0]     → joao@email.com
```

As três listas utilizam o mesmo índice para manter os dados relacionados.

---

# 🔄 Arquitetura atual

A organização do projeto pode ser representada da seguinte forma:

```text
                 ┌─────────────────┐
                 │    Principal    │
                 │                 │
                 │ Fluxo principal │
                 └────────┬────────┘
                          │
              ┌───────────┴───────────┐
              │                       │
              ▼                       ▼
      ┌───────────────┐       ┌────────────────┐
      │    Agenda     │       │     Uteis      │
      │               │       │                │
      │ Adicionar     │       │ Inicialização  │
      │ Listar        │       │ Menu           │
      │ Pesquisar     │       │ Selecionar     │
      │ Atualizar     │       │ Sair           │
      │ Excluir       │       │ Sobre          │
      └───────────────┘       └────────────────┘
```

---

# 📈 Evolução do projeto

## `v0.0.0` — Primeiro protótipo

* Cadastro de apenas um contato.
* Utilização de variáveis `String`.

## `v0.1.0` — Múltiplos contatos

* Cadastro de vários contatos.
* Utilização de arrays.
* Capacidade inicialmente limitada.

## `v0.2.0` — Utilização de listas

* Substituição dos arrays por `List` e `ArrayList`.
* Cadastro de vários contatos sem tamanho fixo.

## `v0.3.0` — Atualização de contatos

* Adicionada a função de alterar contatos.
* Menu expandido.

## `v1.0.0` — Organização por métodos

* Funcionalidades separadas em métodos.
* Código mais organizado.
* Utilização de `boolean` para controle do programa.
* Melhor separação das responsabilidades.

## `v1.1.0` — Modularização

* Criação da classe `Agenda`.
* Criação da classe `Uteis`.
* Separação das responsabilidades entre as classes.
* `Principal` passou a controlar o fluxo principal.
* `Agenda` passou a gerenciar os contatos.
* `Uteis` passou a reunir funcionalidades auxiliares.
* Adicionada a opção **7 — Sobre**.
* Adicionado `JOptionPane`.

## `v1.1.1` — Correção do encerramento

* Corrigido o funcionamento da opção **Sair**.
* `Uteis.sair()` passou a retornar `boolean`.
* `Principal` utiliza o retorno para atualizar `continuar`.
* O `while` agora é encerrado corretamente quando o usuário escolhe a opção 6.
* Versão exibida na inicialização atualizada para `v1.1.1`.

---

# 🎯 Objetivo do projeto

O principal objetivo da Agenda de Contatos é acompanhar a evolução do aprendizado em **Java**, aplicando novos conceitos conforme o projeto cresce.

A evolução atual é:

```text
Variáveis
    ↓
Arrays
    ↓
List / ArrayList
    ↓
Estruturas de repetição
    ↓
Condicionais
    ↓
Métodos
    ↓
Boolean
    ↓
Separação de responsabilidades
    ↓
Múltiplas classes
    ↓
Organização do projeto
    ↓
Correção e melhoria do código
```

---

# 🔮 Próximas melhorias

Possíveis funcionalidades para versões futuras:

* [ ] Criar uma classe `Contato`;
* [ ] Aplicar Programação Orientada a Objetos;
* [ ] Validar nome, celular e email;
* [ ] Impedir contatos duplicados;
* [ ] Ordenar contatos;
* [ ] Salvar contatos em arquivos;
* [ ] Utilizar banco de dados;
* [ ] Criar interface gráfica;
* [ ] Organizar o projeto em diferentes pacotes;
* [ ] Melhorar a interface do sistema.

---

# 👨‍💻 Autor

**Andresson Viana Gaspar**

Projeto desenvolvido para **estudo e prática de Java**, acompanhando a evolução dos fundamentos de programação, organização de código e desenvolvimento de aplicações.

> 🚀 **Aprendendo, praticando e evoluindo a cada versão.**
