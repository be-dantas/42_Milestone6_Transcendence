# Introdução

Por favor, cumpra as seguintes regras:

- Permaneça educado, cortês, respeitoso e construtivo durante todo o processo de avaliação. O bem-estar da comunidade depende disso.

- Identifique, junto ao estudante ou grupo cujo trabalho está sendo avaliado, possíveis disfunções no projeto. Reserve um tempo para discutir e debater os problemas que possam ter sido identificados.

- Você deve considerar que pode haver diferenças na forma como seus colegas entenderam as instruções do projeto e o escopo de suas funcionalidades. Mantenha sempre a mente aberta e avalie da forma mais honesta possível. A pedagogia só é útil se, e somente se, a avaliação por pares for feita com seriedade.

# Diretrizes

- Avalie apenas o trabalho entregue no repositório Git do estudante ou grupo avaliado.

- Verifique novamente se o repositório Git pertence ao(s) estudante(s). Certifique-se de que o projeto é o esperado. Além disso, confira se `git clone` é usado em uma pasta vazia.

- Verifique cuidadosamente se nenhum alias malicioso foi usado para enganar você e fazê-lo avaliar algo que não corresponde ao conteúdo do repositório oficial.

- Para evitar surpresas e, se aplicável, revisem juntos quaisquer scripts usados para facilitar a correção (scripts de teste ou automação).

- Se você não concluiu o trabalho que irá avaliar, deve ler o subject inteiro antes de iniciar o processo de avaliação.

- Use as flags disponíveis para reportar um repositório vazio, um programa que não funciona, erro de Norma, trapaça e assim por diante.
Em tais casos, o processo de avaliação termina e a nota final é 0, ou -42 em caso de trapaça. No entanto, exceto em caso de trapaça, os estudantes são fortemente encorajados a revisar juntos o trabalho entregue, a fim de identificar erros que não devem ser repetidos no futuro.

- Lembre-se de que, durante toda a defesa, não pode haver segfault, nem qualquer outra finalização inesperada, prematura, descontrolada ou inesperada do programa; caso contrário, a nota final será 0. Use a flag apropriada. Você nunca deve precisar editar qualquer arquivo, exceto o arquivo de configuração, caso ele exista. Se quiser editar um arquivo, reserve um tempo para explicitar os motivos ao estudante avaliado e certifique-se de que ambos concordam com isso.

- Você também deve verificar a ausência de vazamentos de memória. Qualquer memória alocada no heap deve ser devidamente liberada antes do fim da execução. Você pode usar qualquer uma das diferentes ferramentas disponíveis no computador, como leaks, valgrind ou e_fence. Em caso de vazamentos de memória, marque a flag apropriada.

# Instruções gerais

## Testes preliminares

- Quaisquer credenciais, chaves de API e variáveis de ambiente devem ser configuradas dentro de um arquivo `.env` durante a avaliação. Caso quaisquer credenciais ou chaves de API estejam disponíveis no repositório Git e fora do arquivo `.env` criado durante a avaliação, a avaliação termina e a nota é 0.

- Certifique-se de que o arquivo docker compose está na raiz do repositório.

- Execute o comando `docker-compose up --build`.

- Como a avaliação deste projeto é mais flexível, não interrompa o processo de avaliação a menos que encontre um erro 500, uma falha, ou algo que realmente não funcione dentro do escopo do projeto.

## Backend

- O backend deve ser desenvolvido usando o framework NestJS.

- O banco de dados deve ser um banco PostgreSQL.

- Durante todo o processo de avaliação, não deve haver nenhum aviso ou erro não tratado.

## Frontend

- O frontend deve ser feito usando um framework TypeScript.

- Qualquer biblioteca TypeScript/JavaScript é permitida.

- Durante todo o processo de avaliação, não deve haver nenhum aviso ou erro não tratado.

## Verificações básicas

- O site está disponível no endereço escolhido pelos estudantes.

- O usuário consegue fazer login usando o recurso OAuth da intranet 42.

- Ao fazer login pela primeira vez, o usuário é solicitado a adicionar informações à sua conta (nome de exibição/apelido, avatar e assim por diante).

- Se não estiver logado, o usuário tem acesso a pouca ou nenhuma informação e é solicitado a entrar.

- O site é uma Single Page Application. O usuário consegue usar os botões "Voltar" e "Avançar" do navegador.

