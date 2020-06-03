---
title: Gerenciando o consentimento do usuário para aplicativos no Microsoft 365
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
description: Saiba mais sobre o consentimento do usuário para os aplicativos e como ativá-los para permitir que aplicativos de terceiros acessem as informações do Microsoft 365.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498312"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gerenciando o consentimento do usuário para aplicativos no Microsoft 365

Essa configuração controla se os usuários podem dar esse consentimento aos aplicativos que usam o OpenID Connect e OAuth 2,0 para entrar e solicitar o acesso aos dados. Um aplicativo pode ser criado de dentro de sua própria organização ou pode vir de outra organização do Office 365 ou de terceiros.

Se você ativar essa configuração, esses aplicativos solicitarão aos usuários permissão para acessar os dados da sua organização, e os usuários poderão escolher se desejam permiti-lo. Se você desativar essa configuração, os administradores deverão dar o consentimento para esses aplicativos antes que os usuários possam usá-los. Nesse caso, considere configurar um fluxo de trabalho de consentimento de administrador no portal do Azure para que os usuários possam enviar uma solicitação de aprovação de administrador para usar qualquer aplicativo bloqueado.

Um usuário pode fornecer acesso somente aos aplicativos que ele possua e que acessam suas informações do Office 365. Não é possível permitir que um aplicativo acesse quaisquer outras informações do usuário.

## <a name="turning-user-consent-on-or-off"></a>Ativar ou desativar o consentimento do usuário
<a name="__toc379982114"> </a>

Confira aqui como ativar ou desativar o consentimento do usuário para aplicativos.

1. No centro de administração, vá para a página **configurações** do \> **org**Settings  >  [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) e selecione **consentimento do usuário para aplicativos**.

2. Na página **consentimento do usuário para aplicativos** , selecione a opção para ativar ou desativar o consentimento do usuário.

## <a name="more-info"></a>Mais informações
<a name="__toc379982114"> </a>

Para saber mais sobre como definir suas configurações de consentimento no Azure Active Directory, leia [Configurar o fluxo de trabalho de consentimento do administrador](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).

Para saber mais sobre como gerenciar o consentimento do usuário para aplicativos, leia o [Gerenciamento de consentimento para aplicativos e avaliar solicitações de consentimento](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).