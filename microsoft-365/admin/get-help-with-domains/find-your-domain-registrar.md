---
title: Localizar seu registrador de domínio
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.openlocfilehash: af883f53c8c45aee2594b0f5b8b9da57e5717f9e
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706389"
---
# <a name="find-your-domain-registrar"></a><span data-ttu-id="d17ab-103">Localizar seu registrador de domínio</span><span class="sxs-lookup"><span data-stu-id="d17ab-103">Find your domain registrar</span></span>

 <span data-ttu-id="d17ab-104">Caso não encontre o conteúdo que está procurando, **[verifique as perguntas frequentes sobre domínios](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="d17ab-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
## <a name="domain-registrar"></a><span data-ttu-id="d17ab-105">Registrador de domínios</span><span class="sxs-lookup"><span data-stu-id="d17ab-105">Domain registrar</span></span>
  
### <a name="find-your-domain-name-registrar"></a><span data-ttu-id="d17ab-106">Localizar o registrador de nomes de domínio</span><span class="sxs-lookup"><span data-stu-id="d17ab-106">Find your domain name registrar</span></span>

>[!NOTE]
> <span data-ttu-id="d17ab-107">Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="d17ab-107">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="d17ab-p101">Na [página de pesquisa do InterNIC](https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio. Por exemplo, *contoso.com.*</span><span class="sxs-lookup"><span data-stu-id="d17ab-p101">On the [InterNIC search page](https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example,  *contoso.com.*</span></span> 
    
2. <span data-ttu-id="d17ab-110">Selecione a opção **Domínio** e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d17ab-110">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="d17ab-p102">Na página **Whois Search Results**, localize a entrada **Registrar**. Ela informará a organização que presta o serviço de registrador para o seu domínio.</span><span class="sxs-lookup"><span data-stu-id="d17ab-p102">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists the organization that provides registrar service for your domain.</span></span> 
    
## <a name="dns-hosting-provider"></a><span data-ttu-id="d17ab-113">Provedor de hospedagem de DNS</span><span class="sxs-lookup"><span data-stu-id="d17ab-113">DNS hosting provider</span></span>
  
### <a name="find-your-dns-hosting-provider"></a><span data-ttu-id="d17ab-114">Localizar o provedor de hospedagem de DNS</span><span class="sxs-lookup"><span data-stu-id="d17ab-114">Find your DNS hosting provider</span></span>

>[!NOTE]
> <span data-ttu-id="d17ab-115">Somente domínios terminados em *.COM*, *.NET* e *.EDU* funcionam com esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="d17ab-115">Only domains ending in *.COM*, *.NET*, and *.EDU* work with this tool.</span></span>
  
1. <span data-ttu-id="d17ab-p103">Na [página de pesquisa do InterNIC]( https://go.microsoft.com/fwlink/p/?LinkId=402770), na caixa **Whois Search**, digite seu domínio. Por exemplo, contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d17ab-p103">On the [InterNIC search page]( https://go.microsoft.com/fwlink/p/?LinkId=402770), in the **Whois Search** box, type your domain. For example, contoso.com.</span></span> 
    
2. <span data-ttu-id="d17ab-118">Selecione a opção **Domínio** e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d17ab-118">Select the **Domain** option, and then select **Submit**.</span></span>
    
3. <span data-ttu-id="d17ab-119">Na página **Whois Search Results**, localize a primeira entrada em **Name Server**.</span><span class="sxs-lookup"><span data-stu-id="d17ab-119">On the **Whois Search Results** page, locate the first **Name Server** entry.</span></span> 
    
4. <span data-ttu-id="d17ab-p104">Copie as informações do servidor de nomes (NS) que aparecem após os dois-pontos (:) e, em seguida, cole-as na caixa **Pesquisar** na parte superior da página. Selecione **Nameserver** e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="d17ab-p104">Copy the name server (NS) information that appears after the colon (:), and then paste it into the **Search** box at the top of the page. Select **Nameserver**, and then select **Submit**.</span></span>
    
5. <span data-ttu-id="d17ab-p105">Na página **Whois Search Results**, localize a entrada **Registrar**. Ela informará o provedor de hospedagem de DNS, o provedor de DNS a que pertence o servidor de nomes do seu domínio.</span><span class="sxs-lookup"><span data-stu-id="d17ab-p105">On the **Whois Search Results** page, locate the **Registrar** entry. This entry lists your DNS hosting provider, the DNS provider who owns the name server for your domain.</span></span> 
    
---

