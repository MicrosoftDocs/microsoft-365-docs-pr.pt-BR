---
title: Gerenciar arquivos e mensagens em quarentena como administrador
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Os administradores podem aprender a exibir e gerenciar mensagens em quarentena para todos os usuários no Exchange Online Protection (EOP). Os administradores em organizações com o Microsoft Defender para Office 365 também podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a91f53f8efe4fa6944f0debff472da87b7f17e0c
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167486"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Gerenciar arquivos e mensagens em quarentena como administrador no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plano 1 e plano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas. Para obter mais informações, consulte [Mensagens de email em quarentena no EOP.](quarantine-email-messages.md)

Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte). Os administradores também podem relatar falsos positivos à Microsoft.

Os administradores em organizações com o Microsoft Defender para Office 365 também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.

Você pode exibir e gerenciar mensagens em quarentena no Centro de Conformidade e Segurança ou no PowerShell (organizações do PowerShell do Exchange Online para Microsoft 365 com caixas de correio no Exchange Online; PowerShell do EOP autônomo para organizações sem caixas de correio do Exchange Online). &

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>. Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões no Centro de Conformidade e Segurança antes de poder realizar os procedimentos deste artigo:
  - Para agir em mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança ou Administrador **de** <sup>\*</sup> Quarentena.
  - Para acesso somente leitura a mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de funções Leitor **Global** ou **Leitor de** Segurança.

  Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias no Centro de Segurança e Conformidade _e_ permissões para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.
  - <sup>\*</sup>Os membros do grupo **de** função Administrador  de Quarentena também precisam ser membros do grupo de funções Gerenciamento de Higienização no [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) para realizar procedimentos de quarentena no PowerShell do Exchange Online.

- As mensagens em quarentena são mantidas por um período padrão antes de elas ser excluídas automaticamente:
  - 30 dias para mensagens em quarentena por políticas anti-spam (spam, phishing e email em massa). Este é o valor padrão e máximo. Para configurar (menos) esse valor, consulte [Configurar políticas anti-spam.](configure-your-spam-filter-policies.md)
  - 15 dias para mensagens que contêm malware.
  - 15 dias para arquivos em quarentena pelos Anexos Seguros do SharePoint, OneDrive e Microsoft Teams no Defender para Office 365.

  Quando uma mensagem expira da quarentena, você não pode recuperá-la.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Usar o Centro de Conformidade & segurança para gerenciar mensagens de email em quarentena

### <a name="view-quarantined-email"></a>Exibir email em quarentena

1. No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.

2. Verifique se **o modo de exibição** em quarentena está definido como o email de valor **padrão.**

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para exibir um máximo de sete colunas. Os valores padrão são marcados com um asterisco (<sup>\*</sup>):

   - **Recebido**<sup>\*</sup>
   - **Remetente**<sup>\*</sup>
   - **Assunto**<sup>\*</sup>
   - **Motivo da quarentena**<sup>\*</sup>
   - **Lançado?**<sup>\*</sup>
   - **Tipo de política**<sup>\*</sup>
   - **Expires**
   - **Recipiente**
   - **ID da mensagem**
   - **Nome da política**
   - **Tamanho**
   - **Direção**

   Quando você terminar, clique em **Salvar**, ou clique em **Definido como padrão**.

