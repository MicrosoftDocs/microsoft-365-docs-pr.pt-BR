---
title: Gerenciar o consentimento do usuário para aplicativos no Microsoft 365
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
description: Saiba mais sobre o consentimento do usuário para aplicativos e como ativos para permitir que aplicativos de terceiros acessem as informações do Microsoft 365 dos usuários.
ms.openlocfilehash: 1f6f08161d6dd85964f07ec4d48f9f2cc23a1ead
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914553"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gerenciar o consentimento do usuário para aplicativos no Microsoft 365

Essa configuração controla se os usuários podem dar esse consentimento a aplicativos que usam o OpenID Connect e o OAuth 2.0 para entrar e solicitações para acessar dados. Um aplicativo pode ser criado de dentro de sua própria organização ou pode vir de outra organização do Office 365 ou de terceiros.

Se você ativar essa configuração, esses aplicativos pedirão permissão aos usuários para acessar os dados da sua organização e os usuários poderão optar por permitir. Se você desativar essa configuração, os administradores devem consentir com esses aplicativos antes que os usuários possam usá-los. Nesse caso, considere configurar um fluxo de trabalho de consentimento de administrador no portal do Azure para que os usuários possam enviar uma solicitação de aprovação do administrador para usar qualquer aplicativo bloqueado.

Um usuário pode fornecer acesso somente aos aplicativos que ele possua e que acessam suas informações do Office 365. Não é possível permitir que um aplicativo acesse quaisquer outras informações do usuário.

## <a name="turning-user-consent-on-or-off"></a>A ligar ou desligar o consentimento do usuário
<a name="__toc379982114"> </a>

Veja como ativar ou desativar o consentimento do usuário para aplicativos.

1. No centro de administração, vá para a página **Configurações** do Serviço de configurações da Organização e \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) selecione Consentimento **do usuário para aplicativos.**

2. Na página **Consentimento do usuário para aplicativos,** selecione a opção para ativar ou desativar o consentimento do usuário.

## <a name="more-info"></a>Mais informações
<a name="__toc379982114"> </a>

Para saber mais sobre como configurar suas configurações de consentimento no Active Directory do Azure, leia [Configure the admin consent workflow](/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Para saber mais sobre como gerenciar o consentimento do usuário para aplicativos, leia [Managing consent to applications and evaluating consent requests](/azure/active-directory/manage-apps/manage-consent-requests).