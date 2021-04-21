---
title: Adicionar um domínio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
description: Saiba como adicionar outro domínio à sua assinatura.
ms.openlocfilehash: a641005913f7dfd866366f0f8065019dd5c17fe8
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903737"
---
# <a name="add-another-domain"></a><span data-ttu-id="1a272-103">Adicionar outro domínio</span><span class="sxs-lookup"><span data-stu-id="1a272-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="1a272-104">Sua empresa pode precisar de vários nomes de domínio para finalidades diferentes.</span><span class="sxs-lookup"><span data-stu-id="1a272-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="1a272-105">Por exemplo, talvez você queira adicionar uma ortografia diferente do nome da sua empresa, pois os clientes já o estão usando e suas comunicações falharam ao entrar em contato com você.</span><span class="sxs-lookup"><span data-stu-id="1a272-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="1a272-106">Experimente!</span><span class="sxs-lookup"><span data-stu-id="1a272-106">Try it!</span></span>

1. <span data-ttu-id="1a272-107">No Centro de administração do Microsoft 365, escolha **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="1a272-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="1a272-108">Em **Obter sua configuração de domínio personalizado,** selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="1a272-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="1a272-109">Escolha **Gerenciar** e, em seguida, **Adicionar domínio**.</span><span class="sxs-lookup"><span data-stu-id="1a272-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="1a272-110">Insira o novo nome de domínio que você deseja adicionar e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="1a272-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="1a272-111">Entre no registrador de domínios, nesse caso, GoDaddy e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="1a272-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="1a272-112">Se solicitado, entre no registrador e escolha **Autorizar**.</span><span class="sxs-lookup"><span data-stu-id="1a272-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="1a272-113">Escolha **Adicionar os registros DNS para mim** e selecione **Next**.</span><span class="sxs-lookup"><span data-stu-id="1a272-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="1a272-114">Escolha os serviços para seu novo domínio e desempure as caixas de seleção de todos os serviços que serão manipulados por um domínio diferente.</span><span class="sxs-lookup"><span data-stu-id="1a272-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="1a272-115">Por exemplo, se você quiser apenas usar o novo domínio para email, escolha **Exchange** e des limpar as caixas de seleção do **Skype for Business** e gerenciamento de dispositivos móveis para o Office **365**.</span><span class="sxs-lookup"><span data-stu-id="1a272-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="1a272-116">Selecione **Próximo,** **Autorizar**, **Próximo** e, em **seguida, Concluir**.</span><span class="sxs-lookup"><span data-stu-id="1a272-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="1a272-117">Seu novo domínio foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="1a272-117">Your new domain has been added.</span></span>

<span data-ttu-id="1a272-118">Para receber emails em seu novo domínio, você precisará adicionar um novo alias de email para cada usuário:</span><span class="sxs-lookup"><span data-stu-id="1a272-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="1a272-119">Selecione **Usuários,** **Usuários ativos** e selecione o usuário que receberá o novo alias.</span><span class="sxs-lookup"><span data-stu-id="1a272-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="1a272-120">Escolha **Gerenciar aliases de email** e adicione um **alias**.</span><span class="sxs-lookup"><span data-stu-id="1a272-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="1a272-121">Insira o nome de usuário e escolha o novo domínio na listada.</span><span class="sxs-lookup"><span data-stu-id="1a272-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="1a272-122">Selecione **Salvar alterações** e feche a janela.</span><span class="sxs-lookup"><span data-stu-id="1a272-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="1a272-123">Repita estas etapas para cada usuário que deve receber emails no novo domínio.</span><span class="sxs-lookup"><span data-stu-id="1a272-123">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="1a272-124">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="1a272-124">Related content</span></span>

<span data-ttu-id="1a272-125">Adicionar um domínio ao [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (artigo) Adicionar registros [DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) para conectar seu domínio (artigo) Alterar nameservers para configurar o [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) com qualquer registrador de domínios (artigo) [Perguntas frequentes](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) sobre domínios (artigo)</span><span class="sxs-lookup"><span data-stu-id="1a272-125">[Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (article) [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) (article) [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) (article) [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article)</span></span>