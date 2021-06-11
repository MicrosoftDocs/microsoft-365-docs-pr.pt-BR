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
description: Os administradores podem aprender a exibir e gerenciar mensagens em quarentena para todos os usuários no Proteção do Exchange Online (EOP). Os administradores em organizações com o Microsoft Defender para Office 365 também podem gerenciar arquivos em quarentena no SharePoint Online, OneDrive for Business e Microsoft Teams.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 01d5011248d1c0fc0daab0d04e1cca39e26e34bd
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878887"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Gerenciar arquivos e mensagens em quarentena como administrador no EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nas organizações do Microsoft 365 com caixas de correio no Exchange Online ou em organizações autônomas do Exchange Online Protection (EOP) sem caixas de correio do Exchange Online, a quarentena retém mensagens potencialmente perigosas ou indesejadas. Para obter mais informações, consulte [Mensagens de email em quarentena no EOP](quarantine-email-messages.md).

Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte). Os administradores também podem relatar falsos positivos à Microsoft.

Os administradores em organizações com o Microsoft Defender para Office 365 também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, OneDrive for Business e Microsoft Teams.

Você visualiza e gerencia mensagens em quarentena no portal do Microsoft 365 Defender ou no PowerShell (Exchange Online PowerShell para organizações Microsoft 365 com caixas de correio no Exchange Online; EOP PowerShell autônomo para organizações sem Exchange Online caixas de correio).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Do que você precisa saber para começar?

- Para abrir o portal Microsoft 365 Defender, vá para <https://security.microsoft.com> . Para abrir a página Quarentena imediatamente, vá para <https://security.microsoft.com/quarantine>.

