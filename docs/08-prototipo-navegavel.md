# 08 – Prototipação funcional e navegável

O protótipo está na página **Telas (protótipo)** do Figma. Todas as telas ficam na mesma página, porque o Figma não liga telas de páginas diferentes no modo de apresentação.

**Link do protótipo:** https://www.figma.com/proto/ezXFmUokd7Vfb36NjGNrG0?node-id=2010-2&starting-point-node-id=2010%3A2

## Números

| Item | Quantidade |
|---|---|
| Telas | 33 (incluindo o diagrama do ciclo de vida) |
| Sobreposições (modais, menus, listas de seleção e avisos) | 49 |
| Interações configuradas | 815 |
| Fluxos iniciais (pontos de partida) | 10 |
| Seções na página | 12 |

## Como navegar

1. Abra o link do protótipo (ou, no arquivo, clique em **Apresentar ▶** na página Telas).
2. No painel **Fluxos**, à esquerda, escolha o fluxo do perfil que quer testar.
3. Clique em qualquer área para ver em azul o que é clicável (comportamento padrão do Figma).
4. Para voltar ao início do fluxo, pressione **R**.

## Fluxos

### 1. Visitante: landing → login → painel

Landing → **Entrar no SGP** → Login → **Entrar** → “Entrando…” (avança sozinho em 1,2 s) → Painel – Início.
Na landing, os 12 cards de funcionalidade abrem sobreposições navegáveis entre si (anterior, próxima, fechar). Sobre e Funcionalidades rolam a página; Consultar portarias leva à consulta pública.

### 2. Consulta pública (sem login)

Consulta pública – busca → linha **98/2026** → Consulta pública – Portaria 98/2026 → **Baixar PDF** (aviso “Arquivo gerado”). O cabeçalho volta à landing ou leva ao login.

### 3. Login com erro · 3b. Recuperar senha

- **3:** Login – Erro → **Entrar** → Carregando → Painel.
- **3b:** Recuperar senha 1 → **Enviar link** → 2 (reenviar mostra o aviso “Link reenviado”) → **Abrir link do e-mail (simulação)** → 3 → **Salvar nova senha** → 4 → **Ir para o login**.

### 4. Servidora: painel, alertas e ciência

Painel – Início → **Dar ciência na Portaria 98/2026** → Ciência → **Estou ciente do teor** → Alertas.
Pelo menu: Carga horária (exportar gera aviso), Alertas (abas por tipo; Ver portaria, Dar ciência, Solicitar prorrogação), Extrato (abas Todas/Vigentes/Encerradas/Revogadas; Exportar PDF). O avatar abre o **menu do usuário**, com troca de perfil, Meu extrato e Sair.

### 5. Solicitante → Emissor → nova portaria

1. **Solicitação – nova** (Maria, solicitante): tipo de pedido, setor, prazo e membros sugeridos; **Membro externo** abre o modal; o X de um membro mostra o aviso “Membro removido” → **Enviar solicitação**.
2. **Solicitações – fila do Emissor** (João): **Aprovar e elaborar** (ou Devolver).
3. **Nova portaria 1 a 4**: cada etapa tem Continuar e Voltar; o indicador de etapas permite voltar a uma etapa concluída; **Salvar rascunho** mostra o aviso.
4. **Etapa 5 – Membros**: Diego Alves passaria de 9 h para 11 h; o alerta bloqueia o **Continuar**. Clicar no **X** da linha do Diego leva à versão **ajustada**, com Fábio Nunes no lugar.
5. **Etapa 6 – Revisão**: cada bloco tem **Editar**; **Enviar para assinatura no SIPAC** volta à lista de portarias.

### 6. Emissor: alterar, retificar, revogar

Portaria 112/2026 – detalhe → **Ações** (menu sobreposto) →
- **Alterar membros** → Enviar para assinatura → volta ao detalhe;
- **Retificar** → Enviar para assinatura → volta ao detalhe;
- **Prorrogar** → Nova portaria (mesmo objeto);
- **Revogar** → escolher “Com portaria substituta” ou “Sem substituta” → **Continuar para a nova portaria**.

Clicar fora do menu de ações o fecha.

### 7. Emissor: portarias e Boletim de Serviço

Portarias – busca (filtros; **Limpar filtros** mostra aviso; **Gerar relatório** gera arquivo) → linha 112/2026 → detalhe. **Boletim de Serviço** → Boletim de setembro/2026 → **Gerar boletim (PDF)**. **Nova portaria** abre a etapa 1.

### 8. Gestão: relatórios · 9. Chefia: relatórios do setor

Relatórios – gestão (Helena Duarte) e Relatórios – chefia de setor (Roberto Lima): abas Carga horária e Histórico por objeto; **Baixar PDF**. A chefia vê só os servidores do próprio setor.

## Mapa de navegação

