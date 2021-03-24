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
description: Descreve como atribuir licenças do Microsoft 365 a contas de usuário, individualmente ou com base na associação ao grupo.
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051527"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Atribuir licenças do Microsoft 365 a contas de usuário

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Para o modelo de identidade somente na nuvem, você pode atribuir licenças do Microsoft 365 às contas de usuário à medida que elas são criadas, dependendo de como você as cria.

Para o modelo de identidade híbrida, quando as contas de usuário do Active Directory Domain Services (AD DS) são sincronizadas pela primeira vez, elas não são atribuídas automaticamente a um local ou uma licença do Microsoft 365. **Você deve configurar cada conta de usuário com um local de usuário antes ou com a atribuição de uma licença.**

Em ambos os casos, você deve atribuir uma licença a contas de usuário para que seus usuários possam acessar serviços do Microsoft 365, como email e Microsoft Teams.

Você pode atribuir licenças a contas de usuário individualmente ou automaticamente por meio da associação ao grupo.

Para atribuir licenças do Microsoft 365 a contas de usuário individuais, você pode usar:

- [O Centro de administração do Microsoft 365](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Centro de administração do Azure AD

## <a name="group-based-licensing"></a>Licenciamento com base em grupo

Você pode configurar grupos de segurança no Azure AD para atribuir automaticamente licenças de um conjunto de assinaturas a todos os membros do grupo. Isso é conhecido como *licenciamento baseado em grupo*. Se uma conta de usuário for adicionada ou removida do grupo, as licenças das assinaturas do grupo serão automaticamente atribuídas ou não atribuídas à conta do usuário.

Verifique se você tem licenças suficientes para todos os membros do grupo. Se você ficar sem licenças, os novos usuários não receberão licenças até que as licenças estejam disponíveis.

>[!Note]
>Você não deve configurar o licenciamento baseado em grupo para grupos que contenham contas do Azure para empresas (B2B).
>

Para obter mais informações, consulte [licenciamento baseado em grupo no Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Próximas etapas

Com o conjunto apropriado de contas de usuário que foram atribuídas licenças, agora você está pronto para:

- [Implementar segurança](../security/defender-365-security/security-roadmap.md)
- [Implantar software cliente, como o Microsoft 365 Apps](/DeployOffice/deployment-guide-microsoft-365-apps)
- [Configurar o gerenciamento de dispositivos](device-management-roadmap-microsoft-365.md)
- [Configurar serviços e aplicativos](configure-services-and-applications.md)