- Para se conectar ao PowerShell do Exchange Online, confira [Conectar ao PowerShell do Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Para se conectar ao EOP PowerShell autônomo, consulte [Conectar-se ao PowerShell do Exchange Online Protection.](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Você precisa de permissões em **Exchange Online** antes de poder realizar os procedimentos neste artigo:
  - Para tomar medidas em mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função Gerenciamento da **Organização,** Administrador de Segurança **ou** Administrador **de** <sup>\*</sup> Quarentena.
  - Para acesso somente leitura a mensagens em quarentena para todos os usuários, você precisa ser membro dos grupos de função Leitor **Global** ou **Leitor de** Segurança.

  Para obter mais informações, confira [Permissões no Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Observações**:

  - Adicionar usuários à função correspondente do Azure Active Directory no Centro de administração do Microsoft 365 fornece aos usuários as permissões necessárias _e_ para outros recursos no Microsoft 365. Para obter mais informações, confira o artigo [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).
  - O grupo de função **Gerenciamento de Organização Somente para Exibição** no [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) também fornece acesso somente leitura ao recurso.
  - <sup>\*</sup>Os membros **do** grupo de função Administrador  de Quarentena também [](/Exchange/permissions-exo/permissions-exo#role-groups) precisam ser membros do grupo de função Gerenciamento de Higienização no Exchange Online para realizar procedimentos de quarentena no Exchange Online PowerShell.

- As mensagens em quarentena são mantidas por um período de tempo padrão antes que sejam excluídas automaticamente:
  - 30 dias para mensagens em quarentena por políticas anti-spam (spam, phishing e email em massa). Esse é o valor padrão e máximo. Para configurar (mais baixo) esse valor, consulte [Configure anti-spam policies](configure-your-spam-filter-policies.md).
  - 15 dias para mensagens que contêm malware.
  - 15 dias para arquivos em quarentena Cofre anexos para SharePoint, OneDrive e Microsoft Teams no Defender para Office 365.

  Quando uma mensagem expira da quarentena, você não pode recuperá-la.

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-email-messages"></a>Usar o portal Microsoft 365 Defender para gerenciar mensagens de email em quarentena

### <a name="view-quarantined-email"></a>Exibir email em quarentena

1. No portal Microsoft 365 Defender, acesse **Email & colaboração** \> **Analisar** \> **Quarentena**.

2. Na página **Quarentena,** verifique se **o Modo de** Exibição em quarentena está definido como o email de valor **padrão.**

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para exibir um máximo de sete colunas. Os valores padrão são marcados com um asterisco (<sup>\*</sup>):

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

4. Para filtrar os resultados, clique em **Filtro**. Os filtros disponíveis são:
   - **Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:
     - **Hoje**
     - **Próximos 2 dias**
     - **Próximas 7 semanas**
     - **Personalizado**: Insira uma **Data de início** e uma **Data de término**.
   - **Hora recebida**: Insira uma **Data de início** e uma **Data de término**.
   - **Motivo da quarentena**:
     - **Política**: A mensagem corresponderia às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).
     - **Em massa**
     - **Phish**: O veredito do filtro de spam foi **phishing email** ou proteção anti-phishing em quarentena a mensagem ( configurações de [spoof](set-up-anti-phishing-policies.md#spoof-settings) ou proteção [de representação](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).
     - **Malware**
     - **Spam**
     - **Phishing de alta confiança**
   - **Tipo de Política**: Filtre mensagens por tipo de política:
     - **Política anti-malware**
     - **Cofre Política de anexos**
     - **Política Anti-phish**:
     - **Política de filtro de conteúdo hospedado** (política antispam)
     - **Regra de transporte**
   - **Destinatário de** email : Todos os usuários ou somente mensagens enviadas a você. Os usuários finais só podem gerenciar mensagens em quarentena enviadas a eles.

   Para limpar o filtro, clique em **Limpar**. Para ocultar o submenu do filtro, clique novamente em **Filtro**.

5. Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas. Os curingas não possuem suporte. Você pode pesquisar pelos seguintes valores:
   - **ID da mensagem**: o identificador globalmente exclusivo da mensagem.

     Por exemplo, você [usou](message-trace-scc.md) o rastreamento de mensagens para procurar uma mensagem que foi enviada a um usuário em sua organização e determina que a mensagem foi colocada em quarentena em vez de entregue. Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares ( \<\> ). Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.
   - **Nome da política**: Use o nome completo da política da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.
   - **Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.
   - **Assunto**: use todo o assunto da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.
   - **Nome da** política : o nome da política responsável pela quarentena da mensagem.

   Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.

Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).

#### <a name="view-quarantined-message-details"></a>Exiba detalhes da mensagem em quarentena

Quando você seleciona uma mensagem de email na lista, os seguintes detalhes da mensagem estão disponíveis no sobremenu de detalhes exibido:

- **ID da mensagem**: o identificador globalmente exclusivo da mensagem.
- **Endereço do remetente**.
- **Recebido**: a data e a hora em que a mensagem foi recebida.
- **Assunto**
- **Motivo da** quarentena: mostra se uma mensagem foi identificada como **Spam,** **Massa,** **Phish,** correspondência de uma regra de fluxo de emails **(** regra de transporte ), ou foi identificada como contendo **Malware**.
- **Contagem de destinatários**
- **Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.
- **Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.
- **Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.
- **Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.

### <a name="take-action-on-quarantined-email"></a>Tomar medidas quanto aos e-mails em quarentena

Depois de selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no sobremenu de detalhes:

- **Mensagem de** versão : No sobrevoo que aparece, escolha as seguintes opções:
  - **Relatar mensagens à Microsoft** para análise : isso é selecionado por padrão e relata a mensagem erroneamente em quarentena para a Microsoft como um falso positivo. Se a mensagem foi colocada em quarentena como spam, massa, phishing ou malware, a mensagem também será relatada à Equipe de Análise de Spam da Microsoft. Dependendo da análise, as regras de filtro de spam em todo o serviço podem ser ajustadas para permitir a passagem da mensagem.
  - Escolha uma das seguintes opções:
    - **Liberar mensagens para todos os destinatários**
    - **Liberar mensagens para destinatários específicos**
    - **Liberar mensagens para outras pessoas:** não há suporte para liberar mensagens de malware para outras pessoas que não os destinatários originais.

  Quando terminar, clique em **Liberar mensagens**.

  Observações sobre a liberação de mensagens:

  - Não é possível liberar uma mensagem para o mesmo destinatário mais de uma vez.
  - Somente os destinatários que não receberam a mensagem aparecerão na lista de destinatários em potencial.

- **Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem. Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa). Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:
- **Mensagem de** visualização : no sobrevoo que aparece, escolha uma das seguintes opções:
  - **Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.
  - **Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.
- **Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será imediatamente excluída sem ser enviada aos destinatários originais.
- **Baixar mensagem**: no sobrevoo que aparece, selecione Eu compreendo os riscos de **baixar** essa mensagem para salvar uma cópia local da mensagem no formato .eml.
- **Bloquear remetente**: adicione o remetente à lista de Remetentes Bloqueados na sua caixa de correio. Para obter mais informações, consulte [Bloquear um remetente](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Enviar mensagem**: no sub-sub-texto que aparece, escolha as seguintes opções:
  - **Tipo de objeto**: **Email** (padrão), **URL** ou **Anexo.**
  - **Formato de envio**: **ID** da Mensagem de Rede (padrão, com o valor correspondente na caixa **ID** da Mensagem de Rede) ou **Arquivo** (navegue até um arquivo .eml ou .msg local). Observe que, se você selecionar **Arquivo** e, em seguida, selecionar ID da Mensagem de **Rede,** o valor inicial se foi.
  - **Destinatários**: Digite em locação um destinatário original da mensagem ou clique em **Selecionar Todos** para identificar todos os destinatários. Você também pode clicar em **Selecionar Tudo** e remover seletivamente destinatários individuais.
  - **Motivo do envio:** **não deve ter sido bloqueado** (padrão) ou deve ter sido **bloqueado**.

  Quando terminar, clique em **Enviar**.

Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Tome medidas em várias mensagens quanto aos e-mails em quarentena

Quando você seleciona várias mensagens em quarentena na lista (até 100), o **sobrevoo** de ações em massa aparece onde você pode tomar as seguintes ações:

- **Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.

  > [!NOTE]
  > Considere o seguinte cenário: john@gmail.com envia uma mensagem para faith@contoso.com e john@subsidiary.contoso.com. O Gmail bifurca essa mensagem em duas cópias que são encaminhadas para a quarentena como phishing na Microsoft. Um administrador libera ambas as mensagens para admin@contoso.com. A primeira mensagem liberada que atinge a caixa de correio de administrador é entregue. A segunda mensagem liberada é identificada como entrega duplicada e ignorada. A mensagem será identificada como duplicata se tiver a mesma ID da mensagem e receber o tempo.

- **Excluir mensagens**: depois de clicar em **Sim** no aviso exibido, as mensagens serão imediatamente excluídas sem serem enviadas aos destinatários originais.

Quando terminar, clique em **Fechar**.

## <a name="use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365"></a>Use o portal Microsoft 365 Defender para gerenciar arquivos em quarentena no Defender para Office 365

> [!NOTE]
> Os procedimentos para arquivos em quarentena nesta seção estão disponíveis apenas para assinantes do Microsoft Defender Office 365 Plano 1 e Plano 2.

Em organizações com o Defender para Office 365, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, OneDrive for Business e Microsoft Teams. Para habilitar a proteção para esses arquivos, consulte [Ativar Cofre anexos para SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md).

### <a name="view-quarantined-files"></a>Exibir arquivos em quarentena

1. No portal Microsoft 365 Defender, acesse **Email & colaboração** \> **Analisar** \> **Quarentena**.

2. Na página **Quarentena,** **altere Exibir em quarentena** para os arquivos de **valor**. Você pode classificar em um campo clicando em um header de coluna disponível.

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para exibir um máximo de sete colunas. As colunas padrão são marcadas com um asterisco ( <sup>\*</sup> ):
   - **Usuário**<sup>\*</sup>
   - **Local**<sup>\*</sup>
   - **Nome do arquivo**<sup>\*</sup>
   - **URL do arquivo**<sup>\*</sup>
   - **Tamanho do arquivo**<sup>\*</sup>
   - **Expira**<sup>\*</sup>
   - **Lançado?**<sup>\*</sup>
   - **Detectado por**
   - **Modificado pelo tempo**

4. Para filtrar os resultados, clique em **Filtro**. Os filtros disponíveis são:
   - **Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:
     - **Hoje**
     - **Próximos 2 dias**
     - **Próximas 7 semanas**
     - Um intervalo de data/hora personalizado.
   - **Tempo de recebido**
   - **Motivo da quarentena**: o único valor disponível é **Malware**.
   - **Tipo de política**

Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir detalhes sobre ele e para tomar medidas nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).

#### <a name="view-quarantined-file-details"></a>Exibir detalhes do arquivo em quarentena

Quando você seleciona um arquivo na lista, os seguintes detalhes do arquivo estão disponíveis no sobremenu de detalhes que é aberto:

- **Nome do arquivo**
- **URL do** arquivo : URL que define o local do arquivo (por exemplo, em SharePoint Online).
- **Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.
- **Expira**: a data em que o arquivo será excluído da quarentena.
- **Detectado por**: Defender para Office 365 ou mecanismo anti-malware da Microsoft.
- **Lançado?**
- **Nome do malware**
- **ID do** documento: um identificador exclusivo para o documento.
- **Tamanho do** arquivo : em quilobytes (KB).
- **Organização** A ID exclusiva da sua organização.
- **Última modificação**
- **Modificado por**: o usuário que modificou o arquivo pela última vez.
- Valor do Algoritmo de Hash Seguro de **256 bits (SHA-256)**: Você pode usar esse valor de hash para identificar o arquivo em outros armazenamentos de reputação ou em outros locais em seu ambiente.

### <a name="take-action-on-quarantined-files"></a>Tomar medidas em arquivos em quarentena

Ao selecionar um arquivo na lista, você pode tomar as seguintes ações no arquivo no sobremenu de detalhes:

- **Arquivos de versão**: Selecione (padrão) ou desmarcar Arquivos de relatório para **a Microsoft** para análise e clique em **Liberar arquivos**.
- **Baixar o arquivo**
- **Remover arquivo da quarentena**

Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.

#### <a name="actions-on-multiple-quarantined-files"></a>Ações em vários arquivos em quarentena

Quando você seleciona vários arquivos em quarentena na lista (até 100), o sobrevoo de ações em massa aparece onde você pode tomar as seguintes ações: 

- **Liberar arquivos**
- **Excluir arquivos**: depois de clicar **em Sim** no aviso que aparece, os arquivos serão imediatamente excluídos.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Use Exchange Online PowerShell ou EOP PowerShell autônomo para exibir e gerenciar mensagens e arquivos em quarentena

Os cmdlets que você usa para exibir e gerencia mensagens e arquivos em quarentena são:

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage): observe que este cmdlet é apenas para mensagens, não arquivos em quarentena de Cofre Attachments para SharePoint, OneDrive e Microsoft Teams.

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
