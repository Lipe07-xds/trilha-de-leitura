# 📚 Trilha de Leitura

**Documento de Especificação de Software**

| Informação | Descrição |
|---|---|
| Projeto | Trilha de Leitura |
| Tipo | Aplicação Web |
| Autor | Filipe Xavier |
| Linguagem principal | JavaScript |
| Frontend | React + Vite |
| Armazenamento | LocalStorage |
| Versão | 1.0 |

---

## 1. TERMO DE ABERTURA DO PROJETO (PROJECT CHARTER)

### 1.1. Título do Projeto

**Trilha de Leitura — Organize suas leituras e acompanhe sua evolução.**

### 1.2. Problema Real

Muitas pessoas possuem o hábito ou o desejo de ler livros, mas enfrentam dificuldades para organizar suas leituras, acompanhar o progresso de cada obra e manter um registro dos livros concluídos.

Frequentemente, essas informações ficam distribuídas entre anotações físicas, aplicativos diferentes ou simplesmente são esquecidas. Isso dificulta o acompanhamento da evolução individual e a organização dos objetivos de leitura.

### 1.3. Proposta de Valor

O Trilha de Leitura propõe uma solução simples e acessível para centralizar o gerenciamento das leituras pessoais em um único ambiente.

A aplicação permitirá cadastrar livros, acompanhar o progresso por páginas, organizar as obras por status de leitura e registrar anotações pessoais, proporcionando ao usuário uma visão clara de sua jornada literária.

Seu principal diferencial é oferecer as funcionalidades essenciais para o acompanhamento de leituras em uma interface intuitiva, sem exigir cadastro de conta ou conexão com um servidor.

### 1.4. Escopo do Projeto

**Escopo In (Funcionalidades incluídas):**

- Cadastro de livros com título, autor, quantidade total de páginas e categoria.
- Edição e exclusão de livros cadastrados.
- Atualização da página atual de leitura.
- Organização dos livros por status: Quero Ler, Lendo e Concluído.
- Registro de anotações pessoais relacionadas aos livros.
- Exibição de estatísticas básicas, como quantidade de livros cadastrados, em andamento e concluídos.
- Armazenamento dos dados no navegador utilizando LocalStorage.

**Escopo Out (Funcionalidades não incluídas):**

- Criação de contas, autenticação e gerenciamento de usuários.
- Sincronização de dados entre diferentes dispositivos.
- Compartilhamento de livros, comentários ou interação entre leitores.
- Integração com APIs externas para busca automática de livros.
- Leitura de livros diretamente dentro da aplicação.
- Recomendações automáticas de livros por inteligência artificial.
- Aplicativo mobile nativo.

---

## 2. HISTÓRIAS DE USUÁRIO (USER STORIES)

As histórias de usuário representam as principais necessidades dos usuários em relação às funcionalidades do sistema.

**US01 — Cadastro de livros**

Como leitor, quero cadastrar os livros que pretendo ler ou que já estou lendo, para que eu possa organizar minhas obras em um único lugar.

**US02 — Acompanhamento de leitura**

Como leitor, quero atualizar a página em que parei de ler, para que eu possa acompanhar meu progresso e saber quanto falta para concluir cada livro.

**US03 — Organização por status**

Como leitor, quero organizar meus livros por status de leitura, para que eu consiga identificar facilmente quais pretendo ler, quais estou lendo e quais já concluí.

**US04 — Registro de anotações**

Como leitor, quero registrar anotações pessoais sobre cada livro, para que eu possa guardar pensamentos, reflexões e informações importantes durante a leitura.

**US05 — Visualização de estatísticas**

Como leitor, quero visualizar estatísticas da minha biblioteca, para que eu possa acompanhar minha evolução e a quantidade de livros já concluídos.

---

## 3. REQUISITOS DO SISTEMA

### 3.1. Requisitos Funcionais (RF)

Os requisitos funcionais descrevem as operações que o sistema deverá executar.

