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
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051693"
---
# <a name="protect-user-and-device-access"></a>Proteger acesso de usuário e de dispositivo

Proteger o acesso aos seus dados e serviços do Microsoft 365 é fundamental para se defender contra ataques cibernéticos e proteger contra a perda de dados. As mesmas proteções podem ser aplicadas a outros aplicativos SaaS em seu ambiente e até mesmo a aplicativos locais publicados com o Proxy de Aplicativo do Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Etapa 1: Revisar recomendações

Recursos recomendados para proteger identidades e dispositivos que acessam o Office 365, outros serviços SaaS e aplicativos locais publicados com o Proxy de Aplicativo do Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Mais idiomas](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Etapa 2: proteger contas de administrador e acesso
As contas administrativas que você usa para administrar seu ambiente do Microsoft 365 incluem privilégios elevados. Esses são alvos valiosos para hackers e cyberattackers. 

Comece usando contas de administrador somente para administração. Os administradores devem ter uma conta de usuário separada para uso regular e não administrativo e usar somente sua conta administrativa quando necessário para concluir uma tarefa associada à função de trabalho.

Proteja suas contas de administrador com autenticação multifacional e acesso condicional. Para obter mais informações, consulte [Protegendo contas de administrador.](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts) 

Em seguida, configure o gerenciamento de acesso privilegiado no Office 365. O gerenciamento de acesso privilegiado permite o controle de acesso granular sobre tarefas de administrador privilegiadas no Office 365. Ele pode ajudar a proteger sua organização contra violações que podem usar contas de administrador privilegiadas existentes com acesso permanente a dados confidenciais ou acesso a configurações críticas.

- [Visão geral do gerenciamento de acesso privilegiado](privileged-access-management-overview.md)
- [Configurar gerenciamento de acesso privilegiado](privileged-access-management-configuration.md)

Outra recomendação principal é usar estações de trabalho configuradas especificamente para o trabalho administrativo. Esses são dispositivos dedicados que são usados apenas para tarefas administrativas. Consulte [Proteger o acesso privilegiado](/windows-server/identity/securing-privileged-access/securing-privileged-access).

Por fim, você pode reduzir o impacto da falta de acesso administrativo inadvertida criando duas ou mais contas de acesso de emergência em seu locatário. Consulte [Gerenciar contas de acesso de emergência no Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Etapa 3: Configurar políticas recomendadas de acesso a dispositivos e identidades
A autenticação multifacional (MFA) e as políticas de acesso condicional são ferramentas poderosas para atenuar contra contas comprometidas e acesso não autorizado. Recomendamos a implementação de um conjunto de políticas que foram testadas juntas. Para obter mais informações, incluindo etapas de implantação, consulte [Configurações de acesso a dispositivos](../security/defender-365-security/microsoft-365-policies-configurations.md)e identidade.

 Essas políticas implementam os seguintes recursos:
- Autenticação de fator mult
- Acesso condicional
- Proteção de aplicativos do Intune (proteção de aplicativos e dados para dispositivos)
- Conformidade de dispositivos com o Intune
- Azure AD Identity Protection

Implementar a conformidade de dispositivos do Intune exige o registro do dispositivo. Gerenciar dispositivos permite garantir que eles sejam saudáveis e compatíveis antes de permitir que eles acessem recursos em seu ambiente. Consulte [Registrar dispositivos para gerenciamento no Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Etapa 4: Configurar políticas de acesso a dispositivos do SharePoint

A Microsoft recomenda que você proteja o conteúdo em sites do SharePoint com conteúdo altamente regulamentado e confidenciais com controles de acesso ao dispositivo. Para obter mais informações, consulte [Recomendações de política para proteger sites e arquivos do SharePoint.](../security/defender-365-security/sharepoint-file-access-policies.md)



