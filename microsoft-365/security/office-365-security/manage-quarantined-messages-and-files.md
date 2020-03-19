---
title: Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (regras de transporte).
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857066"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Gerenciar arquivos e mensagens em quarentena como um administrador no Office 365

A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações do Office 365 com caixas de correio em organizações do Exchange Online ou do Exchange Online Protection (EOP) independentes sem caixas de correio do Exchange Online. Para obter mais informações, consulte [Quarantine in Office 365](quarantine-email-messages.md).

Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte). Os administradores também podem relatar falsos positivos para a Microsoft.

Administradores nas organizações com a proteção avançada contra ameaças do Office 365 (ATP) também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.

Você exibir e gerenciar mensagens em quarentena no centro de conformidade & segurança ou no PowerShell (PowerShell do Exchange Online para clientes do Office 365; PowerShell de proteção do Exchange Online para clientes autônomos do EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o centro de conformidade & segurança do Office 365, <https://protection.office.com>vá para. Para abrir a página de quarentena diretamente, acesse <https://protection.office.com/quarantine>.

- Para se conectar ao Exchange Online PowerShell, confira [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Você precisa receber permissões antes de gerenciar a quarentena como um administrador. As permissões são controladas pela função de **quarentena** no centro de conformidade de & de segurança. Por padrão, essa função é atribuída aos grupos de função **Gerenciamento da organização** (administradores globais), **administrador de quarentena**e administrador de **segurança** no centro de conformidade do & de segurança. Para obter mais informações, consulte [permissões no centro de conformidade & segurança do Office 365](permissions-in-the-security-and-compliance-center.md).

- As mensagens em quarentena são mantidas por um período de tempo padrão antes de serem excluídas automaticamente:

  - Mensagens colocadas em quarentena por políticas antispam (spam, phishing e email em massa): 30 dias. Este é o valor padrão e máximo. Para configurar esse valor, consulte [Configure anti-spam Policies in Office 365](configure-your-spam-filter-policies.md).

  - Mensagens em quarentena por regras de fluxo de email (a ação de regra é **entregar a mensagem para a quarentena hospedada**): 30 dias. Não é possível alterar esse valor.

  - Mensagens que contêm malware: 15 dias.

  Quando uma mensagem expira da quarentena, não é possível recuperá-la.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Usar o centro de conformidade de & de segurança para gerenciar mensagens de email em quarentena

### <a name="view-quarantined-email"></a>Exibir email em quarentena

1. No centro de segurança e conformidade, vá para a **quarentena**de **análise** \> de **Gerenciamento** \> de ameaças.

2. Verifique se a **exibição em quarentena** está definida com o valor padrão **email**.

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para mostrar um máximo de sete colunas. Os valores padrão são marcados com um asterisco (<sup>\*</sup>):

   - **Recebido**<sup>\*</sup>

   - **Enviou**<sup>\*</sup>

   - **Assunto**<sup>\*</sup>

   - **Motivo da quarentena**<sup>\*</sup>

   - **Solta?**<sup>\*</sup>

   - **Tipo de política**<sup>\*</sup>

   - **Expira**<sup>\*</sup>

   - **Recipient**

   - **ID da mensagem**

   - **Nome da política**

   - **Tamanho**

   - **Direction**

   Quando tiver terminado, clique em **salvar**ou em **definir como padrão**.

4. Para filtrar os resultados, clique em **Filtrar**. Os filtros disponíveis são:

   - **Tempo expira**: filtrar mensagens por quando elas expirarem da quarentena:

     - **Empresas**

     - **Próximos 2 dias**

     - **Próximos 7 dias**

     - **Personalizado**: Insira uma **data de início** e uma **data de término**.

   - **Hora de recebimento**: Insira uma **data de início** e uma data de **término**.

   - **Motivo da quarentena**:

     - **Política**: a mensagem correspondeu às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).

     - **Impresso**

     - **Phish**

     - **Malware**

     - **Spam**

     - **Phishing de alta confiança**

   - **Destinatário do email**: todos os usuários ou apenas as mensagens enviadas a você. Os usuários finais só podem gerenciar mensagens em quarentena enviadas para eles.

   Para limpar o filtro, clique em **limpar**. Para ocultar o submenu de filtro, clique em **Filtrar** novamente.

5. Use **classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas. Não há suporte para curingas. Você pode pesquisar pelos seguintes valores:

   - **ID da mensagem**: o identificador global exclusivo da mensagem.

        Por exemplo, você usou o [rastreamento de mensagens](message-trace-scc.md) para procurar uma mensagem que foi enviada a um usuário na sua organização, e você determina que a mensagem foi colocada em quarentena em vez de distribuída. Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares (\<\>). Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Endereço de email do remetente**: o endereço de email de um único remetente.

   - **Endereço de email do destinatário**: o endereço de email de um único destinatário.

   - **Subject**: usar o assunto inteiro da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.

   Depois de inserir os critérios de pesquisa, clique ![em atualizar](../media/scc-quarantine-refresh.png) botão **Atualizar** para filtrar os resultados.

Após localizar uma mensagem em quarentena específica, selecione a mensagem para exibir os detalhes sobre ela e execute a ação sobre ela (por exemplo, exibir, liberar, baixar ou excluir a mensagem).

#### <a name="export-message-results"></a>Exportar resultados de mensagens

1. Selecione as mensagens em que você está interessado e clique em **Exportar resultados**.

2. Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.

3. Quando a exportação estiver pronta, você poderá nomear e escolher o local de download para o arquivo. csv.

#### <a name="view-quarantined-message-details"></a>Exibir detalhes da mensagem em quarentena

Quando você seleciona uma mensagem de email na lista, os seguintes detalhes da mensagem aparecem no painel de submenu **detalhes** :

- **ID da mensagem**: o identificador global exclusivo da mensagem.

- **Endereço do remetente**

- **Recebido**: a data/hora em que a mensagem foi recebida.

- **Subject**

- **Motivo da quarentena**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.

- **Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **exibir cabeçalho da mensagem** para ver a lista completa de destinatários.

- **Expira**: a data/hora em que a mensagem será excluída automaticamente e permanentemente da quarentena.

- **Liberação para**: todos os endereços de email (se houver) para os quais a mensagem foi liberada.

- **Ainda não foi liberado para**: todos os endereços de email (se houver) para os quais a mensagem ainda não foi liberada.

### <a name="take-action-on-quarantined-email"></a>Executar ação em emails em quarentena

Após selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel de submenu **detalhes** :

- **Mensagem de lançamento**: no painel de submenus exibido, escolha as seguintes opções:

  - **Relatar mensagens à Microsoft para análise**: isso é selecionado por padrão e relata a mensagem em quarentena errada à Microsoft como um falso positivo. Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou com malware, a mensagem também é relatada para a equipe de análise de spam da Microsoft. Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a mensagem.

  - Escolha uma das seguintes opções:

    - **Liberar mensagens para todos os destinatários**

    - **Liberar mensagens para destinatários específicos**

    - **Liberar mensagens para outras pessoas**

  Quando tiver concluído, clique em **liberar mensagens**.

  Observações sobre o lançamento de mensagens:

  - Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.

  - Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.

- **Exibir cabeçalho da mensagem**: escolha este link para ver o texto do cabeçalho da mensagem. Para analisar os valores e campos de cabeçalho em profundidade, copie o texto do cabeçalho da mensagem para a área de transferência e escolha **analisador de cabeçalho de mensagem da Microsoft** para ir para o analisador de conectividade remota (clique com o botão direito do mouse e escolha **abrir em uma nova guia** se não quiser deixar o Office 365 para concluir essa tarefa). Cole o cabeçalho da mensagem na página na seção analisador de cabeçalho de mensagem e escolha **analisar cabeçalhos**:

- **Mensagem de visualização**: no painel de submenus que aparece, escolha uma das seguintes opções:

  - **Modo de exibição Source**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.
  
  - **Exibição de texto**: mostra o corpo da mensagem em texto sem formatação.

- **Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.

- **Mensagem de download**: no painel do submenu que aparece, selecione compreendo **os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato. eml.

- **Enviar mensagem**: no painel de submenu que aparece, escolha as seguintes opções:

  - **Tipo de objeto**: **email** (padrão), **URL**ou **anexo**.

  - **Formato de envio**: **ID de mensagem de rede** (padrão, com o valor correspondente na caixa ID de mensagem de **rede** ) ou **arquivo** (navegue até um arquivo. eml ou. msg local). Observe que, se você selecionar **arquivo** e, em seguida, selecionar **ID de mensagem de rede**, o valor inicialmente será desperdido.

  - **Destinatários**: digite no leasing um destinatário original da mensagem ou clique em **selecionar tudo** para identificar todos os destinatários. Você também pode clicar em **selecionar todos** e, em seguida, remover seletivamente destinatários individuais.

  - **Motivo do envio**: **não deve ter sido bloqueado** (padrão) ou **deve ter sido bloqueado**.

  Quando tiver concluído, clique em **Enviar**.

Se você não liberar ou remover a mensagem, ela será excluída depois que o período de retenção de quarentena padrão expirar.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Executar ação em várias mensagens de email em quarentena

Quando você seleciona várias mensagens em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:

- **Mensagens de lançamento**: as opções são as mesmas que quando você libera uma única mensagem, exceto que não é possível selecionar **mensagens de liberação para destinatários específicos**; Você só pode selecionar **a mensagem de liberação para todos os destinatários** ou **liberar mensagens para outras pessoas**.

- **Excluir mensagens**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.

Quando tiver concluído, clique em **fechar**.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Somente ATP: usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena

> [!NOTE]
> Os procedimentos para arquivos em quarentena nesta seção estão disponíveis somente para assinantes do plano ATP 1 e do plano 2.

Em organizações com ATP, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.

### <a name="view-quarantined-files"></a>Exibir arquivos em quarentena

1. No centro de segurança e conformidade, vá para a **quarentena**de **análise** \> de **Gerenciamento** \> de ameaças.

2. Altere o **modo de exibição colocado em quarentena** para os **arquivos**de valor padrão. Você pode classificar em um campo clicando em um cabeçalho de coluna disponível.

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para mostrar um máximo de sete colunas. As colunas padrão são marcadas com um asterisco<sup>\*</sup>():

   - **Usuário**<sup>\*</sup>

   - **Alocações**<sup>\*</sup>

   - **Nome do arquivo**<sup>\*</sup>

   - **URL do arquivo**<sup>\*</sup>

   - **Tamanho do arquivo**<sup>\*</sup>

   - **Expira**<sup>\*</sup>

   - **Solta?**<sup>\*</sup>

   - **Detectado por**

   - **Modificado por hora**

4. Para filtrar os resultados, clique em **Filtrar**. Os filtros disponíveis são:

   - **Tempo expira**: filtrar mensagens por quando elas expirarem da quarentena:

     - **Empresas**

     - **Próximos 2 dias**

     - **Próximos 7 dias**

     - Um intervalo personalizado de data/hora.

   - **Hora de recebimento**

   - **Motivo da quarentena**: o único valor disponível é **malware**.

Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir os detalhes sobre ele e execute a ação nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).

