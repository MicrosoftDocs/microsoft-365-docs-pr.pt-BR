---
title: Atribuir licenças do Microsoft 365 a contas de usuário
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2019
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
ms.openlocfilehash: 60936e52bffa58d50419f771e670848ee76271fd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686965"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>Atribuir licenças do Microsoft 365 a contas de usuário

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Para o modelo de identidade somente na nuvem, você pode atribuir licenças do Microsoft 365 a contas de usuário à medida que elas são criadas, dependendo de como você as cria.

Para o modelo de identidade híbrida, quando as contas de usuário dos serviços de domínio Active Directory (AD DS) são sincronizadas pela primeira vez, elas não recebem automaticamente uma licença do Microsoft 365. Primeiro você deve configurar cada conta de usuário com um local de usuário.

Em ambos os casos, você deve atribuir uma licença às contas de usuário para que seus usuários possam acessar os serviços do Microsoft 365, como email e Microsoft Teams.

Você pode atribuir licenças a contas de usuário individualmente ou automaticamente através da Associação de grupo.

Para atribuir licenças do Microsoft 365 a contas de usuário individuais, você pode usar:

- [O Centro de administração do Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [PowerShell para Microsoft 365](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)

Para atribuição de licença automática, confira [Licenciamento baseado em grupo no Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

## <a name="next-steps"></a>Próximas etapas

Com o conjunto completo de contas de usuário às quais foram atribuídas licenças, agora você está pronto para:

- [Implementar a segurança](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [Implantar software cliente, como o Microsoft 365 aplicativos](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [Configurar o gerenciamento de dispositivo móvel no Microsoft 365](https://support.office.com/article/set-up-mobile-device-management-mdm-in-office-365-dd892318-bc44-4eb1-af00-9db5430be3cd)
- [Configurar serviços e aplicativos](configure-services-and-applications.md)
