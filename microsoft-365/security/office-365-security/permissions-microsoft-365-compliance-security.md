---
title: Políticas de alerta nos centros de conformidade e segurança do Microsoft 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Usando a central de segurança do Microsoft 365 ou o centro de conformidade da Microsoft 365, você pode gerenciar as permissões centralmente para todas as tarefas relacionadas à segurança ou conformidade.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cc0c69008d942e213f3a86e2852265969dd1971
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203072"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Permissões novo centro de segurança do Microsoft 365 e no centro de conformidade do Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Sua organização precisa gerenciar cenários de segurança e conformidade que abrangem todos os serviços do Microsoft 365. E você precisa ter flexibilidade para dar permissões de administrador para as pessoas certas no grupo de TI da sua organização. Usando a central de segurança do Microsoft 365 ou o centro de conformidade da Microsoft 365, você pode gerenciar as permissões centralmente para todas as tarefas relacionadas à segurança ou conformidade.

Depois que o administrador global atribuir essas funções de administrador, os administradores têm acesso aos recursos e dados que abrangem todos os serviços no Microsoft 365, como a Centro de Segurança do Microsoft 365, o Centro de conformidade do Microsoft 365, o Azure, o Office 365 e o Enterprise Mobility + Security.

## <a name="what-the-microsoft-365-roles-are"></a>Quais são as funções do Microsoft 365

As funções que aparecem no centro de conformidade do Microsoft 365 e no centro de segurança da Microsoft 365 são funções do Azure Active Directory. Essas funções foram projetadas para se alinharem com funções de trabalho no grupo de TI da sua organização, tornando mais fácil dar a uma pessoa todas as permissões necessárias para realizar o trabalho.

****

