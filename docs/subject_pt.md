# Preâmbulo

Antes de tudo, parabéns por chegar a este marco! Você está entrando agora no
projeto final do seu Common Core e, sim, ele não será fácil.
Transcendence é um projeto em grupo (4-5 pessoas), cujo objetivo é impulsionar sua
criatividade, autoconfiança, adaptabilidade a novas tecnologias e habilidades de trabalho em equipe.
Vocês criarão, em equipe, uma aplicação web do mundo real que pode seguir muitos caminhos,
dependendo dos módulos escolhidos e das decisões tomadas. Pensem bem juntos antes de começar.

**O projeto é dividido em duas partes:**

- A parte obrigatória, que é o núcleo fixo do projeto para o qual todos os membros
da equipe devem contribuir.
- Um conjunto de módulos, que vocês podem escolher e que contam para a nota final.

> [  !  ]
>Este é um projeto em grupo longo. Escolhas ruins no início e falta de
>coordenação da equipe custarão muito tempo. O gerenciamento do projeto e da equipe
>terá forte impacto nos resultados. Todos os membros devem
>participar ativamente e contribuir tanto para a parte obrigatória quanto para
>os módulos.

## II.1 Organização da equipe e gerenciamento do projeto

Como este é um projeto em grupo, uma boa organização da equipe é crucial para o sucesso. Vocês devem
estabelecer funções e responsabilidades claras desde o início.

### II.1.1 Funções obrigatórias da equipe

Sua equipe deve atribuir as seguintes funções (uma pessoa pode ter várias funções se a
equipe tiver 4 membros):

- Product Owner (PO): define a visão do produto, prioriza funcionalidades e garante que o projeto atenda às necessidades dos usuários.
  - Mantém o backlog do produto.
  - Toma decisões sobre funcionalidades e prioridades.
  - Valida o trabalho concluído.
  - Comunica-se com as partes interessadas (avaliadores, colegas).
- Gerente de Projeto (PM) / Scrum Master: facilita a coordenação da equipe e
remove obstáculos.
  - Organiza reuniões da equipe e sessões de planejamento.
  - Acompanha progresso e prazos.
  - Garante a comunicação da equipe.
  - Gerencia riscos e bloqueios.
- Líder Técnico / Arquiteto: supervisiona decisões técnicas e arquitetura.
  - Define a arquitetura técnica.
  - Toma decisões sobre a pilha tecnológica.
  - Garante qualidade de código e boas práticas.
  - Revisa mudanças críticas de código.
- Desenvolvedores (todos os membros da equipe): implementam funcionalidades e módulos.
  - Escrevem código para as funcionalidades atribuídas.
  - Participam de revisões de código.
  - Testam suas implementações.
  - Documentam seu trabalho.

>**Tamanho da equipe:**
>- 4 pessoas: alguns membros terão várias funções (ex.: PM + Desenvolvedor, PO + Desenvolvedor).
>- 5 pessoas: as funções podem ser mais especializadas, com PO, PM, Tech Lead e 2 Desenvolvedores dedicados.
>- Todas as funções devem estar claramente documentadas no seu README.md.

### II.1.2 Práticas recomendadas de gerenciamento de projeto

Embora não seja obrigatório, recomendamos fortemente implementar algumas práticas básicas de gerenciamento de projeto para ajudar sua equipe a ter sucesso:

- Comunicação regular: reúnam-se regularmente (semanalmente ou a cada duas semanas) para alinhar progresso
e bloqueios.
- Organização de tarefas: usem ferramentas simples como GitHub Issues, Trello ou até um documento
compartilhado para acompanhar quem faz o quê.
- Divisão do trabalho: dividam o projeto em tarefas menores e gerenciáveis.
- Revisões de código: tentem fazer com que pelo menos outro membro da equipe revise mudanças importantes
no código.
- Documentação: mantenham notas sobre decisões importantes e sobre como as coisas funcionam.
- Canal de comunicação: usem Discord, Slack ou similar para comunicação rápida da equipe.

> Essas práticas são recomendações para ajudar vocês a organizar o trabalho.
> Encontrem o que funciona melhor para sua equipe! O importante é que todos contribuam e o trabalho seja bem coordenado.

> [  !  ]
>**Durante a avaliação, a equipe deverá explicar:**
>- Como as funções foram distribuídas.
>- Como o trabalho foi organizado e dividido.
>- Como vocês se comunicaram e se coordenaram como equipe.
>- Como cada membro contribuiu para o projeto.
>- Todos os membros da equipe devem ser capazes de explicar o projeto e suas
> contribuições.

# Parte obrigatória

O conteúdo do projeto depende de vocês. Sim, vocês precisam trazer suas próprias ideias e decidir
juntos qual aplicação construir como equipe.
É um passo além do que vocês fizeram anteriormente no Common Core. Vocês precisam pensar
no projeto como um todo, não apenas nas funcionalidades que vão implementar.
Claro, vocês não serão totalmente livres — existem restrições —, mas a ideia é de vocês.

## III.1 O que estamos fazendo?

Primeiro, vocês deverão criar um arquivo README.md completo. Os requisitos detalhados
para o README estão especificados na seção Requisitos do README, no final deste
documento.

