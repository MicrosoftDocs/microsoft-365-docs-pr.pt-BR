---
title: 'Etapa 4: Configurar o bypass de tráfego'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda e configure os navegadores da web e os dispositivos de borda para executar bypass de tráfego dos locais confiáveis do Office 365.
ms.openlocfilehash: f52921fdc0a5329e3fffae687855a653f7026df6
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865076"
---
# <a name="step-4-configure-traffic-bypass"></a><span data-ttu-id="69dbd-103">Etapa 4: Configurar o bypass de tráfego</span><span class="sxs-lookup"><span data-stu-id="69dbd-103">Step 4: Configure traffic bypass</span></span>

<span data-ttu-id="69dbd-104">*Esta etapa é opcional e se aplica às versões E3 e E5 do Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="69dbd-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

<span data-ttu-id="69dbd-p101">Como o tráfego geral da Internet pode ser arriscado, as redes de organizações típicas reforçam a segurança com dispositivos de borda, como servidores proxy, interrupção e inspeção de SSL, dispositivos de inspeção de pacotes e sistemas de prevenção de perda de dados. Leia sobre alguns dos problemas com dispositivos de interceptação de rede em Usar soluções ou dispositivos de rede de terceiros em tráfego do Office 365.</span><span class="sxs-lookup"><span data-stu-id="69dbd-p101">Because general Internet traffic can be risky, typical organization networks enforce security with edge devices such as proxy servers, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. Read about some of the issues with network interception devices at Using third-party network devices or solutions on Office 365 traffic.</span></span>

<span data-ttu-id="69dbd-p102">No entanto, os endereços IP e nomes de domínio DNS usados pelos serviços de nuvem do Microsoft 365 são conhecidos. Além disso, o tráfego e os serviços por si só são protegidos por vários recursos de segurança. Como essa proteção e segurança já está em funcionamento, os dispositivos de borda não precisam duplicá-la. Os destinos intermediários e o processamento de segurança duplicado do tráfego do Microsoft 365 podem reduzir significativamente o desempenho.</span><span class="sxs-lookup"><span data-stu-id="69dbd-p102">However, the DNS domain names and IP addresses used by Microsoft 365 cloud-based services are well known. Additionally, the traffic and services themselves are protected with many security features. Because this security and protection is already in place, your edge devices don’t need to duplicate it. Intermediate destinations and duplicate security processing for Microsoft 365 traffic can dramatically decrease performance.</span></span>

<span data-ttu-id="69dbd-p103">A primeira etapa para eliminar destinos intermediários e processamento de segurança duplicado é identificar o tráfego do Microsoft 365. A Microsoft definiu os seguintes intervalos de endereços IP e tipos de nomes de domínio de DNS, conhecidos como pontos de extremidade:</span><span class="sxs-lookup"><span data-stu-id="69dbd-p103">The first step in eliminating intermediate destinations and duplicate security processing is to identify Microsoft 365 traffic. Microsoft has defined the following types of DNS domain names and IP address ranges, known as endpoints:</span></span>

- <span data-ttu-id="69dbd-p104">Otimizar – necessário para a conectividade com todos os serviços do Office 365 e representa mais de 75% da largura de banda, conexões e volume de dados do Microsoft 365. Esses pontos de extremidade representam os cenários do Microsoft 365 que são mais importantes no desempenho, latência e disponibilidade da rede.</span><span class="sxs-lookup"><span data-stu-id="69dbd-p104">Optimize - Required for connectivity to every Office 365 service and represent over 75% of Microsoft 365 bandwidth, connections, and volume of data. These endpoints represent Microsoft 365 scenarios that are the most sensitive to network performance, latency and availability.</span></span>
- <span data-ttu-id="69dbd-115">Permitir – necessário para a conectividade com os recursos e serviços específicos do Microsoft 365, mas não são tão sensíveis ao desempenho e à latência da rede quanto os da categoria Otimizar.</span><span class="sxs-lookup"><span data-stu-id="69dbd-115">Allow - Required for connectivity to specific Microsoft 365 services and features but are not as sensitive to network performance and latency as those in the Optimize category.</span></span>
 - <span data-ttu-id="69dbd-p105">Padrão – representam os serviços e dependências do Microsoft 365 que não precisam de otimização. Você pode considerar os pontos de extremidade de categoria padrão como tráfego normal da Internet.</span><span class="sxs-lookup"><span data-stu-id="69dbd-p105">Default - Represent Microsoft 365 services and dependencies that do not require any optimization. You can treat Default category endpoints as normal Internet traffic.</span></span>

