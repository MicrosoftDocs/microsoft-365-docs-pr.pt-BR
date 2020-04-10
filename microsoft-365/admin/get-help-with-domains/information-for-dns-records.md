---
title: Coletar as informações de que você precisa para criar registros de DNS do Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Saiba como localizar os valores/informações de que você precisa para criar registros DNS para o Office 365. '
ms.custom: okr_smb
ms.openlocfilehash: 2490532894ef00bab5de3f406b0c104529423382
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210375"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="defca-103">Coletar as informações de que você precisa para criar registros de DNS do Office 365</span><span class="sxs-lookup"><span data-stu-id="defca-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="defca-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="defca-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="defca-105">Etapa 1: localizar o valor do registro TXT e verificar</span><span class="sxs-lookup"><span data-stu-id="defca-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="defca-106">No centro de administração do Microsoft 365, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="defca-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker range="o365-germany"

1. <span data-ttu-id="defca-107">No centro de administração, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="defca-107">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="defca-108">No centro de administração, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="defca-108">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="defca-109">Na página **domínios** , selecione seu domínio e, em seguida, selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="defca-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="defca-110">Você precisará voltar para o assistente de configuração de domínios para ver o valor específico que precisa adicionar.</span><span class="sxs-lookup"><span data-stu-id="defca-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="defca-111">Na página **verificar domínio** , selecione **Adicionar um registro txt**e, em seguida, selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="defca-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="defca-112">Copie o **valor txt** mostrado.</span><span class="sxs-lookup"><span data-stu-id="defca-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="defca-113">Ele tem a seguinte aparência: **MS = msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="defca-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="defca-114">Vá para [criar registros DNS em qualquer provedor de Hospedagem de DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione o seu host DNS na lista de registradores para ver as instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="defca-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="defca-115">Siga as etapas para criar o registro TXT (ou o registro MX) em seu host DNS e verifique o domínio em Office 365.</span><span class="sxs-lookup"><span data-stu-id="defca-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="defca-116">Remova o registro TXT (ou o registro MX) do seu host DNS depois que o domínio for verificado no Office 365.</span><span class="sxs-lookup"><span data-stu-id="defca-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="defca-117">Etapa 2: localizar o valor de registro MX para email e muito mais</span><span class="sxs-lookup"><span data-stu-id="defca-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="defca-118">No centro de administração do Microsoft 365, vá para a página **Configurar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="defca-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
::: moniker range="o365-germany"

1. <span data-ttu-id="defca-119">No centro de administração, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="defca-119">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="defca-120">No centro de administração, acesse a página <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a> .</span><span class="sxs-lookup"><span data-stu-id="defca-120">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="defca-121">Na página **Domínios**, selecione o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="defca-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="defca-122">Em **Configurações de DNS necessárias**, você verá os registros DNS a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="defca-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="defca-123">Você deverá manter essas informações disponíveis enquanto faz alterações em seu host DNS; portanto, copie e cole os valores.</span><span class="sxs-lookup"><span data-stu-id="defca-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="defca-124">Os grupos de registros DNS listados nessa página dependem das escolhas que você listou em **Objetivo de domínio**.</span><span class="sxs-lookup"><span data-stu-id="defca-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="defca-125">Vá para [criar registros DNS em qualquer provedor de Hospedagem de DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione o seu host DNS na lista de registradores para ver instruções passo a passo para adicionar registros no site do host DNS.</span><span class="sxs-lookup"><span data-stu-id="defca-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="defca-126">Siga as etapas para criar os registros em seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="defca-126">Follow the steps for creating the records at your DNS host.</span></span>