#### <a name="export-file-results"></a>Exportar resultados de arquivo

1. Selecione os arquivos nos quais você está interessado e clique em **Exportar resultados**.

2. Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.

3. Quando a exportação estiver pronta, você poderá nomear e escolher o local de download para o arquivo. csv.

#### <a name="view-quarantined-file-details"></a>Exibir detalhes de arquivo em quarentena

Quando você seleciona um arquivo na lista, os seguintes detalhes de arquivo são exibidos no painel de submenu **detalhes** :

- **Nome do arquivo**

- **URL do arquivo**: URL que define o local do arquivo (por exemplo, no SharePoint Online).

- **Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.

- **Expira**: a data em que o arquivo será excluído da quarentena.

- **Detectado por**: ATP (proteção avançada contra ameaças) ou mecanismo antimalware da Microsoft.

- **Solta?**

- **Nome do malware**

- **ID do documento**: um identificador exclusivo para o documento.

- **Tamanho do arquivo**: em kilobytes (KB).

- **Organização** A ID exclusiva da sua organização.

- **Última modificação**

- **Modificado por**: o usuário que modificou o arquivo pela última vez.

- **Algoritmo de hash seguro 256 bits (SHA-256) valor**: você pode usar esse valor de hash para identificar o arquivo em outros repositórios de reputação ou em outros locais em seu ambiente.

