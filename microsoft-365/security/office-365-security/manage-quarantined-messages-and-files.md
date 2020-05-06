---
title: Gerenciar arquivos e mensagens em quarentena como um administrador
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
ms.custom:
- seo-marvel-apr2020
description: Neste artigo, você aprenderá como os administradores podem gerenciar mensagens e arquivos em quarentena para usuários no Office 365.
ms.openlocfilehash: e69887b54b3e892775c16fa3e306da3b17ab7db3
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036168"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator"></a>Gerenciar arquivos e mensagens em quarentena como um administrador

A quarentena contém mensagens potencialmente perigosas ou indesejadas nas organizações que utilizam Microsoft 365 com caixas de correio do Exchange Online ou Exchange Online Protection (EOP) de organizações autônomas, sem as caixas de correio do Exchange Online. Para obter mais informações, consulte [Quarentena no Office 365](quarantine-email-messages.md).

Os administradores podem exibir, liberar e excluir todos os tipos de mensagens em quarentena para todos os usuários. Somente os administradores podem gerenciar mensagens que foram colocadas em quarentena como malware, phishing de alta confiança ou como resultado de regras de fluxo de emails (também conhecidas como regras de transporte). Os administradores também podem relatar falsos positivos para a Microsoft.

Administradores nas organizações com a proteção avançada contra ameaças do Office 365 (ATP) também podem exibir, baixar e excluir arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.

