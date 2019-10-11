---
title: Propriedades detalhadas no log de auditoria do Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- BCS160
- MET150
ms.assetid: ce004100-9e7f-443e-942b-9b04098fcfc3
description: Descrições das propriedades adicionais incluídas em um registro de log de auditoria do Office 365.
ms.openlocfilehash: 04b2c0bf5d4a3a534e166e82b0261f71e7788294
ms.sourcegitcommit: db580dc2626328d324f65c7380a5816a500688a7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37437791"
---
# <a name="detailed-properties-in-the-office-365-audit-log"></a>Propriedades detalhadas no log de auditoria do Office 365

Ao exportar os resultados de uma pesquisa de log de auditoria do centro de conformidade & segurança, você tem a opção de baixar todos os resultados que atendem aos critérios de pesquisa. Para fazer isso, selecione **Exportar resultados** \> **baixar todos os resultados** na página **pesquisa de log de auditoria** . Para obter mais informações, consulte [Search the Audit Log In The Office 365](search-the-audit-log-in-security-and-compliance.md).
  
 Quando exportar todos os resultados de uma pesquisa de log de auditoria, os dados brutos do log de auditoria unificada do Office 365 serão copiados para um arquivo CSV (valores separados por vírgula) baixados para o computador local. Este arquivo contém informações adicionais de cada registro de auditoria em uma coluna chamada **AuditData**. Esta coluna contém uma propriedade de vários valores para várias propriedades do registro de log de auditoria. Cada um dos pares **Propriedade: valor** nessa propriedade de vários valores é separado por uma vírgula. 
  
