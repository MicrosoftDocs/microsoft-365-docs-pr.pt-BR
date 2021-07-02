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
ms.openlocfilehash: def9fbe201e158f1e071a67caeaf29ed26732f97
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256838"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="272a1-103">Coletar as informações necessárias para criar registros DNS</span><span class="sxs-lookup"><span data-stu-id="272a1-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="272a1-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="272a1-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="272a1-105">Etapa 1: encontre o valor do registro TXT e verifique</span><span class="sxs-lookup"><span data-stu-id="272a1-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="272a1-106">No Centro de administração do Microsoft 365, vá para **a** página Configurações \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios.</a></span><span class="sxs-lookup"><span data-stu-id="272a1-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="272a1-107">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="272a1-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="272a1-108">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="272a1-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="272a1-109">Na página **Domínios,** selecione seu domínio e selecione **Iniciar configuração**.</span><span class="sxs-lookup"><span data-stu-id="272a1-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="272a1-110">Você precisará voltar para o assistente de configuração de domínios para ver o valor específico que precisa adicionar.</span><span class="sxs-lookup"><span data-stu-id="272a1-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="272a1-111">Na página **Verificação de** Domínio, selecione Adicionar um registro **TXT** aos registros DNS do domínio e selecione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="272a1-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="272a1-112">Copie o **valor TXT** mostrado.</span><span class="sxs-lookup"><span data-stu-id="272a1-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="272a1-113">É assim: **MS=msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="272a1-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="272a1-114">Vá para [Adicionar registros DNS para conectar seu domínio](create-dns-records-at-any-dns-hosting-provider.md)e siga as etapas para adicionar registros no site do host DNS.</span><span class="sxs-lookup"><span data-stu-id="272a1-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="272a1-115">Siga as etapas para criar o registro TXT (ou registro MX) em seu host DNS e verifique o domínio de volta Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="272a1-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="272a1-116">Remova o registro TXT (ou registro MX) do host DNS depois que o domínio for verificado Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="272a1-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="272a1-117">Etapa 2: Encontrar o valor do registro MX para email e muito mais</span><span class="sxs-lookup"><span data-stu-id="272a1-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="272a1-118">No Centro de administração do Microsoft 365, vá para **a** página Configurações \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domínios.</a></span><span class="sxs-lookup"><span data-stu-id="272a1-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="272a1-119">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="272a1-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="272a1-120">No centro do administrador, acesse a página **Configurações de** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="272a1-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="272a1-121">Na página **Domínios**, selecione o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="272a1-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="272a1-122">Escolha **Gerenciar DNS,** selecione **Mais Opções** Adicionar seu próprio  >  **DNS** e selecione **Continuar** para ver os registros DNS a adicionar.</span><span class="sxs-lookup"><span data-stu-id="272a1-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="272a1-123">Você deverá manter essas informações disponíveis enquanto faz alterações em seu host DNS; portanto, copie e cole os valores.</span><span class="sxs-lookup"><span data-stu-id="272a1-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="272a1-124">Os grupos de registros DNS listados nessa página dependem das escolhas que você listou em **Objetivo de domínio**.</span><span class="sxs-lookup"><span data-stu-id="272a1-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="272a1-125">Vá para [Adicionar registros DNS para conectar seu domínio](create-dns-records-at-any-dns-hosting-provider.md)e siga as etapas para adicionar registros no site do host DNS.</span><span class="sxs-lookup"><span data-stu-id="272a1-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="272a1-126">Siga as etapas para criar os registros em seu host DNS.</span><span class="sxs-lookup"><span data-stu-id="272a1-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="272a1-127">Conteúdo relacionado</span><span class="sxs-lookup"><span data-stu-id="272a1-127">Related content</span></span>

<span data-ttu-id="272a1-128">[Perguntas frequentes sobre domínios](../setup/domains-faq.yml) (artigo)</span><span class="sxs-lookup"><span data-stu-id="272a1-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="272a1-129">[Localizar e corrigir problemas após adicionar seu domínio ou registros DNS ](find-and-fix-issues.md) (artigo)</span><span class="sxs-lookup"><span data-stu-id="272a1-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="272a1-130">[Gerenciar domínios](index.yml) (página de link)</span><span class="sxs-lookup"><span data-stu-id="272a1-130">[Manage domains](index.yml) (link page)</span></span>