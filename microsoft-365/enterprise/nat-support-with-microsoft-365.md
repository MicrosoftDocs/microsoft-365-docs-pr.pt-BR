---
title: Suporte NAT com o Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: Este artigo fornece detalhes sobre como aproximar o número de clientes que você pode usar por endereço IP em sua organização usando NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686914"
---
# <a name="nat-support-with-office-365"></a><span data-ttu-id="4c689-103">Suporte NAT com o Office 365</span><span class="sxs-lookup"><span data-stu-id="4c689-103">NAT support with Office 365</span></span>

<span data-ttu-id="4c689-104">*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4c689-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="4c689-105">Anteriormente, as diretrizes sugeriam que o número máximo de clientes do Exchange que você deveria usar por endereço IP para se conectar ao Office 365 era de cerca de 2.000 clientes por porta de rede.</span><span class="sxs-lookup"><span data-stu-id="4c689-105">Previously, guidance suggested that the maximum number of Exchange clients you should use per IP address to connect to Office 365 was about 2,000 clients per network port.</span></span>
  
## <a name="why-use-nat"></a><span data-ttu-id="4c689-106">Por que usar NAT?</span><span class="sxs-lookup"><span data-stu-id="4c689-106">Why use NAT?</span></span>

<span data-ttu-id="4c689-107">Usando NAT, milhares de pessoas em uma rede corporativa podem "compartilhar" alguns endereços IP publicamente que podem ser reenvelados.</span><span class="sxs-lookup"><span data-stu-id="4c689-107">By using NAT, thousands of people on a corporate network can "share" a few publicly routable IP addresses.</span></span>
  
<span data-ttu-id="4c689-108">A maioria das redes corporativas usa espaço de endereço IP privado (RFC1918).</span><span class="sxs-lookup"><span data-stu-id="4c689-108">Most corporate networks use private (RFC1918) IP address space.</span></span> <span data-ttu-id="4c689-109">O espaço de endereço privado é alocado pela IANA (Autoridade de Números Atribuídos pela Internet) e destina-se exclusivamente a redes que não são roteadas diretamente da Internet global.</span><span class="sxs-lookup"><span data-stu-id="4c689-109">Private address space is allocated by the Internet Assigned Numbers Authority (IANA) and intended solely for networks that do not route directly to and from the global Internet.</span></span>
  
<span data-ttu-id="4c689-110">Para fornecer acesso à Internet a dispositivos em um espaço de endereço IP privado, as organizações usam tecnologias de gateway como firewalls e proxies que fornecem serviços nat (conversão de endereços de rede) ou conversão de endereços de porta (PAT).</span><span class="sxs-lookup"><span data-stu-id="4c689-110">To provide Internet access to devices on a private IP address space, organizations use gateway technologies like firewalls and proxies that provide network address translation (NAT) or port address translation (PAT) services.</span></span> <span data-ttu-id="4c689-111">Esses gateways fazem com que o tráfego de dispositivos internos para a Internet (incluindo o Office 365) pareça vir de um ou mais endereços IP publicamente que podem ser circulados.</span><span class="sxs-lookup"><span data-stu-id="4c689-111">These gateways make traffic from internal devices to the Internet (including Office 365) appear to be coming from one or more publicly routable IP addresses.</span></span> <span data-ttu-id="4c689-112">Cada conexão de saída de um dispositivo interno é traduzida para uma porta TCP de origem diferente no endereço IP público.</span><span class="sxs-lookup"><span data-stu-id="4c689-112">Each outbound connection from an internal device translates to a different source TCP port on the public IP address.</span></span> 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a><span data-ttu-id="4c689-113">Por que você precisa ter tantas conexões abertas no Office 365 ao mesmo tempo?</span><span class="sxs-lookup"><span data-stu-id="4c689-113">Why do you need to have so many connections open to Office 365 at the same time?</span></span>