>**Exemplos de projeto: seu projeto pode assumir muitas formas. Aqui estão alguns exemplos válidos:**
>- Um jogo Pong multiplayer com sistema de torneio
>- Uma plataforma colaborativa com funcionalidades em tempo real
>- Uma rede social com interações entre usuários
>- Um jogo online (xadrez, jogo da velha etc.) com matchmaking
>- Uma aplicação de gerenciamento de projetos
>- Qualquer outra aplicação web criativa que atenda aos requisitos
>- O ponto principal é criar algo envolvente que demonstre suas habilidades técnicas e criatividade.

## III.2 Requisitos gerais

Construir um projeto inteiro é complicado, e muitas coisas podem dar errado. Para ajudar,
fornecemos uma lista de requisitos gerais que vocês devem seguir. Se eles não forem cumpridos,
o projeto será rejeitado.

**Os requisitos são os seguintes:**

- O projeto deve ser uma aplicação web e requer um frontend, um backend e um
banco de dados.
- Git deve ser usado com mensagens de commit claras e significativas. O repositório deve mostrar:

  - Commits de todos os membros da equipe.
  - Mensagens de commit claras descrevendo as alterações.
  - Distribuição adequada do trabalho entre a equipe.
- O deploy deve usar uma solução de conteinerização (Docker, Podman ou equivalente) e executar com um único comando.
- Seu site deve ser compatível com a versão estável mais recente do Google Chrome.
- Nenhum aviso ou erro deve aparecer no console do navegador.
- O projeto deve incluir páginas acessíveis de Política de Privacidade e Termos de Serviço
com conteúdo relevante.

> [  !  ]
> **Política de Privacidade e Termos de Serviço:** essas páginas serão verificadas durante a avaliação. Elas devem:
> - Ser facilmente acessíveis pela aplicação (ex.: links no rodapé).
> - Conter conteúdo relevante e adequado ao seu projeto.
> - Não ser páginas vazias ou placeholders.
> - Páginas ausentes ou inadequadas de Política de Privacidade/Termos de Serviço resultarão na rejeição do projeto.

> [  !  ]
> **Suporte multiusuário (obrigatório):** seu site deve oferecer suporte a vários usuários simultaneamente. Este é um requisito central do projeto. Os usuários devem conseguir interagir com a aplicação ao mesmo tempo, sem conflitos ou problemas de desempenho. Isso inclui:
>- Vários usuários podem estar logados e ativos ao mesmo tempo.
>- Ações concorrentes de diferentes usuários são tratadas corretamente.
>- Atualizações em tempo real são refletidas para todos os usuários conectados quando aplicável.
>- Não ocorrem corrupção de dados nem condições de corrida com ações simultâneas de usuários.

## III.3 Requisitos técnicos

Esta seção, assim como a anterior, é obrigatória. Depois disso, vocês poderão escolher os
módulos que desejam usar no próximo capítulo.
- Um frontend claro, responsivo e acessível em todos os dispositivos.
- Use um framework CSS ou uma solução de estilos à sua escolha (ex.: Tailwind CSS,
Bootstrap, Material-UI, Styled Components etc.).
- Armazene credenciais (chaves de API, variáveis de ambiente etc.) em um arquivo local .env que seja
ignorado pelo Git, e forneça um arquivo .env.example.
- O banco de dados deve ter um esquema claro e relações bem definidas.
- Sua aplicação deve ter um sistema básico de gerenciamento de usuários. Os usuários devem
conseguir se cadastrar e fazer login com segurança:

  - No mínimo: autenticação por e-mail e senha com segurança adequada (senhas
com hash, salt etc.).
  - Métodos adicionais de autenticação (OAuth, 2FA etc.) podem ser implementados
por meio de módulos.
- Todos os formulários e entradas de usuário devem ser devidamente validados tanto no frontend quanto no
backend.
- No backend, HTTPS deve ser usado em todos os lugares.

> **O que é um framework?** Para este projeto, um framework é definido como uma
> ferramenta abrangente que fornece:
> - Uma arquitetura estruturada e convenções para organizar o código.
> - Funcionalidades integradas para tarefas comuns (roteamento, gerenciamento de estado etc.).
> - Um ecossistema completo de ferramentas e bibliotecas.

> **Exemplos:**
> - Frameworks frontend: React, Vue, Angular, Svelte, Next.js (estes são frameworks).
> - Frameworks backend: Express, Fastify, NestJS, Django, Flask, Ruby on Rails.
> - Não são frameworks: jQuery (biblioteca), Lodash (biblioteca utilitária), Axios (cliente HTTP).

> **Nota:** React é considerado um framework neste contexto devido ao seu ecossistema e padrões arquiteturais, embora tecnicamente seja uma biblioteca.

# Módulos

Vocês precisarão obter 14 pontos no total para concluir o projeto. Cada módulo maior
vale 2 pontos, e cada módulo menor vale 1 ponto.

**As seguintes categorias estão disponíveis. Vocês podem escolher vários módulos de qualquer categoria:**

- Web
- Acessibilidade e internacionalização
- Gerenciamento de usuários
- Inteligência artificial
- Cibersegurança
- Jogos e experiência do usuário
- DevOps
- Dados e análise
- Blockchain
- Módulos à escolha

