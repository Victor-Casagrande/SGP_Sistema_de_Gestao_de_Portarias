# 04 – Critérios de aceitação

Os critérios estão escritos no formato **Dado / Quando / Então**. Cada cenário pode ser verificado no protótipo do Figma; o campo **Tela** indica onde. Os requisitos e as regras citados estão em [05 – Requisitos](05-requisitos.md) e [06 – Regras de negócio](06-regras-de-negocio.md).

## Interfaces obrigatórias

### a) Login com usuário e senha

O usuário é a **matrícula SIAPE** e a senha é a mesma da rede institucional (LDAP/AD da Reitoria, RNF01).

| # | Cenário | Dado | Quando | Então | Tela |
|---|---|---|---|---|---|
| CA-L1 | Login válido | um servidor com matrícula e senha corretas | clica em **Entrar** | vê o estado “Entrando…” e em seguida a Home com o próprio nome e perfil | Login – Padrão → Login – Carregando → Painel – Início |
| CA-L2 | Credenciais inválidas | matrícula ou senha incorretas | clica em **Entrar** | vê a mensagem “Matrícula ou senha incorretos. Confira os dados e tente novamente.”, o campo de senha fica em vermelho e há a dica sobre maiúsculas e minúsculas | Login – Erro |
| CA-L3 | Mostrar senha | a senha digitada | clica no ícone de olho | a senha fica visível | Login – Padrão |
| CA-L4 | Sem seletor de perfil | qualquer usuário | abre a tela de login | não há escolha de perfil: o perfil vem do cadastro (RN05) | Login – Padrão |
| CA-L5 | Acesso à recuperação | a tela de login | clica em **Esqueci minha senha** | vai para a recuperação de senha | Recuperar senha – 1 |
| CA-L6 | Ajuda | a tela de login | lê o rodapé do formulário | encontra a orientação “Problemas para entrar? Fale com a DTIC do campus.” | Login – Padrão |

### b) Recuperação de senha

| # | Cenário | Dado | Quando | Então | Tela |
|---|---|---|---|---|---|
| CA-R1 | Pedir o link | a tela “Recuperar senha” | informa a matrícula SIAPE e clica em **Enviar link** | vê “Verifique seu e-mail”, com o e-mail institucional parcialmente oculto e a validade de 30 minutos | Recuperar senha – 1 → 2 |
| CA-R2 | Reenviar | a tela “Verifique seu e-mail” | aguarda o contador | pode pedir o reenvio depois de 60 segundos | Recuperar senha – 2 |
| CA-R3 | Regras da nova senha | o link aberto | digita a nova senha | vê, item a item, se ela tem pelo menos 8 caracteres, uma letra maiúscula, um número e se as duas senhas são iguais | Recuperar senha – 3 |
| CA-R4 | Concluir | uma senha que atende às quatro regras | clica em **Salvar nova senha** | vê “Senha alterada” e o botão **Ir para o login** | Recuperar senha – 3 → 4 → Login |
| CA-R5 | Voltar | qualquer etapa da recuperação | clica em **Voltar ao login** | retorna ao login sem perder nada | Recuperar senha – 1 e 2 |
| CA-R6 | Senha única | a nova senha salva | entra em outro sistema institucional | a mesma senha funciona, porque a troca é feita no LDAP (RNF01) | — |

### c) Home com menu

| # | Cenário | Dado | Quando | Então | Tela |
|---|---|---|---|---|---|
| CA-H1 | Menu lateral | um usuário autenticado | abre qualquer tela interna | vê o menu lateral com o item atual destacado e o botão **Sair** | Painel – Início |
| CA-H2 | Menu conforme o perfil | uma servidora que também é solicitante | abre a Home | o menu mostra Início, Portarias, Solicitações, Carga horária, Alertas e Extrato; **Nova portaria** aparece só para Emissores e **Relatórios** só para Gestão e Chefias (RN05) | Painel – Início; Relatórios – gestão |
| CA-H3 | Resumo pessoal | a servidora Maria Silva, docente | abre a Home | vê portarias vigentes, horas em portarias (8 h de 10 h), alertas e ciências pendentes | Painel – Início |
| CA-H4 | Pendência acionável | uma ciência pendente | clica em **Dar ciência na Portaria 98/2026** | abre a tela de ciência da portaria | Painel – Início → Ciência |
| CA-H5 | Barra superior | qualquer tela interna | olha o topo | vê a busca, o sino de notificações com indicador e o menu do usuário com nome e perfil | Painel – Início |
| CA-H6 | Sair | o menu lateral ou o menu do usuário | clica em **Sair** | volta à tela de login | Painel – Início |

