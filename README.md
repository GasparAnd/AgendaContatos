📱 Agenda de Contatos

Projeto didático de Agenda de Contatos desenvolvido em Java na disciplina de Programação Orientada a Objetos (POO). Criado para praticar conceitos fundamentais de programação e acompanhar a evolução da organização, estruturação e persistência de dados de um projeto.

O projeto começou como uma aplicação simples e evoluiu gradualmente, passando por variáveis, arrays, listas, métodos, persistência em arquivos e introdução a classes e objetos.

📌 Versão atual

V.3.0.0

Nesta versão, foi introduzida a classe Contato.java, responsável por representar os dados de um contato por meio dos atributos nome, celular e email.

A classe permite criar objetos que agrupam as informações de cada contato, introduzindo conceitos fundamentais da Programação Orientada a Objetos.

O projeto mantém as funcionalidades de CRUD e persistência desenvolvidas nas versões anteriores. Entretanto, as operações da agenda ainda utilizam listas paralelas de String, e a integração completa dos objetos Contato está prevista para uma evolução futura.

Principais características
Introdução à classe Contato;
Criação e instanciação de objetos;
Atributos para nome, celular e e-mail;
Cadastro, listagem, pesquisa, atualização e exclusão de contatos;
Carregamento dos dados ao iniciar a aplicação;
Salvamento dos dados ao sair do sistema;
Organização do código em classes com responsabilidades distintas.
🚀 Funcionalidades
Opção	Funcionalidade
1	➕ Adicionar contato
2	📋 Listar contatos
3	🔎 Procurar contato
4	✏️ Alterar contato
5	🗑️ Excluir contato
6	🚪 Sair com salvamento
7	ℹ️ Informações sobre a Agenda
🛠️ Tecnologias utilizadas
☕ Java;
Classes e objetos;
List e ArrayList;
Entrada de dados com Scanner;
Interface com JOptionPane;
Entrada e saída de arquivos: FileWriter, PrintWriter e BufferedReader;
Estruturas de controle: while, switch, for e if-else;
Métodos static;
Tipo primitivo boolean;
Método de String equalsIgnoreCase();
Métodos de listas: add(), get(), set(), remove() e size();
Pacotes Java.
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

🧩 Organização das classes
Principal.java

Responsável pelo fluxo principal da aplicação.

Suas responsabilidades são:

Criar as listas de nomes, celulares e e-mails;
Acionar o carregamento inicial dos dados por meio da classe Persistencia;
Inicializar o programa e o Scanner;
Exibir a inicialização e o menu;
Controlar o laço while;
Receber a opção do usuário e encaminhar cada operação para a classe responsável;
Acionar o salvamento dos dados ao encerrar o sistema;
Fechar o Scanner ao finalizar a execução.

A classe também instancia um objeto Contato com dados de exemplo:

java
Contato contato1 = new Contato();

contato1.nome = "Arthur Dent";
contato1.celular = "4242-4242";
contato1.email = "arthur@galaxy.com";


Esse trecho demonstra a criação de um objeto e o acesso aos seus atributos.

Observação: o objeto contato1 ainda não está integrado às listas utilizadas pelo CRUD nem à persistência.

Contato.java

Classe introduzida na versão V.3.0.0, responsável por representar um contato.

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

A classe permite criar objetos que agrupam os dados de uma pessoa.

Exemplo:

java
Contato contato = new Contato();

contato.nome = "Arthur Dent";
contato.celular = "4242-4242";
contato.email = "arthur@galaxy.com";


Essa implementação introduz os conceitos de classe, objeto, atributo, instanciação e estado de um objeto.

Agenda.java

A classe Agenda concentra as funcionalidades relacionadas ao CRUD dos contatos.

Método	Responsabilidade
adicionar()	Cadastra um novo contato.
listar()	Exibe os contatos cadastrados.
pesquisar()	Procura um contato pelo nome.
atualizar()	Altera os dados de um contato.
excluir()	Remove um contato.

Os métodos trabalham atualmente com listas separadas de nomes, celulares e e-mails.

Essa organização mantém as operações do CRUD separadas do fluxo principal da aplicação.

Persistencia.java

Classe responsável pela leitura e gravação dos dados em arquivo de texto.

Método	Responsabilidade
carregarContatos()	Lê os dados do arquivo e preenche as listas utilizadas pela agenda.
salvarContatos()	Grava os dados das listas no arquivo de texto.

A persistência permite recuperar os contatos em execuções futuras.

O carregamento acontece na inicialização, enquanto o salvamento é acionado pela opção de saída do sistema.