Recomendamos fortemente escolher os módulos somente depois que suas ideias estiverem claras e vocês tiverem
um bom entendimento do que querem construir.
Além disso, mirar em mais de 14 pontos no total pode ser uma boa ideia, especialmente se
alguns módulos não forem validados durante a avaliação.

> [  !  ]
>**Importante - Dependências de módulos e avaliação:**
>- Alguns módulos exigem que outros módulos sejam implementados primeiro (marcados com notas informativas).
>- Módulos de jogos (oponente de IA, torneio, customização de jogo, modo espectador, multiplayer 3+, adicionar outro jogo) exigem que pelo menos um jogo seja implementado primeiro.
>- O módulo de estatísticas de jogo exige que um jogo seja implementado.
>- Funcionalidades avançadas de chat exigem a funcionalidade básica de chat do módulo "Interação entre usuários".
>- SSR é incompatível com o backend blockchain ICP.
>- Planejem os módulos cuidadosamente para garantir que funcionem juntos de forma coerente!
>- Durante a avaliação: vocês deverão demonstrar cada módulo declarado. Somente módulos totalmente funcionais e corretamente implementados contarão para a pontuação final. Módulos não funcionais ou incompletos = 0 pontos.

## IV.1 Web

- Maior: usar um framework tanto para o frontend quanto para o backend.
  - Usar um framework frontend (React, Vue, Angular, Svelte etc.).
  - Usar um framework backend (Express, NestJS, Django, Flask, Ruby on Rails
etc.).
  - Frameworks full-stack (Next.js, Nuxt.js, SvelteKit) contam como ambos se vocês usarem
suas capacidades de frontend e backend.
- Menor: usar um framework frontend (React, Vue, Angular, Svelte etc.).
- Menor: usar um framework backend (Express, Fastify, NestJS, Django etc.).
- Maior: implementar funcionalidades em tempo real usando WebSockets ou tecnologia similar.
  - Atualizações em tempo real entre clientes.
  - Tratar conexão/desconexão de forma adequada.
  - Broadcast eficiente de mensagens.
- Maior: permitir que usuários interajam com outros usuários. Os requisitos mínimos são:
  - Um sistema básico de chat (enviar/receber mensagens entre usuários).
  - Um sistema de perfil (visualizar informações do usuário).
  - Um sistema de amigos (adicionar/remover amigos, ver lista de amigos).
- Maior: uma API pública para interagir com o banco de dados usando uma chave de API segura,
rate limiting, documentação e pelo menos 5 endpoints:

  - GET /api/{something}
  - POST /api/{something}
  - PUT /api/{something}
  - DELETE /api/{something}
- Menor: usar um ORM para o banco de dados.
- Menor: um sistema completo de notificações para todas as ações de criação, atualização e exclusão.
- Menor: funcionalidades colaborativas em tempo real (espaços compartilhados, edição ao vivo, desenho colaborativo etc.).
- Menor: Server-Side Rendering (SSR) para melhorar desempenho e SEO.
- Menor: Progressive Web App (PWA) com suporte offline e instalabilidade.
- Menor: sistema de design customizado com componentes reutilizáveis, incluindo uma
paleta de cores, tipografia e ícones adequados (mínimo: 10 componentes reutilizáveis).
- Menor: implementar busca avançada com filtros, ordenação e paginação.
- Menor: sistema de upload e gerenciamento de arquivos.
  - Suportar vários tipos de arquivos (imagens, documentos etc.).
  - Validação no cliente e no servidor (tipo, tamanho, formato).
  - Armazenamento seguro de arquivos com controle de acesso adequado.
  - Funcionalidade de pré-visualização de arquivos quando aplicável.
  - Indicadores de progresso para uploads.
  - Capacidade de excluir arquivos enviados.

## IV.2 Acessibilidade e internacionalização

- Maior: conformidade completa de acessibilidade (WCAG 2.1 AA), com suporte a leitores de tela,
navegação por teclado e tecnologias assistivas.
- Menor: suporte a múltiplos idiomas (pelo menos 3 idiomas).
  - Implementar sistema de i18n (internacionalização).
  - Pelo menos 3 traduções completas.
  - Seletor de idioma na interface.
  - Todo texto visível ao usuário deve ser traduzível.
- Menor: suporte a idiomas da direita para a esquerda (RTL).
  - Suporte a pelo menos um idioma RTL (árabe, hebraico etc.).
  - Espelhamento completo do layout (não apenas direção do texto).
  - Ajustes específicos de interface para RTL quando necessário.
  - Alternância fluida entre LTR e RTL.
- Menor: suporte a navegadores adicionais.
  - Compatibilidade completa com pelo menos 2 navegadores adicionais (Firefox, Safari, Edge
etc.).
  - Testar e corrigir todas as funcionalidades em cada navegador.
  - Documentar quaisquer limitações específicas de navegador.
  - UI/UX consistente em todos os navegadores suportados.

## IV.3 Gerenciamento de usuários

- Maior: gerenciamento e autenticação padrão de usuários.
  - Usuários podem atualizar suas informações de perfil.
  - Usuários podem enviar um avatar (com um avatar padrão caso nenhum seja fornecido).
  - Usuários podem adicionar outros usuários como amigos e ver seu status online.
  - Usuários têm uma página de perfil exibindo suas informações.