A tabela a seguir descreve as propriedades que são incluídas (dependendo do serviço do Office 365 no qual um evento ocorre) na coluna **AuditData** de várias propriedades. O **serviço do Office 365 que tem essa** coluna de propriedade indica o serviço e o tipo de atividade (usuário ou administrador) que inclui a propriedade. Para obter informações mais detalhadas sobre essas propriedades ou sobre as propriedades que podem não estar listadas neste tópico, consulte [esquema de API de atividade de gerenciamento do Office 365](https://go.microsoft.com/fwlink/p/?LinkId=717993).
  
> [!TIP]
> Você pode usar o recurso de transformação JSON no Power Query no Excel para dividir a coluna **AuditData** em várias colunas, de modo que cada propriedade tenha sua própria coluna. Isso permite classificar e filtrar em uma ou mais dessas propriedades. Para saber como fazer isso, confira [exportar, configurar e exibir registros de log de auditoria](export-view-audit-log-records.md). 
  
|**Propriedade**|**Descrição**|**Serviço do Office 365 que tem essa propriedade**|
|:-----|:-----|:-----|
|Actor|A conta de usuário ou de serviço que executou a ação.|Azure Active Directory|
|AddOnName|O nome de um complemento que foi adicionado, removido ou atualizado em uma equipe. O tipo de Complementos no Microsoft Teams é um bot, um conector ou uma guia.|Microsoft Teams|
|AddOnType|O tipo de um complemento que foi adicionado, removido ou atualizado em uma equipe. Os valores a seguir indicam o tipo de complemento.  <br/> **1** -indica um bot.<br/> **2** -indica um conector.<br/> **3** -indica uma tabulação.|Microsoft Teams|
|AzureActiveDirectoryEventType|O tipo de evento do Azure Active Directory. Os valores a seguir indicam o tipo de evento.  <br/> **0** -indica um evento de login de conta.<br/> **1** -indica um evento de segurança do aplicativo do Azure.|Azure Active Directory|
|ChannelGuid|A ID de um canal do Microsoft Teams. A equipe em que o canal está localizado é identificada pelas propriedades **teamname** e **TeamGuid** .|Microsoft Teams|
|ChannelName|O nome de um canal do Microsoft Teams. A equipe em que o canal está localizado é identificada pelas propriedades **teamname** e **TeamGuid** .|Microsoft Teams|
|Cliente|O dispositivo cliente, o so do dispositivo e o navegador do dispositivo usado para o evento de logon (por exemplo, Nokia Lumia 920; Windows Phone 8; IE Mobile 11).|Azure Active Directory|
|ClientInfoString|Informações sobre o cliente de email que foi usado para executar a operação, como uma versão do navegador, uma versão do Outlook e informações sobre dispositivos móveis|Exchange (atividade de caixa de correio)|
|ClientIP|O endereço IP do dispositivo que foi usado quando a atividade foi registrada. O endereço IP é exibido em um formato de endereço IPv4 ou IPv6.<br/><br/>Observe que para a atividade de administração de eventos do Azure Active Directory, o endereço IP não é registrado e o valor da propriedade ClientIP `null`é. |Exchange e Azure Active Directory|
|ClientIPAddress|O mesmo que ClientIP.|SharePoint|
|CreationTime|A data e hora no Tempo Universal Coordenado (UTC) de quando o usuário realizou a atividade.|Todos|
|DestinationFileExtension|A extensão de um arquivo que foi copiado ou movido. Essa propriedade é exibida somente para as atividades de usuário filecopied e filemoved.|SharePoint|
|DestinationFileName|O nome do arquivo é copiado ou movido. Essa propriedade é exibida somente para as ações filecopied e filemoved.|SharePoint|
|DestinationRelativeUrl|A URL da pasta de destino em que um arquivo é copiado ou movido. A combinação dos valores para **SiteUrl**, **DestinationRelativeURL**e a propriedade **DestinationFileName** é o mesmo que o valor da propriedade **ObjectID** , que é o nome do caminho completo para o arquivo que foi copiado. Essa propriedade é exibida somente para as atividades de usuário filecopied e filemoved.|SharePoint|
|EventSource|Identifica que um evento ocorreu no SharePoint. Os valores possíveis são **SharePoint** e **ObjectModel**.|SharePoint|
|ExternalAccess|Para a atividade de administração do Exchange, especifica se o cmdlet foi executado por um usuário da sua organização, pela equipe do Microsoft Datacenter ou por uma conta de serviço do Datacenter ou por um administrador delegado. O valor **Falso** indica que o cmdlet foi executado por alguém em sua organização. O valor **Verdadeiro** indica que o cmdlet foi executado pela equipe do datacenter, por uma conta de serviço do datacenter ou por um administrador delegado.  <br/> Para a atividade de caixa de correio do Exchange, especifica se uma caixa de correio foi acessada por um usuário fora da sua organização.|Exchange|
|ExtendedProperties|As propriedades estendidas de um evento do Azure Active Directory.|Azure Active Directory|
|ID|A ID da entrada de relatório. A identificação identifica exclusivamente a entrada de relatório.|Todos|
|InternalLogonType|Reservado para uso interno.|Exchange (atividade de caixa de correio)|
|ItemType|O tipo de objeto que foi acessado ou modificado. Os valores possíveis incluem **arquivo**, **pasta**, **Web**, **site**, **locatário**e **DocumentLibrary**.|SharePoint|
|LoginStatus|Identifica falhas de logon que podem ter ocorrido.|Azure Active Directory|
|LogonType|O tipo de acesso de caixa de correio. Os valores a seguir indicam o tipo de usuário que acessou a caixa de correio.  <br/><br/> **0** -indica um proprietário de caixa de correio.<br/> **1** -indica um administrador.<br/> **2** -indica um representante. <br/>**3** -indica o serviço de transporte no datacenter da Microsoft.<br/> **4** -indica uma conta de serviço no datacenter da Microsoft. <br/>**6** -indica um administrador delegado.|Exchange (atividade de caixa de correio)|
|MailboxGuid|O GUID do Exchange da caixa de correio que foi acessada.|Exchange (atividade de caixa de correio)|
|MailboxOwnerUPN|O endereço de email da pessoa que possui a caixa de correio que foi acessada.|Exchange (atividade de caixa de correio)|
|Members|Lista os usuários que foram adicionados ou removidos de uma equipe. Os valores a seguir indicam o tipo de função atribuído ao usuário.  <br/><br/> **1** -indica a função do proprietário.<br/> **2** -indica a função de membro.<br/> **3** -indica a função de convidado. <br/><br/>A propriedade Members também inclui o nome da sua organização e o endereço de email do membro.|Microsoft Teams|
|ModifiedProperties (Name, NewValue, OldValue)|A propriedade está incluída para eventos de administrador, como adicionar um usuário como membro de um site ou grupo de administradores de um conjunto de sites. A propriedade inclui o nome da propriedade que foi modificada (por exemplo, o grupo de administração do site) o novo valor da propriedade Modified (como o usuário que foi adicionado como administrador do site e o valor anterior do objeto Modified.|All (atividade de administração)|
|IDs|Para o log de auditoria do administrador do Exchange, o nome do objeto que foi modificado pelo cmdlet.  <br/> Para a atividade do SharePoint, o nome de caminho de URL completo do arquivo ou pasta acessado por um usuário.  <br/> Para a atividade do Azure AD, o nome da conta de usuário que foi modificada.|Todos|
|Operation|O nome do usuário ou atividade administrativa. O valor dessa propriedade corresponde ao valor que foi selecionado na lista suspensa **atividades** . Se **Mostrar resultados de todas as atividades** tiver sido selecionado, o relatório incluirá entradas para todas as atividades de usuário e administrador de todos os serviços. Para obter uma descrição das operações/atividades registradas no log de auditoria do Office 365, consulte a guia **atividades auditadas** em [Pesquisar o log de auditoria no Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> Para a atividade de administração do Exchange, essa propriedade identifica o nome do cmdlet que foi executado.|Todos|
|ID|O GUID da sua organização do Office 365.|Todos|
|Caminho|O nome da pasta da caixa de correio em que a mensagem que foi acessada está localizada. Essa propriedade também identifica a pasta na qual uma mensagem é criada ou copiada/movida.|Exchange (atividade de caixa de correio)|
|Parâmetros|Para atividades de administração do Exchange, o nome e o valor de todos os parâmetros que foram usados com o cmdlet identificado na Propriedade Operation.|Exchange (atividade de administração)|
|RecordType|O tipo de operação indicado pelo registro. Os valores a seguir indicam o tipo de registro.  <br/><br/> **1** -indica um registro do log de auditoria do administrador do Exchange. <br/>**2** : indica um registro do log de auditoria de caixa de correio do Exchange para uma operação executada em um item de caixa de correio único. <br/>**3** -também indica um registro do log de auditoria de caixa de correio do Exchange. Esse tipo de registro indica que a operação foi executada em vários itens da caixa de correio de origem (como mover vários itens para a pasta itens excluídos ou excluir permanentemente vários itens). <br/>**4** -indica uma operação de administração de site no SharePoint, como um administrador ou usuário que atribui permissões a um site. <br/>**6** -indica uma operação relacionada a um arquivo ou pasta no SharePoint, como um usuário exibindo ou modificando um arquivo. <br/>**8** -indica uma operação de administrador executada no Azure Active Directory. <br/>**9** -indica eventos de logon do OrgID no Azure Active Directory. Este tipo de registro está sendo preterido. <br/>**10** -indica eventos de cmdlet de segurança que foram executados pela equipe da Microsoft no Data Center. <br/>**11** -indica eventos de proteção contra perda de dados (DLP) no SharePoint.<br/> **12** -indica eventos do Sway. <br/>**13** -indica eventos DLP no Exchange, quando configurados com uma política de DLP unificada. Eventos de DLP baseados em regras de fluxo de mensagens do Exchange (também conhecidas como regras de transporte) não são suportados.<br>**14** -indica o compartilhamento de eventos no SharePoint.<br/> **15** -indica eventos de logon do serviço de token seguro (STS) no Azure Active Directory. <br/>**18** -indica eventos de segurança & central de conformidade. <br/>**20** -indica eventos do Power bi. <br/>**21**-indica eventos do Dynamics 365.<br/>**22** -indica eventos do Yammer. <br/>**23** -indica eventos do Skype for Business. <br/>**24** -indica eventos de descoberta eletrônica. Esse tipo de registro indica as atividades que foram realizadas executando pesquisas de conteúdo e gerenciando casos de descoberta eletrônica no centro de segurança e conformidade. Para saber mais, confira [Pesquisar atividades de descoberta eletrônica no log de auditoria do Office 365](search-for-ediscovery-activities-in-the-audit-log.md).<br/>**25, 26 ou 27** -indica eventos do Microsoft Teams. <br/>**28** -indica eventos de phishing e malware do Exchange Online Protection e dos eventos avançados de proteção contra ameaças do Office 365.<br/> **30** -indica eventos de fluxo da Microsoft.<br/> **31** -indica eventos de descoberta eletrônica avançados.<br/> **32** -indica eventos do Microsoft Stream.<br/> **35** -indica eventos do Microsoft Project. <br/> **36** -indica eventos de lista do SharePoint.<br/> **38** : indica eventos relacionados a políticas de retenção e rótulos de retenção no centro de segurança e conformidade.  <br/>**40** : indica eventos que resultam de sinais de alerta de segurança e conformidade.<br/> **41** -indica o tempo de bloqueio de links seguros e eventos de substituição de bloqueio no Office 365 Advanced Threat Protection.<br/>**44** -indica eventos de análise do local de trabalho. <br/>**45** -indica eventos de aplicativo do PowerApps. <br/> **47** -indica eventos de phishing e malware do Office 365 proteção avançada contra ameaças para arquivos no SharePoint, no onedrive e no Microsoft Teams. <br/> **52** : indica eventos relacionados à API REST de insights de dados.<br/>**54** -indica eventos de item de lista do SharePoint.<br/>**55** : indica eventos de tipo de conteúdo do SharePoint.
|ResultStatus|Indica se a ação (especificada na propriedade **Operation** ) foi bem-sucedida ou não.  <br/> Para a atividade de administração do Exchange, o valor é **true** (bem-sucedido) ou **false** (com falha).|Todos  <br/>|
|SecurityComplianceCenterEventType|Indica que a atividade era um evento de centro de conformidade de & de segurança. Todas as atividades de segurança & centro de conformidade terão o valor **0** para esta propriedade.|Centro de Conformidade e Segurança|
|SharingType|O tipo de permissões de compartilhamento que foi atribuído ao usuário com o qual o recurso foi compartilhado. Esse usuário é identificado na propriedade **UserSharedWith** .|SharePoint|
|Site|O GUID do site onde o arquivo ou pasta acessado pelo usuário está localizado.|SharePoint|
|SiteUrl|A URL do site onde o arquivo ou pasta acessado pelo usuário está localizado.|SharePoint|
|SourceFileExtension|A extensão do arquivo que foi acessado pelo usuário. Esta propriedade fica em branco se o objeto que foi acessado for uma pasta.|SharePoint|
|SourceFileName|O nome do arquivo ou pasta acessado pelo usuário.|SharePoint|
|SourceRelativeUrl|O URL da pasta que contém o arquivo acessado pelo usuário. A combinação dos valores para **SiteUrl**, **SourceRelativeURL**e a propriedade **sourceFileName** é o mesmo que o valor da propriedade **ObjectID** , que é o nome do caminho completo para o arquivo acessado pelo usuário.|SharePoint|
|Subject|A linha de assunto da mensagem que foi acessada.|Exchange (atividade de caixa de correio)|
|TabType| O tipo de guia adicionado, removido ou atualizado em uma equipe. Os valores possíveis para esta propriedade são:  <br/><br/> **PIN do Excel** -uma guia do Excel.  <br/> **Ramal** : todos os aplicativos de terceiros e de terceiros; como agenda de classe, VSTS e formulários.  <br/> **Observações** -guia do OneNote.  <br/> **Pdfpin** -uma guia PDF.  <br/> **Powerbi** -uma guia powerbi.  <br/> **Powerpointpin** -uma guia do PowerPoint.  <br/> **Sharepointfiles** -uma guia do SharePoint.  <br/> **Página da Web** -uma guia site fixo.  <br/> **Wiki-guia** -uma guia wiki.  <br/> **Wordpin** -uma guia do Word.|Microsoft Teams|
|Target|O usuário em que a ação (identificado na propriedade **Operation** ) foi executada em. Por exemplo, se um usuário convidado for adicionado ao SharePoint ou a uma equipe da Microsoft, esse usuário será listado nessa propriedade.|Azure Active Directory|
|TeamGuid|A ID de uma equipe no Microsoft Teams.|Microsoft Teams|
|TeamName|O nome de uma equipe no Microsoft Teams.|Microsoft Teams|
|UserAgent|Informações sobre o navegador do usuário. Essas informações são fornecidas pelo navegador.|SharePoint|
|UserDomain|Informações de identidade sobre a organização de locatário do usuário (ator) que executou a ação.|Azure Active Directory|
|UserID|O usuário que executou a ação (especificada na propriedade **Operation** ) que resultou no registro que está sendo registrado. Observe que os registros da atividade realizada por contas do sistema (como o Sharepoint\sistema ou o NT AUTHORITY\SYSTEM) também estão incluídos no log de auditoria.|Todos|
|UserKey|Uma ID alternativa para o usuário identificado na propriedade **userid** . Por exemplo, essa propriedade é preenchida com a identificação exclusiva do Passport (PUID) para eventos executados por usuários no SharePoint. Essa propriedade também pode especificar o mesmo valor que a propriedade **userid** de eventos que ocorrem em outros serviços e eventos executados por contas do sistema.|Todos|
|UserSharedWith|O usuário com o qual um recurso foi compartilhado. Essa propriedade será incluída se o valor da propriedade **Operation** for **sharingset**. Este usuário também está listado na coluna **compartilhado com** no relatório.|SharePoint|
|UserType|O tipo de usuário que executou a operação. Os valores a seguir indicam o tipo de usuário. <br/> <br/> **0** -um usuário regular. <br/>**2** -um administrador na sua organização do Office 365. <sup>1</sup> <br/>**3** -um administrador de datacenter da Microsoft ou uma conta de sistema de datacenter. <br/>**4** -uma conta do sistema. <br/>**5** -um aplicativo. <br/>**6** -entidade de serviço.<br/>**7** -uma política personalizada.<br/>**8** -uma política do sistema.|Todos|
|Versão|Indica o número da versão da atividade (identificado pela propriedade **Operation** ) registrada.|Todos|
|Carga de trabalho|O serviço do Office 365 em que a atividade ocorreu. Os valores possíveis para esta propriedade são:  <br/> <br/>**SharePoint<br/>onedrive<br/>Exchange<br/>AzureActiveDirectory<br/>DataCenterSecurity<br/>Compliance<br/>Sway<br/>Skype for Business<br/>SecurityComplianceCenter<br/>PowerBI<br/>CRM<br/>Yammer<br/>MicrosoftTeams<br/>ThreatIntelligence<br/>MicrosoftFlow<br/>MicrosoftStream<br/>DlpSharePointClassificationData<br/>Project<br/>PowerApps<br/>Workplace Analytics**|Todos|
||||

> [!NOTE]
><sup>1</sup> para eventos relacionados ao Azure Active Directory, o valor de um administrador não é usado em um registro de auditoria. Os registros de auditoria para atividades realizadas por administradores indicarão que um usuário regular (por exemplo, **UserType: 0**) realizou a atividade. A propriedade **userid** identificará a pessoa (usuário regular ou administrador) que realizou a atividade.<br/>


As propriedades descritas acima também são exibidas quando você clica em **mais informações** ao exibir os detalhes de um evento específico. 
  
![Clique em mais informações para exibir as propriedades detalhadas do registro de eventos do log de auditoria](media/6df582ae-d339-4735-b1a6-80914fb77a08.png)
  
