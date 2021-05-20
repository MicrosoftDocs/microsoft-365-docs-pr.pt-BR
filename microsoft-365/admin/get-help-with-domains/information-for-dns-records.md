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
description: Reúna os valores/informações necessários para criar registros DNS para conectar seu domínio à Microsoft 365 assinatura.
ms.openlocfilehash: c8ff30c27e67c8a29b7122ea80a6a33f0594b1b9
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "52582951"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="29aeb-103">Coletar as informações necessárias para criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="29aeb-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="29aeb-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="29aeb-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="29aeb-105">Etapa 1: encontre o valor do registro TXT e verifique</span><span class="sxs-lookup"><span data-stu-id="29aeb-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="29aeb-106">No centro Microsoft 365 de administração,  vá para a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios de</a> Instalação.</span><span class="sxs-lookup"><span data-stu-id="29aeb-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="29aeb-107">No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios de</a> Instalação.</span><span class="sxs-lookup"><span data-stu-id="29aeb-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="29aeb-108">No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios de</a> Instalação.</span><span class="sxs-lookup"><span data-stu-id="29aeb-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="29aeb-109">Na página **Domínios,** selecione seu domínio e selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="29aeb-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="29aeb-110">Você precisará voltar para o assistente de configuração de domínios para ver o valor específico que precisa adicionar.</span><span class="sxs-lookup"><span data-stu-id="29aeb-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="29aeb-111">Na página **Verificar domínio,** selecione Adicionar um registro **TXT** em vez disso e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="29aeb-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="29aeb-112">Copie o **valor TXT** mostrado.</span><span class="sxs-lookup"><span data-stu-id="29aeb-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="29aeb-113">É assim: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="29aeb-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="29aeb-114">Vá para [Criar registros DNS em](create-dns-records-at-any-dns-hosting-provider.md)qualquer provedor de hospedagem DNS e selecione seu host DNS na lista de registradores para ver as instruções passo a passo.</span><span class="sxs-lookup"><span data-stu-id="29aeb-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="29aeb-115">Siga as etapas para criar o registro TXT (ou registro MX) em seu host DNS e verifique o domínio de volta Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29aeb-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="29aeb-116">Remova o registro TXT (ou registro MX) do host DNS depois que o domínio for verificado Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="29aeb-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="29aeb-117">Etapa 2: Encontrar o valor do registro MX para email e muito mais</span><span class="sxs-lookup"><span data-stu-id="29aeb-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="29aeb-118">No centro Microsoft 365 de administração,  vá para a página \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios de</a> Instalação.</span><span class="sxs-lookup"><span data-stu-id="29aeb-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="29aeb-119">No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domínios de</a> Instalação.</span><span class="sxs-lookup"><span data-stu-id="29aeb-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="29aeb-120">No centro de administração,  vá para a página > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domínios de</a> Instalação.</span><span class="sxs-lookup"><span data-stu-id="29aeb-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="29aeb-121">Na página **Domínios**, selecione o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="29aeb-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="29aeb-122">Em **Configurações de DNS necessárias**, você verá os registros DNS a serem adicionados.</span><span class="sxs-lookup"><span data-stu-id="29aeb-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="29aeb-123">Você deverá manter essas informações disponíveis enquanto faz alterações em seu host DNS; portanto, copie e cole os valores.</span><span class="sxs-lookup"><span data-stu-id="29aeb-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="29aeb-124">Os grupos de registros DNS listados nessa página dependem das escolhas que você listou em **Objetivo de domínio**.</span><span class="sxs-lookup"><span data-stu-id="29aeb-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="29aeb-125">Vá para Criar registros DNS em qualquer provedor de hospedagem [DNS](create-dns-records-at-any-dns-hosting-provider.md)e selecione seu host DNS na lista de registradores para ver instruções passo a passo para adicionar registros no site desse host DNS.</span><span class="sxs-lookup"><span data-stu-id="29aeb-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="29aeb-126">Siga as etapas para criar os registros em seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="29aeb-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="29aeb-127">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="29aeb-127">Related content</span></span>

<span data-ttu-id="29aeb-128">[Perguntas frequentes sobre domínios](../setup/domains-faq.yml) (artigo)</span><span class="sxs-lookup"><span data-stu-id="29aeb-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>

<span data-ttu-id="29aeb-129">[Localizar e corrigir problemas após adicionar o seu domínio ou registros DNS](find-and-fix-issues.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="29aeb-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>

<span data-ttu-id="29aeb-130">[Gerenciar domínios](index.yml) (página de link)</span><span class="sxs-lookup"><span data-stu-id="29aeb-130">[Manage domains](index.yml) (link page)</span></span>