- Menor: estatísticas de jogo e histórico de partidas (requer um módulo de jogo).
  - Acompanhar estatísticas de jogo do usuário (vitórias, derrotas, ranking, nível etc.).
  - Exibir histórico de partidas (jogos 1v1, datas, resultados, adversários).
  - Mostrar conquistas e progressão.
  - Integração com ranking.

> Este módulo exige que vocês tenham implementado pelo menos um jogo (veja a seção
"Jogos e experiência do usuário"). Vocês não podem declarar este módulo
sem um jogo funcional.
- Menor: implementar autenticação remota com OAuth 2.0 (Google, GitHub, 42
etc.).
- Maior: sistema avançado de permissões:
  - Visualizar, editar e excluir usuários (CRUD).
  - Gerenciamento de papéis (admin, usuário, convidado, moderador etc.).
  - Diferentes visualizações e ações com base no papel do usuário.
- Maior: um sistema de organizações:
  - Criar, editar e excluir organizações.
  - Adicionar usuários a organizações.
  - Remover usuários de organizações.
  - Visualizar organizações e permitir que usuários executem ações específicas dentro de uma organização (mínimo: criar, ler, atualizar).
- Menor: implementar um sistema completo de 2FA (autenticação de dois fatores) para os
usuários.
- Menor: dashboard de análises e insights de atividade dos usuários.

## IV.4 Inteligência artificial

- Maior: introduzir um oponente de IA para jogos.
  - A IA deve ser desafiadora e capaz de vencer ocasionalmente.
  - A IA deve simular comportamento humano (não uma jogada perfeita).
  - Se vocês implementarem opções de customização do jogo, a IA deve ser capaz de usá-las.
  - Vocês devem ser capazes de explicar a implementação da IA durante a avaliação.

> Este módulo exige que vocês tenham implementado pelo menos um jogo (veja a seção
"Jogos e experiência do usuário"). A IA deve ser capaz de jogar
seu jogo de forma competente.
- Maior: implementar um sistema RAG (Retrieval-Augmented Generation) completo.
  - Interagir com um grande conjunto de dados de informações.
  - Usuários podem fazer perguntas e receber respostas relevantes.
  - Implementar recuperação adequada de contexto e geração de respostas.
- Maior: implementar uma interface completa para um sistema de LLM.
  - Gerar texto e/ou imagens com base na entrada do usuário.
  - Tratar respostas em streaming corretamente.
  - Implementar tratamento de erros e rate limiting.
- Maior: sistema de recomendação usando machine learning.
  - Recomendações personalizadas com base no comportamento do usuário.
  - Filtragem colaborativa ou filtragem baseada em conteúdo.
  - Melhorar continuamente as recomendações ao longo do tempo.
- Menor: IA de moderação de conteúdo (moderação automática, exclusão automática, aviso automático
etc.)
- Menor: integração de voz/fala para acessibilidade ou interação.
- Menor: análise de sentimento para conteúdo gerado por usuários.
- Menor: sistema de reconhecimento e marcação de imagens.

## IV.5 Cibersegurança

- Maior: implementar WAF/ModSecurity (reforçado) + HashiCorp Vault para segredos:
  - Configurar ModSecurity/WAF rigoroso.
  - Gerenciar segredos no Vault (chaves de API, credenciais, variáveis de ambiente), criptografados e isolados.

## IV.6 Jogos e experiência do usuário

- Maior: implementar um jogo web completo em que usuários possam jogar uns contra os
outros.
  - O jogo pode ser multiplayer em tempo real (ex.: Pong, xadrez, jogo da velha, jogos de cartas etc.).
  - Jogadores devem conseguir disputar partidas ao vivo.
  - O jogo deve ter regras claras e condições de vitória/derrota.
  - O jogo pode ser 2D ou 3D.
- Maior: jogadores remotos — permitir que dois jogadores em computadores separados joguem o
mesmo jogo em tempo real.
  - Tratar latência de rede e desconexões de forma adequada.
  - Fornecer uma experiência fluida para jogo remoto.
  - Implementar lógica de reconexão.
- Maior: jogo multiplayer (mais de dois jogadores).
  - Suporte para três ou mais jogadores simultaneamente.
  - Mecânicas de jogo justas para todos os participantes.
  - Sincronização adequada entre todos os clientes.

> Este módulo exige que vocês tenham implementado pelo menos um jogo (veja a seção
"Jogos e experiência do usuário"). Vocês estão estendendo o jogo para
suportar três ou mais jogadores.
- Maior: adicionar outro jogo com histórico de usuário e matchmaking.
  - Implementar um segundo jogo distinto.
  - Acompanhar histórico e estatísticas do usuário para este jogo.
  - Implementar um sistema de matchmaking.
  - Manter desempenho e responsividade.

> Este módulo exige que vocês já tenham implementado um primeiro jogo
(veja o módulo "Implementar um jogo web completo" acima). Vocês não podem
declarar este módulo sem ter um primeiro jogo funcional.
- Maior: implementar gráficos 3D avançados usando uma biblioteca como Three.js ou Babylon.js.
  - Criar um ambiente 3D imersivo.
  - Implementar técnicas avançadas de renderização.
  - Garantir desempenho fluido e interação do usuário.
