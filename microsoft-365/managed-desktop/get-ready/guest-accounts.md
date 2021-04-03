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
ms.openlocfilehash: bbf679a01716fc48d37b241d69740f50a985f048
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574602"
---
# <a name="prerequisites-for-guest-accounts"></a>Pré-requisitos para contas de convidados

A Área de Trabalho Gerenciada da Microsoft requer as seguintes configurações em sua organização do Azure AD para acesso à conta de convidado. Você pode ajustar essas configurações no [portal do Azure](https://portal.azure.com) em **Identidades Externas / Colaboração externa**:

-   **Administradores e usuários na função de convidado convidado podem convidar definido** como **Sim**
-   Para **restrições de** colaboração, escolha qualquer uma dessas opções:
    -   Se você selecionar Permitir que convites sejam enviados para **qualquer domínio (mais inclusivo),** nenhuma outra configuração será necessária.
    -   Se você selecionar Negar convites para **os domínios especificados,** certifique-se de Microsoft.com não está listado nos domínios de destino.
    -   Se você selecionar Permitir convites somente para os **domínios especificados (mais restritivos),** certifique-se de Microsoft.com *está* listado nos domínios de destino.

Se você definir restrições que interagem com essas configurações, certifique-se de excluir as Contas de Serviço de Local de Trabalho Modernas **do** Azure Active Directory. Por exemplo, se você tiver uma política de acesso condicional que impeça que  contas de convidado acessem o portal do Intune, exclua o grupo Contas de Serviço de Trabalho Moderno dessa política.

## <a name="steps-to-get-ready"></a>Etapas para se preparar

1. Revise [os pré-requisitos da Área de Trabalho Gerenciada da Microsoft.](prerequisites.md)
2. Use [ferramentas de avaliação de preparação.](readiness-assessment-tool.md)
3. [Pré-requisitos para contas de convidado](guest-accounts.md) (Este artigo)
4. [Configuração de rede na Área de Trabalho Gerenciada da Microsoft](network.md)
5. [Preparar certificados e perfis de rede da Área de Trabalho Gerenciada da Microsoft](certs-wifi-lan.md)
6. [Preparar o acesso aos recursos locais da Área de Trabalho Gerenciada da Microsoft](authentication.md)
7. [Aplicativos na Área de Trabalho Gerenciada da Microsoft](apps.md)
8. [Preparar unidades mapeadas da Área de Trabalho Gerenciada da Microsoft](mapped-drives.md)
9. [Preparar recursos de impressão da Área de Trabalho Gerenciada da Microsoft](printing.md)