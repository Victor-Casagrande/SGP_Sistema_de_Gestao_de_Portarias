# 03 – Mapeamento de talentos e habilidades

O mapeamento parte das competências que o projeto exige, registra o nível de cada integrante (autoavaliação) e usa esses níveis para definir os papéis, a alocação dos pacotes da [EAP](02-eap.md) e a matriz RACI.

## 1. Competências que o projeto exige

| # | Competência | Onde é usada no projeto |
|---|---|---|
| C1 | Levantamento de requisitos e entrevista | Entrevista com o Diretor-Geral; RF, RNF e RN |
| C2 | Modelagem de processos e regras de negócio | Ciclo de vida da portaria; limites de carga horária; as quatro ações |
| C3 | Design de interface (UI) | Telas, hierarquia visual, tipografia, cores |
| C4 | Experiência do usuário (UX) e usabilidade | Fluxos por perfil, mensagens de erro, etapas guiadas |
| C5 | Figma: componentes, variantes, variáveis e estilos | Design system |
| C6 | Figma: prototipação e sobreposições | Protótipo navegável, modais, menus e avisos |
| C7 | Escrita técnica e documentação | Termo de Abertura, plano, EAP, README |
| C8 | Git e GitHub | Repositório de entrega |
| C9 | Gestão ágil (Scrum) | Backlog, sprints, eventos |
| C10 | Conhecimento do domínio (serviço público, IFC, SIPAC, LGPD) | Regras de vigência, perfis, privacidade |
| C11 | Acessibilidade | Contraste, tamanho de texto, estados de foco e erro |
| C12 | Comunicação e apresentação | Condução das sprints, validação com o professor e com o cliente |

## 2. Matriz de habilidades

Autoavaliação de cada integrante. Escala: **1** sem experiência · **2** básico, precisa de apoio · **3** autônomo · **4** consegue ensinar os colegas.

| Competência | Victor Casagrande | Lucas Duarte Lopes | Willighan Tinelli de Souza |
|---|:-:|:-:|:-:|
| C1 Levantamento de requisitos | **3** | **3** | **3** |
| C2 Processos e regras de negócio | **3** | 2 | **3** |
| C3 Design de interface | 2 | **3** | 2 |
| C4 UX e usabilidade | 2 | 2 | 2 |
| C5 Figma – design system | 1 | **4** | **3** |
| C6 Figma – prototipação | **3** | **4** | **3** |
| C7 Documentação técnica | 2 | 2 | **4** |
| C8 Git e GitHub | 2 | 2 | **3** |
| C9 Scrum | **3** | **4** | **3** |
| C10 Domínio (IFC, SIPAC, LGPD) | 2 | **3** | **3** |
| C11 Acessibilidade | **3** | **3** | 2 |
| C12 Comunicação | **3** | **4** | **3** |
| Disposição para desenvolver novas competências | 2 | 2 | 3 |

Em negrito, os níveis 3 e 4 (autônomo ou capaz de ensinar).

### Leitura da matriz

| Integrante | Pontos fortes | Lacunas |
|---|---|---|
| Victor Casagrande | Requisitos (C1), regras de negócio (C2), prototipação (C6), acessibilidade (C11) | Design system (C5 = 1), design de interface (C3), documentação (C7), Git (C8) |
| Lucas Duarte Lopes | Design system (C5 = 4), prototipação (C6 = 4), Scrum (C9 = 4), comunicação (C12 = 4), design de interface (C3) | Regras de negócio (C2), documentação (C7), Git (C8) |
| Willighan Tinelli de Souza | Documentação (C7 = 4), Git (C8), regras de negócio (C2), domínio (C10), design system e prototipação (C5, C6) | Design de interface (C3), acessibilidade (C11) |
| **Equipe** | Levantamento de requisitos (todos com 3) | **UX e usabilidade (todos com 2)** |

## 3. Papéis e alocação

O **Product Owner** é o Diretor-Geral do Campus Videira, cliente e dono do produto. Os papéis da equipe seguem os vistos em Engenharia de Software I e foram atribuídos a quem tem os maiores níveis nas competências de cada papel.

| Integrante | Papel no projeto | Papel no Scrum | Por quê (competências) | Pacotes da EAP |
|---|---|---|---|---|
| Lucas Duarte Lopes | Designer UI/UX | Scrum Master | C5 = 4, C6 = 4, C3 = 3; C9 = 4 e C12 = 4 para conduzir os eventos | Design system, login, Home, telas do solicitante e do emissor, sobreposições, landing page, revisões e retrospectivas, arquivo final do Figma (160 h) |
| Victor Casagrande | Analista de Requisitos e representante do PO | Time de desenvolvimento | C1 = 3, C2 = 3, C12 = 3; C11 = 3 para revisar acessibilidade | Roteiro e transcrição da entrevista, regras de negócio, requisitos, critérios de aceitação, histórias de usuário, telas de gestão e consulta pública, funcionalidades da landing, teste de navegação, validação com o professor (148 h) |
| Willighan Tinelli de Souza | Gerente de Projeto e Engenheiro de Software (protótipo) | Time de desenvolvimento | C7 = 4, C8 = 3, C10 = 3; C5 = 3 e C6 = 3 | Termo de Abertura, plano, EAP, RACI, rastreabilidade, ícones, recuperação de senha, telas do servidor, conexões e fluxos do protótipo, revisão cruzada, repositório, lições aprendidas (156 h) |

