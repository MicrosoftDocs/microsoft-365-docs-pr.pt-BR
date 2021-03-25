---
title: Localizar e liberar mensagens em quarentena como um usuário
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os usuários podem aprender como exibir e gerenciar mensagens em quarentena no Exchange Online Protection (EOP) que deveriam ter sido entregues a eles.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 961912427f9c343f8235f0ed8e990431669ff9e5
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203032"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>Localizar e liberar mensagens em quarentena como usuário no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas. Para obter mais informações, consulte [Quarentena no EOP](quarantine-email-messages.md).

Como usuário, você pode exibir, liberar e excluir mensagens em quarentena em que você é um destinatário, e a mensagem foi colocada em quarentena como spam ou email em massa. A partir de abril de 2020, você pode exibir ou excluir mensagens de phishing em quarentena (phishing sem alta confiança) em que você é um destinatário. Você visualiza e gerencia suas mensagens em quarentena no Centro de Conformidade e Segurança ou (se um administrador configurou isso) em [notificações de spam do usuário final](use-spam-notifications-to-release-and-report-quarantined-messages.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>. Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.

- Os administradores conseguem configurar pelo tempo que as mensagens forem mantidas em quarentena antes de serem excluídas permanentemente (políticas anti-spam). As mensagens que saíram da quarentena se tornam irrecuperáveis. Para obter mais informações, consulte [Configure as políticas de anti-spam no EOP](configure-your-spam-filter-policies.md).

- Os administradores também podem [habilitar as notificações de spam do usuário final](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications) na políticas anti-spam. Os usuários podem liberar as mensagens de spam na quarentena, diretamente a partir dessas notificações. Os usuários podem revisar as mensagens de phishing na quarentena (menos as mensagens de phishing de alta confiança), diretamente a partir dessas notificações. Para obter mais informações, consulte [Notificações de spam do usuário final no EOP](use-spam-notifications-to-release-and-report-quarantined-messages.md).

- As mensagens que foram colocadas na quarentena por phishing de alta confiança, malware ou por regras do fluxo de email (também conhecidas como regras de transporte) estão disponíveis apenas para administradores e não são visíveis para os usuários. Para obter mais informações, consulte [Gerenciar mensagens e arquivos em quarentena como administrador no EOP](manage-quarantined-messages-and-files.md).

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
   - **Nome da política**
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
     - **Golpe**

   - **Tipo de Política**: Filtre mensagens por tipo de política:
     - **Política Anti-phish**:
     - **Política de filtro de conteúdo hospedado** (política antispam)

   Para limpar o filtro, clique em **Limpar**. Para ocultar o submenu do filtro, clique novamente em **Filtro**.

4. Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas. Os curingas não possuem suporte. Você pode pesquisar pelos seguintes valores:

   - **ID da mensagem**: o identificador globalmente exclusivo da mensagem. Se você selecionar uma mensagem na lista, o valor da **ID da mensagem** será exibido no painel **Detalhes** que é exibido. Os administradores podem usar [Rastreamento da mensagem](message-trace-scc.md) para localizar mensagens e seus valores da ID da mensagem correspondentes.

   - **Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.

   - **Nome da política**: Use o nome completo da política da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.

   - **Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.

   - **Assunto**: use todo o assunto da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.

   Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.

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

- **Motivo da quarentena**: Exibe se a mensagem foi identificada como **Spam**, **Em massa** ou **Golpe**.

- **Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.

- **Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.

- **Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.

- **Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.

### <a name="take-action-on-quarantined-email"></a>Tomar medidas quanto aos e-mails em quarentena

Depois de selecionar uma mensagem, você tem opções para o que fazer com as mensagens no painel de submenu **Detalhes**:

- **Mensagem de liberação**: no painel de submenu que é exibido, escolha se quer o **Relatório de mensagens do Microsoft para ser analisado**. Essa opção é selecionada por padrão e relata a mensagem em quarentena incorreta à Microsoft como um falso positivo.

  Quando terminar, clique em **Liberar mensagens**.

- **Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem. Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa). Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:

- **Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:
  - **Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.
  - **Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.

- **Remover da quarentena**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída.

Quando terminar, clique em **Fechar**.

Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Tome medidas em várias mensagens quanto aos e-mails em quarentena

Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:

- **Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.

- **Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.

Quando terminar, clique em **Fechar**.