<span data-ttu-id="69dbd-118">Você pode encontrar os intervalos de endereços IP e os nomes de domínio DNS em [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span><span class="sxs-lookup"><span data-stu-id="69dbd-118">You can find the DNS domain names and IP address ranges at [https://aka.ms/o365endpoints](https://aka.ms/o365endpoints).</span></span>

<span data-ttu-id="69dbd-119">A Microsoft recomenda que você:</span><span class="sxs-lookup"><span data-stu-id="69dbd-119">Microsoft recommends that you:</span></span>

- <span data-ttu-id="69dbd-p106">Use scripts PAC (configuração automática de Proxy) nos navegadores da Internet dos computadores no local para executar o bypass dos servidores proxy para os nomes de domínio DNS dos serviços baseados na nuvem do Microsoft 365. Para obter o script PAC mais recente do Microsoft 365, confira o script Get-Pacfile do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69dbd-p106">Use Proxy Automatic Configuration (PAC) scripts on the Internet browsers of your on-premises computers to bypass your proxy servers for the DNS domain names of Microsoft 365 cloud-based services. For the latest Microsoft 365 PAC script, see the Get-Pacfile PowerShell script.</span></span>
- <span data-ttu-id="69dbd-p107">Analise seus dispositivos de borda para determinar o processamento duplicado e configure-os para encaminhar o tráfego sem processamento para os pontos de extremidade Otimizar e Permitir, o que é conhecido como executar o bypass de tráfego.</span><span class="sxs-lookup"><span data-stu-id="69dbd-p107">Analyze your edge devices to determine the duplicate processing and then configure them to forward traffic to Optimize and Allow endpoints without processing. This is known as traffic bypass.</span></span> 
- 
<span data-ttu-id="69dbd-p108">Os dispositivos de borda incluem firewalls, interrupção e inspeção de SSL, dispositivos de inspeção empacotados e sistemas de prevenção de perda de dados. Para configurar e atualizar as configurações de dispositivos de borda, você pode usar um script ou uma chamada REST para consumir uma lista estruturada de pontos de extremidade do serviço Web de Pontos de extremidade do Office 365. Para saber mais, confira [URL do serviço Web e endereço IP do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span><span class="sxs-lookup"><span data-stu-id="69dbd-p108">Edge devices include firewalls, SSL Break and Inspect, and packet inspection devices, and data loss prevention systems. To configure and update the configurations of edge devices, you can use a script or a REST call to consume a structured list of endpoints from the Office 365 Endpoints web service. For more information, see [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

<span data-ttu-id="69dbd-p109">Observe que você está apenas ignorando o processamento normal de segurança de rede e proxy do tráfego para os pontos de extremidade da categoria Otimizar e Permitir do Microsoft 365. Todo o outro tráfego geral da Internet será intermediado por proxy e estará sujeito ao processamento existente de segurança da rede.</span><span class="sxs-lookup"><span data-stu-id="69dbd-p109">Note that you are only bypassing normal proxy and network security processing for traffic to Microsoft 365 Optimize and Allow categories endpoints. All other general Internet traffic will be proxied and be subject to your existing network security processing.</span></span>


<span data-ttu-id="69dbd-129">Como um ponto de verificação provisório, é possível ver os [critérios de saída](networking-exit-criteria.md#crit-networking-step4) para esta etapa.</span><span class="sxs-lookup"><span data-stu-id="69dbd-129">As an interim checkpoint, you can see the [exit criteria](networking-exit-criteria.md#crit-networking-step4) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="69dbd-130">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="69dbd-130">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step5.png)|[<span data-ttu-id="69dbd-131">Otimizar o desempenho do serviço entre o cliente e o Office 365</span><span class="sxs-lookup"><span data-stu-id="69dbd-131">Optimize client and Office 365 service performance</span></span>](networking-optimize-tcp-performance.md) |



