---
title: Localizar um registrador de domínios para Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: b5b633ba-1e56-4a98-8ff5-2acaac63a5c8
description: Aprenda a localizar seu registrador de domínios e seu provedor de hospedagem de DNS usando a pesquisa do InterNIC.
ms.openlocfilehash: 71af74a0f94f2cdc251dab78fd59e9bdd90da5ce
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/09/2020
ms.locfileid: "43210387"
---
# <a name="find-your-domain-registrar-for-office-365"></a><span data-ttu-id="51a1f-103">Localizar um registrador de domínios para Office 365</span><span class="sxs-lookup"><span data-stu-id="51a1f-103">Find your domain registrar for Office 365</span></span>

 <span data-ttu-id="51a1f-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="51a1f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="51a1f-105">Registrador de domínios</span><span class="sxs-lookup"><span data-stu-id="51a1f-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="51a1f-106">Localizar o registrador de nomes de domínio</span><span class="sxs-lookup"><span data-stu-id="51a1f-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="51a1f-107">Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="51a1f-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="51a1f-108">Na [página de pesquisa do InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio.</span><span class="sxs-lookup"><span data-stu-id="51a1f-108">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="51a1f-109">Por exemplo,  *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="51a1f-109">For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="51a1f-110">Selecione a opção **Domínio** e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="51a1f-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="51a1f-111">Na página **Whois Search Results**, localize a entrada **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="51a1f-111">On the **Whois Search Results** page, locate the **Registrar** entry.</span></span> <span data-ttu-id="51a1f-112">Ela informará a organização que presta o serviço de registrador para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="51a1f-112">This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="51a1f-113">Provedor de hospedagem de DNS</span><span class="sxs-lookup"><span data-stu-id="51a1f-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="51a1f-114">Localizar o provedor de hospedagem de DNS</span><span class="sxs-lookup"><span data-stu-id="51a1f-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="51a1f-115">Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="51a1f-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="51a1f-116">Na [página de pesquisa do InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio.</span><span class="sxs-lookup"><span data-stu-id="51a1f-116">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain.</span></span> <span data-ttu-id="51a1f-117">Por exemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="51a1f-117">For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="51a1f-118">Selecione a opção **Domínio** e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="51a1f-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="51a1f-119">Na página **Whois Search Results**, localize a primeira entrada em **Name Server**.</span><span class="sxs-lookup"><span data-stu-id="51a1f-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="51a1f-120">Copie o NS (servidor de nomes) que aparece depois dos dois-pontos (:) e cole-o na caixa **Search**, na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="51a1f-120">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page.</span></span> <span data-ttu-id="51a1f-121">Selecione **Nameserver** e depois selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="51a1f-121">Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="51a1f-p105">Na página **Whois Search Results**, localize a entrada **Registrar**. Ela informará o provedor de hospedagem de DNS, o provedor de DNS a que pertence o servidor de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="51a1f-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

