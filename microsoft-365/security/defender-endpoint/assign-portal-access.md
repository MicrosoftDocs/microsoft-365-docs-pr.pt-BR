---
title: Atribuir acesso do usuário ao Centro de Segurança do Microsoft Defender
description: Atribua acesso somente leitura e gravação ou leitura ao portal do Microsoft Defender para Ponto de Extremidade.
keywords: atribuir funções de usuário, atribuir acesso de leitura e gravação, atribuir acesso somente leitura, usuário, funções de usuário, funções
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/28/2018
ms.technology: mde
ms.openlocfilehash: 71215c4988351644cfa4d79503c097c932caf9d6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164741"
---
# <a name="assign-user-access-to-microsoft-defender-security-center"></a>Atribuir acesso do usuário ao Centro de Segurança do Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aplica-se a:**
- Azure Active Directory
- Office 365
- [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Deseja experimentar o Defender para Ponto de Extremidade? [Inscreva-se para uma avaliação gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

O Defender para Ponto de Extremidade oferece suporte a duas maneiras de gerenciar permissões:

- **Gerenciamento de permissões básicas**: definir permissões para acesso total ou somente leitura.
- Controle de acesso baseado em função **(RBAC)**: definir permissões granulares definindo funções, atribuindo grupos de usuários do Azure AD às funções e concedendo aos grupos de usuários acesso a grupos de dispositivos. Para obter mais informações sobre o RBAC, consulte [Manage portal access using role-based access control](rbac.md).

> [!NOTE]
> Se você já tiver atribuído permissões básicas, poderá alternar para o RBAC a qualquer momento. Considere o seguinte antes de fazer a opção:
> 
> - Os usuários com acesso total (usuários atribuídos à função de diretório Administrador Global ou Administrador de Segurança no Azure AD) são atribuídos automaticamente à função de administrador padrão do Defender para Ponto de Extremidade, que também tem acesso total. Grupos de usuários adicionais do Azure AD podem ser atribuídos à função de administrador do Defender for Endpoint após alternar para RBAC.  Somente os usuários atribuídos à função de administrador do Defender for Endpoint podem gerenciar permissões usando o RBAC. 
> - Os usuários que têm acesso somente leitura (Leitores de Segurança) perderão acesso ao portal até receberem uma função. Observe que somente grupos de usuários do Azure AD podem ser atribuídos a uma função em RBAC.
> - Depois de alternar para o RBAC, você não poderá voltar a usar o gerenciamento de permissões básicas.

## <a name="related-topics"></a>Tópicos relacionados

- [Usar permissões básicas para acessar o portal](basic-permissions.md)
- [Gerenciar o acesso ao portal usando o RBAC](rbac.md)
