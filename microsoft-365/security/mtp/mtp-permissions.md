---
title: Gerenciar o acesso aos dados do Microsoft 365 defender no centro de segurança do Microsoft 365
description: Saiba como gerenciar permissões para dados no Microsoft 365 defender
keywords: acesso, permissões, MTP, Proteção contra Ameaças da Microsoft, M365, segurança, MCAS, MDATP, Cloud App Security, Proteção Avançada contra Ameaças do Microsoft Defender, escopo, gerar escopo, RBAC
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 55b7b8c5755b773a4d53c95017a0a17a85495dee
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847243"
---
# <a name="manage-access-to-microsoft-365-defender"></a>Gerenciar o acesso ao Microsoft 365 defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Aplica-se a:**
- Microsoft 365 defender

As contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados do Microsoft 365 defender:
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
O acesso aos dados do Microsoft 365 defender pode ser controlado usando o escopo atribuído aos grupos de usuários no Microsoft defender para controle de acesso baseado em função de ponto de extremidade (RBAC). Se o seu acesso não tiver sido definido para um conjunto específico de dispositivos no defender para ponto de extremidade, você terá acesso total aos dados no Microsoft 365 defender. No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.

Por exemplo, se você pertencer apenas um grupo de usuários com uma função do Microsoft defender para ponto de extremidade e esse grupo de usuários tiver acesso apenas aos dispositivos de vendas, você verá apenas dados sobre os dispositivos de vendas no Microsoft 365 defender. [Saiba mais sobre as configurações RBAC no Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acesso ao Microsoft Cloud App Security
Durante a visualização, o Microsoft 365 defender não aplica os controles de acesso com base nas configurações de segurança do aplicativo na nuvem. O acesso aos dados do Microsoft 365 defender não é afetado por essas configurações.

## <a name="related-topics"></a>Tópicos relacionados

- [Funções do Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [Microsoft defender para ponto de extremidade RBAC](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Funções do Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
