---
title: Trabalhar com um parceiro para arquivar dados de terceiros
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Saiba como configurar um conector personalizado para importar dados de terceiros de fontes de dados como o Salesforce, o Yahoo Messenger ou o Yammer.
ms.openlocfilehash: c3b824909ae1243e2dd1f12b799e53d00d9615ca
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126650"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a>Trabalhar com um parceiro para arquivar dados de terceiros

Você pode trabalhar com um parceiro da Microsoft para importar e arquivar dados de uma fonte de dados de terceiros para o Microsoft 365. Um parceiro pode fornecer um conector personalizado que é configurado para extrair itens da fonte de dados de terceiros (em uma base regular) e, em seguida, importar esses itens. O conector de parceiro converte o conteúdo de um item da fonte de dados em um formato de mensagem de email e, em seguida, armazena os itens em caixas de correio. Após a importação dos dados de terceiros, é possível aplicar recursos de conformidade do Microsoft 365, como retenção de litígio, pesquisa de conteúdo, arquivamento in-loco, auditoria e políticas de retenção da Microsoft 365 a esses dados.
  
Veja a seguir uma visão geral do processo e as etapas necessárias para trabalhar com um parceiro da Microsoft para importar dados de terceiros.

[Step 1: Find a third-party data partner](#step-1-find-a-third-party-data-partner)

[Etapa 2: criar e configurar uma caixa de correio de dados de terceiros](#step-2-create-and-configure-a-third-party-data-mailbox-in-office-365)

[Step 3: Configure user mailboxes for third-party data](#step-3-configure-user-mailboxes-for-third-party-data)

[Etapa 4: fornecer informações ao seu parceiro](#step-4-provide-your-partner-with-information)

[Etapa 5: registrar o conector de dados de terceiros no Azure Active Directory](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a>Como funciona o processo de importação de dados de terceiros

A ilustração e a descrição a seguir explicam como funciona o processo de importação de dados de terceiros ao trabalhar com um parceiro.
  
![Como funciona o processo de importação de dados de terceiros](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. O cliente trabalha com o parceiro escolhido para configurar um conector que extrairá itens da fonte de dados de terceiros e, em seguida, importará esses itens para o Microsoft 365.
    
2. O conector de parceiro se conecta a fontes de dados de terceiros por meio de uma API de terceiros (em uma base agendada ou definida) e extrai itens da fonte de dados. O conector do parceiro converte o conteúdo de um item em um formato de mensagem de email. Consulte a seção [mais informações](#more-information) para obter uma descrição do esquema de formato de mensagem. 
    
3. O conector de parceiro se conecta ao serviço do Azure no Microsoft 365 usando o serviço Web do Exchange (EWS) por meio de um ponto de extremidade conhecido.
    
4. Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:
    
   1. **Itens que têm uma ID de usuário que corresponde a uma conta de usuário:** Se o conector de parceiro puder mapear a ID de usuário do item da fonte de dados de terceiros para uma ID de usuário específica no Office 365, o item será copiado para a pasta **limpezas** na pasta itens recuperáveis do usuário. Os usuários não podem acessar os itens na pasta Remoções. No entanto, você pode usar as ferramentas de descoberta eletrônica para pesquisar itens na pasta expurgações.
    
   1. **Itens que não têm uma ID de usuário que corresponde a uma conta de usuário:** Se o conector de parceiro não puder mapear a ID de usuário de um item para uma ID de usuário específica, o item será copiado para a pasta **caixa de entrada** da caixa de correio de dados de terceiros. Importar itens para a caixa de entrada permite que você ou alguém em sua organização entre na caixa de correio de terceiros para exibir e gerenciar esses itens e ver se os ajustes precisam ser feitos na configuração do conector do parceiro.
 
## <a name="step-1-find-a-third-party-data-partner"></a>Etapa 1: encontrar um parceiro de dados de terceiros

Um componente fundamental para o arquivamento de dados de terceiros no Microsoft 365 é a localização e o trabalho de um parceiro da Microsoft especializados na captura de dados de uma fonte de dados de terceiros e sua importação para o Office 365. Depois que os dados são importados, eles podem ser arquivados e preservados junto com outros dados da sua organização, como email do Exchange e documentos do SharePoint e do OneDrive for Business. Um parceiro cria um conector que extrai dados das fontes de dados de terceiros de sua organização (como BlackBerry, Facebook, Google +, Thomson Reuters, Twitter e YouTube) e transmite esses dados para uma API do Office 365 que importa itens para caixas de correio do Exchange como mensagens de email. 
  
As seções a seguir listam os parceiros da Microsoft (e as fontes de dados de terceiros que eles dão suporte) que estão participando do programa para arquivar dados de terceiros no Office 365.

[17a-4 LLC](#17a-4-llc)
  
[ArchiveSocial](#archivesocial)
  
[Globanet](#globanet)
  
[OpenText](#opentext)
  
[Smarsh](#smarsh)

[Verba](#verba)
  
### <a name="17a-4-llc"></a>17a-4 LLC

o [17a-4 LLC](https://www.17a-4.com) suporta as seguintes fontes de dados de terceiros:
  
- BlackBerry
    
- Fluxos de dados do Bloomberg
    
- Cisco Jabber
    
- FactSet
    
- HipChat
    
- InvestEdge
    
- LivePerson
    
- MessageLabs Data Streams
    
- OpenText
    
- Oracle/ATG 'click-to-call' Live Help
    
- Pivot IMTRADER
    
- Microsoft SharePoint
    
- MindAlign
    
- Sitrion One (Newsgator)
    
- Skype for Business (Lync/OCS)
    
- Skype for Business Online (Lync Online)
    
- Bancos de dados SQL
    
- Squawker
    
- Thomson Reuters Eikon Messenger
  

  
### <a name="archivesocial"></a>ArchiveSocial

O [ArchiveSocial](https://www.archivesocial.com) suporta as seguintes fontes de dados de terceiros: 
  
- Facebook
    
- Flickr
    
- Instagram
    
- LinkedIn
    
- Pinterest
    
- Twitter
    
- YouTube
    
- Vimeo
  
### <a name="globanet"></a>Globanet

O [Globanet](https://www.globanet.com) suporta as seguintes fontes de dados de terceiros: 
  
- AOL with Pivot Client 
    
- BlackBerry Call Logs (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Chat
    
- Bloomberg Mail
    
- Caixa
    
- CipherCloud for Salesforce Chatter
    
- Servidor de presença de IM da Cisco &amp; (v10, v 10.5.1 SU1, v 11.0, v 11.5 SU2)

- Equipes do Cisco WebEx

- Compartilhamento do Citrix Workspace &amp;

- CrowdCompass

- Arquivos de texto delimitados por personalização
    
- Arquivos XML personalizados
    
- Facebook (páginas)
    
- FactSet
    
- FXConnect
    
- ICE Chat/YellowJacket
    
- Jive
    
- Macgregor XIP

- Microsoft Exchange Server
    
- Microsoft OneDrive for Business

- Microsoft Teams
       
- Microsoft Yammer
    
- Mobile Guard
    
- Navegação dinâmica
    
- Salesforce Chatter

- Skype for Business Online
    
- Skype for Business, versões 2007 R2 - 2016 (local)
    
- Slack Enterprise Grid
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Thomson Reuters Dealings 3000 / FX Trading
    
- Twitter
    
- UBS Chat
    
- YouTube
  
### <a name="opentext"></a>OpenText

A [OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) suporta as seguintes fontes de dados de terceiros: 
  
- Axs Encrypted
    
- Axs Exchange
    
- Axs Local Archive
    
- Axs PlaceHolder
    
- Axs Signed
    
- Bloomberg
    
- Thomson Reuters
  
### <a name="smarsh"></a>Smarsh

O [Smarsh](https://www.smarsh.com) suporta as seguintes fontes de dados de terceiros: 
  
- META
    
- American Idol
    
- Apple Juice
    
- AOL with Pivot Client
    
- Ares
    
- Bazaar Voice
    
- Bear Share
    
- Bit Torrent
    
- BlackBerry Call Logs (v5, v10, v12)
    
- BlackBerry Messenger (v5, v10, v12)
    
- BlackBerry PIN (v5, v10, v12)
    
- BlackBerry SMS (v5, v10, v12)
    
- Bloomberg Mail
    
- CellTrust
    
- Importação de bate-papo
    
- Política e registros de bate-papo em tempo real
    
- Instabilidade
    
- Servidor de presença de IM da Cisco &amp; (v 9.0.1, v 9.1, v 9.1.1 SU1, v10, v 10.5.1 SU1)
    
- Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)
    
- Importação de colaboração
    
- Registro de colaboração em tempo real
    
- Conexão Direta
    
- Facebook
    
- FactSet
    
- FastTrack
    
- Gnutella
    
- Google +
    
- GoToMyPC
    
- Hopster
    
- HubConnex
    
- IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)
    
- IBM Connections Chat Cloud
    
- IBM Connections Social Cloud
    
- IBM SameTime Advanced 8.5.2 IFR1
    
- IBM SameTime Communicate 9.0
    
- IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)
    
- IBM SameTime Complete 9.0
    
- IBM SameTime Conference 9.0
    
- IBM SameTime Meeting 8.5.2 IFR1
    
- ICE/YellowJacket
    
- Importação de mensagem Instantânea
    
- Política e registro de mensagem instantânea em tempo real
    
- Indii Messenger
    
- Instant Bloomberg
    
- IRC
    
- Jive
    
- Jive 6 Real Time Logging (v6, v7)
    
- Jive Import
    
- JXTA
    
- LinkedIn
    
- Microsoft Lync (2010, 2013)
    
- MFTP
    
- Microsoft Lync 2013 Voice
    
- Microsoft SharePoint (2010, 2013)
    
- Microsoft SharePoint Online
    
- Microsoft UC (Unified Communications)
    
- MindAlign
    
- Mobile Guard
    
- MSN
    
- My Space
    
- NEONetwork
    
- Office 365 Lync Dedicated
    
- Office 365 Shared IM
    
- Pinterest
    
- Navegação dinâmica
    
- QQ
    
- Skype for Business 2015
    
- SoftEther
    
- Symphony
    
- Thomson Reuters Eikon
    
- Thomson Reuters Messenger
    
- Tor
    
- TTT
    
- Twitter
    
- WinMX
    
- Winny
    
- Instant
    
- Yammer
    
- YouTube
    

### <a name="verba"></a>Verba

O [verba](https://www.verba.com) suporta as seguintes fontes de dados de terceiros: 
  
- Avaya Aura Video
    
- Avaya Aura Voice
    
- Avtec Radio
    
- Bosch/Telex Radio
    
- BroadSoft Vídeo
    
- BroadSoft Voice
    
- Centile Voice
    
- Cisco Jabber IM
    
- Cisco UC Video
    
- Cisco UC Voice
    
- Vídeo do Cisco UCCX/UCCE
    
- Voz do Cisco UCCX/UCCE
    
- ESChat Radio
    
- Geoman Contact Expert
    
- IP Trade Voice
    
- Luware LUCS Contact Center
    
- Microsoft UC (Unified Communications)
    
- Mitel MiContact Center for Lync (prairieFyre)
    
- Oracle / Acme Packet Session Border Controller Video
    
- Oracle / Acme Packet Session Border Controller Voice
    
- Singtel Mobile Voice
    
- SIPREC Video
    
-  SIPREC Voice 
    
- Skype for Business / Lync IM
    
- Skype for Business / Lync Video
    
- Skype for Business / Lync Voice
    
- Speakerbus Voice
    
- Standard SIP/H.323 Video
    
- Standard SIP/H.323 Voice
    
- Truphone Voice
    
- TwistedPair Radio
    
- Windows Desktop Computer Screen
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-office-365"></a>Etapa 2: criar e configurar uma caixa de correio de dados de terceiros no Office 365

Aqui estão as etapas para criar e configurar uma caixa de correio de dados de terceiros para importar dados para o Office 365. Como explicado anteriormente, os itens são importados para esta caixa de correio se o conector de parceiro não puder mapear a ID de usuário do item para uma conta de usuário.
  
 **Concluir estas tarefas no centro de administração do Microsoft 365**
  
1. Criar uma conta de usuário e atribuí-la a uma licença do Exchange Online Plan 2; consulte [Adicionar usuários ao Office 365](https://go.microsoft.com/fwlink/p/?LinkId=692098). Uma licença do plano 2 é necessária para colocar a caixa de correio em retenção de litígio ou habilitar uma caixa de correio de arquivo morto com uma cota de armazenamento ilimitada.
    
2. Adicione a conta de usuário para a caixa de correio de dados de terceiros à função de administrador de **Administradores do Exchange** no Office 365; Confira [atribuir funções de administrador no Office 365](https://go.microsoft.com/fwlink/p/?LinkId=532393).
    
    > [!TIP]
    > Anote as credenciais da conta do usuário. Você precisa enviá-las para o seu parceiro, conforme descrito na Etapa 4. 
  
 **Concluir estas tarefas no centro de administração do Exchange**
  
1. Ocultar a caixa de correio de dados de terceiros no catálogo de endereços e em outras listas de endereços em sua organização; consulte [manage user Mailboxes](https://go.microsoft.com/fwlink/p/?LinkId=616058). Como alternativa, você pode executar o seguinte comando do PowerShell:
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. Atribua a permissão **FullAccess** à caixa de correio de dados de terceiros para que administradores ou gerentes de conformidade possam abrir a caixa de correio de dados de terceiros no cliente da área de trabalho do Outlook; consulte [Manage Permissions for Recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).
    
3. Habilite os seguintes recursos relacionados à conformidade para a caixa de correio de dados de terceiros:
    
    - Habilitar a caixa de correio de arquivo morto; consulte [habilitar caixas de correio de arquivo morto](enable-archive-mailboxes.md) e [habilitar o arquivamento ilimitado](enable-unlimited-archiving.md). Isso permite que você libere espaço de armazenamento na caixa de correio principal Configurando uma política de arquivamento que move itens de dados de terceiros para a caixa de correio de arquivo morto. Isso fornece armazenamento ilimitado para dados de terceiros.
    
    - Colocar a caixa de correio de dados de terceiros em Retenção de Litígio. Você também pode aplicar uma política de retenção da Microsoft 365 no centro de segurança e conformidade. Colocar esta caixa de correio em retenção mantém itens de dados de terceiros (indefinidamente ou por um período especificado) e impede que eles sejam excluídos da caixa de correio. Consulte um dos seguintes tópicos:
    
      - [Colocar uma caixa de correio em Retenção de Litígio](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
      - [Saiba mais sobre políticas de retenção e rótulos de retenção](retention.md)
    
    - Habilitar o log de auditoria de caixa de correio para proprietário, representante e acesso de administrador à caixa de correio de dados de terceiros; consulte [habilitar a auditoria de caixa de correio](enable-mailbox-auditing.md). Isso permite que você faça a auditoria de todas as atividades realizadas por qualquer usuário que tenha acesso à caixa de correio de dados de terceiros.

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a>Etapa 3: configurar caixas de correio de usuário para dados de terceiros

A próxima etapa é configurar as caixas de correio do usuário para oferecer suporte a dados de terceiros. Conclua essas tarefas usando o centro de administração do Exchange ou usando os cmdlets do Windows PowerShell correspondentes.
  
1. Habilitar a caixa de correio de arquivo morto para cada usuário; consulte [habilitar caixas de correio de arquivo morto](enable-archive-mailboxes.md) e [habilitar o arquivamento ilimitado](enable-unlimited-archiving.md).
    
2. Coloque as caixas de correio do usuário em retenção de litígio ou aplique uma política de retenção da Microsoft 365; consulte um dos seguintes tópicos: 
    
    - [Colocar uma caixa de correio em Retenção de Litígio](https://go.microsoft.com/fwlink/p/?LinkId=404420)
    
    - [Saiba mais sobre políticas de retenção e rótulos de retenção](retention.md)
    
    Conforme mencionado anteriormente, quando você coloca as caixas de correio em retenção, é possível definir uma duração para a retenção dos itens da fonte de dados de terceiros, ou você pode optar por reter itens indefinidamente.

## <a name="step-4-provide-your-partner-with-information"></a>Etapa 4: fornecer informações ao seu parceiro

A etapa final é fornecer ao seu parceiro as seguintes informações para que eles possam configurar o conector para se conectar à sua organização para importar dados para caixas de correio do usuário e para a caixa de correio de dados de terceiros. 
  
- O ponto de extremidade usado para se conectar ao serviço do Azure no Office 365:

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- As credenciais de logon (ID de usuário e senha do Microsoft 365) da caixa de correio de dados de terceiros que você criou na etapa 2. Essas credenciais são necessárias para que o conector do parceiro possa acessar e importar itens para a caixa de correio do usuário e a caixa de correio de dados de terceiros.
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a>Etapa 5: registrar o conector de dados de terceiros no Azure Active Directory

Desde 30 de setembro de 2018, o serviço do Azure no Office 365 começará a usar a autenticação moderna no Exchange Online para autenticar conectores de dados de terceiros que tentam se conectar à sua organização para importar dados. O motivo dessa alteração é que a autenticação moderna fornece mais segurança do que o método atual, que se baseia em uma lista de permissões para conectores de terceiros que usam o ponto de extremidade descrito anteriormente para se conectar ao serviço do Azure.

Para permitir que um conector de dados de terceiros se conecte ao Office 365 usando o novo método de autenticação moderna, um administrador em sua organização deve se concordar em registrar o conector como um aplicativo de serviço confiável no Azure Active Directory. Isso é feito aceitando uma solicitação de permissão para permitir que o conector acesse os dados da sua organização no Azure Active Directory. Depois que você aceita essa solicitação, o conector de dados de terceiros é adicionado como um aplicativo corporativo ao Azure Active Directory e representado como uma entidade de serviço. Para obter mais informações sobre o processo de consentimento, consulte [consentimento do administrador do locatário](https://docs.microsoft.com/skype-sdk/trusted-application-api/docs/tenantadminconsent).

Aqui estão as etapas para acessar e aceitar a solicitação de registro do conector:

1. Vá até [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e entre usando as credenciais de um administrador global.

   A caixa de diálogo a seguir é exibida. Você pode expandir os acentos para revisar as permissões que serão atribuídas ao conector.

   ![A caixa de diálogo de solicitação de permissões é exibida](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. Clique em **Aceitar**.

Após aceitar a solicitação, o [portal do Azure](https://portal.azure.com) é exibido. Para exibir a lista de aplicativos da sua organização, clique **Azure Active Directory**em  >  **aplicativos corporativos**do Azure Active Directory. O conector de dados de terceiros do Office 365 está listado na folha **aplicativos empresariais** .

> [!IMPORTANT]
> Após 30 de setembro de 2018, os dados de terceiros não serão mais importados para caixas de correio em sua organização se você não registrar um conector de dados de terceiros no Azure Active Directory. Observação os conectores de dados de terceiros existentes (aqueles criados antes de 30 de setembro de 2018) também devem ser registrados no Azure Active Directory seguindo o procedimento na etapa 5.

### <a name="revoking-consent-for-a-third-party-data-connector"></a>Revogar o consentimento de um conector de dados de terceiros

Depois que sua organização concorda com a solicitação de permissões para registrar um conector de dados de terceiros no Azure Active Directory, sua organização pode revogar esse consentimento a qualquer momento. No entanto, revogar o consentimento de um conector significa que os dados da fonte de dados de terceiros não serão mais importados para o Office 365.

Para revogar o consentimento de um conector de dados de terceiros, você pode excluir o aplicativo (excluindo a entidade de serviço correspondente) do Azure Active Directory usando a lâmina **aplicativos corporativos** no portal do Azure ou usando o [Remove-MsolServicePrincipal](https://docs.microsoft.com/powershell/module/msonline/remove-msolserviceprincipal) no Office 365 PowerShell. Você também pode usar o cmdlet [Remove-AzureADServicePrincipal](https://docs.microsoft.com/powershell/module/azuread/remove-azureadserviceprincipal) no PowerShell do Azure Active Directory.
  
## <a name="more-information"></a>Mais informações

- Conforme explicado anteriormente, os itens de fontes de dados de terceiros são importados para caixas de correio do Exchange como mensagens de email. O conector de parceiro importa o item usando um esquema exigido pela API do Office 365. A tabela a seguir descreve as propriedades de mensagem de um item de uma fonte de dados de terceiros após importá-lo para uma caixa de correio do Exchange como uma mensagem de email. A tabela também indica se a propriedade da mensagem é obrigatória. As propriedades obrigatórias devem ser preenchidas. Se um item não tiver uma propriedade obrigatória, ele não será importado para o Office 365. O processo de importação retorna uma mensagem de erro explicando por que um item não foi importado e qual propriedade está ausente.<br/><br/>
    
    |**Propriedade da mensagem**|**Obrigatório?**|**Descrição**|**Valor de Exemplo**|
    |:-----|:-----|:-----|:-----|
    |**FROM** <br/> |Sim  <br/> |O usuário que criou ou enviou originalmente o item na fonte de dados de terceiros. O conector de parceiro tenta mapear a ID de usuário do item de origem (por exemplo, uma alça do Twitter) para uma conta de usuário para todos os participantes (usuários nos campos de e para). Uma cópia da mensagem será importada para a caixa de correio de cada participante. Se nenhum dos participantes do item puder ser mapeado para uma conta de usuário, o item será importado para a caixa de correio de arquivamento de terceiros no Office 365.  <br/> <br/> O participante identificado como o remetente do item deve ter uma caixa de correio ativa na organização para a qual o item está sendo importado. Se o remetente não tem uma caixa de correio ativa, o seguinte erro é retornado:<br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |**TO** <br/> |Sim  <br/> |O usuário que recebeu um item, caso seja aplicável a um item na fonte de dados.  <br/> | `bob@contoso.com` <br/> |
    |**Assunto** <br/> |Não  <br/> |O assunto do item de origem.  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |**PÓS-DATADOS** <br/> |Sim  <br/> |A data em que o item foi originalmente criado ou Postado na fonte de dados do cliente. Por exemplo, essa data quando uma mensagem do Twitter foi tweeted.  <br/> | `01 NOV 2015` <br/> |
    |**ÓRGÃO** <br/> |Não  <br/> |O conteúdo da mensagem ou publicação. Para algumas fontes de dados, o conteúdo dessa propriedade pode ser o mesmo que o conteúdo da propriedade **ASSUNTO**. Durante o processo de importação, o conector parceiro tenta manter a fidelidade total da fonte de conteúdo possível. Se for possível, arquivos, gráficos ou outros tipos de conteúdo do corpo do item de origem estarão incluídos nesta propriedade. Caso contrário, o conteúdo do item de origem estará incluído na propriedade **ANEXO**. O conteúdo dessa propriedade depende do conector de parceiro e da capacidade da plataforma de origem.  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |**ANEXAR** <br/> |Não  <br/> |Se um item na fonte de dados (como um tweet no Twitter ou uma conversa de mensagem instantânea) tiver um arquivo anexado ou incluir imagens, a conexão de parceiro tentará primeiro incluir anexos na propriedade **Body** . Se isso não for possível, então será adicionado à propriedade * * ATTACHMENT * *. Outros exemplos de anexos incluem Curtidas no Facebook, metadados da fonte de conteúdo e respostas a uma mensagem ou publicação.  <br/> | `image.gif` <br/> |
    |**MESSAGECLASS** <br/> |Sim  <br/> | Esta é uma propriedade com múltiplos valores, que é criada e preenchida pelo conector parceiro. O formato dessa propriedade é `IPM.NOTE.Source.Event` . (Essa propriedade deve começar com `IPM.NOTE` . Este formato é semelhante ao da `IPM.NOTE.X` classe de mensagens.) Esta propriedade inclui as seguintes informações:  <br/><br/>`Source`: Indica a fonte de dados de terceiros; por exemplo, Twitter, Facebook ou BlackBerry.  <br/> <br/>  `Event`: Indica o tipo de atividade que foi executado na fonte de dados de terceiros que produziu os itens; por exemplo, um tweet no Twitter ou uma postagem no Facebook. Eventos são específicos à fonte de dados.  <br/> <br/>  Uma finalidade dessa propriedade é filtrar itens específicos com base na fonte de dados na qual um item teve origem ou com base no tipo de evento. Por exemplo, em uma pesquisa de Descoberta Eletrônica você poderia criar uma consulta de pesquisa para encontrar todos os tweets publicados por um usuário específico.  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- Quando os itens são importados com êxito para caixas de correio no Office 365, um identificador exclusivo é retornado de volta para o chamador como parte da resposta HTTP. Esse identificador, chamado `x-IngestionCorrelationID` , pode ser usado para fins de solução de problemas subsequentes por parceiros para o controle de ponta a ponta dos itens. É recomendável que os parceiros capturem essas informações e as registrem de acordo no lado deles. Veja aqui um exemplo de uma resposta HTTP que mostra esse identificador:

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- Você pode usar a ferramenta de pesquisa de conteúdo no centro de segurança e conformidade para pesquisar itens que foram importados para caixas de correio de uma fonte de dados de terceiros. Para pesquisar especificamente esses itens importados, você pode usar os seguintes pares de propriedade de mensagem-valor na caixa palavra-chave de uma pesquisa de conteúdo.
    
  - **`kind:externaldata`**: Use este par de propriedade-valor para pesquisar todos os tipos de dados de terceiros. Por exemplo, para pesquisar itens que foram importados de uma fonte de dados de terceiros e continham a palavra "contoso" na propriedade Subject do item importado, você usaria a consulta de palavra-chave `kind:externaldata AND subject:contoso` .
    
  - **`itemclass:ipm.externaldata.<third-party data type>`**: Use este par de propriedade-valor para pesquisar apenas um tipo de dados de terceiros. Por exemplo, para pesquisar apenas dados do Facebook que contenham a palavra "contoso" na propriedade Subject, você usaria a consulta de palavra-chave `itemclass:ipm.externaldata.Facebook* AND subject:contoso` . 

  Para obter uma lista completa de valores a serem usados para tipos de dados de terceiros para a `itemclass` propriedade, confira [usar a pesquisa de conteúdo para pesquisar dados de terceiros que foram importados para o Office 365](use-content-search-to-search-third-party-data-that-was-imported.md).
    
   Veja mais informações sobre como usar a Pesquisa de Conteúdo e criar consultas de pesquisa de palavra-chave em:
    
  - [Pesquisa de Conteúdo no Office 365](content-search.md)
    
  - [Consultas de palavra-chave e condições de pesquisa para Pesquisa de Conteúdo](keyword-queries-and-search-conditions.md)
 
