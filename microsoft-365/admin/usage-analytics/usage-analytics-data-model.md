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
description: 'Saiba como a análise de uso se conecta a uma API e fornece tendência mensal de uso de vários serviços do Microsoft 365.  '
ms.openlocfilehash: d7b3e7e9467a57f913f069c48249e82b5958aabb
ms.sourcegitcommit: 039205fdaaa2a233ff7e95cd91bace474b84b68c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611443"
---
# <a name="microsoft-365-usage-analytics-data-model"></a>Modelo de dados de análise de uso do Microsoft 365

## <a name="data-for-the-microsoft-365-usage-analytics-tables"></a>Dados para as tabelas de análise de uso do Microsoft 365

A análise de uso do Microsoft 365 conecta-se a uma API que expõe um modelo de dados multidimensionais. As APIs estão em visualização e podem ser acessadas `https://reports.office.com/pbi/v1.0/\<tenantid\>` em (substitua o \<tenant id\> GUID do locatário). 
  
> [!NOTE]
> Para saber mais, confira [Trabalhar com relatórios de uso do Microsoft 365 no Microsoft Graph.](https://go.microsoft.com/fwlink/p/?linkid=864336) 
  
Essa API fornece informações sobre a tendência mensal de uso dos vários serviços do Microsoft 365. Para saber exatamente quais são os dados retornados pela API, confira a tabela na seção a seguir.
  
## <a name="data-tables-returned-by-the-microsoft-365-reporting-api"></a>Tabelas de dados retornadas pela API de Relatórios do Microsoft 365

|**Nome da tabela**|**Informações na tabela**|**Intervalo de datas**|
|:-----|:-----|:-----|
|Uso de Produtos do Locatário  <br/> |Contém totais mensais de usuários habilitados, ativos, usuários retidos mês a mês, usuários de primeira vez e usuários ativos cumulativos.  <br/> |Contém dados agregados mensalmente por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Atividade de Produtos do Locatário  <br/> |Contém os totais mensais de atividades e a contagem de usuários ativos para várias atividades dentro dos produtos.  <br/> Veja [definição de usuário ativo](active-user-in-usage-reports.md) para saber mais sobre as atividades em um produto que são retornadas nesta tabela de dados.  <br/> |Contém dados agregados mensalmente por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Licenças do Office do Locatário  <br/> |Contém dados sobre o número de assinaturas do Microsoft Office atribuídas aos usuários  <br/> |Contém dados de estado de fim do mês por um período de 12 meses sem fim, incluindo o mês parcial atual.  <br/> |
|Uso da Caixa de Correio do Locatário  <br/> |Contém dados sobre a caixa de correio do usuário, para a contagem total de caixas de correio e como o armazenamento é usado.  <br/> |Contém dados de estado de fim do mês por um período de 12 meses sem fim, incluindo o mês parcial atual.  <br/> |
|Uso do Cliente do Locatário  <br/> |Contém os dados sobre o número de usuários que usam ativamente clientes/dispositivos específicos para conectarem-se ao Exchange Online, ao Skype for Business e ao Yammer.  <br/> |Contém dados agregados mensalmente por um período de 12 meses sem interrupção, incluindo o mês parcial corrente.  <br/> |
|Uso Online do SharePoint do Locatário  <br/> |Contém dados sobre os sites do SharePoint, incluindo sites de Equipe ou de Grupo, como o número total de sites, o número de documentos no site, o número de arquivos por tipo de atividade e armazenamento usado.  <br/> |Contém dados de estado de fim do mês por um período de 12 meses sem fim, incluindo o mês parcial atual.  <br/> |
|Uso do OneDrive for Business do Locatário  <br/> |Contém dados sobre as contas do OneDrive, como o número de contas, o número de documentos em OneDrives, o armazenamento usado, a contagem de arquivos por tipo de atividade.  <br/> |Contém dados de estado de fim do mês por um período de 12 meses sem fim, incluindo o mês parcial atual.  <br/> |
|Uso de grupos do Microsoft 365 para locatários  <br/> |Contém dados sobre o uso de Grupos do Microsoft 365, incluindo Caixa de Correio, SharePoint e Yammer.  <br/> |Contém dados de estado de fim do mês por um período de 12 meses sem fim, incluindo o mês parcial atual.  <br/> |
|Ativação do Office do Locatário  <br/> |Contém dados sobre o número de ativações de assinatura do Office, contagem de ativação por dispositivo (Android/iOS/Mac/PC), ativações por plano de serviço, por exemplo, Aplicativos do Microsoft 365 para empresas, Visio, Project.  <br/> |Contém dados de estado de fim do mês por um período de 12 meses sem fim, incluindo o mês parcial atual.  <br/> |
|Estado do Usuário  <br/> |Contém metadados sobre os usuários, incluindo o nome de exibição do usuário, os produtos atribuídos, o local, o departamento, o título, a empresa. Esses dados são sobre os usuários que foram atribuídos com uma licença durante o último mês completo. Cada usuário é representado exclusivamente por uma ID de usuário.  <br/> |Esses dados referem-se aos usuários que tinham uma licença atribuída durante o último mês completo.  <br/> |
|Atividade do Usuário  <br/> |Contém informações de nível de cada usuário sobre as atividades executadas por usuários licenciados.  <br/> Veja [definição de usuário ativo](active-user-in-usage-reports.md) para saber mais sobre as atividades em um produto que são retornadas nesta tabela de dados.  <br/> |Esses dados referem-se aos usuários que executaram uma atividade em qualquer um dos serviços durante o último mês completo.  <br/> |
   
Expanda as seções a seguir para ver as informações detalhadas de cada tabela de dados.
  
### <a name="data-table---user-state"></a>Tabela de dados - Estado do Usuário

Esta tabela fornece detalhes de nível de usuário para todos os usuários que têm uma licença atribuída a eles durante o último mês completo. Ele traz dados do Azure Active Directory.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|UserId  <br/> |ID de usuário exclusiva que representa um usuário e permite a junção com outras tabelas de dados dentro do conjunto de dados.  <br/> |
|Período de tempo  <br/> |Valor do mês para o qual esta tabela tem dados.  <br/> |
|UPN  <br/> |Nome UPN, identifica exclusivamente o usuário para que possa ingressar com outras fontes de dados externas.  <br/> |
|DisplayName  <br/> |Nome de exibição do usuário.  <br/> |
|IDType  <br/> |O tipo de ID é definido como 1 se o usuário for um usuário do Yammer que se conecta usando a ID do Yammer ou 0 se ele se conectar ao Yammer usando sua ID do Microsoft 365.  <br/> O valor é 1 para representar que esse usuário se conecta ao Yammer com sua ID do Yammer e não com a ID do Microsoft 365  <br/> |
|HasLicenseEXO  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o Exchange.  <br/> |
|HasLicenseODB  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o OneDrive for Business.  <br/> |
|HasLicenseSPO  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o SharePoint Online.  <br/> |
|HasLicenseYAM  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o Yammer.  <br/> |
|HasLicenseSFB  <br/> |Defina como verdadeiro se o usuário tiver recebido uma licença e tiver sido habilitado para usar o Skype For Business.  <br/> |
|HasLicenseTeams  <br/> |De definida como true se o usuário tiver uma licença atribuída e habilitar o uso do Microsoft Teams.  <br/> |
|Empresa  <br/> |Os dados da empresa representados no Azure Active Directory para este usuário.  <br/> |
|Departamento  <br/> |Os dados do departamento representados no Azure Active Directory para este usuário.  <br/> |
|LocationCity  <br/> |Os dados da cidade representados no Azure Active Directory para este usuário.  <br/> |
|LocationCountry  <br/> |Os dados do país representados no Azure Active Directory para este usuário.  <br/> |
|LocationState  <br/> |Os dados do estado representados no Azure Active Directory para este usuário.  <br/> |
|LocationOffice  <br/> |Escritório do usuário.  <br/> |
|Título  <br/> |Os dados do título representados no Azure Active Directory para este usuário.  <br/> |
|Excluído  <br/> |True se o usuário tiver sido excluído do Microsoft 365 no último mês completo.  <br/> |
|DeletedDate  <br/> |Data em que o usuário foi excluído do Microsoft 365.  <br/> |
|YAM_State  <br/> |Estados do usuário no sistema do Yammer, podem ser ativos, excluídos ou suspensos.  <br/> |
|YAM_ActivationDate  <br/> |Data em que o usuário inseriu o estado de ativo no Yammer.  <br/> |
|YAM_DeletionDate  <br/> |Data em que o usuário inseriu o estado de excluído no Yammer.  <br/> |
|YAM_SuspensionDate  <br/> |Data em que o usuário inseriu o estado de suspenso no Yammer.  <br/> |
   
### <a name="data-table---user-activity"></a>Tabela de dados - Atividades do Usuário

Essa tabela contém dados sobre cada usuário que tinha uma atividade em qualquer um dos serviços no mês anterior.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|UserID  <br/> |ID de usuário exclusiva que representa um usuário e permite a junção com outras tabelas de dados dentro do conjunto de dados.  <br/> |
|IDType  <br/> |O tipo de ID é definido como 1 se o usuário for um usuário do Yammer que se conecta usando a ID do Yammer ou 0 se ele se conectar ao Yammer usando sua ID do Microsoft 365.  <br/> O valor é 1 para representar que esse usuário se conecta ao Yammer com sua ID do Yammer e não com a ID do Microsoft 365  <br/> |
|Período de tempo  <br/> |Valor do mês para o qual esta tabela representa dados.  <br/> |
|EXO_EmailSent  <br/> |Número de emails enviados.  <br/> |
|EXO_EmailReceived  <br/> |Número de emails recebidos.  <br/> |
|EXO_EmailRead  <br/> |Número de atividades de leitura de emails que o usuário realizou, pode ser várias vezes ler um email já lido ou um email recebido anteriormente.  <br/> |
|EXO_AppointmentCreated  <br/> |Número de compromissos criados.  <br/> |
|EXO_MeetingAccepted  <br/> |Número de reuniões aceitas.  <br/> |
|EXO_MeetingCancelled  <br/> |Número de reuniões canceladas.  <br/> |
|EXO_MeetingDeclined  <br/> |Número de reuniões recusadas.  <br/> |
|EXO_MeetingSent  <br/> |Número de reuniões enviadas.  <br/> |
|ODB_FileViewedModified  <br/> |Número de arquivos com os quais este usuário interagiu em qualquer OneDrive for Business (por exemplo, criado, atualizado, excluído, visualizado ou baixado).  <br/> |
|ODB_FileSynched  <br/> |Número de arquivos sincronizados por este usuário em qualquer OneDrive for Business.  <br/> |
|ODB_FileSharedInternally  <br/> |Número de arquivos que esse usuário compartilhou internamente de qualquer OneDrive for Business ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|ODB_FileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer OneDrive for Business.  <br/> |
|ODB_AccessByOwner  <br/> |Número de arquivos com os quais o usuário interagiu que residem no seu próprio OneDrive for Business.  <br/> |
|ODB_AccessOthers  <br/> |Número de arquivos com os quais o usuário interagiu que residem no OneDrive for Business do usuário.  <br/> |
|SPO_GroupFileViewedModified  <br/> |Número de arquivos com os quais este usuário interagiu em qualquer site do grupo.  <br/> |
|SPO_GroupFileSynched  <br/> |Número de arquivos que este usuário sincronizou em qualquer site do grupo.  <br/> |
|SPO_GroupFileSharedInternally  <br/> |A contagem de arquivos que foram compartilhados com usuários dentro da organização ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|SPO_GroupFileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer site do grupo.  <br/> |
|SPO_GroupAccessByOwner  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site do grupo do usuário.  <br/> |
|SPO_GroupAccessByOthers  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site do grupo de outro usuário.  <br/> |
|SPO_OtherFileViewedModified  <br/> |Número de arquivos com os quais esse usuário interagiu em qualquer outro site.  <br/> |
|SPO_OtherFileSynched  <br/> |Número de arquivos que este usuário sincronizou de qualquer outro site.  <br/> |
|SPO_OtherFileSharedInternally  <br/> |Número de arquivos que esse usuário compartilhou internamente de qualquer outro site ou com usuários dentro de grupos (que podem incluir usuários externos). <br/> |
|SPO_OtherFileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer outro site.  <br/> |
|SPO_OtherAccessedByOwner  <br/> |Número de sites com os que o usuário interagiu que residem em outro site de sua propriedade.  <br/> |
|SPO_OtherAccessedByOthers  <br/> |Número de sites com os que o usuário interagiu que residem em outro site que outro usuário possui.  <br/> |
|SPO_TeamFileViewedModified  <br/> |Número de arquivos com os quais este usuário interagiu em qualquer site da equipe.  <br/> |
|SPO_TeamFileSynched  <br/> |Número de arquivos que este usuário sincronizou de qualquer site de equipe.  <br/> |
|SPO_TeamFileSharedInternally  <br/> |Número de arquivos que esse usuário compartilhou internamente de qualquer site de equipe ou com usuários dentro de grupos (que podem incluir usuários externos).  <br/> |
|SPO_TeamFileSharedExternally  <br/> |Número de arquivos que este usuário compartilhou externamente de qualquer site de equipe.  <br/> |
|SPO_TeamAccessByOwner  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site de equipe do usuário.  <br/> |
|SPO_TeamAccessByOthers  <br/> |Número de arquivos com os quais o usuário interagiu que residem em um site de equipe de outro usuário.  <br/> |
|Teams_ChatMessages  <br/> |Número de mensagens de chat enviadas.  <br/> |
|Teams_ChannelMessage  <br/> |Número de mensagens postadas nos canais.  <br/> |
|Teams_CallParticipate  <br/> |Número de chamadas das que o usuário participou.  <br/> |
|Teams_MeetingParticipate  <br/> |Número de reuniões que o usuário ingressou.  <br/> |
|Teams_HasOtherAction  <br/> |Valor booliana se o usuário realizou outras ações no Microsoft Teams.  <br/> |
|YAM_MessagePost  <br/> |Número de mensagens do Yammer que este usuário publicou.  <br/> |
|YAM_MessageLiked  <br/> |Número de mensagens do Yammer que este usuário curtiu.  <br/> |
|YAM_MessageRead  <br/> |Número de mensagens do Yammer que este usuário leu.  <br/> |
|SFB_P2PSummary  <br/> |Número de sessões de ponto a ponto das quais este usuário participou.  <br/> |
|SFB_ConfOrgSummary  <br/> |Número de sessões de conferência organizadas por este usuário.  <br/> |
|SFB_ConfPartSummary  <br/> |Número de sessões de conferência das quais este usuário participou.  <br/> |

> [!NOTE]
> Teams_HasOtherAction significa que o usuário é considerado ativo, mas tem um valor zero para as Mensagens de Chat, chamadas 1:1, Mensagens de Canal, Total de Reuniões e Reuniões organizadas.
   
### <a name="data-table---tenant-product-usage"></a>Tabela de dados - Uso de Produto do Locatário

Esta tabela fornece dados de adoção mensalmente em termos de usuários habilitados, ativos, de retorno e de primeira vez para cada produto no Microsoft 365. Os valores do Microsoft 365 representam o uso ativo em qualquer um dos produtos.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Produto  <br/> |Nome dos produtos para os quais as informações de uso são resumidas. O valor do Microsoft 365 na coluna do produto representa a atividade em qualquer um dos produtos  <br/> |
|Período de tempo  <br/> |Valor do mês. Haverá uma linha por produto por mês nos últimos 12 meses, incluindo o mês corrente parcial.  <br/> |
|EnabledUsers  <br/> |Número de usuários habilitados para usar o produto para o valor de período de tempo, se um usuário foi habilitado para parte do mês, eles ainda são contados.  <br/> |
|ActiveUsers  <br/> |Número de usuários que realizaram uma atividade intencional no produto para o valor de período de tempo.  <br/> Um usuário é contado como ativo para um produto em um mês específico se ele tiver executado uma das principais atividades no produto. As principais atividades estão disponíveis na tabela **Atividade de produtos do locatário**.  <br/> |
|CumulativeActiveUsers  <br/> |Número de usuários que estão habilitados para usar um produto e que usaram o produto até o mês-prazo pelo menos uma vez desde o início da coleta de dados no novo sistema de uso.  <br/> |
|MoMReturningUsers  <br/> |Número de usuários que estão ativos no mês-prazo e que também estavam ativos no mês anterior.  <br/> |
|FirstTimeUsers  <br/> |Número de usuários que ficaram ativos no prazo pela primeira vez desde a coleta de dados, no novo sistema de uso.  <br/> Um usuário é contado como usuário iniciante em um mês específico se detectarmos sua atividade pela primeira vez desde o início do conjunto de dados neste novo sistema de relatórios. Depois de contado como um usuário de primeira vez, mesmo que esse usuário tenha uma grande lacuna em sua atividade, ele nunca será contado novamente como um usuário de primeira vez  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-product-activity"></a>Tabela de dados - Atividade de Produto do Locatário

Esta tabela fornece totais mensais de atividade e a contagem de usuários ativos para várias atividades dentro dos produtos.
  
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

Esta tabela consiste em dados resumidos em todos os usuários licenciados do Exchange Online que possuem uma caixa de correio de usuário. Ela contém o estado de fim do mês em todas as caixas de correio de usuário. Os dados nessa tabela não são aditivos em vários meses. Os dados do último mês nesta tabela representam o estado mais recente.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|TotalMailboxes  <br/> |Número de caixas de correio de usuário da assinatura do Microsoft 365.  <br/> |
|IssueWarningQuota  <br/> |Cota total para a emissão de avisos nas caixas de correio de todos os usuários.  <br/> |
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

Esta tabela fornece dados de resumo mensal sobre os clientes que os usuários estão usando para se conectar ao Exchange Online, Skype for Business e Yammer. Esta tabela ainda não tem dados de uso de cliente para o SharePoint Online e o OneDrive for Business.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|Produto  <br/> |Nome do produto no Microsoft 365 para o qual os dados de uso do cliente estão disponíveis.  <br/> |
|ClientId  <br/> |Nome de cada dispositivo usado para conectar-se ao produto.  <br/> |
|UserCount  <br/> |Número de usuários que usaram cada um dos clientes para cada produto.  <br/> |
|Período de tempo  <br/> |Valor do mês  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-sharepoint-online-usage"></a>Tabela de dados - Uso do SharePoint Online do Locatário

Essa tabela consiste em dados de resumo mensal sobre o uso ou a atividade de sites do SharePoint Online. Isso só abrange os sites de equipe e os sites de grupo. O estado do fim do mês dos sites do SharePoint Online é representado nesta coluna, por exemplo, se um usuário criou cinco documentos e usou 10 MB para o armazenamento total e, em seguida, excluiu alguns arquivos e adicionou mais arquivos para que, no final do mês, o estado dos arquivos fosse sete no total que usa cinco MB de armazenamento, o valor representado nesta tabela é o estado de fim do mês. Essa tabela está oculta para evitar a dupla contagem das agregações e é usada como uma fonte para a criação de duas tabelas de referência.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|SiteType  <br/> |Valor de tipo de site (qualquer/equipe/grupo) (qualquer representa qualquer um desses 2 tipos de site).  <br/> |
|TotalSites  <br/> |Número de sites existentes ao fim do prazo.  <br/> |
|DocumentCount  <br/> |O número total de documentos existentes no site ao fim do prazo.  <br/> |
|Diplansed  <br/> |Armazenamento total usado somado em todos os sites ao fim do prazo.  <br/> |
|ActivityType  <br/> |Número de sites que gravaram os vários tipos de atividade do arquivo (qualquer/arquivos ativos/arquivos compartilhados EXT/INT/arquivos sincronizados).  <br/> Representa qualquer atividade de arquivo que foi executada.  <br/> |
|SitesWithOwnerActivities  <br/> |Número de sites ativos, em que o proprietário do site executou uma determinada atividade de arquivo nos próprios sites. Você pode obter o proprietário do site do comando **get-sposite do** PowerShell. Essa é a pessoa responsável pelo site.   <br/> |
|SitesWithNonOwnerActivities  <br/> |Número de sites ativos somados para o mês, onde os usuários, que não o proprietário do site, realizaram uma determinada atividade de arquivo nos sites. Você pode obter o proprietário do site do comando **get-sposite do** PowerShell. Essa é a pessoa responsável pelo site. <br/> |
|ActivityTotalSites  <br/> |Número de sites que registraram qualquer atividade durante o prazo. Se um site que teve atividade anterior no prazo, e foi excluído até o final do prazo, ela ainda seria contado no total do site ativo para esse prazo.  <br/> |
|Período de tempo  <br/> |Esta coluna tem o valor de data. Usada como relação Muitos para um para a tabela Calendário.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-onedrive-usage"></a>Tabela de dados - Uso do OneDrive do Locatário

Essa tabela fornece dados sobre as contas do OneDrive, como o número de contas, o número de documentos em contas do OneDrive, o armazenamento usado, a contagem de arquivos por tipo de atividade. O estado de fim do mês para contas do OneDrive for Business é representado nesta tabela. Por exemplo, se um usuário criou cinco documentos que usavam 10 MB de armazenamento e, em seguida, excluiu alguns arquivos e adicionou mais arquivos para que, no final do mês, ele tivesse sete arquivos que usam cinco MB de armazenamento, o final do valor do mês é representado nesta tabela no final do mês.
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|SiteType  <br/> |O valor é "OneDrive".  <br/> |
|TotalSites  <br/> |Número de contas do OneDrive for Business existentes ao fim do prazo.  <br/> |
|DocumentCount  <br/> |Número total de documentos existentes em todas as contas do OneDrive for Business ao fim do prazo  <br/> |
|Diplansed  <br/> |Armazenamento total usado somado em toda a conta do OneDrive ao fim do prazo.  <br/> |
|ActivityType  <br/> |Número de contas que gravaram os vários tipos de atividade do arquivo (qualquer/arquivos ativos/arquivos compartilhados EXT/INT/arquivos sincronizados).  <br/> Qualquer representa qualquer atividade de arquivo realizada  <br/> |
|SitesWithOwnerActivities  <br/> |Número de contas ativas do OneDrive for Business, onde o proprietário da conta executou uma determinada atividade de arquivo em sua própria conta.  <br/> |
|SitesWithNonOwnerActivities  <br/> |Número de contas do OneDrive for Business em que a atividade do arquivo foi realizada por usuários que não o proprietário da conta.  <br/> |
|ActivityTotalSites  <br/> |Número de contas do OneDrive for Business que registraram qualquer atividade durante o prazo. Se uma conta do OneDrive for Business teve atividade anterior no prazo, e foi excluída até o final do prazo, ela ainda seria contada nas contas ativas do OneDrive for Business para esse prazo.  <br/> |
|Período de tempo  <br/> |Esta coluna tem o valor de data. Usada como relação Muitos para um para a tabela Calendário.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   
### <a name="data-table---tenant-microsoft-365-groups-usage"></a>Tabela de dados - Uso de Grupos do Locatário do Microsoft 365

Esta tabela fornece dados sobre como os Grupos do Microsoft 365 são usados em toda a organização.
  
****

|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|TimeFrame  <br/> |Valor do mês. Haverá uma linha por produto por mês nos últimos 12 meses, incluindo o mês corrente parcial.  <br/> |
|GroupType  <br/> |Tipo de grupo (particular/público/qualquer).  <br/> |
|TotalGroups  <br/> |Número de grupos em cada tipo de grupo.  <br/> |
|ActiveGroups  <br/> |Número de grupos ativos.  <br/> |
|MBX_TotalGroups  <br/> |Número de grupos de caixas de correio.  <br/> |
|MBX_ActiveGroups  <br/> |Número de grupos de caixas de correio ativas.  <br/> |
|MBX_TotalActivities  <br/> |Número de atividades de caixa de correio.  <br/> |
|MBX_TotalItems  <br/> |Número de itens de caixa de correio.  <br/> |
|MBX_StorageUsed  <br/> |Quantidade de armazenamento de caixa de correio usado.  <br/> |
|SPO_TotalGroups  <br/> |Número de grupos do SharePoint.  <br/> |
|SPO_ActiveGroups  <br/> |Número de grupos ativos do SharePoint.  <br/> |
|SPO_FileAccessedActiveGroups  <br/> |Número de grupos do SharePoint que acessaram atividades de arquivo.  <br/> |
|SPO_FileSyncedActiveGroups  <br/> |Número de grupos do SharePoint que possuem atividades sincronizadas de arquivos.  <br/> |
|SPO_FileSharedInternallyActiveGroups  <br/> |Número de grupos do SharePoint que compartilharam atividades internamente ou com grupos (que podem incluir usuários externos).  <br/> |
|SPO_FileSharedExternallyActiveGroups  <br/> |Número de grupos do SharePoint que compartilharam atividades externamente.  <br/> |
|SPO_TotalActivities  <br/> |Número de atividades do SharePoint.  <br/> |
|SPO_FileAccessedActivities  <br/> |Número de atividades acessadas pelo arquivo do SharePoint.  <br/> |
|SPO_FileSyncedActivities  <br/> |Número de atividades sincronizadas de arquivo do SharePoint.  <br/> |
|SPO_FileSharedInternallyActivities  <br/> |Número de atividades compartilhadas internamente do arquivo do SharePoint ou com grupos (que podem incluir membros externos).  <br/> |
|SPO_FileSharedExternallyActivities  <br/> |Número de atividades externas compartilhadas no arquivo do SharePoint.  <br/> |
|SPO_TotalFiles  <br/> |Número de arquivos do SharePoint.  <br/> |
|SPO_ActiveFiles  <br/> |Número de arquivos ativos do SharePoint.  <br/> |
|SPO_StorageUsed  <br/> |Quantidade de armazenamento do SharePoint usado.  <br/> |
|YAM_TotalGroups  <br/> |Número de grupos do Yammer.  <br/> |
|YAM_ActiveGroups  <br/> |Número de grupos ativos do Yammer.  <br/> |
|YAM_LikedActiveGroups  <br/> |Número de grupos do Yammer que têm atividades como.  <br/> |
|YAM_PostedActiveGroups  <br/> |Número de grupos do Yammer que possuem atividades de postagem.  <br/> |
|YAM_ReadActiveGroups  <br/> |Número de grupos do Yammer que têm atividades de leitura.  <br/> |
|YAM_TotalActivities  <br/> |Número de atividades do Yammer.  <br/> |
|YAM_LikedActivities  <br/> |Número de atividades como o Yammer.  <br/> |
|YAM_PostedActivties  <br/> |Número de atividades de postagem do Yammer.  <br/> |
|YAM_ReadActivites  <br/> |Número de atividades de leitura do Yammer.  <br/> |
   
### <a name="data-table---tenant-office-activation"></a>Tabela de dados - Ativação do Office do Locatário

A tabela fornece dados sobre o número de ativações de assinatura do Office nos planos de serviço, por exemplo, Aplicativos do Microsoft 365 para empresas, Visio, Project. Ela também fornece dados sobre o número de ativações por dispositivo (Android/iOS/Mac/PC).
  
|**Nome da coluna**|**Descrição da coluna**|
|:-----|:-----|
|ServicePlanName  <br/> |Lista dos valores de nome do plano de serviço e contagens de ativações por dispositivo, conforme ilustrado nas colunas abaixo.  <br/> |
|TotalEnabled  <br/> |Número de usuários habilitados por nome do plano de serviço até o final do prazo.  <br/> |
|TotalActivatedUsers  <br/> |Número de usuários que ativaram cada plano de serviço até o final do prazo.  <br/> |
|AndroidCount  <br/> |Número de ativações por plano de serviço para dispositivo Android até o final do prazo.  <br/> |
|iOSCount  <br/> |Número de ativações por plano de serviço para dispositivo iOS até o fim do prazo.  <br/> |
|MacCount  <br/> |Número de ativações por plano de serviço para dispositivo MAC até o fim do prazo.  <br/> |
|PcCount  <br/> |Número de ativações por plano de serviço para dispositivo PC até o fim do prazo.  <br/> |
|WinRtCount  <br/> |Número de ativações por plano de serviço para dispositivo Windows Mobile até o fim do prazo.  <br/> |
|Período de tempo  <br/> |Esta coluna tem o valor de data. Usada como relação Muitos para um para a tabela Calendário.  <br/> |
|Data do Conteúdo  <br/> |Se o prazo mostrar o mês atual, esse valor representará a última data do mês atual para o qual os dados estão disponíveis.  <br/> Se o prazo mostrar o mês anterior, esse valor representará a última data do mês do prazo.  <br/> |
   

