# 06 – Regras de negócio

<<<<<<< HEAD
As regras de negócio descrevem as políticas do campus que o sistema precisa respeitar, independentemente da tela. Todas foram tiradas da entrevista com o Diretor-Geral. Os pontos que estavam pouco claros na gravação foram confirmados com o professor da disciplina em **22/10/2026** (marcados como “professor”).
=======
As regras de negócio descrevem as políticas do campus que o sistema precisa respeitar, independentemente da tela. Todas foram tiradas da entrevista com o Diretor-Geral; a RN02 foi complementada por pesquisa da equipe e precisa ser confirmada com o Gabinete.
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

## Resumo

| ID | Regra | Fonte |
|---|---|---|
<<<<<<< HEAD
| RN01 | Quem emite portarias | entrevista 15:52, 40:36, 41:32; professor (22/10/2026) |
| RN02 | Início da vigência | entrevista 01:07:12; professor (22/10/2026) |
| RN03 | As quatro ações sobre uma portaria | entrevista 23:48–27:04; professor (22/10/2026) para a prorrogação |
| RN04 | Limites de carga horária | entrevista 46:12–48:32; professor (22/10/2026) para a exceção |
| RN05 | Perfis de acesso | entrevista 14:56–18:12, 42:56, 51:20–52:16 |
| RN06 | Transparência e LGPD | entrevista 51:20–53:12 |
| RN07 | Membros e papéis | entrevista 14:00–14:28, 38:44–39:12 |
| RN08 | Prazos e vácuo | entrevista 05:36, 07:00, 24:16, 59:16; professor (22/10/2026) |
=======
| RN01 | Quem emite portarias | entrevista 15:52, 40:36, 41:32 |
| RN02 | Início da vigência | entrevista 01:07:12; pesquisa |
| RN03 | As quatro ações sobre uma portaria | entrevista 23:48–27:04 |
| RN04 | Limites de carga horária | entrevista 46:12–48:32 |
| RN05 | Perfis de acesso | entrevista 14:56–18:12, 42:56, 51:20–52:16 |
| RN06 | Transparência e LGPD | entrevista 51:20–53:12 |
| RN07 | Membros e papéis | entrevista 14:00–14:28, 38:44–39:12 |
| RN08 | Prazos e vácuo | entrevista 05:36, 07:00, 24:16, 59:16 |
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881
| RN09 | Nada é apagado | entrevista 25:12, 36:24 |

---

<<<<<<< HEAD
## Regras atômicas

Cada regra acima reúne regras menores. Para que cada uma possa ser verificada e testada isoladamente, elas estão desdobradas abaixo no formato **condição → ação**, com a restrição ou exceção quando houver. Os números RN01 a RN09 são os mesmos citados no Figma.

