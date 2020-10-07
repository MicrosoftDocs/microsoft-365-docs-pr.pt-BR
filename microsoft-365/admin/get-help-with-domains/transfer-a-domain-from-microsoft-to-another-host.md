---
title: Transferir um domínio da Microsoft para outro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Encontre as etapas aqui para transferir um domínio da Microsoft para outro registrador. '
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370319"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="d938a-103">Transferir um domínio da Microsoft para outro host</span><span class="sxs-lookup"><span data-stu-id="d938a-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="d938a-104">Você não pode transferir um domínio do Microsoft 365 para outro registrador por 60 dias após adquirir o domínio da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d938a-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="d938a-105">Uma consulta _whois_   mostra um registrador de domínio comprado pela Microsoft como domínios com o oeste da West.</span><span class="sxs-lookup"><span data-stu-id="d938a-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="d938a-106">No entanto, somente a Microsoft deve ser contatada em relação ao seu domínio adquirido pela Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d938a-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="d938a-107">Siga estas etapas para obter um código no Microsoft 365 e, em seguida, vá para o outro site de registrador de domínio para configurar a transferência do seu nome de domínio para o novo registrador.</span><span class="sxs-lookup"><span data-stu-id="d938a-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="d938a-108">Transferir um domínio</span><span class="sxs-lookup"><span data-stu-id="d938a-108">Transfer a domain</span></span>

1. <span data-ttu-id="d938a-109">No centro de administração, vá para domínios de  **configurações**   >  **Domains**.</span><span class="sxs-lookup"><span data-stu-id="d938a-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="d938a-110">Na página **domínios** , selecione o domínio do Microsoft 365 que você deseja transferir para outro registrador de domínios e, em seguida, selecione **verificar integridade**.</span><span class="sxs-lookup"><span data-stu-id="d938a-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="d938a-111">Na parte superior da página, selecione o **domínio de transferência**.</span><span class="sxs-lookup"><span data-stu-id="d938a-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="d938a-112">Na página **escolher onde transferir o domínio** , selecione **um registrador diferente**e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d938a-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="d938a-113">Na página **desbloquear transferência de domínio** , selecione \*\*desbloquear transferência para <_seu domínio_ > \*\*e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d938a-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="d938a-114">Verifique suas informações de contato de transferência de domínio e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d938a-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="d938a-115">Copie o código de autorização e aguarde cerca de 30 minutos para que o status da transferência de domínio mude para **desbloqueado para transferência** na guia **registro** antes de prosseguir com as próximas etapas.</span><span class="sxs-lookup"><span data-stu-id="d938a-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="d938a-116">Vá para o site do registrador de domínio que você deseja gerenciar o nome de seu domínio no futuro.</span><span class="sxs-lookup"><span data-stu-id="d938a-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="d938a-117">Siga as instruções para transferir um domínio (procure ajuda no site).</span><span class="sxs-lookup"><span data-stu-id="d938a-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="d938a-118">Isso geralmente significa o pagamento das taxas de transferência e a atribuição do authcode ao novo registrador, para que eles possam iniciar a transferência.</span><span class="sxs-lookup"><span data-stu-id="d938a-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="d938a-119">A Microsoft enviará um email para confirmar que recebemos a solicitação de transferência e o domínio será transferido dentro de 5 dias.</span><span class="sxs-lookup"><span data-stu-id="d938a-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="d938a-120">Você pode encontrar a guia **registro** de código de autorização na página  **domínios** no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d938a-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d938a-121">os domínios. uk precisam de um procedimento diferente.</span><span class="sxs-lookup"><span data-stu-id="d938a-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="d938a-122">Entre em contato com o suporte da Microsoft e solicite uma **alteração na marca IPS** para corresponder ao registrador que você deseja gerenciar o seu domínio no futuro.</span><span class="sxs-lookup"><span data-stu-id="d938a-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="d938a-123">Após a alteração da marca, o domínio transfere imediatamente para o novo registrador.</span><span class="sxs-lookup"><span data-stu-id="d938a-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="d938a-124">Você precisará trabalhar com o novo registrador para concluir a transferência, provavelmente pagando as taxas de transferência e adicionando o domínio transferido à sua conta com seu novo registrador.</span><span class="sxs-lookup"><span data-stu-id="d938a-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="d938a-125">Após a conclusão da transferência, você renovará seu domínio no novo registrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="d938a-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="d938a-126">Para concluir o processo, volte para a página **domínios** no centro de administração e selecione  **transferência de domínio completo**.</span><span class="sxs-lookup"><span data-stu-id="d938a-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="d938a-127">Isso marcará o domínio como não mais comprado no Microsoft 365 e desabilitará a assinatura do domínio.</span><span class="sxs-lookup"><span data-stu-id="d938a-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="d938a-128">Ele não removerá o domínio do locatário e não afetará os usuários e caixas de correio existentes no domínio.</span><span class="sxs-lookup"><span data-stu-id="d938a-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="d938a-129">Os domínios comprados pela Microsoft 365 não estão qualificados para as alterações de nameserver ou para transferir o domínio entre as organizações do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d938a-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="d938a-130">Se uma dessas opções for obrigatória, o registro de domínio deverá ser transferido para outro registrador.</span><span class="sxs-lookup"><span data-stu-id="d938a-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
