# SGP – Sistema de Gestão de Portarias

**IFC Campus Videira · Trabalho/Prova: Gestor de Portarias – 2026**

O SGP substitui as planilhas e pastas usadas hoje para controlar portarias no campus. Ele cobre o caminho completo de uma portaria: o pedido do coordenador, a elaboração pelo Gabinete ou pela CGP, a assinatura no SIPAC e a ciência dos membros. Também controla a carga horária de cada servidor em portarias e mantém o histórico que o servidor usa na progressão funcional.

Este repositório reúne a documentação de projeto. O sistema não é codificado nesta etapa: a equipe atua como **projetista/arquiteta** da solução, e as integrações com o LDAP/AD da Reitoria e com o SIPAC são consideradas garantidas.

## Equipe

| Integrante | Papel no projeto | Papel no Scrum |
|---|---|---|
| Victor Casagrande | Analista de Requisitos | Time de desenvolvimento e representante do PO |
| Lucas Duarte Lopes | Designer UI/UX | Scrum Master |
| Willighan Tinelli de Souza | Gerente de Projeto e Engenheiro de Software (protótipo) | Time de desenvolvimento |

**Product Owner:** Diretor-Geral do Campus Videira, entrevistado em 30/03/2026. A distribuição completa está em [03 – Mapeamento de talentos e habilidades](docs/03-mapeamento-de-talentos.md).

## Links

- **Figma (arquivo de design):** https://www.figma.com/design/ezXFmUokd7Vfb36NjGNrG0
- **Protótipo navegável:** https://www.figma.com/proto/ezXFmUokd7Vfb36NjGNrG0?node-id=2010-2&starting-point-node-id=2010%3A2

## Documentos

| # | Documento | Conteúdo |
|---|---|---|
| 01 | [Plano de Projeto (Termo de Abertura)](docs/01-plano-de-projeto.md) | Modelo da disciplina preenchido ([.docx](docs/01-plano-de-projeto.docx) · [.pdf](docs/01-plano-de-projeto.pdf)) |
| 01b | [Planejamento detalhado](docs/01b-planejamento-detalhado.md) | Objetivos SMART, partes interessadas, ciclo de vida, papéis, cronograma, backlog, riscos, qualidade e decisões confirmadas com o professor |
| 02 | [EAP](docs/02-eap.md) | Estrutura analítica orientada a entregas (níveis 0 a 3) e dicionário da EAP |
| 03 | [Mapeamento de talentos e habilidades](docs/03-mapeamento-de-talentos.md) | Competências, matriz de habilidades e matriz RACI |
| 04 | [Critérios de aceitação](docs/04-criterios-de-aceitacao.md) | Critérios do projeto, cenários Dado/Quando/Então e Definição de Pronto |
| 05 | [Requisitos funcionais e não funcionais](docs/05-requisitos.md) | RF01–RF16 priorizados, RNF01–RNF07 mensuráveis (ISO/IEC 25010) e rastreabilidade |
| 06 | [Regras de negócio](docs/06-regras-de-negocio.md) | RN01–RN09, regras atômicas e tabelas de decisão |
| 07 | [Interfaces](docs/07-interfaces.md) | a) Login · b) Recuperação de senha · c) Home com menu |
| 08 | [Prototipação funcional e navegável](docs/08-prototipo-navegavel.md) | Fluxos, telas, sobreposições e como navegar |
| 09 | [Landing page](docs/09-landing-page.md) | Seções, conteúdo e interações |
| 10 | [Design system](docs/10-design-system.md) | Paleta, estilos de texto, cor, efeito, grade e animação, componentes |

## Atendimento ao enunciado

