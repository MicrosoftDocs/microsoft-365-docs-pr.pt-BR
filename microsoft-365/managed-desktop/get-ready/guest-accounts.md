---
title: Pré-requisitos para contas de convidados
description: Diretrizes de configuração para contas de convidado e como ajustá-las
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073184"
---
# <a name="prerequisites-for-guest-accounts"></a>Pré-requisitos para contas de convidados

A Área de Trabalho Gerenciada da Microsoft requer as seguintes configurações em sua organização do Azure AD para acesso à conta de convidado. Você pode ajustar essas configurações no [portal do Azure em](https://portal.azure.com) Identidades **Externas/Colaboração externa:**

-   **Administradores e usuários na função de convidado convidado podem convidar definido** como **Sim**
-   Para **restrições de** colaboração, escolha qualquer uma destas opções:
    -   Se você selecionar Permitir que convites sejam enviados para qualquer domínio **(mais inclusivo),** nenhuma outra configuração é necessária.
    -   Se você selecionar Negar convites para os **domínios especificados,** certifique-se de Microsoft.com não está listado nos domínios de destino.
    -   Se você selecionar Permitir convites apenas para os  **domínios especificados (mais restritivos),** certifique-se de Microsoft.com listados nos domínios de destino.

Se você definir restrições que interagem com essas configurações, certifique-se de excluir as contas do Serviço de Local de Trabalho **Moderno** do Azure Active Directory. Por exemplo, se você tiver uma política de acesso condicional que impeça contas de convidado de acessar o portal do Intune, exclua o grupo Contas de Serviço do **Local** de Trabalho Moderno dessa política.

