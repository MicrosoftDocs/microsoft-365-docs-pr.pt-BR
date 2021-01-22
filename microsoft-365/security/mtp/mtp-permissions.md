---
title: Gerenciar o acesso aos dados do Microsoft 365 Defender na central de segurança do Microsoft 365
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
ms.openlocfilehash: 6f042b0c6314e8e5f80d40d76159712bc817a01c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930133"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Gerenciar o acesso ao Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 Defender

As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 Defender:
- Administrador global
- Administrador de segurança
- Operador de segurança
- Leitor global
- Leitor de segurança

Para revisar as contas com essas funções, [exiba as Permissões no centro de segurança do Microsoft 365](https://security.microsoft.com/permissions).

## <a name="access-to-functionality"></a>Acesso à funcionalidade
O acesso a uma funcionalidade específica é determinado pela sua [função do Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Entre em contato com um administrador global caso precise de acesso a uma funcionalidade específica que exija que você ou seu grupo de usuários tenham uma nova função.

### <a name="approve-pending-automated-tasks"></a>Aprovação de tarefas automatizadas pendentes
[A investigação e a correção automáticas](mtp-autoir-actions.md) podem executar ações em emails, regras de encaminhamento, arquivos, mecanismos de persistência e outros artefatos encontrados durante investigações. Para aprovar ou rejeitar ações pendentes que exijam aprovação explícita, você deve ter determinadas funções atribuídas no Microsoft 365. Para saber mais, confira [Permissões da central de ações](mtp-action-center.md#required-permissions-for-action-center-tasks).

## <a name="access-to-data"></a>Acesso a dados
O acesso aos dados do Microsoft 365 Defender pode ser controlado usando o escopo atribuído a grupos de usuários no Microsoft Defender para RBAC (controle de acesso baseado em função) do Ponto de Extremidade. Se o acesso não tiver sido definido para um conjunto específico de dispositivos no Defender para Ponto de Extremidade, você terá acesso total aos dados no Microsoft 365 Defender. No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.

Por exemplo, se você pertencer a apenas um grupo de usuários com uma função Microsoft Defender para Ponto de Extremidade e esse grupo de usuários tiver acesso somente a dispositivos de vendas, você verá apenas dados sobre dispositivos de vendas no Microsoft 365 Defender. [Saiba mais sobre as configurações de RBAC no Microsoft Defender para Ponto de Extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acesso ao Microsoft Cloud App Security
Durante a visualização, o Microsoft 365 Defender não impõe controles de acesso com base nas configurações do Cloud App Security. O acesso aos dados do Microsoft 365 Defender não é afetado por essas configurações.

## <a name="related-topics"></a>Tópicos relacionados

- [Funções do Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft Defender for Endpoint RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Funções do Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
