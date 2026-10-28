# 01 – Plano de Projeto (Termo de Abertura do Projeto)

O professor confirmou, em 22/10/2026, que o artefato **“Plano de Projeto”** do enunciado é o **Termo de Abertura do Projeto (TAP)**, no modelo da disciplina (PMI Kickoff). As versões no formato original estão em [01-plano-de-projeto.docx](01-plano-de-projeto.docx) e [01-plano-de-projeto.pdf](01-plano-de-projeto.pdf).

O detalhamento do planejamento (ciclo de vida, papéis, cronograma, backlog, riscos e qualidade) está em [01b – Planejamento detalhado](01b-planejamento-detalhado.md).

| | |
|---|---|
| **Título do projeto** | SGP – Sistema de Gestão de Portarias (Gestor Portarias) · IFC Campus Videira |
| **Versão** | 1.1 – 22/10/2026 |

> O projeto começou em Engenharia de Software I sem um Termo de Abertura formal. Este termo consolida o que foi acordado desde a entrevista de 30/03/2026 e as respostas do professor de 22/10/2026, e é a referência de escopo da fase final.

## 1. Detalhes do projeto

### Necessidade de Negócio / Objetivos do Projeto

- Necessidade: as portarias do Campus Videira são controladas em planilhas e pastas. Os pedidos chegam por e-mail, a carga horária de cada servidor é somada à mão, os vencimentos são percebidos tarde e os mesmos dados são digitados de novo no SIPAC (entrevista com o Diretor-Geral, 30/03/2026).
- Objetivo geral: projetar, até 08/11/2026, um sistema web que cubra todo o ciclo de vida das portarias, da solicitação à ciência dos membros, com controle automático de carga horária e histórico permanente.
- Objetivos SMART: (1) entregar os 9 artefatos exigidos até 08/11/2026, 23h59; (2) protótipo com 100% dos fluxos dos 5 perfis navegáveis e nenhum link quebrado; (3) 100% dos requisitos ligados a ao menos uma tela e a um critério de aceitação; (4) toda regra de negócio com fonte na entrevista.

### Requisitos do Projeto

- Sistema web alinhado às regras de negócio do IFC (emissores, vigência, limites de carga horária, LGPD).
- Design personalizado no ambiente do IFC: identidade institucional, imagens, fontes, ícones e ilustrações.
- Uso dos recursos do Figma: componentes, sobreposições, paleta de cores e estilos.
- Protótipo navegável em botões, menus e sobreposições.
- Requisitos levantados em Engenharia de Software I; acesso ao LDAP/AD e ao SIPAC considerado garantido.

### Descrição do Produto / Entregas

- Produto: protótipo de alta fidelidade do SGP no Figma, com landing page, login, recuperação de senha, Home com menu e as telas de servidor, solicitante, emissor, chefia, gestão e consulta pública.
- Entregas: (1) Plano de projeto; (2) EAP; (3) Mapeamento de talentos e habilidades; (4) Critérios de aceitação; (5) Requisitos funcionais e não funcionais; (6) Regras de negócio; (7) Interfaces: login, recuperação de senha e Home com menu; (8) Protótipo funcional e navegável; (9) Landing page.
- Formas de entrega: arquivo do Figma com edição para o professor (Entrega 1) e repositório no GitHub com a documentação (Entrega 2).

### O Projeto Não Inclui

- Codificação, banco de dados, testes automatizados e implantação do sistema.
- Implementação das integrações com o LDAP/AD da Reitoria e com o SIPAC.
- Importação das portarias de 2010 a 2016 (fase futura).
- Exportação para planilhas, por decisão do cliente.
- Versões para celular e tablet: o sistema é administrativo e será usado em computadores.

### Recursos Alocados

- Pessoas: Victor Casagrande, Lucas Duarte Lopes e Willighan Tinelli de Souza; esforço estimado de 508 horas (ver EAP).
- Ferramentas: Figma (plano Education), Miro, GitHub e gravador de áudio.
- Cliente: Diretor-Geral do Campus Videira, para a entrevista e o esclarecimento de dúvidas.

## 2. Lista de partes interessadas

| Nome | Título | Função |
|---|---|---|
| Diretor-Geral do Campus Videira | Product Owner (cliente) | Define as necessidades, prioriza e valida o produto; assina as portarias no SIPAC |
| Prof. Tiago Gonçalves | Professor de Engenharia de Software | Orienta e avalia o projeto; recebe as entregas |
| Victor Casagrande | Analista de Requisitos e representante do PO | Requisitos, regras de negócio, critérios de aceitação e contato com o PO |
| Lucas Duarte Lopes | Designer UI/UX e Scrum Master | Design system, interfaces, landing page e condução das sprints |
| Willighan Tinelli de Souza | Gerente de Projeto e Engenheiro de Software | Termo de Abertura, plano, EAP, protótipo navegável e repositório |

A classificação completa das partes interessadas está no [planejamento detalhado](01b-planejamento-detalhado.md#4-partes-interessadas).

## 3. Cronograma de marcos do projeto

| Marco | Data | Descrição |
|---|---|---|
| 1. Entrevista com o Product Owner | 30/03/2026 | Entrevista gravada com o Diretor-Geral do Campus Videira, em Engenharia de Software I. É a fonte dos requisitos e das regras de negócio. |
| 2. Protótipo completo | 21/10/2026 | Requisitos revisados com a gravação, design system pronto e todas as telas ligadas no modo protótipo, de ponta a ponta. |
| 3. Protótipo validado | 28/10/2026 | Protótipo apresentado ao professor; respostas às questões em aberto registradas e ajustes aplicados. |
| 4. Congelamento | 05/11/2026 | Nenhuma tela ou documento novo; apenas correções encontradas no teste de navegação e na revisão cruzada. |
| 5. Entrega final | 08/11/2026, 23h59 | Figma compartilhado com edição para tiago.goncalves@ifc.edu.br e repositório do GitHub publicado com os 9 artefatos. |

## 4. Considerações do projeto

### Riscos em Alto Nível

- Atraso ou falta de acesso do professor ao Figma ou ao GitHub no momento da correção (nota zero).
- Regra de negócio mal interpretada da entrevista.
- Indisponibilidade de um integrante durante uma sprint.
- Mudanças no Figma quebrarem conexões do protótipo.

### Critérios de Aceitação

- Os 9 artefatos estão no repositório e o professor tem edição no Figma antes de 08/11/2026, 23h59.
- O protótipo cobre os 5 perfis, sem links quebrados, com as três interfaces obrigatórias.
- Todo requisito funcional tem tela e critério de aceitação; todo requisito não funcional é mensurável.
- O Figma usa componentes, sobreposições, paleta e estilos (cor, texto, efeito e grade).

### Hipóteses

- O acesso ao LDAP/AD da Reitoria e ao SIPAC está garantido.
- As regras citadas na entrevista valem para o Campus Videira; as dúvidas restantes foram respondidas pelo professor em 22/10/2026.
- Um usuário pode acumular perfis, que vêm do cadastro institucional.

### Restrições

- Prazo fixo: 08/11/2026, 23h59.
- Equipe de três estudantes, em paralelo às demais disciplinas.
- Ferramentas gratuitas ou de plano educacional; sem código executável.