Você exibir e gerenciar mensagens em quarentena no centro de conformidade & segurança ou no PowerShell (PowerShell do Exchange Online para clientes do Microsoft 365; PowerShell de proteção do Exchange Online para clientes autônomos do EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Para abrir o Centro de Conformidade e Segurança, acesse <https://protection.office.com>. Para abrir a página Quarentena imediatamente, vá para <https://protection.office.com/quarantine>.

- Para se conectar ao Exchange Online PowerShell, consulte [Conectar ao Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para se conectar ao PowerShell do Exchange Online Protection, confira [conectar-se ao PowerShell do Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Você precisa receber permissões antes de gerenciar a quarentena como um administrador. As permissões são controladas pela função de **quarentena** no centro de conformidade de & de segurança. Por padrão, essa função é atribuída aos grupos de função **Gerenciamento da organização** (administradores globais), **administrador de quarentena**e administrador de **segurança** no centro de conformidade do & de segurança. Para saber mais, confira [Permissões no Centro de Conformidade de Segurança](permissions-in-the-security-and-compliance-center.md).

- As mensagens em quarentena são mantidas por um período de tempo padrão antes de serem excluídas automaticamente:

  - Mensagens colocadas em quarentena por políticas antispam (spam, phishing e email em massa): 30 dias. Este é o valor padrão e máximo. Para configurar esse valor, consulte [Configure anti-spam Policies](configure-your-spam-filter-policies.md).

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) em sua organização, entre e [vá para o centro de conformidade de & de segurança](../../compliance/go-to-the-securitycompliance-center.md).

  - Mensagens que contêm malware: 15 dias.

  Quando uma mensagem expira da quarentena, não é possível recuperá-la.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Usar o centro de conformidade de & de segurança para gerenciar mensagens de email em quarentena

### <a name="view-quarantined-email"></a>Exibir email em quarentena

1. No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.

2. Verifique se a **exibição em quarentena** está definida com o valor padrão **email**.

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para exibir um máximo de sete colunas. Os valores padrão são marcados com um asterisco (<sup>\*</sup>):

   - **Recebido**<sup>\*</sup>

   - **Remetente**<sup>\*</sup>

   - **Assunto**<sup>\*</sup>

   - **Motivo da quarentena**<sup>\*</sup>

   - **Lançado?**<sup>\*</sup>

   - **Tipo de política**<sup>\*</sup>

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) em sua organização, entre e [vá para o centro de conformidade de & de segurança](../../compliance/go-to-the-securitycompliance-center.md).

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

     - **Política**: a mensagem correspondeu às condições de uma regra de fluxo de emails (também conhecida como regra de transporte).

     - **Em massa**

     - **Phish**

     - **Malware**

     - **Spam**

     - **Phishing de alta confiança**

   - **Destinatário do email**: todos os usuários ou apenas as mensagens enviadas a você. Os usuários finais só podem gerenciar mensagens em quarentena enviadas para eles.

   Para limpar o filtro, clique em **Limpar**. Para ocultar o submenu do filtro, clique novamente em **Filtro**.

5. Use **Classificar resultados por** (o botão **ID da mensagem** por padrão) e um valor correspondente para localizar mensagens específicas. Os curingas não possuem suporte. Você pode pesquisar pelos seguintes valores:

   - **ID da mensagem**: o identificador globalmente exclusivo da mensagem.

        Por exemplo, você usou o [rastreamento de mensagens](message-trace-scc.md) para procurar uma mensagem que foi enviada a um usuário na sua organização, e você determina que a mensagem foi colocada em quarentena em vez de distribuída. Certifique-se de incluir o valor completo da ID da mensagem, que pode incluir colchetes angulares (\<\>). Por exemplo: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Endereço de e-mail do remetente**: o endereço de e-mail de um único remetente.

   - **Endereço de e-mail do destinatário**: o endereço de e-mail de um único destinatário.

   - **Assunto**: use todo o assunto da mensagem. A pesquisa não diferencia maiúsculas de minúsculas.

   Depois de ter inserido os critérios da pesquisa, clique em ![Atualizar botão](../../media/scc-quarantine-refresh.png) **Atualizar** para filtrar os resultados.

Depois de encontrar uma mensagem específica em quarentena, selecione a mensagem para exibir detalhes sobre ela e execute uma ação (por exemplo: exibir, liberar, fazer download ou excluir a mensagem).

#### <a name="export-message-results"></a>Exporte os resultados da mensagem 

1. Selecione as mensagens que você está interessado e clique em **Exportar resultados**.

2. Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.

3. Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.

#### <a name="view-quarantined-message-details"></a>Exiba detalhes da mensagem em quarentena

Quando você clica em uma mensagem de e-mail na lista, os seguintes detalhes de mensagem são exibidos no painel de submenu **Detalhes**:

- **ID da mensagem**: o identificador globalmente exclusivo da mensagem.

- **Endereço do remetente**.

- **Recebido**: a data e a hora em que a mensagem foi recebida.

- **Assunto**

- **Motivo da quarentena**: mostra se uma mensagem foi identificada como **spam**, **em massa**, **Phish**, corresponde a uma regra de fluxo de emails (**regra de transporte**) ou foi identificada como contendo **malware**.

- **Destinatários**: se a mensagem contiver vários destinatários, você precisará clicar em **Visualizar mensagem** ou **Exibir o cabeçalho da mensagem** para visualizar a lista completa dos destinatários.

- **Expira**: a data/hora em que a mensagem será excluída de forma automática e permanente da quarentena.

- **Liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem foi liberada.

- **Sem liberação para**: todos os endereços de e-mail (se houver) para os quais a mensagem não foi liberada.

### <a name="take-action-on-quarantined-email"></a>Tomar medidas quanto aos e-mails em quarentena

Após selecionar uma mensagem, você tem várias opções para o que fazer com as mensagens no painel de submenu **detalhes** :

- **Mensagem de lançamento**: no painel de submenus exibido, escolha as seguintes opções:

  - **Relatar mensagens à Microsoft para análise**: isso é selecionado por padrão e relata a mensagem em quarentena errada à Microsoft como um falso positivo. Se a mensagem foi colocada em quarentena como spam, em massa, phishing ou com malware, a mensagem também é relatada para a equipe de análise de spam da Microsoft. Dependendo da análise, as regras de filtro de spam de todo o serviço podem ser ajustadas para permitir a mensagem.

  - Escolha uma das seguintes opções:

    - **Liberar mensagens para todos os destinatários**

    - **Liberar mensagens para destinatários específicos**

    - **Liberar mensagens para outras pessoas**

  Quando terminar, clique em **Liberar mensagens**.

  Observações sobre o lançamento de mensagens:

  - Você não pode liberar uma mensagem para o mesmo destinatário mais de uma vez.

  - Somente os destinatários que não receberam a mensagem aparecerão na lista de possíveis destinatários.

- **Exibir cabeçalho da mensagem**: escolha este link para visualizar o texto do cabeçalho da mensagem. Para analisar os valores e campos de cabeçalho em detalhes, copie o texto do cabeçalho da mensagem para a área de transferência e, em seguida, escolha **Analisador de Cabeçalhos de Mensagens da Microsoft** para acessar o Analisar de Conectividade Remota (clique com o botão direito e escolha **Abrir em uma nova guia** se não quiser deixar o Microsoft 365 para concluir essa tarefa). Cole o cabeçalho da mensagem na página na seção Analisador do cabeçalho da mensagem e escolha **Analisar cabeçalhos**:

- **Visualizar mensagem**: no painel de submenu que é exibido, escolha uma das seguintes opções:

  - **Visualização da fonte**: mostra a versão HTML do corpo da mensagem com todos os links desabilitados.
  
  - **Visualização do texto**: mostra o corpo da mensagem em texto sem formatação.

- **Remover da quarentena**: depois de clicar em **Sim** no aviso exibido, a mensagem será excluída imediatamente sem ser enviada aos destinatários originais.

- **Mensagem de download**: no painel de submenu que é exibido, clique em **Compreendo os riscos de baixar esta mensagem** para salvar uma cópia local da mensagem no formato .eml.

- **Enviar mensagem**: no painel de submenu que aparece, escolha as seguintes opções:

  - **Tipo de objeto**: **email** (padrão), **URL**ou **anexo**.

  - **Formato de envio**: **ID de mensagem de rede** (padrão, com o valor correspondente na caixa ID de mensagem de **rede** ) ou **arquivo** (navegue até um arquivo. eml ou. msg local). Observe que, se você selecionar **arquivo** e, em seguida, selecionar **ID de mensagem de rede**, o valor inicialmente será desperdido.

  - **Destinatários**: digite no leasing um destinatário original da mensagem ou clique em **selecionar tudo** para identificar todos os destinatários. Você também pode clicar em **selecionar todos** e, em seguida, remover seletivamente destinatários individuais.

  - **Motivo do envio**: **não deve ter sido bloqueado** (padrão) ou **deve ter sido bloqueado**.

  Quando tiver concluído, clique em **Enviar**.

Se você não liberar ou remover a mensagem, ela será excluída após o término do período de retenção da quarentena padrão.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Tome medidas em várias mensagens quanto aos e-mails em quarentena

Quando você seleciona várias mensagens que estão em quarentena na lista (até 100), o painel de submenu **Ações em massa** é exibido em que você pode realizar as seguintes ações:

- **Mensagens de lançamento**: as opções são as mesmas de quando você libera uma única mensagem, mas não é possível clicar em **Liberar mensagens para destinatários específicos**; você só pode clicar em **Mensagem de lançamento a todos os destinatários** ou **Liberar mensagens para outras pessoas**.

- **Excluir mensagens**: depois de clicar em **Sim** no aviso que é exibido, a mensagem é imediatamente excluída sem ser enviada aos destinatários originais.

Quando terminar, clique em **Fechar**.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Somente ATP: usar o centro de conformidade de & de segurança para gerenciar arquivos em quarentena

> [!NOTE]
> Os procedimentos para arquivos em quarentena nesta seção estão disponíveis somente para assinantes do plano ATP 1 e do plano 2.

Em organizações com ATP, os administradores podem gerenciar arquivos em quarentena no SharePoint Online, no OneDrive for Business e no Microsoft Teams.

### <a name="view-quarantined-files"></a>Exibir arquivos em quarentena

1. No Centro de segurança e conformidade, vá para **Gerenciamento de ameaças** \> **Revisão** \> **Quarentena**.

2. Altere o **modo de exibição colocado em quarentena** para os **arquivos**de valor padrão. Você pode classificar em um campo clicando em um cabeçalho de coluna disponível.

3. Você pode classificar os resultados clicando em um cabeçalho de coluna disponível. Clique em **Modificar colunas** para exibir um máximo de sete colunas. As colunas padrão são marcadas com um asterisco<sup>\*</sup>():

   - **Usuário**<sup>\*</sup>

   - **Alocações**<sup>\*</sup>

   - **Nome do arquivo**<sup>\*</sup>

   - **URL do arquivo**<sup>\*</sup>

   - **Tamanho do arquivo**<sup>\*</sup>

   - **Expira**<sup>\*</sup>

   - **Lançado?**<sup>\*</sup>

   - **Detectado por**

   - **Modificado por hora**

4. Para filtrar os resultados, clique em **Filtro**. Os filtros disponíveis são:

   - **Hora que expira**: filtre as mensagens assim que elas saírem da quarentena:

     - **Hoje**

     - **Próximos 2 dias**

     - **Próximas 7 semanas**

     - Um intervalo personalizado de data/hora.

   - **Hora de recebimento**

   - **Motivo da quarentena**: o único valor disponível é **malware**.

Depois de encontrar um arquivo em quarentena específico, selecione o arquivo para exibir os detalhes sobre ele e execute a ação nele (por exemplo, exibir, liberar, baixar ou excluir a mensagem).

#### <a name="export-file-results"></a>Exportar resultados de arquivo

1. Selecione os arquivos nos quais você está interessado e clique em **Exportar resultados**.

2. Clique em **Sim** na mensagem de confirmação que avisa para manter a janela do navegador aberta.

3. Quando a exportação estiver pronta, você poderá nomear e escolher o local de download do arquivo .csv.

#### <a name="view-quarantined-file-details"></a>Exibir detalhes de arquivo em quarentena

Quando você seleciona um arquivo na lista, os seguintes detalhes de arquivo são exibidos no painel de submenu **detalhes** :

- **Nome do arquivo**

- **URL do arquivo**: URL que define o local do arquivo (por exemplo, no SharePoint Online).

- **Conteúdo mal-intencionado detectado em** A data/hora em que o arquivo foi colocado em quarentena.

- **Expira**: a data em que o arquivo será excluído da quarentena.

- **Detectado por**: ATP (proteção avançada contra ameaças) ou mecanismo antimalware da Microsoft.

- **Lançado?**

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

1. Usando uma conta corporativa ou de estudante que tenha privilégios de administrador global (ou funções apropriadas de segurança & central de conformidade) em sua organização, entre e [vá para o centro de conformidade de & de segurança](../../compliance/go-to-the-securitycompliance-center.md).

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Usar o PowerShell do Exchange Online ou do Exchange Online Protection para exibir e gerenciar arquivos e mensagens em quarentena

Os cmdlets que você usa para exibir e gerenciar mensagens e arquivos em quarentena são:

- [Delete-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Preview-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Observe que este cmdlet é somente para mensagens, e não para arquivos de malware de ATP para SharePoint Online, onedrive for Business ou Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
