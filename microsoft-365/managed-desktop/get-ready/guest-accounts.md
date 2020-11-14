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

A área de trabalho gerenciada da Microsoft exige as seguintes configurações na organização do Azure AD para acesso à conta de convidado. Você pode ajustar essas configurações no [portal do Azure](https://portal.azure.com) em **identidades externas/colaboração externa** :

-   **Administradores e usuários na função convite de convidado podem convidar** definido como **Sim**
-   Para as **restrições de colaboração** , escolha uma destas opções:
    -   Se você selecionar **permitir que os convites sejam enviados para qualquer domínio (mais inclusivo)** , nenhuma outra configuração necessária.
    -   Se você selecionar **negar convites para os domínios especificados** , certifique-se de que o Microsoft.com não esteja listado nos domínios de destino.
    -   Se você selecionar **permitir convites somente para os domínios especificados (mais restritivo)** , certifique-se de que o Microsoft.com *está* listado nos domínios de destino.

Se você definir restrições que interagem com essas configurações, certifique-se de excluir as **contas do serviço de local de trabalho moderno** do Azure Active Directory. Por exemplo, se você tem uma política de acesso condicional que impede que as contas de convidados acessem o portal do Intune, exclua o grupo de **contas de serviço de local de trabalho moderno** desta política.