## Requisitos funcionais

| # | Req. | Dado | Quando | Então |
|---|---|---|---|---|
| CA-01 | RF01 | um coordenador ou presidente de comissão | envia uma solicitação sem justificativa | o envio é recusado e o campo indica “Obrigatória. Pedidos sem justificativa são devolvidos.” |
| CA-02 | RF01 | um solicitante preenchendo o pedido | busca membros por nome ou SIAPE | os membros são escolhidos da base institucional, já com a carga horária após a inclusão |
| CA-03 | RF02 | um emissor na fila de solicitações | clica em **Devolver** sem comentário | a devolução não é concluída, porque o comentário é obrigatório |
| CA-04 | RF02 | um pedido completo | o emissor clica em **Aprovar e elaborar** | a nova portaria abre na etapa 1, com a origem (Solicitação 34/2026) indicada |
| CA-05 | RF03 | um emissor elaborando a portaria | avança pelas etapas | passa pelas 6 etapas na ordem (dados gerais, epígrafe e ementa, preâmbulo, corpo, membros, revisão) e a prévia do documento é atualizada a cada etapa |
| CA-06 | RF03, RN02 | a etapa 1 | marca “Exige publicação no DOU? Não” | o início da vigência pode ser o Boletim de Serviço ou a data indicada no texto |
| CA-07 | RF04, RN04 | um docente com 9 h em portarias | o emissor tenta incluí-lo com mais 2 h | a linha fica em vermelho, aparece o alerta crítico e o botão **Continuar** fica desabilitado até a troca do membro ou a redução das horas |
| CA-08 | RF04, RN07 | um membro externo (aluno) | o emissor o adiciona por **Membro externo** | ele entra sem SIAPE e sem carga horária (“Não se aplica”) |
| CA-09 | RF05 | a etapa de revisão completa | o emissor clica em **Enviar para assinatura no SIPAC** | a portaria passa a “Aguardando assinatura”; nenhum dado é redigitado no SIPAC |
| CA-10 | RF05, RNF02 | o SIPAC fora do ar | o emissor tenta enviar | o envio fica suspenso e o sistema avisa; não há fila offline |
| CA-11 | RF06 | qualquer portaria | é aberta na busca ou no detalhe | mostra um único estado: Solicitada, Em análise, Devolvida, Em elaboração, Aguardando assinatura, Vigente, Vencida ou Revogada |
| CA-12 | RF07, RN03 | a Portaria 112/2026 vigente | o emissor troca Rafael Costa por Juliana Rocha | é gerado o documento acessório 112-A/2026, com data de saída (04/09) e de entrada (05/09), sem mudar o objeto nem a vigência |
| CA-13 | RF07, RF12 | a alteração assinada | Rafael abre o extrato | a participação aparece apenas de 03/04 a 04/09/2026, marcada como “substituído” |
| CA-14 | RF08 | um erro de digitação em nome ou SIAPE | o emissor retifica | só o texto muda, com justificativa obrigatória; o prazo e o conteúdo permanecem |
| CA-15 | RF08, RN03 | uma portaria a revogar | o emissor revoga | é criada uma nova portaria com cláusula revogatória vinculada; a antiga passa a “Revogada” e continua consultável |
| CA-16 | RF09 | um servidor em várias portarias | o sistema soma as horas | o total considera só as portarias vigentes e é comparado à jornada e, para docentes, ao limite de 10 h |
| CA-17 | RF10 | uma portaria perto do vencimento | faltam poucos dias para o fim | presidente, chefia e Gabinete recebem o aviso, e o detalhe da portaria mostra a faixa de alerta |
| CA-18 | RF10 | uma portaria assinada | o membro clica em **Estou ciente do teor** | a ciência fica registrada com data e hora e aparece no detalhe da portaria |
| CA-19 | RF11, RN06 | um visitante sem login | busca “NDE” na consulta pública | vê número, objeto, membros, vigência e situação, sem CPF ou outros dados pessoais |
| CA-20 | RF12 | uma servidora autenticada | abre o extrato | vê todas as suas portarias com período, função, horas e status, e pode exportar em PDF |
| CA-21 | RF13, RN06 | um usuário da Gestão | abre os relatórios | vê a carga horária de todos os servidores e o histórico por objeto, com aviso de acesso restrito |
| CA-22 | RF13, RN05 | uma chefia de setor | abre os relatórios | vê apenas os servidores do próprio setor |
| CA-23 | RF14 | um emissor | escolhe o mês no Boletim de Serviço | vê os atos do mês (portarias, alterações, retificações, revogações) e pode gerar o PDF |
| CA-24 | RF15, RN09 | uma portaria com alterações | é aberto o histórico de versões | aparecem todas as versões com descrição, justificativa, autor, data e número do documento; nada é apagado |

