---
title: Gerenciar o acesso aos dados do Microsoft 365 Defender no centro de segurança do Microsoft 365
description: Saiba como gerenciar permissões para dados no Microsoft 365 Defender
keywords: acesso, permissões, MTP, Proteção contra Ameaças da Microsoft, M365, segurança, MCAS, MDATP, Cloud App Security, Proteção Avançada contra Ameaças do Microsoft Defender, escopo, gerar escopo, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: a619a6ff5256b3b70302d1bef4f0bc21bd7ac3e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927901"
---
# <a name="manage-access-to-microsoft-365-defender-with-azure-active-directory-global-roles"></a>Gerenciar o acesso ao Microsoft 365 Defender com funções globais do Azure Active Directory

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

Há duas maneiras de gerenciar o acesso ao Microsoft 365 Defender
- **Funções do Azure Active Directory Global (AD)**
- **Acesso de função personalizado**

As contas atribuídas às seguintes **funções do Azure Active Directory (AD)** globais podem acessar a funcionalidade e os dados do Microsoft 365 Defender:
- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

Para revisar as contas com essas funções, [exiba as Permissões no centro de segurança do Microsoft 365](https://security.microsoft.com/permissions).

**O acesso** à função personalizada é um novo recurso no Microsoft 365 Defender e permite gerenciar o acesso a dados, tarefas e recursos específicos no Microsoft Defender 365. Funções personalizadas oferecem mais controle do que funções globais do Azure AD, fornecendo aos usuários apenas o acesso de que precisam com as funções menos permissivas necessárias.  Funções personalizadas podem ser criadas além de funções globais do Azure AD. [Saiba mais sobre funções personalizadas.](custom-roles.md)

> ! [OBSERVAÇÃO] Este artigo se aplica apenas ao gerenciamento de funções globais do Azure Active Directory. Para obter mais informações sobre como usar o controle de acesso baseado em função personalizado, consulte [Funções personalizadas para controle de](custom-roles.md) acesso baseado em função

## <a name="access-to-functionality"></a>Acesso à funcionalidade
O acesso a uma funcionalidade específica é determinado pela sua [função do Azure AD](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Entre em contato com um administrador global caso precise de acesso a uma funcionalidade específica que exija que você ou seu grupo de usuários tenham uma nova função.

### <a name="approve-pending-automated-tasks"></a>Aprovação de tarefas automatizadas pendentes
[A investigação e a correção automáticas](mtp-autoir-actions.md) podem executar ações em emails, regras de encaminhamento, arquivos, mecanismos de persistência e outros artefatos encontrados durante investigações. Para aprovar ou rejeitar ações pendentes que exijam aprovação explícita, você deve ter determinadas funções atribuídas no Microsoft 365. Para saber mais, confira [Permissões da central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Acesso a dados
O acesso aos dados do Microsoft 365 Defender pode ser controlado usando o escopo atribuído a grupos de usuários no Microsoft Defender para controle de acesso baseado em função de ponto de extremidade (RBAC). Se seu acesso não tiver sido limitado a um conjunto específico de dispositivos no Defender para Ponto de Extremidade, você terá acesso total aos dados no Microsoft 365 Defender. No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.

Por exemplo, se você pertencer a apenas um grupo de usuários com uma função do Microsoft Defender para Ponto de Extremidade e esse grupo de usuários tiver acesso apenas a dispositivos de vendas, você verá apenas dados sobre dispositivos de vendas no Microsoft 365 Defender. [Saiba mais sobre as configurações do RBAC no Microsoft Defender para Ponto de Extremidade](/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acesso ao Microsoft Cloud App Security
Durante a visualização, o Microsoft 365 Defender não impõe controles de acesso com base nas configurações de Segurança do Aplicativo na Nuvem. O acesso aos dados do Microsoft 365 Defender não é afetado por essas configurações.

## <a name="related-topics"></a>Tópicos relacionados
- [Funções personalizadas no controle de acesso baseado em função para o Microsoft 365 Defender](custom-roles.md)
- [Funções do Microsoft Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender para Endpoint RBAC](/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Funções do Cloud App Security](/cloud-app-security/manage-admins)