| ID | Condição (SE) | Ação (ENTÃO) | Restrição ou exceção |
|---|---|---|---|
| RN01.1 | o usuário não tem perfil Emissor | não pode criar nem efetivar portarias | pode apenas solicitar, se for Solicitante |
| RN01.2 | a portaria trata de atos administrativos, compras ou contratos | o setor emissor é o Gabinete | — |
| RN01.3 | a portaria trata de gestão de pessoas, lotação ou férias | o setor emissor é a CGP | — |
| RN01.4 | a portaria foi elaborada pelo Gabinete ou pela CGP | segue para assinatura do Diretor-Geral no SIPAC | — |
| RN02.1 | o ato exige publicação no DOU | a vigência começa na publicação no DOU | — |
| RN02.2 | o ato não exige DOU e o texto não indica data | a vigência começa na publicação no Boletim de Serviço | — |
| RN02.3 | o texto indica uma data de vigência | vale a data indicada | data retroativa só em caráter excepcional e expressa no ato |
| RN03.1 | a portaria está vigente e um membro precisa ser trocado | gera documento acessório (ex.: 112-A/2026) com datas de saída e de entrada | objeto e validade não mudam |
| RN03.4 | a portaria está vigente e o trabalho continua | prorroga por alteração do prazo, com documento acessório (ex.: 112-B/2026) | objeto não muda; a versão anterior fica no histórico |
| RN03.2 | há erro material (nome, SIAPE, digitação) | gera retificação | conteúdo e prazo não mudam |
| RN03.3 | a portaria precisa deixar de valer | cria nova portaria com cláusula revogatória | a portaria anterior não é apagada |
| RN04.1 | a soma das horas em portarias vigentes ultrapassaria a jornada contratual | bloqueia a inclusão com alerta crítico | — |
| RN04.2 | o servidor é docente e a soma ultrapassaria 10 h semanais | bloqueia a inclusão com alerta crítico | o Emissor pode pedir exceção (RN04.4) |
| RN04.3 | a soma atinge 80% ou mais do limite | mostra o status “Perto do limite” | não bloqueia |
| RN04.4 | há pedido de exceção ao limite docente, com justificativa | o DEP, o DAP ou o DG aprova ou recusa no próprio sistema | só após a aprovação a inclusão é liberada; a decisão fica no histórico |
| RN05.1 | o usuário acumula perfis | pode trocar de perfil pelo menu do usuário | o perfil vem do cadastro, não é escolhido no login (no protótipo, as abas do login só simulam a pessoa de teste) |
| RN05.2 | o usuário é Chefia de setor | vê relatórios só do próprio setor | — |
| RN06.1 | a consulta é pública (sem login) | exibe número, objeto, membros, papéis, horas e vigência | CPF e dados sensíveis nunca aparecem |
| RN06.2 | o relatório compara servidores | exige perfil Gestão ou Chefia | — |
| RN07.1 | o membro é externo (aluno, comunidade, empresa) | é cadastrado sem SIAPE e sem carga horária institucional | não entra no cálculo da RN04 |
| RN08.1 | faltam de 7 a 5 dias para o vencimento de uma portaria com prazo | avisa presidente, chefia e Gabinete | o aviso continua até a prorrogação ou o vencimento |
| RN08.3 | a portaria vai vencer e o trabalho continua | a prorrogação é feita antes do vencimento (RN03.4) | não pode haver vácuo entre o fim do prazo e a prorrogação |
| RN08.2 | o prazo termina sem prorrogação | a portaria passa a “Vencida” | — |
| RN09.1 | a portaria foi assinada | nenhuma exclusão é permitida | versões, alterações e revogadas ficam guardadas |

## Tabelas de decisão

### Início da vigência (RN02)

| Exige publicação no DOU? | O texto indica data? | Início da vigência |
|---|---|---|
| Sim | — | Data da publicação no DOU |
| Não | Sim | Data indicada no texto (ex.: “a partir desta data” = assinatura no SIPAC) |
| Não | Não | Data da publicação no Boletim de Serviço |

### Inclusão de membro (RN04 e RN07)

| Vínculo | Soma após a inclusão | Ação do sistema | Status exibido |
|---|---|---|---|
| Externo | — | Permite; não soma horas | Não se aplica |
| TAE | menor que 80% da jornada | Permite | Dentro do limite |
| TAE | de 80% até a jornada | Permite | Perto do limite / No limite |
| TAE | acima da jornada | Bloqueia com alerta crítico | Acima do limite |
| Docente | menor que 8 h | Permite | Dentro do limite |
| Docente | de 8 h até 10 h | Permite | Perto do limite / No limite |
| Docente | acima de 10 h, sem exceção | Bloqueia com alerta crítico e oferece “Pedir exceção” | Acima do limite |
| Docente | acima de 10 h, com exceção aprovada pelo DEP, DAP ou DG | Permite e registra a exceção no histórico | Acima do limite (exceção aprovada) |

---

=======
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881
## RN01 – Quem emite portarias

Só perfis **Emissores** criam e efetivam portarias. No Campus Videira:

- **Gabinete:** atos administrativos, compras e contratos;
- **CGP (Coordenação de Gestão de Pessoas):** gestão de pessoas, lotação e férias.

<<<<<<< HEAD
O Gabinete e a CGP elaboram; quem **assina** é o **Diretor-Geral**, no SIPAC (confirmado pelo professor em 22/10/2026).
=======
Quais setores emitem é configurável por campus; em alguns campi, só a CGP emite.
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

**No protótipo:** o item **Nova portaria** só aparece no menu do Emissor; na etapa 1 o Emissor escolhe o setor emissor (Gabinete ou CGP), com a explicação de cada um.

## RN02 – Início da vigência

<<<<<<< HEAD
- Atos com **publicação obrigatória no DOU** (nomeação de CD/FG, editais, licitações e contratos) só produzem efeito a partir da publicação no DOU.
- Os demais passam a valer pela publicação no **Boletim de Serviço** ou pela **data indicada no próprio texto** (ex.: “a partir desta data” = data da assinatura no SIPAC).
- Datas futuras e, excepcionalmente, retroativas são permitidas quando expressas no ato.

**Fonte:** entrevista 01:07:12 (“algumas portarias dependem da publicação no Diário Oficial”); lista de atos confirmada pelo professor em 22/10/2026.
=======
- Atos com **publicação obrigatória no DOU** (nomeação de CD/FG, editais, licitações, contratos, dispensas e atos com efeito perante terceiros) só produzem efeito a partir da publicação no DOU.
- Os demais passam a valer pela publicação no **Boletim de Serviço** ou pela **data indicada no próprio texto** (ex.: “a partir desta data” = data da assinatura no SIPAC).
- Datas futuras e, excepcionalmente, retroativas são permitidas quando expressas no ato.

**Fonte:** entrevista 01:07:12; pesquisa (Lei nº 4.965/1966 e Boletins de Serviço do IFC). **Confirmar com o Gabinete.**
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

**No protótipo:** a etapa 1 da nova portaria pergunta “Exige publicação no DOU?” e oferece o início da vigência; o detalhe da portaria mostra a publicação e se o DOU foi exigido.

## RN03 – As quatro ações sobre uma portaria

| Ação | O que faz | O que não muda | Documento gerado |
|---|---|---|---|
| **Cadastro** | Emissão original | — | Portaria com número próprio (ex.: 112/2026) |
<<<<<<< HEAD
| **Alteração** | Substitui membros, registrando a data de saída e a de entrada de cada um, **ou prorroga o prazo** | Objeto (e, na troca de membros, a validade) | Documento acessório vinculado (ex.: 112-A/2026 para membros, 112-B/2026 para prazo); a versão anterior fica no histórico |
| **Retificação** | Corrige erro material (nome, SIAPE, digitação) | Conteúdo e prazo | Retificação vinculada |
| **Revogação** | Encerra a portaria anterior | — | Nova portaria com cláusula revogatória |

**Exemplo no protótipo:** na Portaria 112/2026 (Comissão de Estágio), Juliana Rocha entra no lugar de Rafael Costa a partir de 05/09/2026 pelo documento 112-A/2026. Rafael continua aparecendo no detalhe como “substituído”, e o extrato dele mostra só o período de 03/04 a 04/09/2026. A mesma portaria pode ser **prorrogada** pela tela “Prorrogar”, que gera a alteração 112-B/2026 e estende a vigência até 03/10/2027.
=======
| **Alteração** | Substitui membros, registrando a data de saída e a de entrada de cada um | Objeto e validade | Documento acessório vinculado (ex.: 112-A/2026) |
| **Retificação** | Corrige erro material (nome, SIAPE, digitação) | Conteúdo e prazo | Retificação vinculada |
| **Revogação** | Encerra a portaria anterior | — | Nova portaria com cláusula revogatória |

**Exemplo no protótipo:** na Portaria 112/2026 (Comissão de Estágio), Juliana Rocha entra no lugar de Rafael Costa a partir de 05/09/2026 pelo documento 112-A/2026. Rafael continua aparecendo no detalhe como “substituído”, e o extrato dele mostra só o período de 03/04 a 04/09/2026.
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

