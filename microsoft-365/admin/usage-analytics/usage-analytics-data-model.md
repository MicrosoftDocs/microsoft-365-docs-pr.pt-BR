---
title: Modelo de dados de análise de uso do Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 08c5307c-4a6b-4761-8410-a6c96725760f
description: 'Saiba como a análise de uso se conecta a uma API e fornece tendências mensais de uso de vários serviços da Microsoft 365.  '
ms.openlocfilehash: 6b0b005e6e07e52731a84490a6df7c9ead614321
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402041"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Modelo de dados de análise de uso do Microsoft 365

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Dados das tabelas de análise de uso do Microsoft 365

A análise de uso do Microsoft 365 conecta-se a uma API que expõe um modelo de dados multidimensionais. As APIs estão em versão prévia e podem ser acessadas em `https://reports.office.com/pbi/v1.0/\<tenantid\>` (substitua o \<tenant id\> pelo GUID do locatário). 
  
> [!NOTE]
> Para obter mais informações, consulte [Working with microsoft 365 Usage reports in Microsoft Graph](https://go.microsoft.com/fwlink/p/?linkid=864336). 
  
Esta API fornece informações sobre a tendência mensal de uso dos vários serviços do Microsoft 365. Para saber exatamente quais são os dados retornados pela API, confira a tabela na seção a seguir.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Tabelas de dados retornadas pela API de relatórios do Microsoft 365

|**Nome da tabela**|**Informações na tabela**|**Intervalo de datas**|
|:-----|:-----|:-----|
|Uso de Produtos do Locatário  <br/> |Contém os totais mensais de usuários habilitados e ativos, usuários retidos mensalmente, usuários iniciantes e usuários ativos cumulativos.  <br/> |Contém dados agregados mensalmente por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Atividade de Produtos do Locatário  <br/> |Contém os totais mensais de atividade e a contagem de usuários ativos para várias atividades nos produtos.  <br/> Veja [definição de usuário ativo](active-user-in-usage-reports.md) para saber mais sobre as atividades em um produto que são retornadas nesta tabela de dados.  <br/> |Contém dados agregados mensalmente por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Licenças do Office do Locatário  <br/> |Contém dados sobre o número de assinaturas do Microsoft Office atribuídas aos usuários  <br/> |Contém os dados de estado de fim de mês por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Uso da Caixa de Correio do Locatário  <br/> |Contém dados sobre a caixa de correio do usuário, em termos de contagem total da caixa de correio e como o armazenamento é usado.  <br/> |Contém os dados de estado de fim de mês por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Uso do Cliente do Locatário  <br/> |Contém os dados sobre o número de usuários que usam ativamente clientes/dispositivos específicos para conectarem-se ao Exchange Online, ao Skype for Business e ao Yammer.  <br/> |Contém dados agregados mensalmente por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Uso Online do SharePoint do Locatário  <br/> |Contém dados sobre os sites do SharePoint, incluindo sites de Equipe ou de Grupo, como o número total de sites, o número de documentos no site, o número de arquivos por tipo de atividade e armazenamento usado.  <br/> |Contém os dados de estado de fim de mês por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Uso do OneDrive for Business do Locatário  <br/> |Contém dados sobre as contas do OneDrive, como o número de contas, o número de documentos em OneDrives, o armazenamento usado, a contagem de arquivos por tipo de atividade.  <br/> |Contém os dados de estado de fim de mês por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Uso de grupos do Microsoft 365  <br/> |Contém dados sobre o uso de grupos do Microsoft 365, incluindo a caixa de correio, o SharePoint e o Yammer.  <br/> |Contém os dados de estado de fim de mês por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Ativação do Office do Locatário  <br/> |Contém dados sobre o número de ativações de assinatura do Office, contagem de ativação por dispositivo (Android/iOS/Mac/PC), ativações por plano de serviço, por exemplo, Microsoft 365 Apps for Enterprise, Visio, Project.  <br/> |Contém os dados de estado de fim de mês por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Estado do Usuário  <br/> |Contém metadados sobre os usuários, incluindo o nome de exibição do usuário, os produtos atribuídos, o local, o departamento, o título, a empresa. Esses dados referem-se aos usuários que receberam uma licença durante o último mês completo. Todos os usuários são exclusivamente representados por uma id de usuário.  <br/> |Esses dados referem-se aos usuários que tinham uma licença atribuída durante o último mês completo.  <br/> |
|Atividade do Usuário  <br/> |Contém informações de nível de cada usuário sobre as atividades executadas por usuários licenciados.  <br/> Veja [definição de usuário ativo](active-user-in-usage-reports.md) para saber mais sobre as atividades em um produto que são retornadas nesta tabela de dados.  <br/> |Esses dados referem-se aos usuários que executaram uma atividade em qualquer um dos serviços durante o último mês completo.  <br/> |
   
Expanda as seções a seguir para ver as informações detalhadas de cada tabela de dados.
  
### <a name="data-table---user-state"></a>Tabela de dados - Estado do Usuário

Essa tabela fornece detalhes ao nível de usuário sobre todos os usuários que receberam uma licença durante o último mês completo. Ele traz dados do Azure Active Directory.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|UserId  <br/> |Id de usuário exclusiva que representa um usuário e permite o ingresso com outras tabelas de dados dentro do conjunto de dados.  <br/> |
|Período de tempo  <br/> |Valor do mês para o qual esta tabela tem dados.  <br/> |
|UPN  <br/> |Nome UPN, identifica exclusivamente o usuário para que possa ingressar com outras fontes de dados externas.  <br/> |
|DisplayName  <br/> |Nome de exibição do usuário.  <br/> |
|IDType  <br/> |O tipo de ID é definido como 1 se o usuário for um usuário do Yammer que se conecta usando a ID do Yammer ou 0 se ele se conectar ao Yammer usando sua ID do Microsoft 365.  <br/> O valor é 1 para representar que os usuários se conectam ao Yammer com a ID do Yammer e não com a ID do Microsoft 365  <br/> |
|HasLicenseEXO  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o Exchange.  <br/> |
|HasLicenseODB  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o OneDrive for Business.  <br/> |
|HasLicenseSPO  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o SharePoint Online.  <br/> |
|HasLicenseYAM  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o Yammer.  <br/> |
|HasLicenseSFB  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o Skype For Business.  <br/> |
|HasLicenseTeams  <br/> |Defina como true se o usuário receber uma licença e habilitar o uso do Microsoft Teams.  <br/> |
|Empresa  <br/> |Os dados da empresa representados no Azure Active Directory para este usuário.  <br/> |
|Departamento  <br/> |Os dados do departamento representados no Azure Active Directory para este usuário.  <br/> |
|LocationCity  <br/> |Os dados da cidade representados no Azure Active Directory para este usuário.  <br/> |
|LocationCountry  <br/> |Os dados do país representados no Azure Active Directory para este usuário.  <br/> |
|Locationstate  <br/> |Os dados do estado representados no Azure Active Directory para este usuário.  <br/> |
|LocationOffice  <br/> |Escritório do usuário.  <br/> |
|Título  <br/> |Os dados do título representados no Azure Active Directory para este usuário.  <br/> |
|Excluído  <br/> |True se o usuário foi excluído da Microsoft 365 no último mês completo.  <br/> |
|DeletedDate  <br/> |Data em que o usuário foi excluído do Microsoft 365.  <br/> |
|YAM_State  <br/> |Estados do usuário no sistema do Yammer, pode ser ativo, excluído ou suspenso.  <br/> |
|YAM_ActivationDate  <br/> |Data em que o usuário inseriu o estado de ativo no Yammer.  <br/> |
|YAM_DeletionDate  <br/> |Data em que o usuário inseriu o estado de excluído no Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |Data em que o usuário inseriu o estado de suspenso no Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Tabela de dados - Atividades do Usuário

Essa tabela contém dados sobre cada usuário que tinha uma atividade em qualquer um dos serviços no mês anterior.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|UserID  <br/> |Id de usuário exclusiva que representa um usuário e permite o ingresso com outras tabelas de dados dentro do conjunto de dados.  <br/> |
|IDType  <br/> |O tipo de ID é definido como 1 se o usuário for um usuário do Yammer que se conecta usando a ID do Yammer ou 0 se ele se conectar ao Yammer usando sua ID do Microsoft 365.  <br/> O valor é 1 para representar que os usuários se conectam ao Yammer com a ID do Yammer e não com a ID do Microsoft 365  <br/> |
|Período de tempo  <br/> |Valor do mês para o qual esta tabela representa dados.  <br/> |
|EXO_EmailSent  <br/> |Número de emails enviados.  <br/> |
|EXO_EmailReceived  <br/> |Número de emails recebidos.  <br/> |
|EXO_EmailRead  <br/> |Número de atividades de leitura de email do usuário, pode ser a leitura múltipla de um email já lido ou um email recebido anteriormente.  <br/> |
|EXO_AppointmentCreated  <br/> |Número de compromissos criados.  <br/> |
|EXO_MeetingAccepted  <br/> |Número de reuniões aceitas.  <br/> |
|EXO_MeetingCancelled  <br/> |Número de reuniões canceladas.  <br/> |
|EXO_MeetingDeclined  <br/> |Número de reuniões recusadas.  <br/> |
|EXO_MeetingSent  <br/> |Número de reuniões enviadas.  <br/> |
|ODB_FileViewedModified  <br/> |Número de arquivos com os quais este usuário interagiu em qualquer OneDrive for Business (por exemplo, criado, atualizado, excluído, visualizado ou baixado).  <br/> |
|ODB_FileSynched  <br/> |Número de arquivos sincronizados por este usuário em qualquer OneDrive for Business.  <br/> |
|ODB_FileSharedInternally  <br/> |Número de arquivos que este usuário compartilhou internamente de qualquer OneDrive for Business ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|ODB_FileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer OneDrive for Business.  <br/> |
|ODB_AccessByOwner  <br/> |Número de arquivos com os quais o usuário interagiu que residem no seu próprio OneDrive for Business.  <br/> |
|ODB_AccessOthers  <br/> |Número de arquivos com os quais o usuário interagiu que residem no OneDrive for Business do usuário.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Número de arquivos com os quais este usuário interagiu em qualquer site do grupo.  <br/> |
|SPO_GroupFileSynched  <br/> |Número de arquivos que este usuário sincronizou em qualquer site do grupo.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |A contagem de arquivos que foram compartilhados com usuários dentro da organização ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer site do grupo.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site do grupo do usuário.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site do grupo de outro usuário.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Número de arquivos com os quais este usuário interagiu em qualquer outro site.  <br/> |
|SPO_OtherFileSynched  <br/> |Número de arquivos que este usuário sincronizou de qualquer outro site.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Número de arquivos que este usuário compartilhou internamente de qualquer outro site ou com usuários dentro de grupos (que podem incluir usuários externos). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer outro site.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Número de sites com os quais o usuário interagiu que residem em outro site que possuem.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Número de sites com os quais o usuário interagiu que residem em outro site proprietário de outro usuário.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Número de arquivos com os quais este usuário interagiu em qualquer site da equipe.  <br/> |
|SPO_TeamFileSynched  <br/> |Número de arquivos que este usuário sincronizou de qualquer site de equipe.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Número de arquivos que este usuário compartilhou internamente de qualquer site de equipe ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer site de equipe.  <br/> |
|SPO_TeamAccessByOwner  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site de equipe do usuário.  <br/> |
|SPO_TeamAccessByOthers  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site de equipe de outro usuário.  <br/> |
|Teams_ChatMessages  <br/> |Número de mensagens de chat enviadas.  <br/> |
|Teams_ChannelMessage  <br/> |Número de mensagens postadas nos canais.  <br/> |
|Teams_CallParticipate  <br/> |Número de chamadas que o usuário participou.  <br/> |
|Teams_MeetingParticipate  <br/> |Número de reuniões que o usuário ingressou.  <br/> |
|Teams_HasOtherAction  <br/> |Valor booliano se o usuário realizou outras ações no Microsoft Teams.  <br/> |
|YAM_MessagePost  <br/> |Número da mensagem do Yammer que este usuário postou.  <br/> |
|YAM_MessageLiked  <br/> |Número da mensagem do Yammer que este usuário curtiu.  <br/> |
|YAM_MessageRead  <br/> |Número da mensagem do Yammer que este usuário leu.  <br/> |
|SFB_P2PSummary  <br/> |Número de sessões de ponto a ponto das quais este usuário participou.  <br/> |
|SFB_ConfOrgSummary  <br/> |Número de sessões de conferência organizadas por este usuário.  <br/> |
|SFB_ConfPartSummary  <br/> |Número de sessões de conferência das quais este usuário participou.  <br/> |
   
### <a name="data-table---tenant-product-usage"></a>Tabela de dados - Uso de Produto do Locatário

Esta tabela fornece dados de adoção mês a mês em termos de habilitação, ativos, retorno e usuários da primeira vez para cada produto no Microsoft 365. O valor da Microsoft 365 representa o uso ativo em qualquer um dos produtos.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Produto  <br/> |Nome dos produtos para os quais as informações de uso são resumidas. O valor da Microsoft 365 na coluna produto representa a atividade em qualquer um dos produtos  <br/> |
|Período de tempo  <br/> |Valor do mês. Haverá uma linha por produto por mês nos últimos 12 meses, incluindo o mês corrente parcial.  <br/> |
|EnabledUsers  <br/> |Número de usuários habilitados para usar o produto para o valor do prazo. Se um usuário tiver sido habilitado para parte do mês, eles ainda são contados.  <br/> |
|ActiveUsers  <br/> |Número de usuários que executaram uma atividade intencional no produto para o valor do período de tempo.  <br/> Um usuário é contado como ativo para um produto em um mês específico se ele tiver executado uma das principais atividades no produto. As principais atividades estão disponíveis na tabela **Atividade de produtos do locatário**.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuários que estão habilitados para usar um produto e que usaram o produto até o mês-prazo pelo menos uma vez desde o início da coleta de dados no novo sistema de uso.  <br/> |
|MoMReturningUsers  <br/> |Número de usuários que estão ativos no mês-prazo e que também estavam ativos no mês anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuários que ficaram ativos no prazo pela primeira vez desde a coleta de dados, no novo sistema de uso.  <br/> Um usuário é contado como usuário iniciante em um mês específico se detectarmos sua atividade pela primeira vez desde o início do conjunto de dados neste novo sistema de relatórios. Uma vez contado como o usuário pela primeira vez, mesmo que esse usuário tenha uma grande diferença em suas atividades, elas nunca serão contadas novamente como o usuário da primeira vez  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Tabela de dados - Atividade de Produto do Locatário

Essa tabela fornece os totais mensais de atividade e a contagem de usuários ativos para várias atividades nos produtos.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Período de tempo  <br/> |Valor do mês. Haverá uma linha por produto por mês nos últimos 12 meses, incluindo o mês corrente parcial.  <br/> |
|Produto  <br/> |Nome do produto no Microsoft 365 para o qual os dados de uso estão disponíveis.  <br/> |
|Atividade  <br/> |Nome da atividade em um produto que é usado para demonstrar uso ativo de produto.  <br/> |
|ActivityCount  <br/> |Esse é o número total de ações contadas para cada atividade realizada dentro do produto em todos os usuários ativos.  <br/> **Observação:** Para as atividades do SharePoint Online e do OneDrive for Business, esse valor representa o número de documentos distintos com os quais os usuários interagem.  <br/> |
|ActiveUserCount  <br/> |Número de usuários que executaram a atividade dentro do produto.  <br/> |
|TotalDurationInMinute  <br/> |O valor da duração em minutos entre todos os usuários ativos que usaram a sessão de áudio ou de vídeo em uma atividade aplicável do Skype for Business.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-mailbox-usage"></a>Tabela de dados - Uso da Caixa de Correio do Locatário

Essa tabela consiste em dados de resumo em todos os usuários licenciados do Exchange Online que têm caixas de correio do usuário. Ela contém o estado de fim do mês em todas as caixas de correio de usuário. Os dados nessa tabela não são aditivos em vários meses. Os dados do último mês nesta tabela representam o estado mais recente.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|TotalMailboxes  <br/> |Número de caixas de correio de usuário para assinatura do Microsoft 365.  <br/> |
|IssueWarningQuota  <br/> |Cota total para a emissão de um aviso em todas as caixas de correio de usuários.  <br/> |
|ProhibitSendQuota  <br/> |Cota total para proibir envio em todas as caixas de correio de usuário.  <br/> |
|ProhibitSendReceiveQuota  <br/> |Cota total para cota de proibir Envio/Recebimento em todas as caixas de correio de usuário.  <br/> |
|TotalItemBytes  <br/> |Quantidade de armazenamento usado em todas as caixas de correio de usuário em bytes.  <br/> |
|MailboxesNoWarning  <br/> |Número de caixas de correio de usuário que estava abaixo do limite de aviso de armazenamento.  <br/> |
|MailboxesIssueWarning  <br/> |Número de caixas de correio de usuário que emitiram um aviso relativo à cota de armazenamento.  <br/> |
|MailboxesExceedSendQuota  <br/> |Número de caixas de correio de usuário que excederam a cota de envio.  <br/> |
|MailboxesExceedSendReceiveQuota  <br/> |Número de caixas de correio de usuário que excederam a cota de envio/recebimento.  <br/> |
|DeletedMailboxes  <br/> |Número de caixas de correio de usuário excluídas no prazo.  <br/> |
|Período de tempo  <br/> |Valor do mês.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-client-usage"></a>Tabela de dados - Uso do Cliente do Locatário

Essa tabela fornece dados de resumo mensal sobre os clientes que os usuários estão usando para conectarem-se ao Exchange Online, ao Skype for Business e ao Yammer. Esta tabela ainda não tem dados de uso de cliente para o SharePoint Online e o OneDrive for Business.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Produto  <br/> |Nome do produto no Microsoft 365 para o qual os dados de uso do cliente estão disponíveis.  <br/> |
|ClientId  <br/> |Nome de cada dispositivo usado para conectar-se ao produto.  <br/> |
|ContadoUsuário  <br/> |Número de usuários que usaram cada um dos clientes para cada produto.  <br/> |
|Período de tempo  <br/> |Valor do mês  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Tabela de dados - Uso do SharePoint Online do Locatário

Essa tabela consiste em dados de resumo mensal sobre o uso ou a atividade de sites do SharePoint Online. Isso só abrange os sites de equipe e os sites de grupo. O estado de fim do mês de sites do SharePoint Online é representado nesta coluna, por exemplo, se um usuário tiver criado 5 documentos usado 10 MB para o armazenamento total e, em seguida, excluído alguns arquivos excluídos e adicionado mais arquivos para que ao fim do mês o estado para os arquivos seja 7 total que usa 5 MB de armazenamento, o valor representado nesta tabela é o estado de fim de mês. Essa tabela está oculta para evitar a dupla contagem das agregações e é usada como uma fonte para a criação de duas tabelas de referência.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Sitetype  <br/> |Valor de tipo de site (qualquer/equipe/grupo) (qualquer representa qualquer um desses 2 tipos de site).  <br/> |
|TotalSites  <br/> |Número de sites existentes ao fim do prazo.  <br/> |
|DocumentCount  <br/> |O número total de documentos existentes no site ao fim do prazo.  <br/> |
|Diplaned  <br/> |Armazenamento total usado somado em todos os sites ao fim do prazo.  <br/> |
|Activity  <br/> |Número de sites que gravaram os vários tipos de atividade do arquivo (qualquer/arquivos ativos/arquivos compartilhados EXT/INT/arquivos sincronizados).  <br/> Qualquer representa qualquer atividade de arquivo realizada.  <br/> |
|SitesWithOwnerActivities  <br/> |Número de sites ativos, em que o proprietário do site executou uma determinada atividade de arquivo nos próprios sites.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Número de sites ativos somados para o mês, onde os usuários, que não o proprietário do site, realizaram uma determinada atividade de arquivo nos sites.  <br/> |
|ActivityTotalSites  <br/> |Número de sites que registraram qualquer atividade durante o prazo. Se um site que teve atividade anterior no prazo, e foi excluído até o final do prazo, ela ainda seria contado no total do site ativo para esse prazo.  <br/> |
|Período de tempo  <br/> |Esta coluna tem o valor de data. Usada como relação Muitos para um para a tabela Calendário.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Tabela de dados-uso do OneDrive do locatário

Essa tabela fornece dados sobre as contas do OneDrive, como o número de contas, o número de documentos em contas do OneDrive, o armazenamento usado, a contagem de arquivos por tipo de atividade. O estado de fim do mês para contas do OneDrive for Business é representado nesta tabela. Por exemplo, se um usuário criar 5 documentos que ocupam 10 MB de armazenamento e, em seguida, excluir alguns arquivos e adicionar mais alguns, de modo que ao fim do mês ele tenha 7 arquivos que ocupam 5 MB de armazenamento, o fim do valor do mês é representado nesta tabela no fim do mês.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Sitetype  <br/> |O valor é "OneDrive".  <br/> |
|TotalSites  <br/> |Número de contas do OneDrive for Business existentes ao fim do prazo.  <br/> |
|DocumentCount  <br/> |Número total de documentos existentes em todas as contas do OneDrive for Business ao fim do prazo  <br/> |
|Diplaned  <br/> |Armazenamento total usado somado em todas as contas do OneDrive ao fim do prazo.  <br/> |
|Activity  <br/> |Número de contas que gravaram os vários tipos de atividade do arquivo (qualquer/arquivos ativos/arquivos compartilhados EXT/INT/arquivos sincronizados).  <br/> Qualquer representa qualquer atividade de arquivo realizada  <br/> |
|SitesWithOwnerActivities  <br/> |Número de contas ativas do OneDrive for Business, onde o proprietário da conta executou uma determinada atividade de arquivo em sua própria conta.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Número de contas do OneDrive for Business em que a atividade do arquivo foi realizada por usuários que não o proprietário da conta.  <br/> |
|ActivityTotalSites  <br/> |Número de contas do OneDrive for Business que registraram qualquer atividade durante o prazo. Se uma conta do OneDrive for Business teve atividade anterior no prazo, e foi excluída até o final do prazo, ela ainda seria contada nas contas ativas do OneDrive for Business para esse prazo.  <br/> |
|Período de tempo  <br/> |Esta coluna tem o valor de data. Usada como relação Muitos para um para a tabela Calendário.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Tabela de dados-uso de grupos do Microsoft 365

Esta tabela fornece dados sobre como os grupos do Microsoft 365 são usados em toda a organização.
  
****

|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Prazo  <br/> |Valor do mês. Haverá uma linha por produto por mês nos últimos 12 meses, incluindo o mês corrente parcial.  <br/> |
|GroupType  <br/> |Tipo de grupo (privado/público/any).  <br/> |
|TotalGroups  <br/> |Número de grupos em cada tipo de grupo.  <br/> |
|ActiveGroups  <br/> |Número de grupos ativos.  <br/> |
|MBX_TotalGroups  <br/> |Número de grupos de caixa de correio.  <br/> |
|MBX_ActiveGroups  <br/> |Número de grupos de caixa de correio ativos.  <br/> |
|MBX_TotalActivities  <br/> |Número de atividades de caixa de correio.  <br/> |
|MBX_TotalItems  <br/> |Número de itens de caixa de correio.  <br/> |
|MBX_StorageUsed  <br/> |Quantidade de armazenamento de caixa de correio usada.  <br/> |
|SPO_TotalGroups  <br/> |Número de grupos do SharePoint.  <br/> |
|SPO_ActiveGroups  <br/> |Número de grupos do SharePoint ativos.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Número de grupos do SharePoint que têm atividades acessadas por arquivo.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Número de grupos do SharePoint com atividades sincronizadas de arquivo.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Número de grupos do SharePoint que têm atividades compartilhadas internamente ou com grupos (que podem incluir usuários externos).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Número de grupos do SharePoint que têm atividades compartilhadas externas.  <br/> |
|SPO_TotalActivities  <br/> |Número de atividades do SharePoint.  <br/> |
|SPO_FileAccessedActivities  <br/> |Número de atividades acessadas por arquivo do SharePoint.  <br/> |
|SPO_FileSyncedActivities  <br/> |Número de atividades sincronizadas de arquivos do SharePoint.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Número de atividades compartilhadas de arquivos do SharePoint internamente ou com grupos (que podem incluir membros externos).  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Número de atividades externas compartilhadas por arquivo do SharePoint.  <br/> |
|SPO_TotalFiles  <br/> |Número de arquivos do SharePoint.  <br/> |
|SPO_ActiveFiles  <br/> |Número de arquivos do SharePoint ativos.  <br/> |
|SPO_StorageUsed  <br/> |Quantidade de armazenamento do SharePoint usada.  <br/> |
|YAM_TotalGroups  <br/> |Número de grupos do Yammer.  <br/> |
|YAM_ActiveGroups  <br/> |Número de grupos ativos do Yammer.  <br/> |
|YAM_LikedActiveGroups  <br/> |Número de grupos do Yammer que têm atividades semelhantes.  <br/> |
|YAM_PostedActiveGroups  <br/> |Número de grupos do Yammer que têm atividades de postagem.  <br/> |
|YAM_ReadActiveGroups  <br/> |Número de grupos do Yammer que têm atividades de leitura.  <br/> |
|YAM_TotalActivities  <br/> |Número de atividades do Yammer.  <br/> |
|YAM_LikedActivities  <br/> |Número do Yammer como atividades.  <br/> |
|YAM_PostedActivties  <br/> |Número de atividades de postagem do Yammer.  <br/> |
|YAM_ReadActivites  <br/> |Número de atividades de leitura do Yammer.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>Tabela de dados - Ativação do Office do Locatário

A tabela fornece dados sobre o número de ativações de assinatura do Office nos planos de serviço, por exemplo, Microsoft 365 Apps for Enterprises, Visio, Project. Ela também fornece dados sobre o número de ativações por dispositivo (Android/iOS/Mac/PC).
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Onplanname  <br/> |Lista dos valores de nome do plano de serviço e contagens de ativações por dispositivo, conforme ilustrado nas colunas abaixo.  <br/> |
|TotalEnabled  <br/> |Número de usuários habilitados por nome do plano de serviço até o final do prazo.  <br/> |
|TotalActivatedUsers  <br/> |Número de usuários que ativaram cada plano de serviço até o final do prazo.  <br/> |
|AndroidCount  <br/> |Número de ativações por plano de serviço para dispositivo Android até o final do prazo.  <br/> |
|iOSCount  <br/> |Número de ativações por plano de serviço para dispositivo iOS até o fim do prazo.  <br/> |
|MacCount  <br/> |Número de ativações por plano de serviço para dispositivo MAC até o fim do prazo.  <br/> |
|PcCount  <br/> |Número de ativações por plano de serviço para dispositivo PC até o fim do prazo.  <br/> |
|WinRtCount  <br/> |Número de ativações por plano de serviço para dispositivo Windows Mobile até o fim do prazo.  <br/> |
|Período de tempo  <br/> |Esta coluna tem o valor de data. Usada como relação Muitos para um para a tabela Calendário.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   