## Requisitos não funcionais

| # | Req. | Critério verificável |
|---|---|---|
| CA-N1 | RNF01 | Nome, nome social, SIAPE, CPF, vínculo e lotação nunca são digitados no SGP; vêm do cadastro central. |
| CA-N2 | RNF03 | A busca de membros mostra resultados enquanto o usuário digita, sem bloquear os demais campos. |
| CA-N3 | RNF04 | Toda ação registra autor, data e hora e o que mudou; o IP não aparece em nenhuma tela. |
| CA-N4 | RNF05 | O CPF não aparece na consulta pública nem nos relatórios. |
| CA-N5 | RNF06 | Não existe botão de exportação para planilha; as exportações são em PDF. |
| CA-N6 | Acessibilidade | Texto sobre a cor de ação (`Marca/600`) com contraste mínimo de 4,5:1 (WCAG AA). |
| CA-N7 | Protótipo | Todo campo de seleção abre a lista de opções com a opção atual destacada; clicar numa opção ou fora da lista a fecha. |

## Landing page

| # | Cenário | Então |
|---|---|---|
| CA-LP1 | O visitante clica em **Entrar no SGP** (cabeçalho, hero ou chamada final) | vai para o login |
| CA-LP2 | O visitante clica em um card de funcionalidade | abre a sobreposição daquela funcionalidade, com navegação para a anterior e a próxima e botão de fechar |
| CA-LP3 | O visitante clica em **Consultar portarias** | vai para a consulta pública, sem login |
| CA-LP4 | O visitante clica em **Sobre** ou **Funcionalidades** no cabeçalho | a página rola até a seção correspondente; **Documentos** leva à consulta pública |
| CA-LP5 | O visitante passa o mouse sobre um card ou botão | o elemento muda para o estado de hover |
| CA-LP6 | O visitante clica num link externo do rodapé | o link do IFC abre no navegador ou aparece o aviso de link externo |

## Definição de Pronto (DoD)

Um item do backlog só é considerado **pronto** quando:

1. a tela ou o documento atende a todos os critérios de aceitação ligados a ele;
2. as telas usam componentes do design system e os estilos de texto, cor e efeito, sem valores soltos;
3. todo elemento clicável tem destino no protótipo, ou está documentado como intencionalmente sem destino;
4. os dados de exemplo são coerentes com as outras telas (nomes, números de portaria, horas);
5. os textos foram revisados (ortografia, termos do domínio, mensagens de erro claras);
6. o documento correspondente no repositório foi atualizado;
7. outro integrante revisou e o Product Owner aceitou na revisão da sprint.
