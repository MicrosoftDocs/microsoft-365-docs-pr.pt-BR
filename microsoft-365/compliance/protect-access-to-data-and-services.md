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
description: Saiba como proteger o acesso de usuários e dispositivos aos dados e serviços do Microsoft 365 e se defender contra a perda de dados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64baa2c9e49a9b24841ec50db3e5592ba3d7d55d
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399020"
---
# <a name="protect-user-and-device-access"></a>Proteger acesso de usuário e de dispositivo

Proteger o acesso aos seus dados e serviços do Microsoft 365 é fundamental para se proteger contra ataques cibernéticos e proteger contra perda de dados. As mesmas proteções podem ser aplicadas a outros aplicativos SaaS em seu ambiente e até mesmo a aplicativos locais publicados com o Proxy de Aplicativo do Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Etapa 1: Revise as recomendações

Recursos recomendados para proteger identidades e dispositivos que acessam o Office 365, outros serviços SaaS e aplicativos locais publicados com o Proxy de Aplicativo do Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Etapa 2: proteger contas de administrador e acesso
As contas administrativas que você usa para administrar seu ambiente do Microsoft 365 incluem privilégios elevados. Esses são destinos valiosos para hackers e cyberattackers. 

Comece usando contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso regular, não administrativo e usar sua conta administrativa somente quando necessário para concluir uma tarefa associada à sua função de trabalho.

Proteja suas contas de administrador com autenticação multifacional e acesso condicional. Para obter mais informações, consulte [Protegendo contas de administrador.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts) 

Em seguida, configure o gerenciamento de acesso privilegiado no Office 365. O gerenciamento de acesso privilegiado permite o controle de acesso granular sobre tarefas de administração privilegiadas no Office 365. Ele pode ajudar a proteger sua organização contra violações que possam usar contas de administrador privilegiadas existentes com acesso permanente a dados confidenciais ou acesso a configurações críticas.

- [Visão geral do gerenciamento de acesso privilegiado](privileged-access-management-overview.md)
- [Configurar gerenciamento de acesso privilegiado](privileged-access-management-configuration.md)

Outra recomendação importante é usar estações de trabalho configuradas especificamente para trabalho administrativo. Esses são dispositivos dedicados que são usados apenas para tarefas administrativas. Consulte [Proteger o acesso privilegiado.](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)

Por fim, você pode reduzir o impacto da falta inadvertida de acesso administrativo criando duas ou mais contas de acesso de emergência em seu locatário. Confira [Gerenciar contas de acesso de emergência no Azure AD.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Etapa 3: Configurar políticas de acesso de dispositivo e identidade recomendadas
A MFA (autenticação multifacional) e as políticas de acesso condicional são ferramentas eficientes para atenuar contas comprometidas e acesso não autorizado. Recomendamos implementar um conjunto de políticas que foram testadas juntas. Para obter mais informações, incluindo as etapas de implantação, consulte [Configurações de acesso de](../security/office-365-security/microsoft-365-policies-configurations.md)dispositivo e identidade.

 Essas políticas implementam os seguintes recursos:
- Autenticação de fator mult
- Acesso condicional
- Proteção de aplicativos do Intune (proteção de aplicativos e dados para dispositivos)
- Conformidade de dispositivos com o Intune
- Azure AD Identity Protection

Implementar a conformidade de dispositivos do Intune requer o registro do dispositivo. O gerenciamento de dispositivos permite garantir que eles sejam íntegres e compatíveis antes de permitir que eles acessem os recursos em seu ambiente. Ver [Registrar dispositivos para gerenciamento no Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Etapa 4: Configurar políticas de acesso a dispositivos do SharePoint

A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo altamente regulamentado e confidenciais com controles de acesso a dispositivos. Para saber mais, confira Recomendações de política para proteger arquivos e [sites do SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)



    

