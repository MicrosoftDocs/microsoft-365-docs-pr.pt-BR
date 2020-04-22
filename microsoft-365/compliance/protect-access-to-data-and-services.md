---
title: Proteger acesso de usuário e de dispositivo
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: página de aterrissagem para proteger o acesso a dados e serviços do Microsoft 365
ms.openlocfilehash: 4d09ee0aa0ef36222ae0d238b0e7a44ee23994d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632206"
---
# <a name="protect-user-and-device-access"></a>Proteger acesso de usuário e de dispositivo

Proteger o acesso aos seus dados e serviços do Microsoft 365 é crucial para se defender contra cyberattacks e proteção contra a perda de dados. As mesmas proteções podem ser aplicadas a outros aplicativos SaaS em seu ambiente e até mesmo para aplicativos locais publicados com o proxy de aplicativo do Active Directory do Azure.
  
## <a name="step-1-review-recommendations"></a>Etapa 1: analisar as recomendações

Recursos recomendados para proteger identidades e dispositivos que acessam o Office 365, outros serviços SaaS e aplicativos locais publicados com o Proxy de Aplicativo do Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Etapa 2: proteger contas de administrador e acessar
As contas administrativas que você usa para administrar seu ambiente do Microsoft 365 incluem privilégios elevados. Estes são alvos valiosos para hackers e cyberattackers. 

Comece usando contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso regular e não administrativo e só usarem a conta administrativa, quando necessário, para concluir uma tarefa associada à função de trabalho.

Proteger suas contas de administrador com autenticação multifator e acesso condicional. Para obter mais informações, consulte [protegendo contas de administrador](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts). 

Em seguida, configure o gerenciamento de acesso privilegiado no Office 365. O gerenciamento de acesso privilegiado permite o controle de acesso granular sobre tarefas administrativas privilegiadas no Office 365. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso à dados confidenciais ou acesso a definições de configuração crítica.

- [Visão geral do gerenciamento de acesso privilegiado](privileged-access-management-overview.md)
- [Configurar gerenciamento de acesso privilegiado](privileged-access-management-configuration.md)

Outra recomendação principal é usar as estações de trabalho especificamente configuradas para trabalhos administrativos. Estes são dispositivos dedicados que são usados apenas para tarefas administrativas. Consulte [protegendo o acesso privilegiado](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).

Por fim, você pode reduzir o impacto da falta inadvertida de acesso administrativo, criando duas ou mais contas de acesso de emergência em seu locatário. Consulte [gerenciar contas de acesso de emergência no Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Etapa 3: configurar as políticas recomendadas de acesso de dispositivo e identidades
A MFA (autenticação multifator) e as políticas de acesso condicional são ferramentas poderosas para reduzir as contas comprometidas e o acesso não autorizado. É recomendável implementar um conjunto de políticas que foram testadas juntas. Para obter mais informações, incluindo etapas de implantação, consulte [Identity and Device Access Configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).

 Essas políticas implementam os seguintes recursos:
- Mediante-factor Authentication
- Acesso condicional
- Proteção de aplicativos do Intune (proteção de aplicativos e dados para dispositivos)
- Conformidade de dispositivos com o Intune
- Azure AD Identity Protection

A implementação da conformidade do dispositivo do Intune requer o registro do dispositivo. O gerenciamento de dispositivos permite que você verifique se eles estão íntegros e em conformidade antes de permitir o acesso aos recursos em seu ambiente. Consulte [registrar dispositivos para gerenciamento no Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Etapa 4: configurar as políticas de acesso do dispositivo do SharePoint

A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo confidencial e altamente regulamentado com controles de acesso do dispositivo. Para mais informações, consulte [recomendações de política para proteger sites e arquivos do SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).



    

