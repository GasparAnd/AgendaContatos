# 📱 Agenda de Contatos

Sistema de agenda de contatos desenvolvido em **Java**, com o objetivo de praticar conceitos fundamentais de programação, como listas, métodos, estruturas de repetição, condicionais e entrada de dados pelo teclado.

## 📌 Versão

**v1.0.0**

Nesta versão, o código foi reorganizado utilizando **métodos**, deixando o programa mais organizado e fácil de entender e manter.

---

## 🚀 Funcionalidades

O sistema possui as seguintes opções:

1. **Adicionar contato**
2. **Listar contatos**
3. **Procurar contato**
4. **Alterar contato**
5. **Excluir contato**
6. **Sair do programa**

---

## 🛠️ Tecnologias utilizadas

* **Java**
* `ArrayList`
* `List`
* `Scanner`
* Estrutura `while`
* Estrutura `switch`
* Métodos
* Variável `boolean`

---

## 📂 Estrutura do programa

O programa foi dividido em métodos para separar cada função da agenda:

| Método                  | Função                                |
| ----------------------- | ------------------------------------- |
| `mostraInicializacao()` | Exibe o título e a versão do programa |
| `mostraMenu()`          | Exibe as opções do menu               |
| `selecionaOpcao()`      | Recebe a opção escolhida pelo usuário |
| `adicionar()`           | Cadastra um novo contato              |
| `listar()`              | Exibe todos os contatos               |
| `pesquisar()`           | Procura um contato pelo nome          |
| `atualizar()`           | Altera os dados de um contato         |
| `excluir()`             | Remove um contato                     |
| `sair()`                | Encerra o programa                    |

---

## 📋 Funcionamento

Ao iniciar o programa, uma mensagem de boas-vindas é exibida:

```text
==========================
     AGENDA DE CONTATOS
          v1.0.0
==========================
Bem-vindo!
```

Em seguida, o menu é apresentado:

```text
1 - Adicionar contato
2 - Listar contatos
3 - Procurar contato
4 - Alterar contato
5 - Excluir contato
6 - Sair
```

O usuário escolhe uma opção e o programa executa o método correspondente.

---

## 💾 Armazenamento dos contatos

Os contatos são armazenados em três listas:

```java
List<String> nomes = new ArrayList<>();
List<String> celulares = new ArrayList<>();
List<String> emails = new ArrayList<>();
```

Cada posição representa um contato.

Por exemplo:

```text
nomes[0]       → João
celulares[0]   → 99999-9999
emails[0]      → joao@email.com
```

As três listas utilizam a mesma posição para manter os dados do contato relacionados.

---

## 🔎 Pesquisa de contatos

A pesquisa é realizada pelo nome utilizando:

```java
equalsIgnoreCase()
```

Isso permite procurar o contato sem diferenciar letras maiúsculas e minúsculas.

Por exemplo:

```text
João
joão
JOÃO
```

podem ser encontrados como o mesmo nome.

---

## ✏️ Alteração de contatos

Na opção **Alterar contato**, o programa primeiro procura o contato pelo nome.

Depois, o usuário pode informar:

* Novo nome
* Novo celular
* Novo email

Os valores são atualizados nas listas utilizando:

```java
set()
```

---

## 🗑️ Exclusão de contatos

Na opção **Excluir contato**, o programa procura o contato pelo nome e remove os dados das três listas utilizando:

```java
remove()
```

A mesma posição é removida das três listas para manter os dados organizados.

---

## 🔴 Saída do programa

Na versão atual, o método `sair()` retorna um valor `boolean`:

```java
public static boolean sair() {
    System.out.println("Saindo da Agenda de Contatos...");
    return false;
}
```

No `main`, esse valor é utilizado para alterar a variável `continuar`:

```java
case 6 -> continuar = sair();
```

Quando o método retorna `false`, a variável `continuar` também passa a ser `false`.

Como o menu está dentro de:

```java
while (continuar)
```

o programa encerra quando `continuar` recebe `false`.

---

## 📈 Evolução do projeto

### v0.0.0

* Cadastro de apenas um contato.
* Uso de variáveis `String`.

### v0.1.0

* Cadastro de vários contatos.
* Uso de arrays.
* Capacidade inicial limitada.

### v0.2.0

* Substituição dos arrays por `List` e `ArrayList`.
* Cadastro de vários contatos sem tamanho fixo.

### v0.3.0

* Adicionada a função de **alterar contatos**.
* Menu passou a possuir 6 opções.

### v1.0.0

* Código reorganizado em **métodos**.
* Cada funcionalidade passou a ter seu próprio método.
* Melhor organização e separação das responsabilidades.
* Utilização de `boolean` para controlar a execução do menu.
* Método `sair()` passou a retornar `false` para encerrar o programa.

---

## 🎯 Objetivo da versão 1.0.0

A principal mudança desta versão foi a **organização do código**.

Em vez de colocar toda a lógica dentro do `main`, cada funcionalidade foi separada em um método específico.

Isso torna o código:

* Mais organizado;
* Mais fácil de entender;
* Mais fácil de corrigir;
* Mais fácil de atualizar;
* Mais próximo de uma estrutura profissional de programação.

---

## 👨‍💻 Autor

**Andresson Viana Gaspar**

Projeto desenvolvido para prática e aprendizado de **Java e Programação Orientada a Estruturas e Métodos**.