| Exigência do trabalho | Onde está atendida |
|---|---|
| Sistema web alinhado às regras de negócio da instituição | [06 – Regras de negócio](docs/06-regras-de-negocio.md), tiradas da entrevista com o Diretor-Geral do Campus Videira |
| Design personalizado, em consonância com o ambiente do IFC | Verde institucional, logotipo oficial, termos do serviço público (SIPAC, DOU, Boletim de Serviço, SIAPE) · [10 – Design system](docs/10-design-system.md) |
| Requisitos levantados em Engenharia de Software I | [05 – Requisitos](docs/05-requisitos.md), com o horário de cada trecho da entrevista |
| Imagens, fontes, ícones e ilustrações | Logotipo do IFC, fonte Inter com 11 estilos de texto, 34 ícones em componentes, ilustrações na landing |
| Componentes, sobreposições, paleta de cores e estilos no Figma | 13 componentes com variantes e propriedades (mais 34 ícones), 60 sobreposições (modais, menus, listas de seleção e avisos), 16 estilos de cor ligados a variáveis, 11 de texto, 4 de efeito, 3 de grade e 5 de animação; 48 variáveis (28 de design e 20 de estado do protótipo) |
| Protótipo navegável em botões, menus e sobreposições | 2.648 interações em 89 telas e 60 sobreposições, com 9 fluxos (um por perfil); menu, barra superior e atalhos mudam conforme o perfil que entrou, por meio de variáveis e condições; todos os campos de seleção abrem lista de opções · [08 – Protótipo](docs/08-prototipo-navegavel.md) |
| Plano de Projeto, EAP, talentos, critérios de aceitação | [01](docs/01-plano-de-projeto.md) e [01b](docs/01b-planejamento-detalhado.md), [02](docs/02-eap.md), [03](docs/03-mapeamento-de-talentos.md), [04](docs/04-criterios-de-aceitacao.md) |
| Interfaces a) login, b) recuperação de senha, c) Home com menu | [07 – Interfaces](docs/07-interfaces.md) |
| Landing page | [09 – Landing page](docs/09-landing-page.md) |

## Como abrir o protótipo

1. Abra o arquivo no Figma e vá à página **Telas (protótipo)**.
2. Clique em **Apresentar** (▶, no canto superior direito) ou use o link do protótipo acima.
3. No painel à esquerda da apresentação, escolha um dos **9 fluxos**. Os fluxos de perfil começam na tela de login daquele perfil, para que nome, menu e atalhos apareçam certos desde o início.

| Fluxo | Começa em | Pessoa de exemplo |
|---|---|---|
| 1. Visitante: landing → login | Landing | Público |
| 2. Consulta pública (sem login) | Consulta pública | Público |
| 3. Login com erro | Login – Erro | Público |
| 3b. Recuperar senha | Recuperar senha – 1 | Público |
| 4. Docente: painel, ciência e solicitação | Login — Docente | Maria · Docente EBTT (também Solicitante) |
| 5. Servidor TAE: painel e jornada | Login – Servidor | Fabrício · Servidor TAE |
| 6. Emissor: fila, nova portaria, exceção, ações e Boletim | Login — Emissor | Thiago · Emissor da CGP |
| 7. Chefia: relatórios do setor | Login — Chefe de Setor | Julia · Chefe de Setor (Ciência da Computação) |
| 8. Gestão: relatórios, exceções e assinaturas | Login — Diretor-Geral | Willian · Diretor-Geral |

No login, as abas da faixa **“Ambiente de desenvolvimento”** escolhem com qual pessoa de teste entrar. No sistema real o perfil vem do cadastro institucional (RN05); as abas existem só no protótipo.

## Estrutura do repositório

```
.
├── README.md
└── docs/
    ├── 01-plano-de-projeto.md (.docx, .pdf)   # Termo de Abertura
    ├── 01b-planejamento-detalhado.md
    ├── 02-eap.md … 10-design-system.md
    └── imagens/            # telas exportadas do Figma
```

Os horários citados como “Fonte: entrevista mm:ss” nos documentos apontam para a gravação da entrevista com o Diretor-Geral do Campus Videira. “Professor, 22/10/2026” marca as regras confirmadas com o professor da disciplina.

## Entrega

- **Prazo:** 08/11/2026, 23h59.
- **Entrega 1:** link do Figma com permissão de edição para `tiago.goncalves@ifc.edu.br`.
- **Entrega 2:** este repositório.
