---
title: Configurar a proteção anti-phishing
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como configurar a proteção anti-phishing.
ms.openlocfilehash: bcb6b8bac316b4b74c505656cb9a93e7a87e0830
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927869"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="ce45f-103">Configurar anti-phishing</span><span class="sxs-lookup"><span data-stu-id="ce45f-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="ce45f-104">Phishing é um ataque mal-intencionado em que um email parece ter sido enviado de uma fonte familiar, mas tenta coletar suas informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="ce45f-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="ce45f-105">Por padrão, o Microsoft 365 inclui alguma proteção anti-phishing, mas você pode aumentar essa proteção refinando as configurações.</span><span class="sxs-lookup"><span data-stu-id="ce45f-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="ce45f-106">Vamos dar uma olhada.</span><span class="sxs-lookup"><span data-stu-id="ce45f-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="ce45f-107">Experimente!</span><span class="sxs-lookup"><span data-stu-id="ce45f-107">Try it!</span></span>

1. <span data-ttu-id="ce45f-108">No centro de administração em [https://admin.microsoft.com](https://admin.microsoft.com) , selecione **Segurança**, Gerenciamento **de Ameaças**, **Política**, depois **ATP Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="ce45f-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="ce45f-109">Selecione **Política Padrão** para refiná-la.</span><span class="sxs-lookup"><span data-stu-id="ce45f-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="ce45f-110">Na seção **Representação,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ce45f-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="ce45f-111">Vá para **Adicionar domínios para proteger** e selecione a alternância para incluir automaticamente os domínios que você possui.</span><span class="sxs-lookup"><span data-stu-id="ce45f-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="ce45f-112">Vá para **Ações**, abra o drop-down **se o email** for enviado por um usuário personificado e escolha a ação que você deseja.</span><span class="sxs-lookup"><span data-stu-id="ce45f-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="ce45f-113">Abra o drop-down se o email for enviado por um domínio **personificado** e escolha a ação que você deseja.</span><span class="sxs-lookup"><span data-stu-id="ce45f-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="ce45f-114">Selecione **Ativar dicas de segurança de representação.**</span><span class="sxs-lookup"><span data-stu-id="ce45f-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="ce45f-115">Escolha se as dicas devem ser fornecidas aos usuários quando o sistema detectar usuários, domínios ou caracteres incomuns.</span><span class="sxs-lookup"><span data-stu-id="ce45f-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="ce45f-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ce45f-116">Select **Save**.</span></span>
1. <span data-ttu-id="ce45f-117">Selecione **a inteligência de** caixa de correio e verifique se ela está turned on.</span><span class="sxs-lookup"><span data-stu-id="ce45f-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="ce45f-118">Isso permite que seu email seja mais eficiente por meio de padrões de uso de aprendizagem.</span><span class="sxs-lookup"><span data-stu-id="ce45f-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="ce45f-119">Choose **Add trusted senders and domains**.</span><span class="sxs-lookup"><span data-stu-id="ce45f-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="ce45f-120">Aqui você pode adicionar endereços de email ou domínios que não devem ser classificados como uma representação.</span><span class="sxs-lookup"><span data-stu-id="ce45f-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="ce45f-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span><span class="sxs-lookup"><span data-stu-id="ce45f-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="ce45f-122">Sua organização agora tem melhor proteção contra ameaças de phishing.</span><span class="sxs-lookup"><span data-stu-id="ce45f-122">Your organization now has better protection from phishing threats.</span></span>