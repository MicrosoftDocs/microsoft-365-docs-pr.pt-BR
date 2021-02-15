---
title: Adicionar um domínio
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
description: Saiba como adicionar outro domínio à sua assinatura.
ms.openlocfilehash: a5df440f3b7e28c2bdbc69f9383a8399ef193ed0
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927605"
---
# <a name="add-another-domain"></a><span data-ttu-id="b988e-103">Adicionar outro domínio</span><span class="sxs-lookup"><span data-stu-id="b988e-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="b988e-104">Sua empresa pode precisar de vários nomes de domínio para finalidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="b988e-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="b988e-105">Por exemplo, talvez você queira adicionar uma ortografia diferente do nome da sua empresa, pois os clientes já a estão usando e suas comunicações não alcançaram você.</span><span class="sxs-lookup"><span data-stu-id="b988e-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="b988e-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="b988e-106">Try it!</span></span>

1. <span data-ttu-id="b988e-107">No Centro de administração do Microsoft 365, escolha **Configuração.**</span><span class="sxs-lookup"><span data-stu-id="b988e-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="b988e-108">Em **Obter sua configuração de domínio personalizado,** selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="b988e-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="b988e-109">Escolha **Gerenciar** e, em **seguida, Adicionar domínio.**</span><span class="sxs-lookup"><span data-stu-id="b988e-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="b988e-110">Insira o novo nome de domínio que você deseja adicionar e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="b988e-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="b988e-111">Entre no registrador de domínios, neste caso, GoDaddy e selecione **Próximo.**</span><span class="sxs-lookup"><span data-stu-id="b988e-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="b988e-112">Se solicitado, entre no registrador e escolha **Autorizar.**</span><span class="sxs-lookup"><span data-stu-id="b988e-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="b988e-113">Choose **Add the DNS records for me**, and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="b988e-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="b988e-114">Escolha os serviços para seu novo domínio e des marque as caixas de seleção de todos os serviços que serão tratados por um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="b988e-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="b988e-115">Por exemplo, se você quiser usar apenas o novo domínio para email, escolha **Exchange** e des marque as caixas de seleção do **Skype for Business** e gerenciamento de dispositivos móveis para o Office **365.**</span><span class="sxs-lookup"><span data-stu-id="b988e-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="b988e-116">Selecione **Next**, **Authorize**, **Next** e, em **seguida, Finish**.</span><span class="sxs-lookup"><span data-stu-id="b988e-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="b988e-117">Seu novo domínio foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="b988e-117">Your new domain has been added.</span></span>

<span data-ttu-id="b988e-118">Para receber emails em seu novo domínio, você precisará adicionar um novo alias de email para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="b988e-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="b988e-119">Selecione **Usuários,** **Usuários Ativos** e selecione o usuário ao novo alias.</span><span class="sxs-lookup"><span data-stu-id="b988e-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="b988e-120">Escolha **Gerenciar aliases de email** e, em **seguida, adicione um alias.**</span><span class="sxs-lookup"><span data-stu-id="b988e-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="b988e-121">Insira o nome de usuário e escolha o novo domínio na lista drop-down.</span><span class="sxs-lookup"><span data-stu-id="b988e-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="b988e-122">Selecione **Salvar alterações** e feche a janela.</span><span class="sxs-lookup"><span data-stu-id="b988e-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="b988e-123">Repita essas etapas para cada usuário que deve receber emails no novo domínio.</span><span class="sxs-lookup"><span data-stu-id="b988e-123">Repeat these steps for each user who should receive email at the new domain.</span></span>