---
title: Gerenciar o acesso aos dados da Proteção contra Ameaças da Microsoft no centro de segurança do Microsoft 365
description: Saiba como gerenciar permissões aos dados da Proteção contra Ameaças da Microsoft
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
ms.openlocfilehash: 110bbe6fe48932217c9bdc009d175161fe9226cd
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42235190"
---
# <a name="manage-access-to-microsoft-threat-protection"></a>Gerenciar o acesso à Proteção contra Ameaças da Microsoft

**Aplica-se a:**
- Proteção contra Ameaças da Microsoft



Contas atribuídas às seguintes funções do Azure Active Directory (AD) podem acessar a funcionalidade e os dados da Proteção contra Ameaças da Microsoft:
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
O acesso aos dados da Proteção contra Ameaças da Microsoft pode ser controlado usando o escopo atribuído aos grupos de usuários no RBAC (controle de acesso baseado em função) do Microsoft Defender ATP. Caso seu acesso não tenha sido delimitado a um conjunto específico de dispositivos no Microsoft Defender ATP, você terá acesso total aos dados de Proteção contra Ameaças da Microsoft. No entanto, depois que sua conta tiver um escopo, você só verá os dados dos dispositivos dentro do seu escopo.

Por exemplo, caso você pertença a apenas um grupo de usuários com uma função do Microsoft Defender ATP e esse grupo tenha acesso apenas a dispositivos de vendas, você só verá dados sobre esse tipos de dispositivo na Proteção contra Ameaças da Microsoft. [Saiba mais sobre as configurações de RBAC do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)

### <a name="microsoft-cloud-app-security-access-controls"></a>Controles de acesso ao Microsoft Cloud App Security
Durante a visualização, a Proteção contra Ameaças da Microsoft não impõe controles de acesso com base nas configurações do Cloud App Security. Os dados de Proteção contra Ameaças da Microsoft não são afetados por essas configurações.

## <a name="related-topics"></a>Tópicos relacionados

- [Funções do Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)
- [RBAC do Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/rbac)
- [Funções do Cloud App Security](https://docs.microsoft.com/cloud-app-security/manage-admins)