Os três juntos fazem a entrevista, o mapeamento de talentos, os protótipos de baixa e média fidelidade e a retrospectiva final (44 h). As horas vêm do [dicionário da EAP](02-eap.md#resumo-do-esforço).

**Critérios usados na alocação**

- quem tem nível 3 ou 4 numa competência fica como **responsável (R)** pelos pacotes que mais dependem dela;
- quem tem nível 1 ou 2 participa como **consultado (C)** nesses pacotes, para aprender com o responsável;
- o teste de navegação é feito por quem **não desenhou a maior parte** das telas (Victor), para enxergar falhas que o autor não vê;
- nenhum pacote crítico (login, recuperação de senha, Home, protótipo, entrega) fica sem um segundo integrante consultado.

## 4. Matriz RACI

**R** responsável (executa) · **A** aprova (presta contas) · **C** consultado · **I** informado.

| Entregável | Victor | Lucas | Willighan | Product Owner |
|---|:-:|:-:|:-:|:-:|
| Termo de Abertura do Projeto | C | C | R/A | C |
| Planejamento detalhado (01b) | C | C | R/A | I |
| EAP e dicionário | C | C | R/A | — |
| Mapeamento de talentos | R | R | R/A | — |
| Matriz RACI | C | C | R/A | — |
| Backlog do produto | R/A | C | C | C |
| Requisitos (RF e RNF) | R/A | C | C | C |
| Regras de negócio | R/A | I | C | C |
| Critérios de aceitação | R/A | C | C | I |
| Matriz de rastreabilidade | A | I | R | — |
| Design system (paleta, estilos, componentes) | C | R/A | C | — |
| Interface a) Login | C | R/A | C | I |
| Interface b) Recuperação de senha | C | A | R | I |
| Interface c) Home com menu | C | R/A | C | I |
| Telas do servidor | C | A | R | I |
| Telas do solicitante e do emissor | C | R/A | C | I |
| Telas de gestão, chefia e consulta pública | R | A | C | I |
| Protótipo navegável (conexões e fluxos) | C | A | R | I |
| Sobreposições (modais, menus, listas, avisos) | C | R/A | C | — |
| Landing page | R | R/A | C | I |
| Acompanhamento das sprints | I | R/A | C | — |
| Teste de navegação | R/A | C | C | — |
| Revisão cruzada da documentação | C | C | R/A | — |
| Validação com o professor | R/A | C | C | — |
| Repositório GitHub | C | C | R/A | — |
| Arquivo final do Figma e compartilhamento | I | R/A | I | — |
| Lições aprendidas | C | C | R/A | — |

Cada entregável tem um único **A**. O Product Owner é consultado sobre o que afeta o negócio e informado sobre as telas; a validação com ele acontece por meio do professor e do representante do PO.

## 5. Plano de desenvolvimento da equipe

| Lacuna | Quem | Ação | Com quem | Quando |
|---|---|---|---|---|
| Design system no Figma (C5 = 1) | Victor | Montar as telas de gestão e consulta pública usando os componentes e estilos, com revisão do Lucas | Lucas (C5 = 4) | Sprint 2 |
| Design de interface (C3 = 2) | Victor e Willighan | Sessão de 30 min sobre os quatro princípios de design aplicados nas telas | Lucas (C3 = 3) | Sprint 2 |
| UX e usabilidade (todos com 2) | Equipe | Teste de navegação com uma pessoa de fora da equipe e registro das dificuldades | — | Sprint 3 |
| Documentação técnica (C7 = 2) | Victor e Lucas | Revisão dos próprios documentos com o Willighan antes do congelamento | Willighan (C7 = 4) | Sprint 3 |
| Git e GitHub (C8 = 2) | Victor e Lucas | Cada um faz ao menos um commit no repositório | Willighan (C8 = 3) | Sprint 4 |
| Regras de negócio (C2 = 2) | Lucas | Leitura conjunta de `docs/06` e da transcrição da entrevista | Victor (C2 = 3) | Sprint 2 |
| Acessibilidade (C11 = 2) | Willighan | Conferir contraste e mensagens de erro nas telas que desenhou | Victor (C11 = 3) | Sprint 3 |
