---
title: Sobre as funções de administrador Intune no Centro de administração do Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: As funções de administrador são mapeadas para as funções de negócios e oferecem permissões para realizar tarefas específicas no centro de administração. Por exemplo, o administrador do serviço abre tíquetes de suporte da Microsoft.
ms.openlocfilehash: 48bb0f3d1a3a239025017fda261945094a3eda79
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126076"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Funções de administrador Intune no Centro de administração do Microsoft 365

Sua assinatura do Microsoft 365 ou do Office 365 acompanha um conjunto de funções de administrador que você pode atribuir aos usuários em sua organização usando o Centro de administração do Microsoft 365. Cada função de administrador é mapeada para uma função de negócios comum da empresa e concede permissões para a realização de tarefas específicas nos centros de administração.

O Centro de administração do Microsoft 365 permite gerenciar as funções do Microsoft Intune. No entanto, essas funções são um subconjunto das funções disponíveis no centro de administração do Intune. Procurando as descrições de função detalhadas do Microsoft Intune? Confira [Controle de acesso baseado em função (RBAC) com o Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Para obter mais informações sobre como atribuir funções no Centro de administração do Microsoft 365, confira [Atribuir funções de administrador](assign-admin-roles.md).

::: moniker range="o365-worldwide"

No Centro de administração do Microsoft 365, você pode acessar **Funções** e, em seguida, selecionar qualquer função para abrir seu painel de detalhes. Selecione a guia **Permissões** para exibir a lista detalhada do que os administradores com aquela função têm permissão para fazer. Marque a guia **Atribuir** ou **Administradores atribuídos** para adicionar usuários a funções.

::: moniker-end

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Funções do Microsoft Intune disponíveis no Centro de administração do Microsoft 365

|Função do administrador     |Quem deve ser atribuído com esta função?  |
|---------|---------|
|Gerente de aplicativos     |   Atribuir a função Gerente de aplicativos a usuários que gerenciam o ciclo de vida do aplicativo para aplicativos móveis, configuram aplicativos gerenciados por política e exibem informações sobre os dispositivos e perfis de configuração.  |
|Operador de suporte técnico     |   Atribua a função de operador de suporte técnico a usuários que atribuem aplicativos e políticas a usuários e dispositivos. |
|Administrador de função Intune    |   Atribua o administrador de função do Intune a usuários que podem atribuir permissões do Intune a outros administradores e podem gerenciar funções personalizadas e internas do Intune.   |
|Gerente de Política e Perfil     |   Atribua a função Gerente de Política e Perfil aos usuários para gerenciar políticas de conformidade, perfis de configuração e registro da Apple.   |
|Operador Somente Leitura     |   Atribua a função operador somente leitura para os usuários que só podem visualizar usuários, dispositivos, detalhes de registro e configurações.   |
|Administrador escolar     |   Atribua a função de administrador escolar aos usuários para obter acesso total para gerenciar dispositivos Windows 10 e iOS, aplicativos e configurações no Intune for Education.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Administração delegada para parceiros da Microsoft

Se você está trabalhando com um parceiro da Microsoft, pode atribua funções administrativas a ele. Ele, por sua vez, pode atribuir funções administrativas a usuários em sua empresa (ou nas empresas deles). Isso pode ser conveniente, por exemplo, se ele estiver configurando e gerenciando a sua organização online para você.
  
Um parceiro pode atribuir estas funções: 
  
- Administração total, que tem privilégios equivalentes a um administrador global, com exceção de gerenciamento da autenticação multifatorial pelo Partner Center.

- Administração limitada, que tem privilégios equivalentes à administração de help desk.

Antes que o parceiro possa atribuir funções aos usuários, é preciso adicioná-lo como administrador delegado à sua conta. Esse processo é iniciado por um parceiro autorizado.O parceiro envia um email perguntando se você deseja conceder permissão a ele para atuar como administrador delegado. Para obter instruções, confira [Autorizar ou remover relações de parceiro](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner).
  
## <a name="related-articles"></a>Artigos relacionados

[Sobre as funções de administrador do Microsoft 365 ](about-admin-roles.md)

[Atribuir funções de administrador](assign-admin-roles.md)

[Relatórios de atividades no centro de administração do Microsoft 365](../activity-reports/activity-reports.md)