---
title: Gerenciar o consentimento do usuário para aplicativos Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: Saiba mais sobre o consentimento do usuário para aplicativos e como ativos para permitir que aplicativos de terceiros acessem as informações Microsoft 365 usuários.
ms.openlocfilehash: b8f65b50e50b0e0b4d978388463bbd380ca60d4e
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624496"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gerenciar o consentimento do usuário para aplicativos Microsoft 365

Essa configuração controla se os usuários podem dar esse consentimento aos aplicativos que usam o OpenID Conexão e o OAuth 2.0 para entrar e solicitações de acesso a dados. Um aplicativo pode ser criado de dentro de sua própria organização ou pode vir de outra Office 365 ou de terceiros.

Se você ativar essa configuração, esses aplicativos pedirão permissão aos usuários para acessar os dados da sua organização e os usuários poderão optar por permitir. Se você desativar essa configuração, os administradores devem consentir com esses aplicativos antes que os usuários possam usá-los. Nesse caso, considere configurar um fluxo de trabalho de consentimento de administrador no portal do Azure para que os usuários possam enviar uma solicitação de aprovação do administrador para usar qualquer aplicativo bloqueado.

Um usuário pode fornecer acesso somente aos aplicativos que ele possua e que acessam suas informações do Office 365. Não é possível permitir que um aplicativo acesse quaisquer outras informações do usuário.

## <a name="turning-user-consent-on-or-off"></a>A ligar ou desligar o consentimento do usuário
<a name="__toc379982114"> </a>

Veja como ativar ou desativar o consentimento do usuário para aplicativos.

1. No centro de administração, vá para a **página** Serviços de configurações Configurações Org e \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) selecione Consentimento **do usuário para aplicativos.**

2. Na página **Consentimento do usuário para aplicativos,** selecione a opção para ativar ou desativar o consentimento do usuário.

## <a name="related-content"></a>Conteúdo relacionado 
<a name="__toc379982114"> </a>

[Configurar o fluxo de trabalho de consentimento do administrador](/azure/active-directory/manage-apps/configure-admin-consent-workflow) (artigo)\
[Gerenciando o consentimento para aplicativos e avaliando solicitações de consentimento](/azure/active-directory/manage-apps/manage-consent-requests) (artigo)