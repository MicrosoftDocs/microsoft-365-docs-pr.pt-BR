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
description: Saiba como direcionar o tráfego para um site público existente hospedado fora da Microsoft, se você definiu a Microsoft para gerenciar registros de DNS para o seu domínio personalizado.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572132"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="2781f-103">Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual</span><span class="sxs-lookup"><span data-stu-id="2781f-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="2781f-104">**Se você gerenciar os registros microsoft do seu domínio em seu provedor de hospedagem DNS,** você não precisa se preocupar com os passos neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2781f-104">**If you manage your domain's Microsoft records at your DNS hosting provider**, you don't have to worry about the steps in this topic.</span></span> <span data-ttu-id="2781f-105">Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="2781f-105">Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="2781f-106">**Se a Microsoft gerenciar seus registros de DNS,** para direcionar o tráfego para um site público existente hospedado fora da Microsoft, depois de adicionar seu domínio à Microsoft, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2781f-106">**If Microsoft manages your DNS records**, to route traffic to an existing public website hosted outside of Microsoft, after you add your domain to Microsoft, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="2781f-107">Atualizar registros de DNS no centro administrativo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="2781f-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="2781f-108">No centro do administrador, acesse a página **Configurações de** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a>.</span><span class="sxs-lookup"><span data-stu-id="2781f-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

1. <span data-ttu-id="2781f-109">Na página **Domínios,** selecione o domínio e escolha **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="2781f-109">On the **Domains** page, select the domain and then choose **DNS Records**.</span></span>

1. <span data-ttu-id="2781f-110">Selecione **+ Adicionar registro** e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2781f-110">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="2781f-111">Para **digitar:** **A (Endereço)**</span><span class="sxs-lookup"><span data-stu-id="2781f-111">For **type** enter: **A (Address)**</span></span>
    
   - <span data-ttu-id="2781f-112">Para **Nome do host ou Alias**, digite o seguinte: **@**</span><span class="sxs-lookup"><span data-stu-id="2781f-112">For **Host name or Alias**, type the following: **@**</span></span>
    
   - <span data-ttu-id="2781f-113">Para o **Endereço IP**, digite o endereço IP estático no qual seu site está hospedado no momento (por exemplo, 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="2781f-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
   <span data-ttu-id="2781f-p102">Esse deve ser um endereço IP  *estático*  do site e não um endereço IP  *dinâmico*  . Verifique com o site o local de hospedagem do seu site para garantir que você pode obter um endereço IP estático para o site público.</span><span class="sxs-lookup"><span data-stu-id="2781f-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
1. <span data-ttu-id="2781f-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2781f-116">Select **Save**.</span></span> 
    
<span data-ttu-id="2781f-117">Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.</span><span class="sxs-lookup"><span data-stu-id="2781f-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="2781f-118">Selecione **+ Adicionar registro** e digite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2781f-118">Select **+ Add record** and enter the following:</span></span> 
    
   - <span data-ttu-id="2781f-119">Para **digitar:** **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="2781f-119">For **type** enter: **CNAME (Alias)**</span></span>
    
   - <span data-ttu-id="2781f-120">Para **Nome do host ou Alias**, digite: **www**</span><span class="sxs-lookup"><span data-stu-id="2781f-120">For **Host name or Alias**, type the following: **www**</span></span>
    
   - <span data-ttu-id="2781f-121">Em **Pontos de endereçamento**, digite o FQDN (nome de domínio totalmente qualificado) do seu site (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="2781f-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="2781f-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2781f-122">Select **Save**.</span></span> 
    
<span data-ttu-id="2781f-123">Por último, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2781f-123">Finally, do the following:</span></span>
  
<span data-ttu-id="2781f-124">[Atualize os registros NS do seu domínio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) para apontar para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2781f-124">[Update your domain's NS records](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to point to Microsoft.</span></span> 
  
<span data-ttu-id="2781f-125">Quando os registros NS foram atualizados para apontar para a Microsoft, seu domínio está configurado.</span><span class="sxs-lookup"><span data-stu-id="2781f-125">When the NS records have been updated to point to Microsoft, your domain is all set up.</span></span> <span data-ttu-id="2781f-126">O e-mail será encaminhado para a Microsoft, e o tráfego para o endereço do seu site continuará a ir para o seu atual host do site.</span><span class="sxs-lookup"><span data-stu-id="2781f-126">Email will be routed to Microsoft, and traffic to your website address will continue to go to your current website host.</span></span>