- Menor: funcionalidades avançadas de chat (aprimora o chat básico do módulo de "Interação entre usuários").
  - Capacidade de bloquear usuários para que não enviem mensagens a você.
  - Convidar usuários para jogar diretamente pelo chat.
  - Notificações de jogo/torneio no chat.
  - Acesso a perfis de usuários pela interface do chat.
  - Persistência do histórico de chat.
  - Indicadores de digitação e confirmações de leitura.

> Este módulo aprimora o sistema básico de chat do módulo "Permitir que usuários
interajam". Vocês não podem declarar este módulo sem ter
implementado o chat básico primeiro.
- Menor: implementar um sistema de torneio.
  - Ordem clara de confrontos e sistema de chaves.
  - Acompanhar quem joga contra quem.
  - Sistema de matchmaking para participantes do torneio.
  - Registro e gerenciamento de torneios.

> Este módulo exige que vocês tenham implementado pelo menos um jogo (veja a seção
"Jogos e experiência do usuário"). Não é possível ter torneios
sem um jogo para jogar.
- Menor: opções de customização do jogo.
  - Power-ups, ataques ou habilidades especiais.
  - Mapas ou temas diferentes.
  - Configurações de jogo customizáveis.
  - Opções padrão devem estar disponíveis.

> Este módulo exige que vocês tenham implementado pelo menos um jogo (veja a seção
"Jogos e experiência do usuário"). Vocês estão adicionando customização
a um jogo existente.
- Menor: um sistema de gamificação para recompensar usuários por suas ações.
  - Implementar pelo menos 3 dos seguintes itens: conquistas, medalhas, rankings,
sistema de XP/nível, desafios diários, recompensas
  - O sistema deve ser persistente (armazenado no banco de dados)
  - Feedback visual para usuários (notificações, barras de progresso etc.)
  - Regras claras e mecânicas de progressão

> Embora este seja um módulo menor (1 ponto), implementar um sistema completo
de gamificação pode ser substancial. Foquem em qualidade, não em
quantidade — três funcionalidades bem implementadas são melhores do que seis mal
feitas.
- Menor: implementar modo espectador para jogos.
  - Permitir que usuários assistam a jogos em andamento.
  - Atualizações em tempo real para espectadores.
  - Opcional: chat de espectadores.

> Este módulo exige que vocês tenham implementado pelo menos um jogo (veja a seção
"Jogos e experiência do usuário"). Espectadores precisam de um jogo para
assistir.

## IV.7 DevOps

- Maior: infraestrutura para gerenciamento de logs usando ELK (Elasticsearch, Logstash,
Kibana).
  - Elasticsearch para armazenar e indexar logs.
  - Logstash para coletar e transformar logs.
  - Kibana para visualização e dashboards.
  - Implementar políticas de retenção e arquivamento de logs.
  - Proteger o acesso a todos os componentes.
- Maior: sistema de monitoramento com Prometheus e Grafana.
  - Configurar o Prometheus para coletar métricas.
  - Configurar exporters e integrações.
  - Criar dashboards customizados no Grafana.
  - Configurar regras de alerta.
  - Proteger o acesso ao Grafana.
- Maior: backend como microsserviços.
  - Projetar serviços desacoplados com interfaces claras.
  - Usar APIs REST ou filas de mensagens para comunicação.
  - Cada serviço deve ter uma única responsabilidade.
- Menor: sistema de health check e página de status com backups automatizados e procedimentos de
recuperação de desastre.

## IV.8 Dados e análise

- Maior: dashboard de análises avançadas com visualização de dados.
  - Gráficos interativos (linha, barra, pizza etc.).
  - Atualizações de dados em tempo real.
  - Funcionalidade de exportação (PDF, CSV etc.).
  - Intervalos de datas e filtros customizáveis.
- Menor: funcionalidade de exportação e importação de dados.
  - Exportar dados em vários formatos (JSON, CSV, XML etc.).
  - Importar dados com validação.
  - Suporte a operações em massa.
- Menor: funcionalidades de conformidade com GDPR.
  - Permitir que usuários solicitem seus dados.
  - Exclusão de dados com confirmação.
  - Exportar dados do usuário em formato legível.
  - E-mails de confirmação para operações de dados.

## IV.9 Blockchain

- Maior: armazenar pontuações de torneios na Blockchain.
  - Usar Avalanche e smart contracts Solidity em uma blockchain de teste.
  - Implementar smart contracts para registrar, gerenciar e recuperar pontuações de torneios.
  - Garantir integridade e imutabilidade dos dados.
- Menor: usar ICP (Internet Computer Protocol) para um backend que roda em uma
blockchain (incompatível com SSR).

## IV.10 Módulos à escolha

- Maior: implementar um módulo customizado que não esteja listado acima.
  - O módulo deve ser substancial e demonstrar complexidade técnica.
  - Vocês devem fornecer uma justificativa adequada no README.md explicando:
    - Por que escolheram este módulo.
    - Quais desafios técnicos ele aborda.
    - Como ele agrega valor ao projeto.
    - Por que ele merece status de módulo maior (2 pontos).
  - Tomar atalhos ou implementar funcionalidades triviais resultará em rejeição.
  - Sejam criativos e pensem fora da caixa.
  - O módulo deve ser relevante ao contexto do projeto.
