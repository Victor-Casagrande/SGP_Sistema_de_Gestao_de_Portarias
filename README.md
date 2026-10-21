# SGP – Sistema de Gestão de Portarias

**IFC Campus Videira · Trabalho/Prova: Gestor de Portarias – 2026**

O SGP substitui as planilhas e pastas usadas hoje para controlar portarias no campus. Ele cobre o caminho completo de uma portaria: o pedido do coordenador, a elaboração pelo Gabinete ou pela CGP, a assinatura no SIPAC e a ciência dos membros. Também controla a carga horária de cada servidor em portarias e mantém o histórico que o servidor usa na progressão funcional.

Este repositório reúne a documentação de projeto. O sistema não é codificado nesta etapa: a equipe atua como **projetista/arquiteta** da solução, e as integrações com o LDAP/AD da Reitoria e com o SIPAC são consideradas garantidas.

## Equipe

| Integrante | Papel Scrum |
|---|---|
| Victor Casagrande | Product Owner · Design de interface |
| Lucas Duarte Lopes | Scrum Master · Requisitos, regras de negócio e testes de navegação |
| Willighan Tinelli de Souza | Time de desenvolvimento · Prototipação e critérios de aceitação |

Os papéis são uma proposta; a distribuição completa está em [03 – Mapeamento de talentos e habilidades](docs/03-mapeamento-de-talentos.md).

## Links

- **Figma (arquivo de design):** https://www.figma.com/design/ezXFmUokd7Vfb36NjGNrG0
- **Protótipo navegável:** https://www.figma.com/proto/ezXFmUokd7Vfb36NjGNrG0?node-id=2010-2&starting-point-node-id=2010%3A2

## Documentos

| # | Documento | Conteúdo |
|---|---|---|
| 01 | [Plano de projeto](docs/01-plano-de-projeto.md) | Escopo, Scrum, sprints semanais, backlog, riscos, comunicação |
| 02 | [EAP](docs/02-eap.md) | Estrutura analítica do projeto e dicionário da EAP |
| 03 | [Mapeamento de talentos e habilidades](docs/03-mapeamento-de-talentos.md) | Competências, matriz de habilidades e matriz RACI |
| 04 | [Critérios de aceitação](docs/04-criterios-de-aceitacao.md) | Cenários Dado/Quando/Então por requisito e Definição de Pronto |
| 05 | [Requisitos funcionais e não funcionais](docs/05-requisitos.md) | RF01–RF15 e RNF01–RNF07 com rastreabilidade |
| 06 | [Regras de negócio](docs/06-regras-de-negocio.md) | RN01–RN09 |
| 07 | [Interfaces](docs/07-interfaces.md) | a) Login · b) Recuperação de senha · c) Home com menu |
| 08 | [Prototipação funcional e navegável](docs/08-prototipo-navegavel.md) | Fluxos, telas, sobreposições e como navegar |
| 09 | [Landing page](docs/09-landing-page.md) | Seções, conteúdo e interações |
| 10 | [Design system](docs/10-design-system.md) | Paleta, estilos de texto, cor, efeito e grade, componentes |

## Atendimento ao enunciado

| Exigência do trabalho | Onde está atendida |
|---|---|
| Sistema web alinhado às regras de negócio da instituição | [06 – Regras de negócio](docs/06-regras-de-negocio.md), tiradas da entrevista com o Diretor-Geral do Campus Videira |
| Design personalizado, em consonância com o ambiente do IFC | Verde institucional, logotipo oficial, termos do serviço público (SIPAC, DOU, Boletim de Serviço, SIAPE) · [10 – Design system](docs/10-design-system.md) |
| Requisitos levantados em Engenharia de Software I | [05 – Requisitos](docs/05-requisitos.md), com o horário de cada trecho da entrevista |
| Imagens, fontes, ícones e ilustrações | Logotipo do IFC, fonte Inter com 11 estilos de texto, 34 ícones em componentes, ilustrações na landing |
| Componentes, sobreposições, paleta de cores e estilos no Figma | 10 componentes com variantes e propriedades, 49 sobreposições (modais, menus, listas de seleção e avisos), 16 estilos de cor ligados a variáveis, 11 de texto, 4 de efeito e 3 de grade |
| Protótipo navegável em botões, menus e sobreposições | 815 interações em 33 telas e 49 sobreposições, com 10 fluxos; todos os campos de seleção abrem lista de opções · [08 – Protótipo](docs/08-prototipo-navegavel.md) |
| Plano de projeto, EAP, talentos, critérios de aceitação | [01](docs/01-plano-de-projeto.md), [02](docs/02-eap.md), [03](docs/03-mapeamento-de-talentos.md), [04](docs/04-criterios-de-aceitacao.md) |
| Interfaces a) login, b) recuperação de senha, c) Home com menu | [07 – Interfaces](docs/07-interfaces.md) |
| Landing page | [09 – Landing page](docs/09-landing-page.md) |

## Como abrir o protótipo

1. Abra o arquivo no Figma e vá à página **Telas (protótipo)**.
2. Clique em **Apresentar** (▶, no canto superior direito) ou use o link do protótipo acima.
3. No painel à esquerda da apresentação, escolha um dos **10 fluxos**:

| Fluxo | Começa em | Perfil |
|---|---|---|
| 1. Visitante: landing → login → painel | Landing | Público |
| 2. Consulta pública (sem login) | Consulta pública | Público |
| 3. Login com erro | Login – Erro | Público |
| 3b. Recuperar senha | Recuperar senha – 1 | Público |
| 4. Servidora: painel, alertas e ciência | Painel – Início | Servidor (Maria Silva) |
| 5. Solicitante → Emissor → nova portaria | Nova solicitação | Solicitante e Emissor |
| 6. Emissor: alterar, retificar, revogar | Portaria 112/2026 | Emissor (João Pereira) |
| 7. Emissor: portarias e Boletim de Serviço | Portarias – busca | Emissor |
| 8. Gestão: relatórios | Relatórios – gestão | Gestão (Helena Duarte) |
| 9. Chefia: relatórios do setor | Relatórios – chefia | Chefia de setor (Roberto Lima) |

## Estrutura do repositório

```
.
├── README.md
├── docs/
│   ├── 01-plano-de-projeto.md … 10-design-system.md
│   └── imagens/            # telas exportadas do Figma
└── anexos/
    └── entrevista-diretor-geral-transcricao.txt
```

Os horários citados como “Fonte: entrevista mm:ss” nos documentos apontam para a gravação da entrevista com o Diretor-Geral do Campus Videira. A transcrição em `anexos/` foi gerada automaticamente e revisada; trechos confusos devem ser conferidos no áudio pelo horário.

## Entrega

- **Prazo:** 08/11/2026, 23h59.
- **Entrega 1:** link do Figma com permissão de edição para `tiago.goncalves@ifc.edu.br`.
- **Entrega 2:** este repositório.
