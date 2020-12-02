---
title: 'Experiência do cliente durante a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs '
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: 'Resumo: entenda a experiência de migrar do Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551690"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Experiência do cliente durante a migração para os serviços do Office 365 nas novas regiões de datacenter alemãs 

As migrações do locatário são projetadas para ter um efeito mínimo sobre administradores e usuários. No entanto, há considerações para cada carga de trabalho. Revise as seções a seguir para ter uma compreensão melhor da experiência de migração para as cargas de trabalho.

A seguir estão as principais diferenças entre o Microsoft Cloud Alemanha e os serviços do Office 365 nas novas regiões do datacenter alemão.

| Categoria | Microsoft Cloud Alemanha (Microsoft Cloud Alemanha) | Serviços do Office 365 nas novas regiões de datacenter alemãs  |
|:-------|:-----|:-------|
| Serviços disponíveis do Microsoft 365 para assinatura com apenas um locatário do Office 365 | 15 serviços | 29 serviços <br><br> Para obter mais informações, consulte o [que é a disponibilidade do serviço entre as diferentes ofertas do Office 365 Cloud Service?](ms-cloud-germany-transition.md#serv-avail). |
| Novos recursos | Não há novos recursos disponíveis. | Novos recursos estarão disponíveis consistentes com os serviços do Office 365. |
| Objeto de confiança dos dados | Sim | Não |
| Colaboração entre os locatários com locatários globais do Office 365 | Não | Sim |
| Residência de dados do cliente | Os dados do cliente serão armazenados unicamente nos data centers do alemão. | A Microsoft armazenará os seguintes dados do cliente em repouso exclusivamente na Alemanha: <ul><li> Conteúdo de caixa de correio do Exchange Online (corpo de email, entradas de calendário e conteúdo de anexos de email) </li><li> Conteúdo do site do SharePoint Online e os arquivos armazenados nesse site e arquivos carregados para o OneDrive for Business </li></ul> |
| Termos aplicáveis | [Termos de serviços online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) com este [suplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Termos dos Serviços Online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

O que não está mudando:

- O domínio inicial do locatário (como, por exemplo `contoso.onmicrosoft.de` ) com ID de locatário (GUID) e domínios personalizados serão persistidos após a migração. 

- As solicitações de autenticação para recursos migrados para os serviços do Office 365 são concedidas pelo serviço de autenticação do Azure dos serviços do Office 365 ( `login.microsoftonline.com` ). Durante a migração, os recursos que ainda permanecem no Office 365 Alemanha são autenticados pelo serviço do Azure do Microsoft ( `login.microsoftonline.de` ) existente.

Considerações a observar:

- Para contas de domínio gerenciado, após a cópia do locatário do Azure Active Directory (Azure AD) inicial ser concluída (que é a primeira etapa da migração do Azure AD para o serviço do Office 365 serviços do Azure AD), as alterações de senha, as alterações de redefinição de senha de autoatendimento (SSPR) e as redefinições de senha por administradores devem ser feitas 365 a partir dos portais de As solicitações para atualizar senhas do serviço da Alemanha não terão êxito neste ponto, porque o locatário do Azure AD foi migrado para os serviços do Office 365. Redefinições de senhas de domínio federado não são afetadas, pois elas são concluídas no diretório local.

- Os logons do Azure são apresentados no portal onde o usuário tenta o acesso. Os logs de auditoria estão disponíveis apenas no ponto de extremidade dos serviços do Office 365 após a transição. Antes de migrar até a conclusão da migração, você deve salvar os logs de entrada e de auditoria do portal Alemanha do Microsoft Cloud.

- Redefinições de senha, alterações de senha, redefinição de senha por um administrador para organizações gerenciadas (que não estão usando os serviços de Federação do Active Directory) devem ser realizadas por meio do portal de serviços do Office 365. As tentativas de usuários que acessam portais do Alemanha da nuvem da Microsoft para redefinir senhas falharão.

- As solicitações de entidades de dados do RGPD (regulamentação geral de proteção de dados) são executadas do portal de administração do Azure de serviços do Office 365 para futuras solicitações. Qualquer dado de diagnóstico herdado ou não-cliente residente no Microsoft Cloud Alemanha é excluído em ou antes de 30 dias.

## <a name="subscriptions--licenses"></a>Assinaturas & licenças

- As assinaturas do Office 365 e Dynamics do Microsoft Cloud Alemanha são transidas para a região alemã com a realocação do Azure AD. A organização é atualizada para refletir as novas assinaturas dos serviços do Office 365. Durante o processo de transferência rápida da assinatura, as alterações nas assinaturas são bloqueadas.

- Como o locatário é transicionado para os serviços do Office 365, suas assinaturas e licenças específicas da Alemanha são padronizadas com novas ofertas de serviços do Office 365. As assinaturas de serviços do Office 365 correspondentes são compradas para as assinaturas da Alemanha transferidas. Os usuários com licenças da Alemanha serão atribuídos a licenças de serviços do Office 365. Após a conclusão, as assinaturas da Alemanha herdadas são canceladas e removidas do locatário atual de serviços do Office 365.

- Após a migração de cargas de trabalho individuais, a funcionalidade adicional é disponibilizada por meio dos serviços do Office 365 (como Microsoft Planner e Microsoft Flow) devido às novas assinaturas de serviços do Office 365. Se apropriado para sua organização, o locatário ou administrador de licenciamento pode desabilitar novos planos de serviço conforme você planeja para o gerenciamento de alterações para apresentar os novos serviços. Para obter orientação sobre como desabilitar os planos de serviço atribuídos às licenças dos usuários, consulte [desabilitar o acesso aos serviços do Microsoft 365 enquanto atribui licenças de usuário](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- A transição de URLs de recurso do Exchange do ponto de extremidade da Alemanha herdado `outlook.office.de` para o ponto de extremidade de serviços do Office 365 `outlook.office365.com` após a migração. Seus usuários podem acessar a caixa de correio migrada usando a URL herdada até que a migração seja concluída. Os clientes devem fazer a transição dos usuários para a nova URL o mais rápido possível, depois que a migração do Exchange começar a evitar o afastamento do ambiente da Alemanha. As URLs de serviços do Office 365 para os serviços do Outlook ficam disponíveis somente após o início da migração do Exchange.

- As caixas de correio são migradas como um processo de back-end. Os usuários da sua organização podem estar no Microsoft Cloud Alemanha ou na região alemão durante a transição e fazem parte da mesma organização do Exchange (na mesma lista de endereços global).

- Os usuários do Outlook Web App que acessam o serviço usando uma URL em que sua caixa de correio não residem receberá um prompt de autenticação extra. Por exemplo, se a caixa de correio do usuário estiver nos serviços do Office 365 e a conexão do Outlook Web App do usuário usar o ponto de extremidade herdado `outlook.office.de` , o usuário será autenticado primeiro `login.microsoftonline.de` e depois para `login.microsoftonline.com` . Quando a migração estiver concluída, o usuário poderá acessar a nova URL ( `https://outlook.office365.com` ) e verá apenas a solicitação de entrada única e esperada. 

## <a name="office-services"></a>Serviços do Office

Os serviços do Office Online podem ser acessados via `office.de` antes e durante a transição. Após a transição das caixas de correio dos usuários para os serviços do Office 365, os usuários devem começar a usar as URLs dos serviços do Office 365. Como as cargas de trabalho subsequentes migram para os serviços do Office 365, sua interface do portal do office.com começará a funcionar.

## <a name="exchange-online-protection"></a>Proteção do Exchange Online

- Os recursos de back-end do Exchange Online Protection (EOP) são copiados para a nova região da Alemanha.
- Os usuários do centro de conformidade e segurança do Office 365 precisam fazer a transição para o uso de URLs globais, `https://protection.office.com` como parte da migração.

## <a name="skype-for-business-online"></a>Skype for Business Online

Os clientes existentes do Skype for Business Online farão a transição para o Microsoft Teams. Para obter mais informações, consulte [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) .

## <a name="office-365-video"></a>Vídeo do Office 365

O vídeo do Office 365 está sendo desativado em 1 de março de 2021 e não haverá suporte para o vídeo do Office 365 após a migração do SharePoint Online para as novas regiões do datacenter alemão ser concluída. O conteúdo do vídeo do Office 365 será migrado como parte da migração do SharePoint Online. No entanto, vídeos no Office 365 video não serão reproduzidos na UI de vídeo do Office 365 após a migração do SharePoint. Saiba mais sobre a linha do tempo de migração na [transição de vídeo do Office 365 para a visão geral do Microsoft Stream (clássico)](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline).

## <a name="next-step"></a>Próxima etapa

[Entender ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mais informações

Introdução:

- [Migração do Microsoft Cloud Alemanha para os serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)

Mover-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [Serviços](ms-cloud-germany-transition-add-general.md), [dispositivos](ms-cloud-germany-transition-add-devices.md), [experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md).

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](https://aka.ms/d365ceoptin)
- [Informações do programa de migração do Power BI](https://aka.ms/pbioptin)
- [Introdução à atualização do Microsoft Teams](https://aka.ms/SkypeToTeams-Home)