4. Para filtrar os resultados, clique em **Filtro**. Os filtros disponíveis são:

   - **Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:
     - **Hoje**
     - **Próximos 2 dias**
     - **Próximas 7 semanas**
     - **Personalizado**: Insira uma **Data de início** e uma **Data de término**.

   - **Hora recebida**: Insira uma **Data de início** e uma **Data de término**.

   - **Motivo da quarentena**:
     - **Política:** a mensagem a correspondência das condições de uma regra de fluxo de emails (também conhecida como regra de transporte).
     - **Em massa**
     - **Phish**: o veredito do filtro de spam foi email de **phishing** ou proteção anti-phishing colocou a mensagem em quarentena (configurações de [spoof](set-up-anti-phishing-policies.md#spoof-settings) ou proteção [contra representação).](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
     - **Malware**
     - **Spam**
     - **Phishing de alta confiança**

   - **Tipo de Política**: Filtre mensagens por tipo de política:
     - **Política anti-malware**
     - **Política de Anexos Seguros**
     - **Política Anti-phish**:
     - **Política de filtro de conteúdo hospedado** (política antispam)
     - **Regra de transporte**

   - **Destinatário de** email: todos os usuários ou apenas mensagens enviadas para você. Os usuários finais só podem gerenciar mensagens em quarentena enviadas a eles.

   Para limpar o filtro, clique em **Limpar**. Para ocultar o submenu do filtro, clique novamente em **Filtro**.

5. Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas. Os curingas não possuem suporte. Você pode pesquisar pelos seguintes valores:

   - **ID da mensagem**: o identificador globalmente exclusivo da mensagem.

     Por exemplo, [](message-trace-scc.md) você usou o rastreamento de mensagens para procurar uma mensagem que foi enviada para um usuário em sua organização e você determina que a mensagem foi colocada em quarentena em vez de entregue. Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares ( \<\> ). Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.

   - **Nome da política**: Use o nome completo da política da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.

   - **Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.

   - **Assunto**: use todo o assunto da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.

   - **Nome da** política: o nome da política responsável pela quarentena da mensagem.

   Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.

Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).

#### <a name="view-quarantined-message-details"></a>Exiba detalhes da mensagem em quarentena

Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:

- **ID da mensagem**: o identificador globalmente exclusivo da mensagem.

- **Endereço do remetente**.

- **Recebido**: a data e a hora em que a mensagem foi recebida.

- **Assunto**

- **Motivo da** quarentena: mostra se uma mensagem foi identificada como **Spam** **,** Bulk , **Phish**, matched a mail flow rule (**Transport rule**), ou foi identificada como contendo **Malware**.

- **Contagem de destinatários**

- **Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.

- **Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.

- **Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.

- **Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.

### <a name="take-action-on-quarantined-email"></a>Tomar medidas quanto aos e-mails em quarentena

Depois de selecionar uma mensagem, você tem várias opções sobre o que fazer com as mensagens no painel do **menu** desdopo Detalhes:

- **Mensagem de** liberação: no painel do menu desdolado exibido, escolha as seguintes opções:

  - **Relatar mensagens à Microsoft para** análise: ela é selecionada por padrão e relata a mensagem erroneamente em quarentena à Microsoft como um falso positivo. Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou malware, a mensagem também será relatada à Equipe de Análise de Spam da Microsoft. Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a passagem da mensagem.

  - Escolha uma das seguintes opções:
    - **Liberar mensagens para todos os destinatários**
    - **Liberar mensagens para destinatários específicos**
    - **Liberar mensagens para outras pessoas:** Observe que não há suporte para a liberação de mensagens de malware para pessoas que não são destinatários originais.

  Quando terminar, clique em **Liberar mensagens**.

  Observações sobre a liberação de mensagens:

  - Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.
  - Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.

- **Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem. Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa). Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:

- **Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:

  - **Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.
  - **Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.

- **Remover da quarentena:** depois de clicar em **Sim** no aviso exibido, a mensagem será imediatamente excluída sem ser enviada aos destinatários originais.

- **Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.

- **Enviar mensagem:** no painel do sub-menu que aparece, escolha as seguintes opções:

  - **Tipo de** objeto: **Email** (padrão), **URL** ou **Anexo.**

  - **Formato de** envio: **ID** da Mensagem de Rede (padrão, com o valor correspondente na caixa **ID** da Mensagem de Rede) ou **Arquivo** (navegue até um arquivo .eml ou .msg local). Observe que, se você selecionar **Arquivo** e, em seguida, selecionar **a ID** da Mensagem de Rede, o valor inicial será eliminado.

  - **Destinatários:** digite na concessão um destinatário original da mensagem ou clique em **Selecionar Tudo** para identificar todos os destinatários. Você também pode clicar **em Selecionar Tudo** e remover seletivamente destinatários individuais.

  - **Motivo do envio:** **Não deveria ter sido bloqueado** (padrão) ou deveria ter sido **bloqueado.**

  Quando terminar, clique em **Enviar.**

Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Tome medidas em várias mensagens quanto aos e-mails em quarentena

Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:

- **Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.

  > [!NOTE]
  > Considere o seguinte cenário: john@gmail.com envia uma mensagem para faith@contoso.com e john@subsidiary.contoso.com. O Gmail bifurca essa mensagem em duas cópias que são encaminhadas para a quarentena como phishing na Microsoft. Um administrador libera essas duas mensagens para admin@contoso.com. A primeira mensagem liberada que atinge a caixa de correio de administrador é entregue. A segunda mensagem liberada é identificada como entrega duplicada e ignorada. As mensagens serão identificadas como duplicatas se elas têm a mesma ID de mensagem e hora recebida.