- Você consegue navegar pelo site usando a versão mais recente do Chrome e um navegador adicional sem encontrar problemas ou erros.

# O site

**Preocupações de segurança**

Certifique-se de que o site é seguro. Verifique o banco de dados para confirmar que as senhas estão com hash. Verifique no servidor a validação/sanitização server-side em formulários e em qualquer entrada de usuário. Se isso não estiver feito, a avaliação termina agora.


**Perfil de usuário - privado**

Quando logado, o usuário tem acesso ao seu perfil, onde pode editar suas informações. Por exemplo, pode alterar seu apelido (que deve ser único) ou seu avatar (que é um avatar padrão caso não tenha sido definido).


**Perfil de usuário - público**

Usuários podem ver o perfil de outros usuários. Um perfil contém informações básicas, como apelido, avatar ou um botão para adicioná-los como amigos.

O usuário pode bloquear outros usuários. Isso significa que ele não receberá mensagens privadas das contas bloqueadas nem verá suas mensagens em canais públicos/privados.


**Interface de amigos**

O usuário tem acesso a uma interface de amigos, onde pode ver seus amigos e seus status (offline/online/em jogo/e assim por diante). Ele também tem acesso a informações básicas sobre eles (nome/apelido, avatar e assim por diante).


**2FA**

O usuário pode ativar/desativar 2FA (autenticação de dois fatores). Se ativado, ele deve passar por essa autenticação para entrar. Por exemplo, 2FA pode usar Google Authenticator, mensagem de texto, e-mail e assim por diante.

# Interface de chat

**Entrar/sair de canais**

Um usuário logado pode acessar o serviço de chat do site. Entrar/sair de canais é uma ação manual. Por exemplo, isso significa que não deve ser feito no logout (o usuário precisa clicar em um botão "Sair do canal" ou algo semelhante). O usuário pode entrar em canais (que já podem estar criados) para conversar. Alguns deles podem ser protegidos por senha. Nesse caso, o usuário deve inserir a senha correta para entrar no canal.


**Uso do chat**

Os usuários podem conversar. As mensagens devem ser enviadas/recebidas instantaneamente.

Se o usuário bloqueou outro usuário, as mensagens da pessoa bloqueada devem ficar ocultas. O usuário pode acessar o perfil de outros jogadores pela interface de chat e também convidá-los para um duelo de Pong.


**Criando canais**

O usuário pode criar novos canais. O criador do canal é definido como dono do canal e possui direitos básicos de moderação (banir/silenciar usuários, adicionar uma senha para proteger o canal, definir novos administradores e assim por diante).


**Funções no canal**

Um usuário que é dono de um canal pode expulsar, banir e silenciar outros usuários e os administradores do canal.

Um usuário que é administrador de um canal pode expulsar, banir e silenciar outros usuários, mas não os donos do canal.

# O jogo

**Sistema de matchmaking**

Quando logado, o usuário tem acesso a um sistema de matchmaking para poder jogar partidas de Pong 1v1 contra outros jogadores no site. Quando encontra uma partida, um novo jogo é carregado e os dois usuários podem começar a jogar.


**Gameplay**

O jogo em si deve ser jogável e respeitar o jogo Pong original. Os controles devem ser intuitivos ou corretamente explicados (com algumas regras ou manual). Quando uma partida termina, uma espécie de tela de fim de jogo é exibida ou a página do jogo simplesmente é encerrada.


**Modo espectador**

Existe um modo espectador. O usuário pode assistir a quaisquer jogos ao vivo. Eles podem ser acessados pela interface de chat ou pela interface de amigos.

Também pode haver uma página dedicada a jogos ao vivo, pela qual o usuário pode acessar qualquer um deles.


**Lags e desconexões**

Desconexões inesperadas e lags precisam ser tratados. O jogo e o site não devem travar quando um usuário estiver enfrentando lags ou estiver desconectado.

Tratar esses problemas de forma eficiente é apreciado, mas não obrigatório:

- Pausar o jogo por uma duração definida.
- Usuários desconectados podem se reconectar.
- Usuários com lag podem alcançar a partida.
- E assim por diante. Qualquer solução é aceitável. O único requisito é: o jogo não deve travar.


**Funcionalidades adicionais**

O usuário pode aproveitar funcionalidades extras, como power-ups, mapas diferentes, conquistas e assim por diante.