### <a name="take-action-on-quarantined-files"></a>Executar ação em arquivos em quarentena

Ao selecionar um arquivo na lista, você pode executar as seguintes ações no arquivo no painel de submenu **detalhes** :

- **Arquivos de lançamento**: selecione (padrão) ou desmarque **arquivos de relatório para a Microsoft para análise**e clique em **liberar arquivos**.

- **Baixar o arquivo**

- **Remover arquivo da quarentena**

Se você não liberar ou remover os arquivos, eles serão excluídos depois que o período de retenção de quarentena padrão expirar.

#### <a name="actions-on-multiple-quarantined-files"></a>Ações em vários arquivos em quarentena

Quando você seleciona vários arquivos em quarentena na lista (até 100), o painel de submenu **ações em massa** aparece onde você pode executar as seguintes ações:

- **Arquivos de versão**

- **Excluir arquivos**: depois de clicar em **Sim** no aviso exibido, os arquivos serão excluídos imediatamente.

Quando tiver concluído, clique em **fechar**.

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Usar o PowerShell do Exchange Online ou do Exchange Online Protection para exibir e gerenciar arquivos e mensagens em quarentena

Os cmdlets que você usa para exibir e gerenciar mensagens e arquivos em quarentena são:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observe que este cmdlet é somente para mensagens, e não para arquivos de malware de ATP para SharePoint Online, onedrive for Business ou Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
