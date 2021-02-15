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
description: Saiba mais sobre o consentimento do usuário para aplicativos e como ativos para permitir que aplicativos de terceiros acessem as informações dos usuários do Microsoft 365.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999556"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Gerenciando o consentimento do usuário para aplicativos no Microsoft 365

Essa configuração controla se os usuários podem dar esse consentimento aos aplicativos que usam OpenID Connect e OAuth 2.0 para entrada e solicitações de acesso a dados. Um aplicativo pode ser criado de dentro de sua própria organização ou pode vir de outra organização do Office 365 ou de terceiros.

Se você ativar essa configuração, esses aplicativos solicitarão aos usuários permissão para acessar os dados da sua organização e os usuários poderão optar por permitir isso. Se você desativar essa configuração, os administradores deverão consentir com esses aplicativos antes que os usuários possam usá-los. Nesse caso, considere configurar um fluxo de trabalho de consentimento do administrador no portal do Azure para que os usuários possam enviar uma solicitação de aprovação do administrador para usar qualquer aplicativo bloqueado.

Um usuário pode fornecer acesso somente aos aplicativos que ele possua e que acessam suas informações do Office 365. Não é possível permitir que um aplicativo acesse quaisquer outras informações do usuário.

## <a name="turning-user-consent-on-or-off"></a>Como ligar ou desligar o consentimento do usuário
<a name="__toc379982114"> </a>

Veja como ativar ou desativar o consentimento do usuário para aplicativos.

1. No centro de administração, vá para a página **Serviços** de Configurações da Organização e \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) selecione Consentimento **do usuário para aplicativos.**

2. Na página **Consentimento do usuário para aplicativos,** selecione a opção para ativar ou desativar o consentimento do usuário.

## <a name="more-info"></a>Mais informações
<a name="__toc379982114"> </a>

Para saber mais sobre como definir suas configurações de consentimento no Azure Active Directory, leia Configurar o fluxo de [trabalho de consentimento do administrador.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)

Para saber mais sobre como gerenciar o consentimento do usuário para aplicativos, leia [Gerenciando o consentimento para aplicativos e avaliando solicitações de consentimento.](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)