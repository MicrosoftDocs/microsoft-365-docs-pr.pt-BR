---
title: O que mudará após a migração para os serviços do Office 365 nas novas regiões do datacenter alemão
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: 'Resumo: entenda o que mudou para mudar do Microsoft Cloud Germany (Microsoft Cloud Deutschland) para os serviços do Office 365 na nova região do datacenter alemão.'
ms.openlocfilehash: 74ad9a662d3ea7a68ef1f82961864eb4468f6098
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591775"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>O que mudará após a migração para os serviços do Office 365 nas novas regiões do datacenter alemão

As migrações de locatários foram projetadas para ter efeito mínimo sobre administradores e usuários. No entanto, há considerações para cada carga de trabalho. Revise as seções a seguir para ter uma melhor compreensão da experiência de migração para as cargas de trabalho.

A seguir estão as principais diferenças entre o Microsoft Cloud Deutschland e os serviços do Office 365 nas novas regiões do datacenter alemão.

| Categoria | Microsoft Cloud Alemanha (Microsoft Cloud Deutschland) | Serviços do Office 365 nas novas regiões de datacenter alemãs  |
|:-------|:-----|:-------|
| Serviços disponíveis do Microsoft 365 para assinatura com apenas um locatário do Office 365 | 15 serviços | 29 serviços <br><br> Para obter mais informações, consulte Qual é a disponibilidade de serviço entre as diferentes ofertas de serviço de [nuvem do Office 365?](ms-cloud-germany-transition.md#serv-avail). |
| Novos recursos | Nenhum novo recursos estará disponível. | Os novos recursos estarão disponíveis de acordo com os serviços do Office 365. |
| Objeto de confiança dos dados | Sim | Não |
| Colaboração entre os locatários com locatários globais do Office 365 | Não | Sim |
| Residência de dados do cliente | Os dados do cliente serão armazenados somente em data centers alemães. | A Microsoft armazenará os seguintes Dados do Cliente em repouso exclusivamente na Alemanha: <ul><li> Conteúdo da caixa de correio do Exchange Online (corpo do email, entradas de calendário e o conteúdo de anexos de email) </li><li> Conteúdo do site do SharePoint Online e os arquivos armazenados nesse site e arquivos carregados no OneDrive for Business </li></ul> |
| Termos aplicáveis | [Termos de Serviços Online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) com este [suplemento](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [Termos dos Serviços Online](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

O que não está mudando:

- O domínio inicial do locatário (como ) com iD de locatário `contoso.onmicrosoft.de` (GUID) e domínios personalizados persistirá após a migração. 

- As solicitações de autenticação para recursos migrados para serviços do Office 365 são concedidas pelo serviço de autenticação do Azure services do Office 365 ( `login.microsoftonline.com` ). Durante a migração, os recursos que permanecem no Office 365 Germany são autenticados pelo serviço Azure alemão existente ( `login.microsoftonline.de` ).

Considerações a observar:

- Para contas de domínio gerenciado, após a cópia do locatário inicial do Azure Active Directory (Azure AD) está concluída (que é a primeira etapa da migração do Azure AD para o serviço do Azure AD dos serviços do Office 365), alterações de senha, alterações de senha de autoatendados (SSPR) e redefinições de senha pelos administradores devem ser feitas a partir dos portais de serviço do Office 365. As solicitações para atualizar senhas do serviço alemão não serão bem-sucedidas neste momento, pois o locatário do Azure AD foi migrado para serviços do Office 365. As redefinições de senhas de domínio federado não são afetadas, porque elas são concluídas no diretório local.

- As inscrições do Azure são apresentadas no portal em que o usuário tenta acessar. Os logs de auditoria estão disponíveis apenas no ponto de extremidade dos serviços do Office 365 após a transição. Antes de migrar até a conclusão da migração, você deve salvar logs de login e auditoria do portal do Microsoft Cloud Deutschland.

- Redefinições de senha, alterações de senha, redefinição de senha por um administrador para organizações gerenciadas (que não estão usando os Serviços de Federação do Active Directory) devem ser executadas por meio do portal de serviços do Office 365. As tentativas dos usuários que acessam portais do Microsoft Cloud Deutschland para redefinir senhas falharão.

- As Solicitações gerais de Assunto de Proteção de Dados (RGPD) são executadas a partir do portal de administração dos serviços do Azure do Office 365 para solicitações futuras. Quaisquer dados de diagnóstico herdados ou não do cliente residentes no Microsoft Cloud Deutschland são excluídos em ou antes de 30 dias.

## <a name="subscriptions--licenses"></a>Assinaturas & Licenças

- As assinaturas do Office 365 e do Dynamics do Microsoft Cloud Deutschland são transidas para a região alemã com a realocação do Azure AD. Em seguida, a organização é atualizada para refletir novas assinaturas de serviços do Office 365. Durante o breve processo de transferência de assinatura, as alterações nas assinaturas são bloqueadas.

- À medida que o locatário é transições para os serviços do Office 365, suas assinaturas e licenças específicas da Alemanha são padronizadas com novas ofertas de serviços do Office 365. Assinaturas de serviços correspondentes do Office 365 são compradas para as assinaturas da Alemanha transferidas. Os usuários que têm licenças da Alemanha receberão licenças de serviços do Office 365. Após a conclusão, as assinaturas herdadas da Alemanha são canceladas e removidas do locatário de serviços do Office 365 atual.

- Após a migração das cargas de trabalho individuais, a funcionalidade adicional é disponibilizada por meio dos serviços do Office 365 (como o Microsoft Planner e o Microsoft Flow) devido às novas assinaturas de serviços do Office 365. Se apropriado para sua organização, o locatário ou administrador de licenciamento pode desabilitar novos planos de serviço conforme você planeja o gerenciamento de alterações para introduzir os novos serviços. Para obter orientações sobre como desabilitar planos de serviço atribuídos às licenças dos usuários, consulte [Disable access to Microsoft 365 services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).

## <a name="exchange-online"></a>Exchange Online

- As URLs de recursos do Exchange transitam do ponto de extremidade da Alemanha herdável para o ponto de extremidade dos serviços do `outlook.office.de` Office 365 `outlook.office365.com` após a migração. Os usuários podem acessar a caixa de correio migrada usando a URL herdada até que a migração seja concluída. Os clientes devem fazer a transição dos usuários para a nova URL assim que possível após a migração do Exchange começar a evitar afetar a reforma do ambiente da Alemanha. As URLs de serviços do Office 365 para serviços do Outlook só ficam disponíveis depois que a migração do Exchange começa.

- As caixas de correio são migradas como um processo de back-end. Os usuários em sua organização podem estar no Microsoft Cloud Deutschland ou na região alemã durante a transição e fazem parte da mesma organização do Exchange (na mesma lista de endereços global).

- Os usuários do Outlook Web App que acessam o serviço usando uma URL onde sua caixa de correio não reside verão um prompt de autenticação extra. Por exemplo, se a caixa de correio do usuário estiver nos serviços do Office 365 e a conexão do Outlook Web App do usuário usar o ponto de extremidade herdado, o usuário primeiro será autenticado para e depois para `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` . Quando a migração for concluída, o usuário poderá acessar a nova URL ( ), e ele verá apenas a única solicitação de `https://outlook.office365.com` entrada esperada. 

## <a name="office-services"></a>Serviços do Office

Os serviços do Office Online são acessíveis `office.de` via antes e durante a transição. Após a transição das caixas de correio dos usuários para os serviços do Office 365, os usuários devem começar a usar URLs de serviços do Office 365. À medida que as cargas de trabalho subsequentes migram para serviços do Office 365, sua interface do portal office.com começará a funcionar.

O serviço mru (mru) usado mais recentemente no Office é uma recorte do Microsoft Cloud Deutschland para os serviços Globais do Office 365, não uma migração. Somente os links de MRU do lado dos serviços globais do Office 365 estarão visíveis após a migração do portal Office.com. Os links de MRU do Microsoft Cloud Deutschland não são visíveis como links MRU nos serviços Globais do Office 365. Nos serviços globais do Office 365, os links de MRU só podem ser acessados depois que a migração de locatários atingir a fase 9.

## <a name="exchange-online-protection"></a>Proteção do Exchange Online

- Os recursos de Proteção do Exchange Online de back-end (EOP) são copiados para a nova região da Alemanha.
- Os usuários do Centro de Conformidade e Segurança do Office 365 precisam fazer a transição para o uso de URLs `https://protection.office.com` globais, como parte da migração.

## <a name="skype-for-business-online"></a>Skype for Business Online

Os clientes existentes do Skype for Business Online farão a transição para o Microsoft Teams. Para obter mais informações, consulte [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) .

## <a name="office-365-video"></a>Vídeo do Office 365

O Vídeo do Office 365 será retirado em 1º de março de 2021 e o Vídeo do Office 365 não terá suporte após a conclusão da migração do SharePoint Online para as novas regiões do datacenter alemão. O conteúdo do Vídeo do Office 365 será migrado como parte da migração do SharePoint Online. No entanto, os vídeos no Vídeo do Office 365 não são reproduzido na interface do usuário de vídeo do Office 365 após a migração do SharePoint. Saiba mais sobre a linha do tempo de migração no [Office 365 Video transition to Microsoft Stream (clássico).](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="next-step"></a>Próxima etapa

[Compreender as ações e os impactos das fases de migração](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>Mais informações

Como começar:

- [Migração do Microsoft Cloud Deutschland para serviços do Office 365 nas novas regiões do datacenter alemão](ms-cloud-germany-transition.md)
- [Assistência de Migração do Microsoft Cloud Deutschland](https://aka.ms/germanymigrateassist)
- [Como aceitar a migração](ms-cloud-germany-migration-opt-in.md)

Movendo-se pela transição:

- [Ações e impactos das fases de migração](ms-cloud-germany-transition-phases.md)
- [Pré-trabalho adicional](ms-cloud-germany-transition-add-pre-work.md)
- Informações adicionais para [o Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos, experiências](ms-cloud-germany-transition-add-experience.md)e [AD FS](ms-cloud-germany-transition-add-adfs.md). [](ms-cloud-germany-transition-add-devices.md)

Aplicativos de nuvem:

- [Informações do programa de migração do Dynamics 365](/dynamics365/get-started/migrate-data-german-region)
- [Informações do programa de migração do Power BI](/power-bi/admin/service-admin-migrate-data-germany)
- [Introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here)