- **Excluir mensagens:** depois de clicar em **Sim** no aviso exibido, as mensagens são imediatamente excluídas sem serem enviadas aos destinatários originais.

Quando terminar, clique em **Fechar**.

## <a name="microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Microsoft Defender para Office 365 Apenas: use o Centro de Conformidade e Segurança & gerenciar arquivos em quarentena

> [!NOTE]
> Os procedimentos para arquivos em quarentena nesta seção estão disponíveis apenas para assinantes do Microsoft Defender para Office 365 Plano 1 e Plano 2.

Em organizações com o Defender para Office 365, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams. Para habilitar a proteção para esses arquivos, confira [Ativar Anexos Seguros para SharePoint, OneDrive e Microsoft Teams.](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="view-quarantined-files"></a>Exibir arquivos em quarentena

1. No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.

2. Alterar **o exibição em quarentena** para os arquivos de **valor.** Você pode classificar em um campo clicando em um header de coluna disponível.

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para exibir um máximo de sete colunas. As colunas padrão são marcadas com um asterisco ( <sup>\*</sup> ):

   - **Usuário**<sup>\*</sup>
   - **Localização**<sup>\*</sup>
   - **Nome do arquivo**<sup>\*</sup>
   - **URL do arquivo**<sup>\*</sup>
   - **Tamanho do Arquivo**<sup>\*</sup>
   - **Expira**<sup>\*</sup>
   - **Lançado?**<sup>\*</sup>
   - **Detectado por**
   - **Modificado por hora**

4. Para filtrar os resultados, clique em **Filtro**. Os filtros disponíveis são:

   - **Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:
     - **Hoje**
     - **Próximos 2 dias**
     - **Próximas 7 semanas**
     - Um intervalo de data/hora personalizado.
   - **Hora de recebido**
   - **Motivo da quarentena:** o único valor disponível é **Malware**.
   - **Tipo de política**

Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir detalhes sobre ele e para agir sobre ele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).

#### <a name="view-quarantined-file-details"></a>Exibir detalhes do arquivo em quarentena

Quando você seleciona um arquivo na lista, os seguintes detalhes do arquivo são exibidos **no** painel de detalhes do painel:

- **Nome do arquivo**
- **URL do** arquivo: URL que define o local do arquivo (por exemplo, no SharePoint Online).
- **Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.
- **Expira :** a data em que o arquivo será excluído da quarentena.
- **Detectado por:** Defender para Office 365 ou mecanismo anti-malware da Microsoft.
- **Lançado?**
- **Nome do malware**
- **ID do** documento: um identificador exclusivo para o documento.
- **Tamanho do** arquivo: em kilobytes (KB).
- **Organização** A ID exclusiva da sua organização.
- **Última modificação**
- **Modificado por:** o usuário que modificou o arquivo pela última vez.
- Valor de Algoritmo de Hash Seguro de **256 bits (SHA-256).** Você pode usar esse valor de hash para identificar o arquivo em outros armazenamentos de reputação ou em outros locais em seu ambiente.

### <a name="take-action-on-quarantined-files"></a>Tomar medidas em arquivos em quarentena

Ao selecionar um arquivo na lista, você pode tomar as seguintes ações no arquivo no **painel** de detalhes do painel:

- **Arquivos de** versão: Selecione (padrão) ou desmarque arquivos de relatório para análise da **Microsoft** e clique em **Liberar arquivos.**
- **Baixar o arquivo**
- **Remover arquivo da quarentena**

Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.

#### <a name="actions-on-multiple-quarantined-files"></a>Ações em vários arquivos em quarentena

Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel do flyout ações em massa é exibido onde você pode tomar as seguintes ações: 

- **Liberar arquivos**
- **Excluir arquivos:** depois de clicar em **Sim** no aviso exibido, os arquivos serão imediatamente excluídos.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Usar o PowerShell do Exchange Online ou o EOP PowerShell autônomo para exibir e gerenciar arquivos e mensagens em quarentena

Os cmdlets que você usa para exibir e gerencia mensagens e arquivos em quarentena são:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)observe que esse cmdlet é destinado apenas a mensagens, não a arquivos de malware de Anexos Seguros para SharePoint, OneDrive e Microsoft Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