- Menor: igual ao módulo maior, mas com escopo menor e menos complexo.
  - Ainda deve demonstrar habilidade técnica e criatividade.
  - Deve agregar valor significativo ao projeto.
  - Requer justificativa no README.md (similar ao Maior, mas por 1 ponto).

# Ideias e exemplos de projetos

Para ajudar vocês a começar e inspirar sua criatividade, este capítulo apresenta ideias concretas de projeto
e exemplos de como alcançar os 14 pontos exigidos. Lembrem-se: estas são apenas
sugestões — sintam-se livres para serem criativos e criarem suas próprias ideias únicas!

## V.1 Exemplo: construindo um jogo Pong

Se vocês escolherem criar um jogo Pong (como no projeto original), veja como podem alcançar
14 pontos:

- Jogos e experiência do usuário: jogo web (2pts) + jogadores remotos (2pts) + sistema de torneio (1pt) + customização de jogo (1pt) = 6 pontos
- Gerenciamento de usuários: gerenciamento padrão de usuários (2pts) + OAuth (1pt) = 3 pontos
- Web: uso de frameworks (frontend + backend = 2pts) + ORM (1pt) = 3 pontos
- Inteligência artificial: oponente de IA (2pts) = 2 pontos
- Total: 14 pontos

> Este é apenas um exemplo. Vocês podem combinar módulos de
diferentes categorias para criar seu próprio projeto único. O ponto principal
é garantir que seus módulos funcionem juntos de forma coerente e agreguem valor
à aplicação.

## V.2 Projetos de jogos

**Estes projetos focam em jogabilidade interativa e competição entre usuários:**

- Pong multiplayer: Pong clássico com torneios, jogo remoto, oponentes de IA
e power-ups.
  - Módulos sugeridos: jogo web, jogadores remotos, sistema de torneio, oponente de IA,
customização de jogo
  - Potencial de pontuação: 14+ pontos
- Plataforma de xadrez online: xadrez em tempo real com matchmaking, classificação ELO,
análise de partidas e modo espectador.
  - Módulos sugeridos: jogo web, jogadores remotos, oponente de IA, modo espectador,
estatísticas de jogo
  - Potencial de pontuação: 15+ pontos
- Arena de jogos de cartas: jogos de cartas multiplayer (Poker, Uno etc.) com torneios
e rankings.
  - Módulos sugeridos: jogo web, multiplayer 3+, sistema de torneio,
gamificação
  - Potencial de pontuação: 14+ pontos
- Minijogo battle royale: jogo battle royale simples para navegador com vários jogadores.
  - Módulos sugeridos: jogo web, multiplayer 3+, funcionalidades em tempo real,
customização de jogo
  - Potencial de pontuação: 14+ pontos
- Plataforma de trivia/quiz: jogo de perguntas multiplayer em tempo real com categorias e
torneios.
  - Módulos sugeridos: jogo web, multiplayer 3+, sistema de torneio,
gamificação, dashboard de análises
  - Potencial de pontuação: 15+ pontos

## V.3 Projetos sociais e colaborativos

**Estes projetos enfatizam interação entre usuários e construção de comunidade:**

- Rede social: perfis de usuários, posts, comentários, curtidas, amigos, chat em tempo real e
notificações.
  - Módulos sugeridos: interação entre usuários, funcionalidades em tempo real, sistema de notificações,
chat avançado, upload de arquivos
  - Potencial de pontuação: 14+ pontos
- Espaço de trabalho colaborativo: edição de documentos em tempo real, gerenciamento de projetos,
chat de equipe e compartilhamento de arquivos.
  - Módulos sugeridos: funcionalidades colaborativas em tempo real, interação entre usuários, sistema de organizações, upload de arquivos, permissões avançadas
  - Potencial de pontuação: 15+ pontos
- Plataforma de fórum: fóruns de discussão com categorias, tópicos, ferramentas de moderação
e sistemas de reputação de usuários.
  - Módulos sugeridos: interação entre usuários, permissões avançadas, gamificação,
IA de moderação de conteúdo, busca avançada
  - Potencial de pontuação: 14+ pontos
- Plataforma de gerenciamento de eventos: criar e gerenciar eventos, sistema de RSVP, integração com calendário e notificações.
  - Módulos sugeridos: interação entre usuários, sistema de notificações, sistema de organizações, API pública, busca avançada
  - Potencial de pontuação: 14+ pontos
- Sistema de gerenciamento de aprendizagem: cursos, tarefas, quizzes, acompanhamento de progresso e interação aluno-professor.
  - Módulos sugeridos: interação entre usuários, sistema de organizações, permissões avançadas, upload de arquivos, dashboard de análises
  - Potencial de pontuação: 15+ pontos

## V.4 Projetos criativos e de mídia

**Estes projetos focam na criação e compartilhamento de conteúdo:**

- Plataforma de streaming de música: upload e streaming de músicas, playlists, recomendações e recursos sociais.
  - Módulos sugeridos: upload de arquivos, interação entre usuários, sistema de recomendação,
