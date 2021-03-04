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
description: Saiba como configurar a proteção anti-phishing.
ms.openlocfilehash: 8cef8f916a8a3e2b27dd7f76ddecd921d59ca0c4
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421998"
---
# <a name="set-up-anti-phishing"></a><span data-ttu-id="fe6fa-103">Configurar anti-phishing</span><span class="sxs-lookup"><span data-stu-id="fe6fa-103">Set up anti-phishing</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvt9r?autoplay=false]

<span data-ttu-id="fe6fa-104">Phishing é um ataque mal-intencionado em que um email parece ter sido enviado de uma fonte familiar, mas tenta coletar suas informações pessoais.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-104">Phishing is a malicious attack where an email looks like it was sent from a familiar source, but it attempts to collect your personal information.</span></span> <span data-ttu-id="fe6fa-105">Por padrão, o Microsoft 365 inclui alguma proteção anti-phishing, mas você pode aumentar essa proteção refinando as configurações.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-105">By default, Microsoft 365 includes some anti-phishing protection, but you can increase that protection by refining the settings.</span></span> <span data-ttu-id="fe6fa-106">Vamos dar uma olhada.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-106">Let's take a look.</span></span>

## <a name="try-it"></a><span data-ttu-id="fe6fa-107">Experimente!</span><span class="sxs-lookup"><span data-stu-id="fe6fa-107">Try it!</span></span>

1. <span data-ttu-id="fe6fa-108">No centro de administração em [https://admin.microsoft.com](https://admin.microsoft.com) , selecione **Segurança,** **Gerenciamento de Ameaças**, **Política**, em **seguida, ATP Anti-phishing**.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-108">In the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), select **Security**, **Threat Management**, **Policy**, then **ATP Anti-phishing**.</span></span>
1. <span data-ttu-id="fe6fa-109">Selecione **Política Padrão** para refiná-la.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-109">Select **Default Policy** to refine it.</span></span>
1. <span data-ttu-id="fe6fa-110">Na seção **Representação,** selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-110">In the **Impersonation** section, select **Edit**.</span></span>
1. <span data-ttu-id="fe6fa-111">Vá para **Adicionar domínios para proteger** e selecione a alternância para incluir automaticamente os domínios que você possui.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-111">Go to **Add domains to protect** and select the toggle to automatically include the domains you own.</span></span>
1. <span data-ttu-id="fe6fa-112">Vá para **Ações**, abra o drop-down **Se o email** for enviado por um usuário personificado, escolha a ação que você deseja.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-112">Go to **Actions**, open the drop-down **If email is sent by an impersonated user**, and choose the action you want.</span></span>

    <span data-ttu-id="fe6fa-113">Abra o drop-down Se o email for enviado por um domínio **personificado** e escolher a ação que você deseja.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-113">Open the drop-down **If email is sent by an impersonated domain** and choose the action you want.</span></span>
1. <span data-ttu-id="fe6fa-114">Selecione **Ativar dicas de segurança de representação.**</span><span class="sxs-lookup"><span data-stu-id="fe6fa-114">Select **Turn on impersonation safety tips**.</span></span> <span data-ttu-id="fe6fa-115">Escolha se as dicas devem ser fornecidas aos usuários quando o sistema detectar usuários, domínios ou caracteres incomuns.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-115">Choose whether tips should be provided to users when the system detects impersonated users, domains, or unusual characters.</span></span> <span data-ttu-id="fe6fa-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-116">Select **Save**.</span></span>
1. <span data-ttu-id="fe6fa-117">Selecione **Inteligência de Caixa** de Correio e verifique se ele está ligado.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-117">Select **Mailbox intelligence** and verify that it's turned on.</span></span> <span data-ttu-id="fe6fa-118">Isso permite que seu email seja mais eficiente aprendendo padrões de uso.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-118">This allows your email to be more efficient by learning usage patterns.</span></span>
1. <span data-ttu-id="fe6fa-119">Escolha **Adicionar senders e domínios confiáveis.**</span><span class="sxs-lookup"><span data-stu-id="fe6fa-119">Choose **Add trusted senders and domains**.</span></span> <span data-ttu-id="fe6fa-120">Aqui você pode adicionar endereços de email ou domínios que não devem ser classificados como uma representação.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-120">Here you can add email addresses or domains that shouldn't be classified as an impersonation.</span></span>
1. <span data-ttu-id="fe6fa-121">Escolha **Revisar suas configurações,** certifique-se de que tudo está correto, selecione **Salvar**, em **seguida, Feche**.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-121">Choose **Review your settings**, make sure everything is correct, select **Save**, then **Close**.</span></span>

    <span data-ttu-id="fe6fa-122">Sua organização agora tem melhor proteção contra ameaças de phishing.</span><span class="sxs-lookup"><span data-stu-id="fe6fa-122">Your organization now has better protection from phishing threats.</span></span>