<span data-ttu-id="4c689-114">O Outlook pode abrir oito ou mais conexões (em situações em que há complementos, calendários compartilhados, caixas de correio etc.).</span><span class="sxs-lookup"><span data-stu-id="4c689-114">Outlook may open eight or more connections (in situations where there are add-ins, shared calendars, mailboxes, etc.).</span></span> <span data-ttu-id="4c689-115">Como há um máximo de 64.000 portas disponíveis em um dispositivo NAT baseado no Windows, pode haver um máximo de 8.000 usuários atrás de um endereço IP antes que as portas sejam esgotadas.</span><span class="sxs-lookup"><span data-stu-id="4c689-115">Because there are a maximum of 64,000 ports available on a Windows-based NAT device, there can be a maximum of 8,000 users behind an IP address before the ports are exhausted.</span></span> <span data-ttu-id="4c689-116">Observe que, se os clientes estão usando dispositivos não baseados no sistema operacional Windows para NAT, o total de portas disponíveis depende do dispositivo NAT ou software que está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="4c689-116">Note that if customers are using non-Windows OS-based devices for NAT, the total available ports are dependent on what NAT device or software is being used.</span></span> <span data-ttu-id="4c689-117">Nesse cenário, o número máximo de portas poderia ser menor que 64.000.</span><span class="sxs-lookup"><span data-stu-id="4c689-117">In this scenario, the maximum number of ports could be less than 64,000.</span></span> <span data-ttu-id="4c689-118">A disponibilidade de portas também é afetada por outros fatores, como o Windows que restringe 4.000 portas para seu próprio uso, o que reduz o número total de portas disponíveis para 60.000.</span><span class="sxs-lookup"><span data-stu-id="4c689-118">Availability of ports is also affected by other factors such as Windows restricting 4,000 ports for its own use, which reduces the total number of available ports to 60,000.</span></span> <span data-ttu-id="4c689-119">Pode haver outros aplicativos, como o Internet Explorer, que podem se conectar ao mesmo tempo, exigindo portas adicionais.</span><span class="sxs-lookup"><span data-stu-id="4c689-119">There may be other applications, such as Internet Explorer, that could connect at the same time, requiring additional ports.</span></span>
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a><span data-ttu-id="4c689-120">Calcular o máximo de dispositivos com suporte por trás de um único endereço IP público com o Office 365</span><span class="sxs-lookup"><span data-stu-id="4c689-120">Calculating maximum supported devices behind a single public IP address with Office 365</span></span>

<span data-ttu-id="4c689-121">Para determinar o número máximo de dispositivos atrás de um único endereço IP público, você deve monitorar o tráfego de rede para determinar o pico de consumo de porta por cliente.</span><span class="sxs-lookup"><span data-stu-id="4c689-121">To determine the maximum number of devices behind a single public IP address, you should monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="4c689-122">Além disso, um fator de pico deve ser usado para o uso da porta (mínimo 4).</span><span class="sxs-lookup"><span data-stu-id="4c689-122">Also, a peak factor should be used for the port usage (minimum 4).</span></span> 
  
 <span data-ttu-id="4c689-123">**Use a fórmula a seguir para calcular o número de dispositivos com suporte por endereço IP:**</span><span class="sxs-lookup"><span data-stu-id="4c689-123">**Use the following formula to calculate the number of supported devices per IP address:**</span></span>
  
<span data-ttu-id="4c689-124">Máximo de dispositivos com suporte por trás de um único endereço IP público = (64.000 - portas restritas)/(Consumo de porta de pico + fator de pico)</span><span class="sxs-lookup"><span data-stu-id="4c689-124">Maximum supported devices behind a single public IP address = (64,000 - restricted ports)/(Peak port consumption + peak factor)</span></span>
  
 <span data-ttu-id="4c689-125">**Por exemplo, se o seguinte for verdadeiro:**</span><span class="sxs-lookup"><span data-stu-id="4c689-125">**For example, if the following were true:**</span></span>
  
- <span data-ttu-id="4c689-126">**Portas restritas:** 4.000 para o sistema operacional</span><span class="sxs-lookup"><span data-stu-id="4c689-126">**Restricted ports:** 4,000 for the operating system</span></span>

- <span data-ttu-id="4c689-127">**Consumo de porta de pico:** 6 por dispositivo</span><span class="sxs-lookup"><span data-stu-id="4c689-127">**Peak port consumption:** 6 per device</span></span>

- <span data-ttu-id="4c689-128">**Fator de pico:** 4</span><span class="sxs-lookup"><span data-stu-id="4c689-128">**Peak factor:** 4</span></span>

<span data-ttu-id="4c689-129">Em seguida, o máximo de dispositivos com suporte por trás de um único endereço IP público = (64.000 - 4.000)/(6 + 4) = 6.000</span><span class="sxs-lookup"><span data-stu-id="4c689-129">Then, the maximum supported devices behind a single public IP address = (64,000 - 4,000)/(6 + 4) = 6,000</span></span>
  
