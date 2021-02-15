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
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a><span data-ttu-id="fe1c4-103">Gerenciando o consentimento do usuário para aplicativos no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fe1c4-103">Managing user consent to apps in Microsoft 365</span></span>

<span data-ttu-id="fe1c4-104">Essa configuração controla se os usuários podem dar esse consentimento aos aplicativos que usam OpenID Connect e OAuth 2.0 para entrada e solicitações de acesso a dados.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-104">This setting controls whether users can give that consent to apps that use OpenID Connect and OAuth 2.0 for sign-in and requests to access data.</span></span> <span data-ttu-id="fe1c4-105">Um aplicativo pode ser criado de dentro de sua própria organização ou pode vir de outra organização do Office 365 ou de terceiros.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-105">An app can be created from within your own organization, or it can come from another Office 365 organization or a third-party.</span></span>

<span data-ttu-id="fe1c4-106">Se você ativar essa configuração, esses aplicativos solicitarão aos usuários permissão para acessar os dados da sua organização e os usuários poderão optar por permitir isso.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-106">If you turn this setting on, those apps will ask users for permission to access your organization’s data, and users can choose whether to allow it.</span></span> <span data-ttu-id="fe1c4-107">Se você desativar essa configuração, os administradores deverão consentir com esses aplicativos antes que os usuários possam usá-los.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-107">If you turn this setting off, then admins must consent to those apps before users may use them.</span></span> <span data-ttu-id="fe1c4-108">Nesse caso, considere configurar um fluxo de trabalho de consentimento do administrador no portal do Azure para que os usuários possam enviar uma solicitação de aprovação do administrador para usar qualquer aplicativo bloqueado.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-108">In this case, consider setting up an admin consent workflow in the Azure portal so users can send a request for admin approval to use any blocked app.</span></span>

<span data-ttu-id="fe1c4-109">Um usuário pode fornecer acesso somente aos aplicativos que ele possua e que acessam suas informações do Office 365.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-109">A user can give access only to apps they own that access their Office 365 information.</span></span> <span data-ttu-id="fe1c4-110">Não é possível permitir que um aplicativo acesse quaisquer outras informações do usuário.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-110">They can't give an app access to any other user's information.</span></span>

## <a name="turning-user-consent-on-or-off"></a><span data-ttu-id="fe1c4-111">Como ligar ou desligar o consentimento do usuário</span><span class="sxs-lookup"><span data-stu-id="fe1c4-111">Turning user consent on or off</span></span>
<span data-ttu-id="fe1c4-112"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="fe1c4-112"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="fe1c4-113">Veja como ativar ou desativar o consentimento do usuário para aplicativos.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-113">Here's how to turn User consent to apps on or off.</span></span>

1. <span data-ttu-id="fe1c4-114">No centro de administração, vá para a página **Serviços** de Configurações da Organização e \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) selecione Consentimento **do usuário para aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="fe1c4-114">In the admin center, go to the **Settings** \> **Org settings** > [Services](https://go.microsoft.com/fwlink/p/?linkid=2053743) page, and then select **User consent to apps**.</span></span>

2. <span data-ttu-id="fe1c4-115">Na página **Consentimento do usuário para aplicativos,** selecione a opção para ativar ou desativar o consentimento do usuário.</span><span class="sxs-lookup"><span data-stu-id="fe1c4-115">On the **User consent to apps** page, select the option to turn user consent on or off.</span></span>

## <a name="more-info"></a><span data-ttu-id="fe1c4-116">Mais informações</span><span class="sxs-lookup"><span data-stu-id="fe1c4-116">More info</span></span>
<span data-ttu-id="fe1c4-117"><a name="__toc379982114"> </a></span><span class="sxs-lookup"><span data-stu-id="fe1c4-117"><a name="__toc379982114"> </a></span></span>

<span data-ttu-id="fe1c4-118">Para saber mais sobre como definir suas configurações de consentimento no Azure Active Directory, leia Configurar o fluxo de [trabalho de consentimento do administrador.](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)</span><span class="sxs-lookup"><span data-stu-id="fe1c4-118">To learn about how to configure your consent settings in Azure active directory, read [Configure the admin consent workflow](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow).</span></span>

<span data-ttu-id="fe1c4-119">Para saber mais sobre como gerenciar o consentimento do usuário para aplicativos, leia [Gerenciando o consentimento para aplicativos e avaliando solicitações de consentimento.](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)</span><span class="sxs-lookup"><span data-stu-id="fe1c4-119">To learn about managing user consent to apps, read [Managing consent to applications and evaluating consent requests](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests).</span></span>