busca avançada, dashboard de análises
  - Potencial de pontuação: 15+ pontos
- Plataforma de compartilhamento de vídeos: enviar e assistir vídeos, comentários, curtidas, inscrições e recomendações.
  - Módulos sugeridos: upload de arquivos, interação entre usuários, sistema de recomendação,
IA de moderação de conteúdo, busca avançada
  - Potencial de pontuação: 16+ pontos
- Galeria de arte: compartilhar obras em galerias, com comentários, curtidas e perfis de artistas.
  - Módulos sugeridos: upload de arquivos, interação entre usuários, reconhecimento de imagem, busca avançada,
sistema de design customizado
  - Potencial de pontuação: 14+ pontos
- Plataforma de blogs: criar e publicar blogs, com comentários, tags, categorias
e engajamento dos leitores.
  - Módulos sugeridos: interação entre usuários, SSR, busca avançada, análise de sentimento, múltiplos idiomas
  - Potencial de pontuação: 14+ pontos
- Plataforma de compartilhamento de receitas: compartilhar receitas, avaliações, comentários, planejamento de refeições e
listas de compras.
  - Módulos sugeridos: interação entre usuários, upload de arquivos, busca avançada, sistema de recomendação, PWA
  - Potencial de pontuação: 14+ pontos

## V.5 Projetos de produtividade e ferramentas

**Estes projetos ajudam usuários a organizar e gerenciar seu trabalho:**

- Sistema de gerenciamento de tarefas: projetos, tarefas, atribuições, prazos, colaboração em equipe e acompanhamento de progresso.
  - Módulos sugeridos: sistema de organizações, interação entre usuários, funcionalidades colaborativas em tempo real, sistema de notificações, dashboard de análises
  - Potencial de pontuação: 15+ pontos
- Plataforma de colaboração em código: compartilhar snippets de código, programação colaborativa, controle de versão e discussões.
  - Módulos sugeridos: interação entre usuários, funcionalidades colaborativas em tempo real, API pública,
busca avançada, sistema de design customizado
  - Potencial de pontuação: 14+ pontos
- Sistema de reservas: reservar recursos (salas, equipamentos, horários), calendário
e notificações.
  - Módulos sugeridos: interação entre usuários, sistema de organizações, sistema de notificações, API pública, busca avançada
  - Potencial de pontuação: 14+ pontos
- Plataforma de marketplace: comprar e vender itens, com avaliações de usuários, mensagens, integração de pagamento e funcionalidade de busca.
  - Módulos sugeridos: interação entre usuários, upload de arquivos, busca avançada, sistema de recomendação, API pública
  - Potencial de pontuação: 14+ pontos
- Rastreador fitness: registrar treinos, acompanhar progresso, desafios, rankings e
recursos sociais.
  - Módulos sugeridos: interação entre usuários, gamificação, dashboard de análises, PWA,
exportação/importação de dados
  - Potencial de pontuação: 14+ pontos

## V.6 Projetos especializados

**Estes projetos atendem nichos ou indústrias específicos:**

- Simulador de trading em tempo real: simulação de negociação de ações e criptomoedas
com dados e portfólios em tempo real.
  - Módulos sugeridos: funcionalidades em tempo real, interação entre usuários, dashboard de análises,
API pública, gráficos 3D avançados
  - Potencial de pontuação: 15+ pontos
- Plataforma de aprendizado de idiomas: lições, exercícios, acompanhamento de progresso e prática
com colegas.
  - Módulos sugeridos: interação entre usuários, gamificação, múltiplos idiomas, integração de voz,
dashboard de análises
  - Potencial de pontuação: 15+ pontos
- Plataforma de adoção de pets: navegar por pets, processo de adoção, perfis de usuários e mensagens.
  - Módulos sugeridos: interação entre usuários, upload de arquivos, busca avançada, sistema de organizações, sistema de notificações
  - Potencial de pontuação: 14+ pontos
- Plataforma de planejamento de viagens: planejar viagens, compartilhar itinerários, recomendações e
recursos sociais.
  - Módulos sugeridos: interação entre usuários, funcionalidades colaborativas em tempo real, sistema de recomendação, múltiplos idiomas, busca avançada
  - Potencial de pontuação: 15+ pontos
- Plataforma de crowdfunding: criar campanhas, doações, atualizações e engajamento da comunidade.
  - Módulos sugeridos: interação entre usuários, upload de arquivos, API pública, dashboard de análises, sistema de notificações
  - Potencial de pontuação: 14+ pontos

> [  !  ]
> Estas são apenas ideias para inspirar vocês. O ponto principal é escolher um projeto
> que:
>- Interesse sua equipe e motive todos a trabalhar nele.
>- Permita implementar os módulos exigidos (mínimo de 14 pontos).
>- Demonstre complexidade técnica e criatividade.
>- Possa ser concluído realisticamente dentro do prazo do projeto.
>- Tenha combinações coerentes de módulos que funcionem bem juntas.
>- Discutam com sua equipe, revisem os módulos disponíveis e escolham com sabedoria!

# Requisitos do README

