---
title: Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual
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
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: Saiba como rotear o tráfego para um site público existente hospedado fora do Office 365, se você tiver definido o Office 365 para gerenciar registros DNS para o seu domínio personalizado.
ms.openlocfilehash: de95818eea729cb11972faf986c9be40bb6e76da
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42250698"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a><span data-ttu-id="c4c6c-103">Atualizar registros DNS para manter seu site com seu provedor de hospedagem atual</span><span class="sxs-lookup"><span data-stu-id="c4c6c-103">Update DNS records to keep your website with your current hosting provider</span></span>

 <span data-ttu-id="c4c6c-p101">**Se você gerenciar seus registros de domínio do Office 365 em seu provedor de host DNS**, não precisa se preocupar com as etapas desse tópico. Seu site permanecerá no mesmo local e as pessoas ainda vão poder acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-p101">**If you manage your domain's Office 365 records at your DNS hosting provider**, you don't have to worry about the steps in this topic. Your website stays where it is and people can still get to it.</span></span> 
  
 <span data-ttu-id="c4c6c-106">**Se o Office 365 gerenciar os registros DNS** a fim de rotear o tráfego para um site público existente hospedado fora do Office 365, após adicionar o domínio ao Office 365, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c4c6c-106">**If Office 365 manages your DNS records**, to route traffic to an existing public website hosted outside of Office 365, after you add your domain to Office 365, do the following:</span></span> 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a><span data-ttu-id="c4c6c-107">Atualizar registros DNS no centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c4c6c-107">Update DNS records in the Microsoft 365 admin center</span></span>
1. <span data-ttu-id="c4c6c-108">No centro de administração, vá para a página de <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domínios</a> de **configurações** \> .</span><span class="sxs-lookup"><span data-stu-id="c4c6c-108">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

2. <span data-ttu-id="c4c6c-109">Na página **Domínios**, selecione o domínio que você usa para o site na lista de domínios e selecione **Configurações de DNS**, no Painel Gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-109">On the **Domains** page, in the list of domains, select the domain you're using for your website, and then select **DNS settings** in the management pane.</span></span> 
    
3. <span data-ttu-id="c4c6c-110">Selecione **+ Novo registro personalizado** e insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c4c6c-110">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="c4c6c-111">Para **Tipo DNS**, insira: **A (Endereço)**</span><span class="sxs-lookup"><span data-stu-id="c4c6c-111">For **DNS type** enter: **A (Address)**</span></span>
    
  - <span data-ttu-id="c4c6c-112">Para **Nome do host ou Alias**, digite o seguinte: **@**</span><span class="sxs-lookup"><span data-stu-id="c4c6c-112">For **Host name or Alias**, type the following: **@**</span></span>
    
  - <span data-ttu-id="c4c6c-113">Para o **Endereço IP**, digite o endereço IP estático no qual seu site está hospedado no momento (por exemplo, 172.16.140.1).</span><span class="sxs-lookup"><span data-stu-id="c4c6c-113">For **IP Address**, type the static IP address for your website where it's currently hosted (for example, 172.16.140.1).</span></span> 
    
    <span data-ttu-id="c4c6c-p102">Esse deve ser um endereço IP  *estático*  do site e não um endereço IP  *dinâmico*  . Verifique com o site o local de hospedagem do seu site para garantir que você pode obter um endereço IP estático para o site público.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-p102">This must be a  *static*  IP address for the website, not a  *dynamic*  IP address. Check with site where your website is hosted to make sure you can get a static IP address for your public website.</span></span> 
    
3. <span data-ttu-id="c4c6c-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-116">Select **Save**.</span></span> 
    
<span data-ttu-id="c4c6c-117">Além disso, você pode criar um registro CNAME para ajudar os clientes a encontrarem seu site.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-117">In addition, you can create a CNAME record to help customers find your website.</span></span>
  
1. <span data-ttu-id="c4c6c-118">Selecione **+ Novo registro personalizado** e insira o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c4c6c-118">Select **+ New custom record** and enter the following:</span></span> 
    
  - <span data-ttu-id="c4c6c-119">Para **Tipo DNS**, insira: **CNAME (Alias)**</span><span class="sxs-lookup"><span data-stu-id="c4c6c-119">For **DNS type** enter: **CNAME (Alias)**</span></span>
    
  - <span data-ttu-id="c4c6c-120">Para **Nome do host ou Alias**, digite: **www**</span><span class="sxs-lookup"><span data-stu-id="c4c6c-120">For **Host name or Alias**, type the following: **www**</span></span>
    
  - <span data-ttu-id="c4c6c-121">Em **Pontos de endereçamento**, digite o FQDN (nome de domínio totalmente qualificado) do seu site (por exemplo, contoso.com).</span><span class="sxs-lookup"><span data-stu-id="c4c6c-121">For **Points to address**, type the fully qualified domain name (FQDN) for your website (for example, contoso.com).</span></span> 
    
2. <span data-ttu-id="c4c6c-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-122">Select **Save**.</span></span> 
    
<span data-ttu-id="c4c6c-123">Por último, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c4c6c-123">Finally, do the following:</span></span>
  
<span data-ttu-id="c4c6c-124">[Atualize os registros NS do seu domínio](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) para apontá-los para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-124">[Update your domain's NS records](https://support.office.com/article/a46bec33-2c78-4f45-a96c-b64b2a5bae22.aspx) to point to Office 365.</span></span> 
  
<span data-ttu-id="c4c6c-p103">Quando os registros NS estiverem atualizados de forma a apontarem para o Office 365, seu domínio estará totalmente configurado. Os emails serão roteados para o Office 365 e o tráfego para o endereço do seu site vai continuar a ser direcionado para o seu provedor de hospedagem atual.</span><span class="sxs-lookup"><span data-stu-id="c4c6c-p103">When the NS records have been updated to point to Office 365, your domain is all set up. Email will be routed to Office 365, and traffic to your website address will continue to go to your current website host.</span></span>
 