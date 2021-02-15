---
title: Identidade somente na nuvem do Microsoft 365
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
description: Descreve como criar usuários e grupos quando sua assinatura do Microsoft 365 está usando a identidade somente na nuvem.
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327922"
---
# <a name="microsoft-365-cloud-only-identity"></a>Identidade somente na nuvem do Microsoft 365

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

Com a identidade somente na nuvem, todos os seus usuários, grupos e contatos são armazenados no locatário do Azure Active Directory (Azure AD) de sua assinatura do Microsoft 365. Aqui estão os componentes básicos da identidade somente na nuvem.
 
![Os componentes básicos da identidade somente na nuvem](../media/about-microsoft-365-identity/cloud-only-identity.png)

Os usuários e suas contas de usuário nas organizações podem ser categorizados de várias maneiras. Por exemplo, alguns são funcionários e têm um status permanente. Alguns são fornecedores, prestadores de serviços ou parceiros que têm um status temporário. Alguns são usuários externos que não têm contas de usuário, mas ainda devem ter acesso a serviços e recursos específicos para dar suporte à interação e à colaboração. Por exemplo:

- As contas do locatário representam os usuários em sua organização para os quais você atribui uma licença para os serviços de nuvem

- As contas entre empresas (B2B) representam usuários de fora da sua organização que você convida para colaborar

Tomar ações dos tipos de usuários em sua organização. O que são os grupos? Por exemplo, você pode agrupar usuários por função ou finalidade de alto nível para sua organização.

Além disso, alguns serviços de nuvem podem ser compartilhados com usuários de fora de sua organização que não tenham contas de usuário. Você também precisará identificar esses grupos de usuários.

Você pode usar grupos no Azure AD para várias finalidades que simplificam o gerenciamento do seu ambiente de nuvem. Por exemplo, com grupos do Azure AD, você pode:

- Use o licenciamento baseado em grupo para atribuir licenças do Microsoft 365 às suas contas de usuário automaticamente assim que elas são adicionadas como membros.
- Adicione contas de usuário a grupos específicos dinamicamente com base nos atributos da conta de usuário, como nome do departamento.
- Provisione automaticamente os usuários para aplicativos de Software como Serviço (SaaS) e para proteger o acesso a esses aplicativos com autenticação multifacional (MFA) e outras políticas de Acesso Condicional.
- Provisione permissões e níveis de acesso para sites de equipe do SharePoint Online.

## <a name="next-steps-for-cloud-only-identity"></a>Próximas etapas para identidade somente na nuvem

- [Gerenciar contas de usuário](manage-microsoft-365-accounts.md)
- [Atribuir licenças às contas de usuário](assign-licenses-to-user-accounts.md)
- [Gerenciar grupos e associações de grupo](manage-microsoft-365-groups.md)
- [Gerenciar senhas de conta de usuário](manage-microsoft-365-passwords.md)
