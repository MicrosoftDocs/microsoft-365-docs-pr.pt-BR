---
title: Localizar seu registrador de domínio
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a localizar seu registrador de domínios e seu provedor de hospedagem de DNS usando a pesquisa do InterNIC.
ms.openlocfilehash: ac405a2aa6a4595c301dae16c27025cfe97c9902
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399927"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="564a5-103">Localizar seu registrador de domínio</span><span class="sxs-lookup"><span data-stu-id="564a5-103">Find your domain registrar</span></span>

 <span data-ttu-id="564a5-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="564a5-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="564a5-105">Registrador de domínios</span><span class="sxs-lookup"><span data-stu-id="564a5-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="564a5-106">Localizar o registrador de nomes de domínio</span><span class="sxs-lookup"><span data-stu-id="564a5-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="564a5-107">Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="564a5-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="564a5-108">Na [página de pesquisa do InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio.</span><span class="sxs-lookup"><span data-stu-id="564a5-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="564a5-109">Por exemplo,  *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="564a5-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="564a5-110">Selecione a opção **Domínio** e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="564a5-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="564a5-111">Na página **Whois Search Results**, localize a entrada **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="564a5-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="564a5-112">Ela informará a organização que presta o serviço de registrador para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="564a5-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="564a5-113">Provedor de hospedagem de DNS</span><span class="sxs-lookup"><span data-stu-id="564a5-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="564a5-114">Localizar o provedor de hospedagem de DNS</span><span class="sxs-lookup"><span data-stu-id="564a5-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="564a5-115">Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="564a5-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="564a5-116">Na [página de pesquisa do InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio.</span><span class="sxs-lookup"><span data-stu-id="564a5-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="564a5-117">Por exemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="564a5-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="564a5-118">Selecione a opção **Domínio** e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="564a5-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="564a5-119">Na página **Whois Search Results**, localize a primeira entrada em **Name Server**.</span><span class="sxs-lookup"><span data-stu-id="564a5-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="564a5-120">Copie o NS (servidor de nomes) que aparece depois dos dois-pontos (:) e cole-o na caixa **Search**, na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="564a5-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="564a5-121">Selecione **Nameserver** e depois selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="564a5-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="564a5-p105">Na página **Whois Search Results**, localize a entrada **Registrar**. Ela informará o provedor de hospedagem de DNS, o provedor de DNS a que pertence o servidor de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="564a5-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