|Função|Descrição|
|---|---|
|**Administrador global**|Acesso a todos os recursos administrativos em todos os serviços do Microsoft 365. Somente os administradores globais podem atribuir outras funções de administrador. Para saber mais, confira [administrador global/administrador da empresa](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator).|
|**Administrador de dados de conformidade**|Acompanhe os dados da sua organização no Microsoft 365, certifique-se de que estejam protegidos e obtenha insights sobre quaisquer problemas para ajudar a atenuar os riscos. Para obter mais informações, confira o [Administrador de Dados de Conformidade](/azure/active-directory/roles/permissions-reference#compliance-data-administrator).|
|**Administrador de conformidade**|Ajude sua organização a se manter em conformidade com quaisquer requisitos regulatórios, gerenciar casos de descoberta eletrônica e manter políticas de governança de dados em locais, identidades e aplicativos do Microsoft 365. Para saber mais, confira o [Administrador de Conformidade](/azure/active-directory/roles/permissions-reference#compliance-administrator).|
|**Operador de segurança**|Exibir, investigar e responder a ameaças ativas a seus usuários, dispositivos e conteúdo da Microsoft 365. Para obter mais informações, confira [Operador de Segurança](/azure/active-directory/roles/permissions-reference#security-operator).|
|**Leitor de segurança**|Exibir e investigar ameaças ativas a seus usuários, dispositivos e conteúdo da Microsoft 365, mas (diferentemente do Operador de segurança) não têm permissões para responder executando uma ação. Para obter mais informações, confira o [Leitor de Segurança](/azure/active-directory/roles/permissions-reference#security-reader).|
|**Administrador de segurança**|Controle a segurança global da sua organização, gerenciando políticas de segurança, analisando análises e relatórios de segurança em produtos da Microsoft 365 e ficando sempre atualizado sobre o panorama das ameaças. Para obter mais informações, confira a[Segurança do Administrador](/azure/active-directory/roles/permissions-reference#security-administrator).|
|**Leitor global**|A versão somente leitura do **Administrador Global**. Exibir todas as configurações e informações administrativas no Microsoft 365. Para saber mais, confira [Leitor Global](/azure/active-directory/roles/permissions-reference#global-reader)..|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>Os administradores globais podem gerenciar as funções no Azure Active Directory

No centro de conformidade do Microsoft 365 e no centro de segurança do Microsoft 365, ao selecionar uma função, você pode exibir suas tarefas. No entanto, para gerenciar essas tarefas, você precisa ir para o Azure Active Directory.

Para saber mais informações, consulte [Exibir e atribuir funções de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

![Vincular permissões no Azure Active Directory](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Gerenciamento de funções em um serviço, em vez do Azure Active Directory

As funções que aparecem no centro de conformidade do Microsoft 365 e no centro de segurança da Microsoft 365 também são exibidas nos serviços que têm permissões. Por exemplo, você pode ver essas funções no Centro de segurança e conformidade.

![Funções no Centro de conformidade e segurança](../../media/m365-roles-in-o365-scc.png)

Para obter mais informações sobre grupos de funções no Centro de Conformidade e Segurança, confira [Permissões no Centro de Conformidade e Segurança](permissions-in-the-security-and-compliance-center.md).

### <a name="breaking-inheritance"></a>Interrompendo herança

É importante compreender que quando você gerencia essas funções no Azure Active Directory, está fazendo centralmente para **todos** os serviços da Microsoft 365. No entanto, quando você gerencia uma função em um serviço específico, como o Centro de conformidade e segurança, gerencia a função **apenas** para esse serviço específico. As atribuições e permissões para uma função em um serviço substituem as permissões concedidas à função do Azure Active Directory.

Isso pode ser útil!. Por exemplo, se uma pessoa for atribuída à função de administrador de segurança, ela não terá permissão para gerenciar incidentes. Mas pode se usar as permissões no Microsoft Defender para Ponto de Extremidade para fornecê-los a permissão específica para gerenciamento de incidentes nesse serviço.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>Onde encontrar informações sobre a função de cada serviço da Microsoft 365

Ao atribuir um usuário a uma das funções de administrador de conformidade ou segurança do Microsoft 365, conceda a essas permissões de usuário a uma série de serviços do Microsoft 365. Use os links abaixo para saber mais sobre as permissões específicas para uma função em cada serviço.

****

|Serviço Microsoft 365|Informações sobre a função|
|---|---|
|Funções de administrador no Office 365 e Microsoft 365 para planos de negócios|[Funções de administrador do Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Azure AD (Azure Active Directory) e Azure AD Identity Protection|[Funções de administrador do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|O que é o Microsoft Defender para Identidade?|[grupos de funções do Microsoft Defender para Identidade](/azure-advanced-threat-protection/atp-role-groups)|
|Proteção de Informações do Azure|[Funções de administrador do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Gerente de Conformidade|[Gerenciador de Conformidade](../../compliance/compliance-manager-setup.md#set-user-permissions-and-assign-roles)|
|Exchange Online|[Controle de acesso baseado em função do Exchange](/exchange/permissions-exo/permissions-exo)|
|Intune|[Controle de acesso baseado em função do Intune](/intune/role-based-access-control)|
|Área de trabalho gerenciada|[Funções de administrador do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[Controle de acesso baseado em função](/cloud-app-security/manage-admins)|
|Centro de conformidade e segurança|[Funções de administrador do Microsoft 365](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Funções de administrador do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Classificação de Segurança|[Funções de administrador do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Funções de administrador do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Sobre a função de administrador do SharePoint no Office 365](/sharepoint/sharepoint-admin-role)|
|Equipes/Skype for Business|[Funções de administrador do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Defender para Ponto de Extremidade|[Controle de acesso baseado na função do Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>Em breve

Ainda estamos trabalhando nas permissões do centro de conformidade do Microsoft 365 e do centro de segurança da Microsoft 365. Por exemplo, no momento estamos trabalhando para oferecer suporte à capacidade de:

- Gerenciar funções no centro de conformidade do Microsoft 365 e no centro de segurança da Microsoft 365, em vez de ir para o Azure Active Directory.
- Personalizar funções adicionando ou removendo permissões específicas.
- Criar funções personalizadas com as permissões que você escolher.