# Chat

## Descrição

Construa um chat TCP simples para comunicação em tempo real entre participantes. Ideal para prática de programação concorrente e distribuída com Elixir.

## Tecnologias Utilizadas

- Elixir e OTP para o servidor TCP.
- Mix para gerenciamento do projeto.

## Requisitos Mínimos

- **Servidor TCP**: Implementar um servidor TCP com `:gen_tcp` que suporte múltiplas conexões de clientes.
- **Identificação de Usuário**: Os usuários devem ser capazes de se identificar com um apelido.
- **Mensagens Globais**: Mensagens enviadas por um usuário devem ser recebidas por todos os usuários conectados.
- **Comandos**: Implementar comandos para:
  - Listar usuários conectados.
  - Sair do chat.
- **Supervisão**: Usar um Supervisor para gerenciar processos do servidor e assegurar resiliência.

## COMANDOS DO SERVIDOR TCP

- `/nick <apelido>`: Define ou altera o apelido do usuário.
- `/list`: Lista todos os usuários conectados.
- `/quit`: Desconecta o usuário do chat.
- Mensagens sem prefixo são consideradas mensagens globais e enviadas a todos os usuários.

## Como Configurar

1. Clone o repositório e navegue até o diretório do projeto.
2. Execute `mix deps.get` para instalar as dependências.
3. Inicie o servidor com `mix run --no-halt`.

## Como Usar

1. Conecte-se ao servidor utilizando um cliente TCP (ex.: `telnet` ou `nc`).
2. Uma vez conectado, utilize os comandos disponíveis para interagir no chat.

## Dicas e Referências

- Revise a [documentação do :gen_tcp](http://erlang.org/doc/man/gen_tcp.html) para entender o funcionamento de servidores TCP em Erlang/Elixir.
- Explore o [Guia de início rápido de GenServer](https://elixir-lang.org/getting-started/mix-otp/genserver.html) para implementar a lógica de servidor.
- Para supervisão de processos, consulte [Supervisor e Aplicação](https://elixir-lang.org/getting-started/mix-otp/supervisor-and-application.html).
- [Elixir School: Concorrência](https://elixirschool.com/pt/lessons/advanced/concurrency/) - Uma introdução à concorrência em Elixir.

## Requisitos Adicionais

- **Testes**: Inclua testes que verifiquem a funcionalidade básica do servidor, como a capacidade de conectar múltiplos clientes e a troca correta de mensagens.
- **Documentação**: Documente as funções públicas do seu servidor, especialmente aquelas que lidam com os comandos do usuário.