```mermaid
flowchart LR
    LAND[Landing] -->|Entrar no SGP| LOGIN[Login]
    LAND -->|Consultar portarias| CP[Consulta pública]
    LAND -.->|cards| FUNC[[12 sobreposições de funcionalidade]]
    CP --> CPD[Consulta – Portaria 98/2026]
    LOGIN -->|Esqueci minha senha| R1[Recuperar 1] --> R2[Recuperar 2] --> R3[Recuperar 3] --> R4[Recuperar 4] --> LOGIN
    LOGIN -->|Entrar| LOAD[Carregando] -->|1,2 s| HOME[Painel – Início]

    HOME --> CARGA[Carga horária]
    HOME --> ALERT[Alertas]
    HOME --> EXT[Extrato]
    HOME --> CIEN[Ciência 98/2026] --> ALERT
    HOME --> SOL[Nova solicitação]

    SOL --> FILA[Fila do Emissor] -->|Aprovar e elaborar| N1[Nova portaria 1]
    N1 --> N2[2] --> N3[3] --> N4[4] --> N5[5 Membros – bloqueio]
    N5 -->|remover Diego| N5A[5 ajustado] --> N6[6 Revisão] -->|Enviar ao SIPAC| BUSCA

    BUSCA[Portarias – busca] --> DET[Portaria 112/2026]
    BUSCA --> BOL[Boletim de Serviço]
    DET -.->|Ações| MENU[[Menu de ações]]
    MENU --> ALT[Alterar membros] --> DET
    MENU --> RET[Retificar] --> DET
    MENU --> REV[Revogar] --> N1
    MENU -->|Prorrogar| N1

    REL[Relatórios – gestão]
    RELC[Relatórios – chefia]
```

## Telas

### Painéis do servidor

| Carga horária | Alertas e ações pendentes |
|---|---|
| ![Carga horária](imagens/08-carga-horaria.png) | ![Alertas](imagens/08-alertas.png) |
| **Extrato curricular** | **Ciência** |
| ![Extrato](imagens/08-extrato.png) | ![Ciência](imagens/08-ciencia.png) |

### Solicitações

| Nova solicitação (solicitante) | Fila do Emissor |
|---|---|
| ![Nova solicitação](imagens/08-solicitacao-nova.png) | ![Fila](imagens/08-solicitacoes-fila.png) |

### Nova portaria (6 etapas)

| 1. Dados gerais | 4. Corpo |
|---|---|
| ![Etapa 1](imagens/08-nova-portaria-1-dados-gerais.png) | ![Etapa 4](imagens/08-nova-portaria-4-corpo.png) |
| **5. Membros – bloqueio pela RN04** | **6. Revisão e envio** |
| ![Etapa 5](imagens/08-nova-portaria-5-membros-bloqueio.png) | ![Etapa 6](imagens/08-nova-portaria-6-revisao.png) |

### Portarias

| Busca | Detalhe com histórico |
|---|---|
| ![Busca](imagens/08-portarias-busca.png) | ![Detalhe](imagens/08-portaria-detalhe.png) |
| **Alterar membros (112-A/2026)** | **Boletim de Serviço** |
| ![Alterar membros](imagens/08-alterar-membros.png) | ![Boletim](imagens/08-boletim-servico.png) |

### Relatórios e consulta pública

| Relatórios – gestão | Consulta pública |
|---|---|
| ![Relatórios](imagens/08-relatorios-gestao.png) | ![Consulta pública](imagens/08-consulta-publica.png) |

## Tipos de interação usados

| Interação no Figma | Onde |
|---|---|
| **Navegar para** (Navigate) | Menu lateral, botões, breadcrumbs, linhas de tabela |
| **Abrir sobreposição** (Open overlay) | Modais de funcionalidade, menus do usuário, menu de ações, listas de seleção, modal de membro externo, avisos |
| **Rolar até** (Scroll to) | Links Sobre e Funcionalidades da landing; cabeçalho da consulta pública |
| **Mudar para** (Change to, variantes interativas) | Hover em botões e cards; segmentos e abas que alternam ao clicar |
| **Após atraso** (After delay) | “Entrando…” avança para a Home; avisos se fecham sozinhos |
| **Fechar sobreposição** | Botão X dos modais e clique fora dos menus |
| **Abrir link** (Open URL) | Links do rodapé para os sites do IFC |

## Listas de seleção e menus do usuário

Todos os 26 campos de seleção do protótipo abrem uma **lista de opções** em sobreposição (23 listas, na seção **Seleções (sobreposições)**). A opção atual aparece destacada; clicar em qualquer opção ou fora da lista fecha a sobreposição.

Cada pessoa de exemplo tem o próprio **menu do usuário** (Maria, João, Helena e Roberto), aberto pelo avatar na barra superior, com a troca entre os perfis que ela acumula, Meu extrato e Sair.

| Lista de seleção | Menu do usuário (Emissor) |
|---|---|
| ![Lista de seleção](imagens/08-selecao-sobreposicao.png) | ![Menu do usuário](imagens/08-menu-usuario-emissor.png) |

## Limitações conhecidas

- Escolher outra opção numa lista fecha a sobreposição, mas o valor exibido no campo não muda (o Figma exigiria uma variante de tela para cada combinação).
- Os campos de texto não aceitam digitação; os valores são de exemplo.
- As telas pessoais (Início, Carga horária, Alertas, Extrato, Ciência) usam a servidora **Maria Silva** em todos os fluxos, inclusive quando acessadas a partir das telas da Gestão ou da Chefia.
- Elementos **intencionalmente sem destino:** o botão “Entrando…” (estado de carregamento) e o **Continuar** desabilitado da etapa 5 com bloqueio.

## Checklist de teste de navegação (Sprint 3)

| Fluxo | Testado por | Data | Resultado |
|---|---|---|---|
| 1. Visitante | | | |
| 2. Consulta pública | | | |
| 3. Login com erro | | | |
| 3b. Recuperar senha | | | |
| 4. Servidora | | | |
| 5. Solicitante → Emissor | | | |
| 6. Emissor: alterar, retificar, revogar | | | |
| 7. Emissor: portarias e Boletim | | | |
| 8. Gestão | | | |
| 9. Chefia | | | |
