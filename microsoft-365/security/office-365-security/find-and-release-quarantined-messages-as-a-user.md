---
title: Localizar e liberar mensagens em quarentena como usuário do Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
description: Como usuário do Office 365, você pode exibir, liberar e excluir suas mensagens em quarentena (mensagens em que você é um destinatário e a filtragem de spam em quarentena colocou a mensagem como spam ou e-mail em massa). Você exibe e gerencia suas mensagens em quarentena no Centro de conformidade e de segurança.
ms.openlocfilehash: 32ae03c555742b9f08c272806464ed75585d08df
ms.sourcegitcommit: 1d5db6e8411b45d0dd1c517339074c2840e33a63
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/10/2020
ms.locfileid: "43216899"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-office-365"></a>Localize e libere mensagens em quarentena como usuário do Office 365

A quarentena mantém mensagens potencialmente perigosas ou indesejadas nas organizações do Office 365 com caixas de correio do Exchange Online ou de organizações autônomas do Exchange Online Protection (EOP) sem as caixas de correio do Exchange Online. Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).

Como usuário, você pode exibir, liberar e excluir mensagens em quarentena em que você é um destinatário, e a mensagem foi colocada em quarentena como spam, e-mail em massa ou (a partir de abril de 2020) phishing. Você visualiza e gerencia suas mensagens em quarentena no Centro de Conformidade e Segurança ou (se um administrador configurou isso) em [notificações de spam do usuário final](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Para abrir o Centro de Conformidade e Segurança do Office 365, vá para <https://protection.office.com>. Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.

- Os administradores conseguem configurar pelo tempo que as mensagens forem mantidas em quarentena antes de serem excluídas permanentemente (políticas anti-spam). As mensagens que saíram da quarentena se tornam irrecuperáveis. Para obter mais informações, consulte [Configure as políticas de anti-spam no Office 365](configure-your-spam-filter-policies.md).

- Os administradores também podem [habilitar as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) na políticas anti-spam. Os usuários podem liberar mensagens em quarentena de spam em quarentena, mas não as mensagens de phishing em quarentena diretamente dessas notificações. Para obter mais informações, consulte [Notificações de spam do usuário final no Office 365](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- As mensagens que foram colocadas em quarentena por regras de phishing, malware ou fluxo de mensagens de alta confiança (também conhecidas como regras de transporte) estão disponíveis apenas aos administradores. Para obter mais informações, consulte [Gerenciar arquivos e mensagens em quarentena como administrador no Office 365](manage-quarantined-messages-and-files.md).

- Você só pode liberar uma mensagem e relatá-la como falso positivo (e não como lixo eletrônico) uma vez.

## <a name="view-your-quarantined-messages"></a>Visualizar suas mensagens em quarentena

1. No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.

2. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para exibir um máximo de sete colunas. Os valores padrão são marcados com um asterisco (<sup>\*</sup>):

   - **Recebido**<sup>\*</sup>

   - **Remetente**<sup>\*</sup>

   - **Assunto**<sup>\*</sup>

   - **Motivo da quarentena**<sup>\*</sup>

   - **Lançado?**<sup>\*</sup>

   - **Tipo de política**<sup>\*</sup>

   - **Expira**<sup>\*</sup>

   - **Recipiente**

   - **ID da mensagem**

   - **Nome da política**: esta propriedade mostra a política que provocou a entrada da mensagem na quarentena. Você pode fornecer essa informação ao seu administrador.

   - **Tamanho**

   - **Direção**

   Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.

3. Para filtrar os resultados, clique em **Filtro**. Os filtros disponíveis são:

   - **Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:

     - **Hoje**

     - **Próximos 2 dias**

     - **Próximas 7 semanas**

     - **Personalizado**: Insira uma **Data de início** e uma **Data de término**.

   - **Hora recebida**: Insira uma **Data de início** e uma **Data de término**.

   - **Motivo da quarentena**:

     - **Em massa**

     - **Spam**

     - **Phish** (Em abril de 2020)

   Para limpar o filtro, clique em **Limpar**. Para ocultar o submenu do filtro, clique novamente em **Filtro**.

4. Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas. Os curingas não possuem suporte. Você pode pesquisar pelos seguintes valores:

   - **ID da mensagem**: o identificador globalmente exclusivo da mensagem. Se você selecionar uma mensagem na lista, o valor da **ID da mensagem** será exibido no painel **Detalhes** que é exibido. Os administradores podem usar [Rastreamento da mensagem](message-trace-scc.md) para localizar mensagens e seus valores da ID da mensagem correspondentes.

   - **Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.

   - **Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.

   - **Assunto**: use todo o assunto da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.

   Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.

Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).

### <a name="export-message-results"></a>Exporte os resultados da mensagem 

1. Selecione as mensagens que você está interessado e clique em **Exportar resultados**.

2. Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.

3. Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.

### <a name="view-quarantined-message-details"></a>Exiba detalhes da mensagem em quarentena

Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:

- **ID da mensagem**: o identificador globalmente exclusivo da mensagem.

- **Endereço do remetente**.

- **Recebido**: a data e a hora em que a mensagem foi recebida.

- **Assunto**

- **Motivo da quarentena**: mostra se uma mensagem foi identificada como **Spam**, **Em massa** ou (desde abril de 2020) **Phish**.

- **Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.

- **Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.

- **Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.

- **Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.

### <a name="take-action-on-quarantined-email"></a>Tomar medidas quanto aos e-mails em quarentena

Depois de selecionar uma mensagem, você tem opções para o que fazer com as mensagens no painel de submenu **Detalhes**:

- **Mensagem de liberação**: no painel de submenu que é exibido, escolha se quer o **Relatório de mensagens do Microsoft para ser analisado**. Essa opção é selecionada por padrão e relata a mensagem em quarentena incorreta à Microsoft como um falso positivo.

  Quando terminar, clique em **Liberar mensagens**.

- **Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem. Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e escolha **Analisador de cabeçalho das mensagens da Microsoft** para acessar o Analisador de conectividade remota (clique com o botão direito do mouse e escolha **Abrir em uma nova guia** se não quiser sair do Office 365 para concluir essa tarefa). Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:

- **Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:

  - **Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.
  
  - **Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.

- **Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.

- **Remover da quarentena**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída.

Quando terminar, clique em **Fechar**.

Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Tome medidas em várias mensagens quanto aos e-mails em quarentena

Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:

- **Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.

- **Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.

Quando terminar, clique em **Fechar**.
