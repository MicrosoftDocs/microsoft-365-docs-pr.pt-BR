---
title: Coletar as informações necessárias para criar registros DNS
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Saiba como encontrar os valores/informações necessários para criar registros DNS para o Microsoft 365. '
ms.openlocfilehash: 45994139b11a2fd5a03b2e979dd6af334bc1f00b
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126366"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="afa59-103">Coletar as informações necessárias para criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="afa59-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="afa59-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="afa59-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="afa59-105">Etapa 1: Encontre o valor do registro TXT e verifique</span><span class="sxs-lookup"><span data-stu-id="afa59-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="afa59-106">No centro de administração do Microsoft 365, vá para a **página** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios da</a> Instalação.</span><span class="sxs-lookup"><span data-stu-id="afa59-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="afa59-107">No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios.</a></span><span class="sxs-lookup"><span data-stu-id="afa59-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="afa59-108">No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios.</a></span><span class="sxs-lookup"><span data-stu-id="afa59-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="afa59-109">Na página **Domínios,** selecione seu domínio e, em seguida, selecione **Iniciar configuração.**</span><span class="sxs-lookup"><span data-stu-id="afa59-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="afa59-110">Você precisará voltar para o assistente de configuração de domínios para ver o valor específico que precisa adicionar.</span><span class="sxs-lookup"><span data-stu-id="afa59-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="afa59-111">Na página **Verificar domínio,** selecione **Adicionar um registro TXT** e, em seguida, **selecione Próximo.**</span><span class="sxs-lookup"><span data-stu-id="afa59-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="afa59-112">Copie o **valor TXT** mostrado.</span><span class="sxs-lookup"><span data-stu-id="afa59-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="afa59-113">Ele tem esta aparência: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="afa59-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="afa59-114">Vá para Criar registros DNS em qualquer provedor de [hospedagem DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione seu host DNS na lista de registradores para ver as instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="afa59-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="afa59-115">Siga as etapas para criar o registro TXT (ou registro MX) em seu host DNS e verifique o domínio novamente no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="afa59-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="afa59-116">Remova o registro TXT (ou registro MX) do host DNS assim que o domínio for verificado no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="afa59-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="afa59-117">Etapa 2: Encontrar o valor do registro MX para email e muito mais</span><span class="sxs-lookup"><span data-stu-id="afa59-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="afa59-118">No centro de administração do Microsoft 365, vá para a **página** Configurar \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios.</a></span><span class="sxs-lookup"><span data-stu-id="afa59-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="afa59-119">No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios.</a></span><span class="sxs-lookup"><span data-stu-id="afa59-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="afa59-120">No centro de administração, vá para a página **Configurar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios.</a></span><span class="sxs-lookup"><span data-stu-id="afa59-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="afa59-121">Na página **Domínios**, selecione o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="afa59-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="afa59-122">Em **Configurações de DNS necessárias**, você verá os registros DNS a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="afa59-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="afa59-123">Você deverá manter essas informações disponíveis enquanto faz alterações em seu host DNS; portanto, copie e cole os valores.</span><span class="sxs-lookup"><span data-stu-id="afa59-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="afa59-124">Os grupos de registros DNS listados nessa página dependem das escolhas que você listou em **Objetivo de domínio**.</span><span class="sxs-lookup"><span data-stu-id="afa59-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="afa59-125">Vá para Criar registros DNS em qualquer provedor de hospedagem [DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione seu host DNS na lista de registradores para ver instruções passo a passo para adicionar registros no site desse host DNS.</span><span class="sxs-lookup"><span data-stu-id="afa59-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="afa59-126">Siga as etapas para criar os registros em seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="afa59-126">Follow the steps for creating the records at your DNS host.</span></span>