| Código | Descrição |
|---|---|
| RF01 | O sistema deve permitir cadastrar livros informando título, autor, quantidade total de páginas e categoria. |
| RF02 | O sistema deve permitir editar e excluir livros cadastrados. |
| RF03 | O sistema deve permitir atualizar a página atual de leitura de cada livro. |
| RF04 | O sistema deve organizar e exibir os livros conforme seus status: Quero Ler, Lendo e Concluído. |
| RF05 | O sistema deve permitir adicionar e editar anotações pessoais vinculadas a cada livro. |
| RF06 | O sistema deve calcular e exibir a porcentagem de progresso da leitura de cada livro. |
| RF07 | O sistema deve apresentar estatísticas com o total de livros cadastrados, em andamento e concluídos. |
| RF08 | O sistema deve salvar automaticamente as alterações realizadas, mantendo os dados disponíveis após o fechamento e a reabertura do navegador. |

### 3.2. Requisitos Não Funcionais (RNF)

Os requisitos não funcionais estabelecem critérios de qualidade e restrições técnicas para o sistema.

| Código | Descrição |
|---|---|
| RNF01 | A interface deve ser responsiva, permitindo a utilização em computadores, tablets e smartphones. |
| RNF02 | O sistema deve ser compatível com navegadores modernos, como Google Chrome, Microsoft Edge e Mozilla Firefox. |
| RNF03 | As operações de cadastro, edição, exclusão e atualização devem apresentar resposta em até 2 segundos em condições normais de utilização. |
| RNF04 | A aplicação deve utilizar o LocalStorage do navegador para persistir os dados, sem depender de um banco de dados externo. |
| RNF05 | A interface deve apresentar navegação intuitiva, com textos claros e identificação visual das principais funcionalidades. |

---

## 4. CASO DE USO PRINCIPAL & TRATAMENTO DE ERROS

### 4.1. Caso de Uso: Atualizar Progresso de Leitura

**Ator principal:** Leitor.

**Objetivo:** Permitir que o usuário atualize seu progresso em determinado livro e acompanhe sua evolução.

**Pré-condição:** O usuário deve possuir pelo menos um livro cadastrado no sistema.

**Fluxo principal:**

1. **Ação do usuário:** O leitor acessa sua biblioteca, seleciona um livro que esteja com o status "Lendo" e informa a página atual em que parou.
2. **Processamento do sistema:** O sistema verifica se o número informado é válido, garantindo que seja maior ou igual a zero e não ultrapasse a quantidade total de páginas do livro. Em seguida, calcula a porcentagem de progresso e atualiza o status caso a leitura tenha sido concluída.
3. **Retorno ao usuário:** O sistema salva as alterações no LocalStorage e apresenta o novo progresso na interface, exibindo a página atual e a porcentagem de leitura concluída.

**Pós-condição:** O progresso atualizado permanece salvo e disponível nas próximas utilizações do sistema.

### 4.2. Fluxo de Exceção e Tratamento de Erros

O sistema deverá tratar situações inesperadas para evitar inconsistências e proporcionar uma experiência adequada ao usuário.

| Situação | Comportamento esperado |
|---|---|
| Campos obrigatórios não preenchidos | O sistema deve impedir o cadastro e informar quais campos precisam ser preenchidos. |
| Quantidade de páginas inválida | O sistema deve rejeitar valores iguais ou inferiores a zero. |
| Página atual superior ao total de páginas | O sistema deve impedir a atualização e apresentar uma mensagem de validação. |
| Livro não encontrado | O sistema deve informar que o registro não existe e retornar à biblioteca. |
| Falha ao salvar no LocalStorage | O sistema deve informar que não foi possível salvar os dados e evitar confirmar uma operação não persistida. |
| Tentativa de excluir um livro | O sistema deve solicitar confirmação antes de realizar a exclusão. |

---

## 5. ARQUITETURA & ESCOLHA DA STACK TECNOLÓGICA

