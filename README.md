📱 Agenda de Contatos

Projeto didático desenvolvido em Java na disciplina de Programação Orientada a Objetos (POO). Seu objetivo é praticar conceitos fundamentais de programação e acompanhar a evolução da organização, estruturação e persistência de dados.

O projeto evolui de uma aplicação procedural simples para uma aplicação modular, incorporando coleções, métodos, persistência em arquivos e conceitos de Programação Orientada a Objetos.

🎯 Objetivo

Construir uma Agenda de Contatos completa, evoluindo gradualmente dos fundamentos da programação procedural para uma aplicação organizada com classes, objetos, coleções e persistência de dados.

📌 Versão atual

V.3.2.0 — Integração de objetos no CRUD e na persistência.

Nesta versão, a classe Contato passa a ser utilizada efetivamente em todas as operações da agenda.

As listas paralelas de nomes, celulares e e-mails foram substituídas por uma única lista de objetos:

java
List<Contato> contatos = new ArrayList<>();


Cada objeto Contato reúne as informações de uma pessoa, incluindo nome, celular e e-mail.

A classe Agenda realiza as operações de cadastro, listagem, pesquisa, atualização e exclusão diretamente sobre essa lista. A classe Persistencia também foi adaptada para carregar e salvar os objetos no arquivo contatos.txt.

Principais novidades
Utilização de List<Contato> como estrutura principal de armazenamento;
Integração da classe Contato com todas as operações do CRUD;
Cadastro de contatos por meio da criação de objetos;
Listagem utilizando for-each;
Pesquisa por nome utilizando equalsIgnoreCase();
Atualização direta dos atributos dos objetos;
Exclusão de objetos da lista;
Carregamento automático dos contatos ao iniciar a aplicação;
Salvamento dos contatos ao selecionar a opção de saída;
Tratamento de registros inválidos durante o carregamento do arquivo;
Organização das responsabilidades entre as classes Principal, Contato, Agenda, Uteis e Persistencia.
🚀 Funcionalidades

O sistema oferece operações básicas de gerenciamento de contatos, conhecidas como CRUD.

Opção	Funcionalidade
1	➕ Adicionar contato
2	📋 Listar contatos
3	🔎 Procurar contato
4	✏️ Alterar contato
5	🗑️ Excluir contato
6	🚪 Sair com salvamento dos dados
7	ℹ️ Informações sobre a Agenda
Operações CRUD
Create — Criar: cadastra um novo contato.
Read — Ler: lista e pesquisa os contatos cadastrados.
Update — Atualizar: modifica os dados de um contato existente.
Delete — Excluir: remove um contato da lista.
🛠️ Tecnologias e conceitos utilizados
☕ Java;
Programação Orientada a Objetos (POO);
Classes, objetos e atributos;
Instanciação de objetos com new;
Referências a objetos;
Interface List;
Implementação ArrayList;
Generics: List<Contato>;
Laço for-each;
Estruturas de controle while, switch, for e if-else;
Entrada de dados com Scanner;
Interface gráfica com JOptionPane;
Manipulação de arquivos com File, FileReader, BufferedReader, FileWriter e PrintWriter;
Tratamento de exceções com IOException;
Comparação de strings com equalsIgnoreCase();
Métodos de listas: add(), remove(), get(), isEmpty() e size();
Métodos static;
Tipo primitivo boolean;
Organização de classes em pacotes Java.
📂 Estrutura do projeto

O projeto utiliza o pacote:

java
package br.edu.principal;


Estrutura atual:

text
Agenda-Contatos/
├── .gitignore
├── README.md
└── src/
    └── br/
        └── edu/
            └── principal/
                ├── Principal.java
                ├── Contato.java
                ├── Agenda.java
                ├── Uteis.java
                └── Persistencia.java


O arquivo contatos.txt é criado no diretório de execução quando os dados são salvos. Sua localização exata depende de como a aplicação é executada.

🧩 Organização das classes
Principal.java

Responsável por inicializar a aplicação e controlar o fluxo principal do programa.

Principais responsabilidades:

Criar a lista List<Contato>;
Carregar os contatos salvos por meio da classe Persistencia;
Inicializar o Scanner;
Exibir a inicialização e o menu;
Controlar o laço principal com while;
Encaminhar as opções selecionadas para a classe Agenda;
Salvar os contatos antes de encerrar o sistema;
Fechar o Scanner ao finalizar a execução.

A lista principal é criada da seguinte forma:

java
List<Contato> contatos = new ArrayList<>();

Persistencia.carregarContatos(contatos);


Dessa maneira, todos os contatos carregados do arquivo ficam disponíveis para as operações da agenda.

O switch encaminha as operações para os métodos correspondentes:

java
switch (opcao) {
    case 1 -> Agenda.adicionar(sc, contatos);
    case 2 -> Agenda.listar(contatos);
    case 3 -> Agenda.pesquisar(sc, contatos);
    case 4 -> Agenda.atualizar(sc, contatos);
    case 5 -> Agenda.excluir(sc, contatos);
    case 6 -> {
        Persistencia.salvarContatos(contatos);
        continuar = Uteis.sair();
    }
    case 7 -> Uteis.sobre();
    default -> System.out.println("Opção inválida!");
}