## RN04 – Limites de carga horária

1. A soma das horas de todas as portarias **vigentes** de um servidor nunca ultrapassa a jornada contratual (ex.: 20, 25 ou 40 h).
<<<<<<< HEAD
2. **Docentes:** no máximo **10 h semanais** em portarias, pelo Regulamento de Atividades Docentes.
3. **Técnicos administrativos (TAE):** apenas o limite contratual.
4. Uma inclusão acima do limite é **bloqueada** com alerta crítico.
5. **Exceção:** o Emissor pede a exceção com justificativa, e o **DEP, o DAP ou o DG** aprova ou recusa **dentro do sistema**; a decisão fica no histórico da portaria (professor, 22/10/2026).
6. “Perto do limite” = 80% ou mais do limite.

**Exemplo no protótipo:** Diego Alves (docente) tem 9 h; incluí-lo com mais 2 h levaria a 11 h. A linha fica vermelha, aparece o alerta e o botão **Continuar** fica desabilitado. Há dois caminhos: **pedir exceção** (link no alerta, que abre o pedido e, do lado da Gestão, a tela de aprovação) ou **substituir** Diego por Fábio Nunes (TAE, de 18 h para 20 h de 40 h), e a portaria pode seguir.
=======
2. **Docentes:** no máximo **10 h semanais** em portarias, pelo Regulamento de Atividades Docentes. Exceções são avaliadas pela Diretora de Ensino.
3. **Técnicos administrativos (TAE):** apenas o limite contratual.
4. Uma inclusão acima do limite é **bloqueada** com alerta crítico.
5. “Perto do limite” = 80% ou mais do limite.

**Exemplo no protótipo:** Diego Alves (docente) tem 9 h; incluí-lo com mais 2 h levaria a 11 h. A linha fica vermelha, aparece o alerta e o botão **Continuar** fica desabilitado. Na versão ajustada, Diego é substituído por Fábio Nunes (TAE, de 18 h para 20 h de 40 h) e a portaria pode seguir.
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

| Situação | Condição | Status exibido |
|---|---|---|
| Dentro do limite | menos de 80% | verde |
| Perto do limite | de 80% a menos de 100% | laranja |
| No limite | exatamente 100% | laranja |
<<<<<<< HEAD
| Acima do limite | inclusão bloqueada, salvo exceção aprovada | vermelho |
=======
| Acima do limite | inclusão bloqueada | vermelho |
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

## RN05 – Perfis de acesso

| Perfil | Quem | O que pode fazer |
|---|---|---|
| **Público / Servidor** | Qualquer pessoa (sem login) / qualquer servidor autenticado | Consultar portarias publicadas; o servidor também vê o próprio extrato e a carga horária e dá ciência |
| **Solicitante** | Coordenadores e presidentes de comissão | Pedir portarias, alterações e prorrogações |
<<<<<<< HEAD
| **Emissor** | Gabinete e CGP | Validar pedidos, elaborar, alterar, prorrogar, retificar, revogar e enviar ao SIPAC; pedir exceção de carga horária; gerar o Boletim de Serviço |
| **Chefia de setor** | Chefes de setor | Relatórios de carga horária **só do próprio setor** |
| **Gestão** | Diretor-Geral (DG), Diretora de Ensino (DEP), Diretor Administrativo (DAP) e Chefe de Gabinete | Relatórios completos; o DEP, o DAP e o DG aprovam exceções ao limite de carga horária |
=======
| **Emissor** | Gabinete e CGP | Validar pedidos, elaborar, alterar, retificar, revogar e enviar ao SIPAC; gerar o Boletim de Serviço |
| **Chefia de setor** | Chefes de setor | Relatórios de carga horária **só do próprio setor** |
| **Gestão** | Diretor-Geral, Diretora de Ensino, Diretor Administrativo e Chefe de Gabinete | Relatórios completos |
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

