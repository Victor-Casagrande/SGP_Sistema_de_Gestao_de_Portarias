# 06 – Regras de negócio

As regras de negócio descrevem as políticas do campus que o sistema precisa respeitar, independentemente da tela. Todas foram tiradas da entrevista com o Diretor-Geral; a RN02 foi complementada por pesquisa da equipe e precisa ser confirmada com o Gabinete.

## Resumo

| ID | Regra | Fonte |
|---|---|---|
| RN01 | Quem emite portarias | entrevista 15:52, 40:36, 41:32 |
| RN02 | Início da vigência | entrevista 01:07:12; pesquisa |
| RN03 | As quatro ações sobre uma portaria | entrevista 23:48–27:04 |
| RN04 | Limites de carga horária | entrevista 46:12–48:32 |
| RN05 | Perfis de acesso | entrevista 14:56–18:12, 42:56, 51:20–52:16 |
| RN06 | Transparência e LGPD | entrevista 51:20–53:12 |
| RN07 | Membros e papéis | entrevista 14:00–14:28, 38:44–39:12 |
| RN08 | Prazos e vácuo | entrevista 05:36, 07:00, 24:16, 59:16 |
| RN09 | Nada é apagado | entrevista 25:12, 36:24 |

---

## RN01 – Quem emite portarias

Só perfis **Emissores** criam e efetivam portarias. No Campus Videira:

- **Gabinete:** atos administrativos, compras e contratos;
- **CGP (Coordenação de Gestão de Pessoas):** gestão de pessoas, lotação e férias.

Quais setores emitem é configurável por campus; em alguns campi, só a CGP emite.

**No protótipo:** o item **Nova portaria** só aparece no menu do Emissor; na etapa 1 o Emissor escolhe o setor emissor (Gabinete ou CGP), com a explicação de cada um.

## RN02 – Início da vigência

- Atos com **publicação obrigatória no DOU** (nomeação de CD/FG, editais, licitações, contratos, dispensas e atos com efeito perante terceiros) só produzem efeito a partir da publicação no DOU.
- Os demais passam a valer pela publicação no **Boletim de Serviço** ou pela **data indicada no próprio texto** (ex.: “a partir desta data” = data da assinatura no SIPAC).
- Datas futuras e, excepcionalmente, retroativas são permitidas quando expressas no ato.

**Fonte:** entrevista 01:07:12; pesquisa (Lei nº 4.965/1966 e Boletins de Serviço do IFC). **Confirmar com o Gabinete.**

**No protótipo:** a etapa 1 da nova portaria pergunta “Exige publicação no DOU?” e oferece o início da vigência; o detalhe da portaria mostra a publicação e se o DOU foi exigido.

## RN03 – As quatro ações sobre uma portaria

| Ação | O que faz | O que não muda | Documento gerado |
|---|---|---|---|
| **Cadastro** | Emissão original | — | Portaria com número próprio (ex.: 112/2026) |
| **Alteração** | Substitui membros, registrando a data de saída e a de entrada de cada um | Objeto e validade | Documento acessório vinculado (ex.: 112-A/2026) |
| **Retificação** | Corrige erro material (nome, SIAPE, digitação) | Conteúdo e prazo | Retificação vinculada |
| **Revogação** | Encerra a portaria anterior | — | Nova portaria com cláusula revogatória |

**Exemplo no protótipo:** na Portaria 112/2026 (Comissão de Estágio), Juliana Rocha entra no lugar de Rafael Costa a partir de 05/09/2026 pelo documento 112-A/2026. Rafael continua aparecendo no detalhe como “substituído”, e o extrato dele mostra só o período de 03/04 a 04/09/2026.

## RN04 – Limites de carga horária

1. A soma das horas de todas as portarias **vigentes** de um servidor nunca ultrapassa a jornada contratual (ex.: 20, 25 ou 40 h).
2. **Docentes:** no máximo **10 h semanais** em portarias, pelo Regulamento de Atividades Docentes. Exceções são avaliadas pela Diretora de Ensino.
3. **Técnicos administrativos (TAE):** apenas o limite contratual.
4. Uma inclusão acima do limite é **bloqueada** com alerta crítico.
5. “Perto do limite” = 80% ou mais do limite.

**Exemplo no protótipo:** Diego Alves (docente) tem 9 h; incluí-lo com mais 2 h levaria a 11 h. A linha fica vermelha, aparece o alerta e o botão **Continuar** fica desabilitado. Na versão ajustada, Diego é substituído por Fábio Nunes (TAE, de 18 h para 20 h de 40 h) e a portaria pode seguir.

| Situação | Condição | Status exibido |
|---|---|---|
| Dentro do limite | menos de 80% | verde |
| Perto do limite | de 80% a menos de 100% | laranja |
| No limite | exatamente 100% | laranja |
| Acima do limite | inclusão bloqueada | vermelho |

## RN05 – Perfis de acesso

| Perfil | Quem | O que pode fazer |
|---|---|---|
| **Público / Servidor** | Qualquer pessoa (sem login) / qualquer servidor autenticado | Consultar portarias publicadas; o servidor também vê o próprio extrato e a carga horária e dá ciência |
| **Solicitante** | Coordenadores e presidentes de comissão | Pedir portarias, alterações e prorrogações |
| **Emissor** | Gabinete e CGP | Validar pedidos, elaborar, alterar, retificar, revogar e enviar ao SIPAC; gerar o Boletim de Serviço |
| **Chefia de setor** | Chefes de setor | Relatórios de carga horária **só do próprio setor** |
| **Gestão** | Diretor-Geral, Diretora de Ensino, Diretor Administrativo e Chefe de Gabinete | Relatórios completos |

- Um usuário pode **acumular perfis** (ex.: uma docente que também coordena um curso é Servidora e Solicitante).
- O perfil vem do cadastro institucional; **não é escolhido na tela de login**.

**No protótipo:** o menu lateral muda conforme o perfil: Nova portaria só para o Emissor e Relatórios só para Gestão e Chefia.

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
- **Não pode haver vácuo:** a prorrogação ou a nova portaria deve ser emitida **antes** do vencimento.

**No protótipo:** a etapa 1 tem o segmento “Tipo de prazo”; a Portaria 112/2026 mostra o aviso de vencimento em 3 dias, e o menu de ações oferece **Prorrogar** (nova portaria com o mesmo objeto).

## RN09 – Nada é apagado

Depois de assinada, nenhuma portaria é excluída. Versões, alterações, retificações e portarias revogadas ficam guardadas permanentemente e continuam no extrato para auditoria.

**No protótipo:** o detalhe da portaria tem o “Histórico de versões” (v1 criada, v2 assinada, v3 alteração 112-A/2026); o extrato lista a portaria revogada 22/2025.