Essa estrutura mantém o fluxo principal separado das operações específicas de gerenciamento dos contatos.

Contato.java

A classe Contato representa cada registro da agenda.

Código atual:

java
package br.edu.principal;

public class Contato {
    public String nome;
    public String celular;
    public String email;
}

Atributos
Atributo	Tipo	Descrição
nome	String	Armazena o nome do contato.
celular	String	Armazena o número de celular.
email	String	Armazena o endereço de e-mail.

Cada objeto reúne os dados relacionados a uma pessoa, evitando a necessidade de manter listas independentes para cada atributo.

Exemplo:

java
Contato contato = new Contato();

contato.nome = "Arthur Dent";
contato.celular = "4242-4242";
contato.email = "arthur@galaxy.com";


Nesta versão, os atributos são públicos e acessados diretamente. O encapsulamento com atributos private, construtores e métodos getters e setters poderá ser introduzido em uma versão futura.

Agenda.java

A classe Agenda concentra as funcionalidades do CRUD e trabalha diretamente com List<Contato>.

Método adicionar()

Recebe os dados informados pelo usuário, cria um objeto Contato, preenche seus atributos e adiciona o objeto à lista.

java
Contato contato = new Contato();

contato.nome = nome;
contato.celular = celular;
contato.email = email;

contatos.add(contato);


Cada cadastro cria um objeto independente, reunindo as informações de um único contato.

Método listar()

Verifica se a lista está vazia utilizando isEmpty().

Quando existem contatos cadastrados, percorre a lista com for-each e exibe os atributos de cada objeto.

java
for (Contato contato : contatos) {
    System.out.println("Nome: " + contato.nome);
    System.out.println("Celular: " + contato.celular);
    System.out.println("Email: " + contato.email);
}

Método pesquisar()

Percorre os objetos da lista e compara o nome informado pelo usuário com o nome de cada contato.

A comparação utiliza:

java
contato.nome.equalsIgnoreCase(nomeBusca)


O método equalsIgnoreCase() permite pesquisar sem diferenciar letras maiúsculas e minúsculas.

Por exemplo, uma pesquisa por arthur dent pode encontrar o contato cadastrado como Arthur Dent.

Método atualizar()

Procura o contato pelo nome e armazena sua referência na variável contatoEncontrado.

Quando o contato é localizado, os atributos são atualizados diretamente:

java
contatoEncontrado.nome = novoNome;
contatoEncontrado.celular = novoCelular;
contatoEncontrado.email = novoEmail;


Como a variável referencia o próprio objeto armazenado na lista, as alterações são realizadas no contato existente, sem a necessidade de substituí-lo por outro objeto.

Método excluir()

Localiza o objeto correspondente ao nome informado e remove esse objeto da lista:

java
contatos.remove(contatoExcluir);


A remoção é realizada diretamente sobre a coleção de objetos Contato.

Resumo dos métodos
Método	Responsabilidade
adicionar()	Cria um objeto e adiciona o contato à lista.
listar()	Exibe todos os contatos cadastrados.
pesquisar()	Procura contatos pelo nome.
atualizar()	Modifica os atributos de um contato existente.
excluir()	Remove um contato da lista.
Persistencia.java

A classe Persistencia é responsável por carregar e salvar os contatos em um arquivo de texto chamado contatos.txt.

Nesta versão, seus métodos trabalham diretamente com List<Contato>.

Método salvarContatos()

Recebe a lista de contatos e grava os dados de cada objeto no arquivo.

Cada contato é armazenado em uma linha, com os campos separados por ponto e vírgula:

text
Arthur Dent;4242-4242;arthur@galaxy.com
Ford Prefect;1234-5678;ford@galaxy.com
Trillian;9876-5432;trillian@galaxy.com


A gravação utiliza FileWriter e PrintWriter.

O trecho responsável pela montagem de cada registro é:

java
for (Contato contato : contatos) {
    String linha = contato.nome + ";" + contato.celular + ";" + contato.email;
    pw.println(linha);
}


Como o FileWriter é utilizado sem o modo de anexação, o arquivo é sobrescrito a cada salvamento. Assim, seu conteúdo passa a representar os contatos presentes na lista naquele momento.

Método carregarContatos()

Verifica se o arquivo existe e, caso exista, realiza a leitura linha a linha utilizando BufferedReader.

Cada linha é dividida nos três campos esperados:

java
String[] dados = linha.split(";");


Quando a linha contém os três campos, um novo objeto Contato é criado:

java
Contato contato = new Contato();

contato.nome = dados[0];
contato.celular = dados[1];
contato.email = dados[2];

contatos.add(contato);


O objeto é adicionado à lista, ficando disponível para as operações do CRUD.

Se a linha não apresentar os três campos esperados, o programa informa que o registro é inválido e continua a leitura.

Resumo dos métodos
Método	Responsabilidade
`carregarContatos
