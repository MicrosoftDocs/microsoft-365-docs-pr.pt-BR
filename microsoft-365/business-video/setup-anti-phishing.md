---
title: Configurar a proteção contra phishing
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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Saiba como configurar a proteção contra phishing.
ms.openlocfilehash: f3a1399c8a6a51c7b14af7ffea8fbaea39cd1541
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701507"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="57c82-103">Configurar o anti-phishing</span><span class="sxs-lookup"><span data-stu-id="57c82-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="57c82-104">Phishing é um ataque mal-intencionado em que um email parece ter sido enviado por uma fonte familiar, mas ele tenta coletar suas informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="57c82-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="57c82-105">Por padrão, o Microsoft 365 inclui alguma proteção contra phishing, mas você pode aumentar essa proteção refinando as configurações.</span><span class="sxs-lookup"><span data-stu-id="57c82-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="57c82-106">Vamos dar uma olhada.</span><span class="sxs-lookup"><span data-stu-id="57c82-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="57c82-107">Experimente!</span><span class="sxs-lookup"><span data-stu-id="57c82-107">Try it!</span></span>

1. <span data-ttu-id="57c82-108">No centro de administração [https://admin.microsoft.com](https://admin.microsoft.com) , selecione **segurança**, **Gerenciamento de ameaças**, **política** e **anti-phishing ATP**.</span><span class="sxs-lookup"><span data-stu-id="57c82-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="57c82-109">Selecione **política padrão** para refinar.</span><span class="sxs-lookup"><span data-stu-id="57c82-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="57c82-110">Na seção **representação** , selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="57c82-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="57c82-111">Vá para **adicionar domínios a serem protegidos** e selecione alternar para incluir automaticamente os domínios que você possui.</span><span class="sxs-lookup"><span data-stu-id="57c82-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="57c82-112">Vá até **ações**, abra o menu suspenso **se email for enviado por um usuário representado** e escolha a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="57c82-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="57c82-113">Abra a lista suspensa **se o email for enviado por um domínio representado** e escolha a ação desejada.</span><span class="sxs-lookup"><span data-stu-id="57c82-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="57c82-114">Selecione **Ativar dicas de segurança de representação**.</span><span class="sxs-lookup"><span data-stu-id="57c82-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="57c82-115">Escolha se as dicas devem ser fornecidas aos usuários quando o sistema detectar usuários, domínios ou caracteres incomuns representados.</span><span class="sxs-lookup"><span data-stu-id="57c82-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="57c82-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="57c82-116">Select **Save**.</span></span>
1. <span data-ttu-id="57c82-117">Selecione **inteligência de caixa de correio** e verifique se ela está ativada.</span><span class="sxs-lookup"><span data-stu-id="57c82-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="57c82-118">Isso permite que seu email seja mais eficiente por padrões de uso de aprendizado.</span><span class="sxs-lookup"><span data-stu-id="57c82-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="57c82-119">Escolha **Adicionar remetentes confiáveis e domínios**.</span><span class="sxs-lookup"><span data-stu-id="57c82-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="57c82-120">Aqui você pode adicionar endereços de email ou domínios que não devem ser classificados como representação.</span><span class="sxs-lookup"><span data-stu-id="57c82-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="57c82-121">Escolha **revisar suas configurações**, verifique se tudo está correto, selecione **salvar** e **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="57c82-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="57c82-122">Agora sua organização tem melhor proteção contra ameaças de phishing.</span><span class="sxs-lookup"><span data-stu-id="57c82-122">Your organization now has better protection from phishing threats.</span></span>