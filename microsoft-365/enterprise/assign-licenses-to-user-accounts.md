---
title: Atribuir licenças do Microsoft 365 a contas de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descreve como atribuir licenças do Microsoft 365 a contas de usuário, individualmente ou com base na associação de grupo.
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326502"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Atribuir licenças do Microsoft 365 a contas de usuário

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para o modelo de identidade somente na nuvem, você pode atribuir licenças do Microsoft 365 a contas de usuário à medida que elas são criadas, dependendo de como você as cria.

Para o modelo de identidade híbrida, quando as contas de usuário dos Serviços de Domínio Active Directory (AD DS) são sincronizadas pela primeira vez, elas não são atribuídas automaticamente a um local ou uma licença do Microsoft 365. **Você deve configurar cada conta de usuário com um local de usuário antes ou junto com a atribuição de uma licença.**

Em ambos os casos, você deve atribuir uma licença a contas de usuário para que os usuários possam acessar os serviços do Microsoft 365, como email e Microsoft Teams.

Você pode atribuir licenças a contas de usuário individualmente ou automaticamente por meio da associação de grupo.

Para atribuir licenças do Microsoft 365 a contas de usuário individuais, você pode usar:

- [O Centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- O centro de administração do Azure AD

## <a name="group-based-licensing"></a>Licenciamento com base em grupo

Você pode configurar grupos de segurança no Azure AD para atribuir automaticamente licenças de um conjunto de assinaturas a todos os membros do grupo. Isso é conhecido como *licenciamento baseado em grupo*. Se uma conta de usuário for adicionada ou removida do grupo, as licenças das assinaturas do grupo serão automaticamente atribuídas ou não atribuídas à conta do usuário.

Verifique se você tem licenças suficientes para todos os membros do grupo. Se você ficar sem licenças, os novos usuários não receberão licenças até que as licenças estejam disponíveis.

>[!Note]
>Você não deve configurar o licenciamento baseado em grupo para grupos que contenham contas do Azure para empresas (B2B).
>

Para obter mais informações, consulte [licenciamento baseado em grupo no Azure AD.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

## <a name="next-steps"></a>Próximas etapas

Com o conjunto apropriado de contas de usuário que foram atribuídas licenças, agora você está pronto para:

- [Implementar segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Implantar software cliente, como o Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Configurar o gerenciamento de dispositivos](device-management-roadmap-microsoft-365.md)
- [Configurar serviços e aplicativos](configure-services-and-applications.md)
