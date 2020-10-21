---
title: Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Saiba como rotear o tráfego para um site público existente hospedado fora da Microsoft, se você tiver configurado o Microsoft para gerenciar registros DNS para o seu domínio personalizado.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645558"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="c6a3c-103">Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual</span><span class="sxs-lookup"><span data-stu-id="c6a3c-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="c6a3c-104">**Se você gerencia os registros da Microsoft do seu domínio em seu provedor de Hospedagem de DNS**, não precisa se preocupar com as etapas deste tópico.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="c6a3c-105">Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="c6a3c-106">**Se a Microsoft gerencia seus registros DNS**, para rotear o tráfego para um site público existente hospedado fora da Microsoft, após adicionar seu domínio à Microsoft, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6a3c-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c6a3c-107">Atualizar registros DNS no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c6a3c-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="c6a3c-108">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="c6a3c-109">Na página **domínios** , selecione o domínio e, em seguida, escolha **registros DNS**.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

3. <span data-ttu-id="c6a3c-110">Em **configurações de DNS**, selecione **registros personalizados**.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-110">Under **DNS settings**, select **Custom Records**.</span></span>

4. <span data-ttu-id="c6a3c-111">Selecione **+ Novo registro personalizado** e insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6a3c-111">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="c6a3c-112">Para **Tipo DNS**, insira: **A (Endereço)**</span><span class="sxs-lookup"><span data-stu-id="c6a3c-112">For **DNS type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="c6a3c-113">Para **Nome do host ou Alias**, digite o seguinte: **@**</span><span class="sxs-lookup"><span data-stu-id="c6a3c-113">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="c6a3c-114">Para o **Endereço IP**, digite o endereço IP estático no qual seu site está hospedado no momento (por exemplo, 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="c6a3c-114">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="c6a3c-p102">Esse deve ser um endereço IP  *estático*  do site e não um endereço IP  *dinâmico*  . Verifique com o site o local de hospedagem do seu site para garantir que você pode obter um endereço IP estático para o site público.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
5. <span data-ttu-id="c6a3c-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-117">Select **Save**.</span></span> 
    
<span data-ttu-id="c6a3c-118">Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-118">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="c6a3c-119">Selecione **+ Novo registro personalizado** e insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6a3c-119">Select **+ New custom record** and enter the following:</span></span> 
    
   - <span data-ttu-id="c6a3c-120">Para **Tipo DNS**, insira: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="c6a3c-120">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="c6a3c-121">Para **Nome do host ou Alias**, digite: **www**</span><span class="sxs-lookup"><span data-stu-id="c6a3c-121">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="c6a3c-122">Em **Pontos de endereçamento**, digite o FQDN (nome de domínio totalmente qualificado) do seu site (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c6a3c-122">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="c6a3c-123">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-123">Select **Save**.</span></span> 
    
<span data-ttu-id="c6a3c-124">Por último, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6a3c-124">Finally, do the following:</span></span>
  
<span data-ttu-id="c6a3c-125">[Atualize os registros ns do seu domínio](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) para apontar para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-125">[Update your domain's NS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to point to Microsoft.</span></span> 
  
<span data-ttu-id="c6a3c-126">Quando os registros NS foram atualizados para apontar para a Microsoft, seu domínio é configurado.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-126">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="c6a3c-127">Os emails serão roteados para a Microsoft, e o tráfego para o seu endereço de site continuará a ir para o host do site atual.</span><span class="sxs-lookup"><span data-stu-id="c6a3c-127">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
 
