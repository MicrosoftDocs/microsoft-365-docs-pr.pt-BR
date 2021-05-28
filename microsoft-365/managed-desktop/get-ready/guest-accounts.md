---
title: Pré-requisitos para contas de convidados
description: Diretrizes de configuração para contas de convidados e como ajustá-las
keywords: Área de Trabalho Gerenciada da Microsoft, Microsoft 365, serviço, documentação
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d29b9d6bdc30d981b273d95925ba740bc92304c4
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694240"
---
# <a name="prerequisites-for-guest-accounts"></a>Pré-requisitos para contas de convidados

Área de Trabalho Gerenciada da Microsoft requer as seguintes configurações em sua organização do Azure AD para acesso à conta de convidado. Você pode ajustar essas configurações no [portal do Azure](https://portal.azure.com) em **Identidades Externas / Configurações de colaboração externa:**

-   Para **restrições de convite de** convidado definidas para usuários membros e usuários atribuídos a funções de administrador específicas podem convidar usuários **convidados,** incluindo convidados com permissões de membro
-   Para **restrições de** colaboração, escolha qualquer uma dessas opções:
    -   Se você selecionar Permitir que convites sejam enviados para **qualquer domínio (mais inclusivo),** nenhuma outra configuração será necessária.
    -   Se você selecionar Negar convites para **os domínios especificados,** certifique-se de Microsoft.com não está listado nos domínios de destino.
    -   Se você selecionar Permitir convites somente para os **domínios especificados (mais restritivos),** certifique-se de Microsoft.com *está* listado nos domínios de destino.

Se você definir restrições que interagem com essas configurações, certifique-se de excluir as Azure Active Directory Contas de Serviço de Local de **Trabalho Modernas.** Por exemplo, se você tiver uma política de acesso condicional que impeça que  contas de convidado acessem o portal do Intune, exclua o grupo Contas de Serviço de Trabalho Moderno dessa política.

## <a name="steps-to-get-ready"></a>Etapas para se preparar

1. Revise [pré-requisitos da Área de Trabalho Gerenciada da Microsoft](prerequisites.md).
2. Use [de avaliação de preparação](readiness-assessment-tool.md).
3. [Pré-requisitos para contas de convidado](guest-accounts.md) (Este artigo)
4. [Configuração de rede na Área de Trabalho Gerenciada da Microsoft](network.md)
5. [Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md)
6. [Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft](authentication.md)
7. [Aplicativos na Área de Trabalho Gerenciada da Microsoft](apps.md)
8. [Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)
9. [Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft](printing.md)