- Um usuário pode **acumular perfis** (ex.: uma docente que também coordena um curso é Servidora e Solicitante).
- O perfil vem do cadastro institucional; **não é escolhido na tela de login**.

<<<<<<< HEAD
**No protótipo:** o login grava a pessoa de teste em variáveis do Figma, e o menu lateral, a barra superior e os atalhos mudam conforme o perfil: Nova portaria e Boletim de Serviço só para o Emissor; Relatórios só para Gestão e Chefia (esta vê só o próprio setor); Solicitações para quem pede e para quem analisa. As abas de perfil no login, marcadas como “Ambiente de desenvolvimento”, existem só para a demonstração.

| Pessoa de teste | Perfis |
|---|---|
| Maria · Docente EBTT | Servidor e Solicitante (presidente da Comissão de TCC) |
| Fabrício · Servidor TAE | Servidor |
| Thiago · CGP | Emissor e Servidor |
| Julia · Coordenação de Ciência da Computação | Chefia de setor e Servidor |
| Willian · Diretor-Geral | Gestão e Servidor |
=======
**No protótipo:** o menu lateral muda conforme o perfil: Nova portaria só para o Emissor e Relatórios só para Gestão e Chefia.
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

## RN06 – Transparência e LGPD

- Portarias são **atos públicos**: nome, papel e carga horária dos membros podem ser exibidos a qualquer pessoa.
- **CPF** e dados sensíveis **nunca** aparecem na consulta pública.
- **Relatórios comparativos** entre servidores ficam restritos à Gestão e às Chefias (estas, só do próprio setor), para evitar constrangimentos.

**No protótipo:** a consulta pública traz o aviso “Dados exibidos”; os relatórios mostram a faixa “Acesso restrito”.

## RN07 – Membros e papéis

- Membros podem ser **servidores** (da base institucional) ou **externos** (alunos, comunidade, empresas).
- Externos são cadastrados **sem SIAPE** e **sem carga horária institucional**.
- Papéis conforme o tipo de portaria: Presidente, Coordenador, Secretário, Membro, Fiscal de contrato.

**No protótipo:** o botão **Membro externo** abre um modal próprio; o externo aparece na lista com “Não se aplica (externo)” na coluna de carga.

## RN08 – Prazos e vácuo

- O prazo pode ser **determinado** (ex.: colegiado, 2 anos), **data fechada** ou **indeterminado** (portarias normativas).
<<<<<<< HEAD
- **Aviso:** presidente, chefia e Gabinete são avisados **de 7 a 5 dias antes** do vencimento (professor, 22/10/2026).
- **Não pode haver vácuo:** a prorrogação deve ser feita **antes** do vencimento. Ela é uma **alteração** da portaria que estende o prazo e mantém o histórico (RN03).

**No protótipo:** a etapa 1 tem o segmento “Tipo de prazo”; a Portaria 112/2026 mostra o aviso de vencimento (faltando 3 dias, depois dos primeiros avisos), e o menu de ações leva à tela **Prorrogar**, que altera o prazo e mantém o histórico.
=======
- **Não pode haver vácuo:** a prorrogação ou a nova portaria deve ser emitida **antes** do vencimento.

**No protótipo:** a etapa 1 tem o segmento “Tipo de prazo”; a Portaria 112/2026 mostra o aviso de vencimento em 3 dias, e o menu de ações oferece **Prorrogar** (nova portaria com o mesmo objeto).
>>>>>>> d6bbe2420940a307e4281d6f372dfda392b37881

## RN09 – Nada é apagado

Depois de assinada, nenhuma portaria é excluída. Versões, alterações, retificações e portarias revogadas ficam guardadas permanentemente e continuam no extrato para auditoria.

**No protótipo:** o detalhe da portaria tem o “Histórico de versões” (v1 criada, v2 assinada, v3 alteração 112-A/2026); o extrato lista a portaria revogada 22/2025.