Uteis.java

A classe Uteis concentra funcionalidades auxiliares relacionadas à interface e ao controle da aplicação.

Método	Responsabilidade
mostraInicializacao()	Exibe o título e a versão do programa.
mostraMenu()	Exibe as opções disponíveis.
selecionaOpcao()	Recebe a opção escolhida pelo usuário.
sair()	Controla o encerramento do sistema.
sobre()	Exibe informações sobre a aplicação utilizando JOptionPane.
🔄 Arquitetura atual

A organização do projeto pode ser representada da seguinte forma:

text
                 ┌─────────────────┐
                 │    Principal    │
                 │                 │
                 │ Fluxo principal │
                 └────┬───────┬────┘
                      │       │
     ┌────────────────┼───────┼────────────────┐
     │                │       │                │
     ▼                ▼       ▼                ▼
┌───────────────┐ ┌────────────────┐ ┌────────────────┐
│    Agenda     │ │  Persistencia  │ │     Uteis      │
│               │ │                │ │                │
│ Adicionar     │ │ Carregar dados │ │ Inicialização  │
│ Listar        │ │ Salvar dados   │ │ Menu           │
│ Pesquisar     │ │                │ │ Selecionar     │
│ Atualizar     │ │                │ │ Sair           │
│ Excluir       │ │                │ │ Sobre          │
└───────────────┘ └────────────────┘ └────────────────┘

                 ┌─────────────────┐
                 │     Contato     │
                 │                 │
                 │ Nome            │
                 │ Celular         │
                 │ E-mail          │
                 └─────────────────┘


Observação: a classe Contato já existe, mas ainda não participa diretamente das operações do CRUD ou da persistência. Sua integração completa poderá ser implementada em uma versão futura.

📈 Evolução do projeto
Versão	Estrutura	Principais conceitos
V.0.0.0	Variáveis simples	String, Scanner, if-else, switch e while
V.0.1.0	Arrays	Vetores, índices, for e capacidade fixa
V.0.2.0	List e ArrayList	Coleções dinâmicas e métodos de manipulação
V.0.3.0	Listas e CRUD	Alteração de contatos com set()
V.1.0.0	Métodos	Organização do código em métodos
V.1.1.0	Classes Agenda e Uteis	Separação de responsabilidades
V.1.1.1	Aprimoramentos	Correção do encerramento e opção Sobre
V.2.1.0	Classe Persistencia	Leitura e gravação de dados em arquivos
V.3.0.0	Classe Contato	Introdução a classes e objetos
🔮 Próximas melhorias

Algumas melhorias que poderão ser implementadas nas próximas versões:

Substituir as listas paralelas por uma única List<Contato>;
Integrar objetos Contato às operações do CRUD;
Criar um construtor para inicializar os atributos;
Aplicar encapsulamento com atributos private;
Implementar métodos getters e setters;
Adaptar a persistência para trabalhar diretamente com objetos Contato;
Validar os dados informados pelo usuário;
Aprimorar o tratamento de erros durante a leitura e gravação de arquivos;
Implementar testes para as funcionalidades do CRUD.
📌 Versão atual

V.3.0.0 — Introdução à Programação Orientada a Objetos.

Esta versão introduz a classe Contato, permitindo representar os dados de uma pessoa por meio de um objeto.

O projeto mantém as funcionalidades de CRUD, a organização em múltiplas classes e a persistência em arquivo de texto desenvolvidas nas versões anteriores.

A integração completa dos objetos com o armazenamento e as operações da agenda está prevista para uma evolução futura.

🏷️ Controle de versões

As versões do projeto podem ser organizadas por tags Git:

text
- v0
  - v0.0.0
  - v0.1.0
  - v0.2.0
  - v0.3.0

- v1
  - v1.0.0
  - v1.1.0
  - v1.1.1

- v2
  - v2.1.0

- v3
  - v3.0.0


As tags devem corresponder às versões efetivamente registradas no repositório.

📚 Considerações finais

A Agenda de Contatos é um projeto didático que acompanha a evolução do aprendizado de Java, desde os fundamentos da programação procedural até a introdução de conceitos de Programação Orientada a Objetos.

Cada versão acrescenta novos conhecimentos e aprimora a organização do código, passando por estruturas de dados, métodos, modularização, persistência de informações e criação de classes.

A versão V.3.0.0 representa o início da utilização de classes e objetos na modelagem dos contatos, preparando o projeto para futuras melhorias na arquitetura e na manutenção do sistema.