Um arquivo README.md deve ser fornecido na raiz do seu repositório Git. Seu objetivo é
permitir que qualquer pessoa não familiarizada com o projeto (colegas, staff, recrutadores etc.) entenda rapidamente
sobre o que é o projeto, como executá-lo e onde encontrar mais informações
sobre o tema.

**O README.md deve incluir pelo menos:**

- A primeira linha deve estar em itálico e conter: Este projeto foi criado como parte
do currículo da 42 por login1, login2, login3[...].
- Uma seção “Descrição” que apresente claramente o projeto, incluindo seu objetivo e uma
breve visão geral.
- Uma seção “Instruções” contendo qualquer informação relevante sobre compilação,
instalação e/ou execução.
- Uma seção “Recursos” listando referências clássicas relacionadas ao tema (documentação, artigos, tutoriais etc.), bem como uma descrição de como a IA foi usada —
especificando para quais tarefas e quais partes do projeto.

> **Nota:** Seções adicionais podem ser necessárias dependendo do projeto (ex.: exemplos de uso, lista de funcionalidades, escolhas técnicas etc.).

Quaisquer adições obrigatórias serão explicitamente listadas abaixo.
- A seção “Descrição” também deve conter um nome claro para o projeto e suas
principais funcionalidades.
- A seção “Instruções” deve mencionar todos os pré-requisitos necessários (software,
ferramentas, versões, configuração como .env etc.) e instruções passo a passo para
executar o projeto.

**Seções adicionais exigidas para esta atividade:**

- Informações da equipe: para cada membro mencionado no topo do README.md, vocês devem fornecer:

  - Função(ões) atribuída(s): PO, PM, Tech Lead, Desenvolvedores etc.
  - Breve descrição de suas responsabilidades.
- Gerenciamento do projeto:
  - Como a equipe organizou o trabalho (distribuição de tarefas, reuniões etc.).
  - Ferramentas usadas para gerenciamento do projeto (GitHub Issues, Trello etc.).
  - Canais de comunicação usados (Discord, Slack etc.).
- Pilha técnica:
  - Tecnologias e frameworks usados no frontend.
  - Tecnologias e frameworks usados no backend.
  - Sistema de banco de dados e por que foi escolhido.
  - Quaisquer outras tecnologias ou bibliotecas significativas.
  - Justificativa para as principais escolhas técnicas.
- Esquema do banco de dados:
  - Representação visual ou descrição da estrutura do banco de dados.
  - Tabelas/coleções e seus relacionamentos.
  - Campos principais e tipos de dados.
- Lista de funcionalidades:
  - Lista completa de funcionalidades implementadas.
  - Qual(is) membro(s) da equipe trabalhou/trabalharam em cada funcionalidade.
  - Breve descrição da funcionalidade de cada item.
- Módulos:
  - Lista de todos os módulos escolhidos (maiores e menores).
  - Cálculo de pontos (Maior = 2pts, Menor = 1pt).
  - Justificativa para a escolha de cada módulo, especialmente para "Módulos à escolha" customizados.
  - Como cada módulo foi implementado.
  - Qual(is) membro(s) da equipe trabalhou/trabalharam em cada módulo.
- Contribuições individuais:
  - Detalhamento do que cada membro da equipe contribuiu.
  - Funcionalidades, módulos ou componentes específicos implementados por cada pessoa.
  - Quaisquer desafios enfrentados e como foram superados.

Qualquer outra informação útil ou relevante é bem-vinda (documentação de uso, limitações conhecidas, licença, créditos etc.).

> [  !  ]
> O README.md é uma parte crítica da avaliação do projeto. Ele deve ser:
>- Claro e bem organizado.
>- Completo, com todas as seções exigidas.
>- Profissional e fácil de ler.
>- Honesto sobre contribuições e desafios.
>- Um README ruim ou incompleto pode impactar negativamente sua avaliação.

# Entrega e avaliação por pares

Entregue seu projeto no repositório Git como de costume. Apenas o trabalho dentro do seu
repositório será avaliado durante a avaliação. Confira os nomes dos arquivos.
Recomendamos fortemente que vocês discutam suas ideias com a equipe e colegas antes de
começar a trabalhar no projeto.
Durante a avaliação, uma breve modificação do projeto poderá ocasionalmente ser solicitada. Isso pode envolver uma pequena alteração de comportamento, algumas linhas de código para escrever ou
reescrever, ou uma funcionalidade simples de adicionar.
Embora esta etapa possa não ser aplicável a todos os projetos, vocês devem estar preparados para ela
caso seja mencionada nas diretrizes de avaliação.
Esta etapa tem como objetivo verificar seu entendimento real de uma parte específica do projeto.
A modificação pode ser realizada em qualquer ambiente de desenvolvimento que vocês escolherem (ex.:
seu setup usual), e deve ser viável em poucos minutos — a menos que um prazo específico
seja definido como parte da avaliação.
Vocês podem, por exemplo, ser solicitados a fazer uma pequena atualização em uma função ou script, modificar uma
exibição, ou ajustar uma estrutura de dados para armazenar uma nova informação etc.
Os detalhes (escopo, alvo etc.) serão especificados nas diretrizes de avaliação e podem
variar de uma avaliação para outra para o mesmo projeto.