<span data-ttu-id="4c689-130">Com o lançamento do pacote de hospedagem do Office 365, incluído nas atualizações de setembro de 2011 para o Microsoft Office Outlook 2007 ou novembro de 2011 para Microsoft Outlook 2010, ou uma atualização posterior, o número de conexões do Outlook (tanto o Office Outlook 2007 com Service Pack 2 quanto o Outlook 2010) para o Exchange pode ser apenas 2.</span><span class="sxs-lookup"><span data-stu-id="4c689-130">With the release of Office 365 hosting pack, included in the updates from September 2011 for Microsoft Office Outlook 2007, or November 2011 for Microsoft Outlook 2010, or a later update, the number of connections from Outlook (both Office Outlook 2007 with Service Pack 2 and Outlook 2010) to Exchange can be as few as 2.</span></span> <span data-ttu-id="4c689-131">Você precisará levar em conta os diferentes sistemas operacionais, comportamentos do usuário e assim por diante para determinar o número mínimo e máximo de portas que sua rede precisará em pico.</span><span class="sxs-lookup"><span data-stu-id="4c689-131">You'll need to factor in the different operating systems, user behaviors, and so on to determine the minimum and maximum number of ports that your network will require at peak.</span></span>
  
<span data-ttu-id="4c689-132">Se você quiser dar suporte a mais dispositivos por trás de um único endereço IP público, siga as etapas descritas para avaliar o número máximo de dispositivos com suporte:</span><span class="sxs-lookup"><span data-stu-id="4c689-132">If you want to support more devices behind a single public IP address, follow the steps outlined to assess the maximum number of devices that can be supported:</span></span>
  
<span data-ttu-id="4c689-133">Monitore o tráfego de rede para determinar o pico de consumo de porta por cliente.</span><span class="sxs-lookup"><span data-stu-id="4c689-133">Monitor network traffic to determine peak port consumption per client.</span></span> <span data-ttu-id="4c689-134">Você deve coletar esses dados:</span><span class="sxs-lookup"><span data-stu-id="4c689-134">You should collect this data:</span></span>
  
- <span data-ttu-id="4c689-135">De vários locais</span><span class="sxs-lookup"><span data-stu-id="4c689-135">From multiple locations</span></span>
    
- <span data-ttu-id="4c689-136">De vários dispositivos</span><span class="sxs-lookup"><span data-stu-id="4c689-136">From multiple devices</span></span>
    
- <span data-ttu-id="4c689-137">Várias vezes</span><span class="sxs-lookup"><span data-stu-id="4c689-137">At multiple times</span></span>
    
<span data-ttu-id="4c689-138">Use a fórmula anterior para calcular o máximo de usuários por endereço IP que podem ter suporte em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="4c689-138">Use the preceding formula to calculate the maximum users per IP address that can be supported in their environment.</span></span>
  
<span data-ttu-id="4c689-139">Há vários métodos para distribuir a carga do cliente entre endereços IP públicos adicionais.</span><span class="sxs-lookup"><span data-stu-id="4c689-139">There are various methods for distributing client load across additional public IP addresses.</span></span> <span data-ttu-id="4c689-140">As estratégias disponíveis dependem dos recursos da solução de gateway corporativo.</span><span class="sxs-lookup"><span data-stu-id="4c689-140">Strategies available depend on the capabilities of the corporate gateway solution.</span></span> <span data-ttu-id="4c689-141">A solução mais simples é segmentar o espaço de endereço do usuário e estaticamente "atribuir" um número de endereços IP a cada gateway.</span><span class="sxs-lookup"><span data-stu-id="4c689-141">The simplest solution is to segment your user address space and statically "assign" a number of IP addresses to each gateway.</span></span> <span data-ttu-id="4c689-142">Outra alternativa que muitos dispositivos gateway oferecem é a capacidade de usar um pool de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="4c689-142">Another alternative that many gateway devices offer is the ability to use a pool of IP addresses.</span></span> <span data-ttu-id="4c689-143">A vantagem do pool de endereços é que ele é muito mais dinâmico e menos provável de exigir ajuste à medida que sua base de usuários cresce.</span><span class="sxs-lookup"><span data-stu-id="4c689-143">The benefit of the address pool is that it is much more dynamic and less likely to require adjustment as your user base grows.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4c689-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="4c689-144">See also</span></span>

[<span data-ttu-id="4c689-145">Gerenciar pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="4c689-145">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="4c689-146">Perguntas frequentes sobre pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="4c689-146">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