### 5.1. Arquitetura Proposta

O Trilha de Leitura será desenvolvido como uma aplicação web no modelo cliente-side, utilizando React para gerenciar a interface e a lógica das funcionalidades.

Os dados serão armazenados localmente no navegador por meio da API LocalStorage, dispensando a necessidade de um servidor backend nesta primeira versão.

**Fluxo simplificado da aplicação:**

```text
          USUÁRIO
             |
             v
      INTERFACE WEB
       (React + CSS)
             |
             v
      LÓGICA DO SISTEMA
         (JavaScript)
             |
             v
        LOCALSTORAGE
             |
             v
      DADOS PERSISTIDOS
       NO NAVEGADOR
```

### 5.2. Tecnologias Escolhidas

| Camada | Tecnologia | Finalidade |
|---|---|---|
| Interface / Frontend | React | Construção dos componentes e gerenciamento da interface. |
| Ferramenta de desenvolvimento | Vite | Configuração e execução do ambiente de desenvolvimento. |
| Estilização | CSS3 | Desenvolvimento do layout e responsividade. |
| Lógica da aplicação | JavaScript | Implementação das regras de negócio e validações. |
| Armazenamento | LocalStorage | Persistência dos dados no navegador. |
| Versionamento | Git e GitHub | Controle de versões e hospedagem do código-fonte. |

### 5.3. Justificativa da Stack Tecnológica

A escolha do React com Vite foi motivada pela facilidade de desenvolvimento de interfaces modernas e pela possibilidade de dividir a aplicação em componentes reutilizáveis. O JavaScript será utilizado tanto para as interações quanto para as regras de negócio.

O LocalStorage foi escolhido por permitir a persistência dos dados diretamente no navegador, reduzindo a complexidade da arquitetura e dispensando a configuração de um backend ou banco de dados externo. Essa combinação atende às necessidades da primeira versão do projeto e permite um desenvolvimento simples e funcional.

---

## 6. CRITÉRIOS DE ACEITE & DEFINIÇÃO DE PRONTO (DEFINITION OF DONE)

O projeto será considerado concluído quando todas as funcionalidades previstas no escopo estiverem implementadas, testadas e funcionando corretamente.

Os seguintes critérios deverão ser atendidos:

- [ ] O sistema deve permitir cadastrar livros com todos os campos obrigatórios.
- [ ] O sistema deve permitir editar e excluir livros cadastrados.
- [ ] Os livros devem ser organizados corretamente conforme seus respectivos status de leitura.
- [ ] O usuário deve conseguir atualizar a página atual e visualizar o progresso percentual da leitura.
- [ ] O sistema deve permitir registrar e editar anotações pessoais em cada livro.
- [ ] As estatísticas devem apresentar valores compatíveis com os livros cadastrados.
- [ ] Os dados devem permanecer salvos após atualizar ou fechar e reabrir o navegador.
- [ ] O sistema deve validar os campos e impedir a entrada de informações inválidas.
- [ ] As mensagens de erro e confirmação devem ser apresentadas corretamente.
- [ ] A interface deve funcionar adequadamente em diferentes tamanhos de tela.
- [ ] O código deve estar organizado e o projeto deve executar sem erros críticos.

**Definição de Pronto:**

O Trilha de Leitura será considerado finalizado quando o usuário conseguir cadastrar, organizar, atualizar e acompanhar seus livros, registrar anotações e visualizar suas estatísticas, com os dados persistidos no LocalStorage e sem apresentar falhas que comprometam o funcionamento das funcionalidades previstas.

---

**Considerações Finais**

O Trilha de Leitura busca oferecer uma solução prática para o gerenciamento de leituras pessoais, priorizando simplicidade, organização e facilidade de utilização.

A especificação apresentada estabelece os limites, requisitos e tecnologias da primeira versão do projeto, servindo como referência para orientar as etapas posteriores de desenvolvimento e testes.

**Fim do Documento de Especificação — Versão 1.0**
