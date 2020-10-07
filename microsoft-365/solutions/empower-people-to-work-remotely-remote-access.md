---
title: Etapa 2. Fornecer acesso remoto a aplicativos e serviços locais
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/27/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- m365solution-remotework
- m365solution-scenario
ms.custom: ''
description: Garanta que seus funcionários remotos possam acessar recursos locais ao otimizar o acesso aos serviços em nuvem do Microsoft 365.
ms.openlocfilehash: 52a338822c28f6ae044f13f60664d66816d6ce5c
ms.sourcegitcommit: 9841058fcc95f7c2fed6af92bc3c3686944829b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48377242"
---
# <a name="step-2-provide-remote-access-to-on-premises-apps-and-services"></a><span data-ttu-id="9aa54-104">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="9aa54-104">Step 2.</span></span> <span data-ttu-id="9aa54-105">Fornecer acesso remoto a aplicativos e serviços locais</span><span class="sxs-lookup"><span data-stu-id="9aa54-105">Provide remote access to on-premises apps and services</span></span>

<span data-ttu-id="9aa54-106">Se sua organização usa uma solução VPN de acesso remoto, geralmente com servidores VPN na borda da rede e clientes VPN instalados nos dispositivos dos usuários, os usuários podem usar conexões VPN de acesso remoto para acessar aplicativos e servidores locais.</span><span class="sxs-lookup"><span data-stu-id="9aa54-106">If your organization uses a remote access VPN solution, typically with VPN servers on the edge of your network and VPN clients installed on your users' devices, your users can use remote access VPN connections to access on-premises apps and servers.</span></span> <span data-ttu-id="9aa54-107">Mas pode ser necessário otimizar o tráfego para os serviços baseados na nuvem do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aa54-107">But you may need to optimize traffic to Microsoft 365 cloud-based services.</span></span>

<span data-ttu-id="9aa54-108">Se os seus usuários não usarem uma solução VPN, você poderá usar o Proxy de Aplicativo do Microsoft Azure Active Directory e a VPN Ponto a Site (P2S) do Azure para fornecer acesso, dependendo de todos os aplicativos serem baseados na Web.</span><span class="sxs-lookup"><span data-stu-id="9aa54-108">If your users do not use a VPN solution, you can use Azure Active Directory (Azure AD) Application Proxy and Azure Point-to-Site (P2S) VPN to provide access, depending on whether all your apps are web-based.</span></span>

<span data-ttu-id="9aa54-109">Há três configurações principais:</span><span class="sxs-lookup"><span data-stu-id="9aa54-109">There are three primary configurations:</span></span>

1. <span data-ttu-id="9aa54-110">Você já está usando uma solução VPN de acesso remoto.</span><span class="sxs-lookup"><span data-stu-id="9aa54-110">You are already using a remote access VPN solution.</span></span>
2. <span data-ttu-id="9aa54-111">Você não está usando uma solução VPN de acesso remoto, você possui identidade híbrida e precisa de acesso remoto apenas a aplicativos locais baseados na Web.</span><span class="sxs-lookup"><span data-stu-id="9aa54-111">You are not using a remote access VPN solution, you have hybrid identity, and you need remote access only to on-premises web-based apps.</span></span>
3. <span data-ttu-id="9aa54-112">Você não está usando uma solução VPN de acesso remoto e precisa acessar aplicativos locais, alguns dos quais não são baseados na Web.</span><span class="sxs-lookup"><span data-stu-id="9aa54-112">You are not using a remote access VPN solution and you need access to on-premises apps, some of which are not web-based.</span></span>

<span data-ttu-id="9aa54-113">Confira este fluxograma para obter as opções de configuração de acesso remoto abordadas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="9aa54-113">See this flowchart for the remote access configuration options discussed in this article.</span></span>

![Configuração de acesso remoto](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-flowchart.png)

<span data-ttu-id="9aa54-115">Com as conexões de acesso remoto, você também pode usar a [Área de Trabalho Remota](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) para conectar os usuários a um computador local.</span><span class="sxs-lookup"><span data-stu-id="9aa54-115">With remote access connections, you can also use [Remote Desktop](https://support.microsoft.com/help/4028379/windows-10-how-to-use-remote-desktop) to connect your users to an on-premises PC.</span></span> <span data-ttu-id="9aa54-116">Por exemplo, um trabalhador remoto pode usar a Área de Trabalho Remota para conectar-se ao computador em seu escritório a partir de dispositivos Windows, iOS ou Android.</span><span class="sxs-lookup"><span data-stu-id="9aa54-116">For example, a remote worker can use Remote Desktop to connect to the PC in their office from their Windows, iOS or Android device.</span></span> <span data-ttu-id="9aa54-117">Uma vez conectados remotamente, eles podem usá-la como se estivessem sentados na frente dela.</span><span class="sxs-lookup"><span data-stu-id="9aa54-117">Once they are remotely connected, they can use it as if they were sitting in front of it.</span></span>

## <a name="optimize-performance-for-remote-access-vpn-clients-to-microsoft-365-cloud-services"></a><span data-ttu-id="9aa54-118">Otimize o desempenho dos clientes VPN de acesso remoto aos serviços de nuvem do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9aa54-118">Optimize performance for remote access VPN clients to Microsoft 365 cloud services</span></span>

<span data-ttu-id="9aa54-119">Se os seus funcionários remotos estiverem usando um cliente VPN tradicional para obter acesso remoto à rede da organização, verifique se o cliente VPN possui suporte para túnel dividido.</span><span class="sxs-lookup"><span data-stu-id="9aa54-119">If your remote workers are using a traditional VPN client to obtain remote access to your organization network, verify that the VPN client has split tunneling support.</span></span>

<span data-ttu-id="9aa54-120">Sem o túnel dividido, todo o seu tráfego de trabalho remoto é enviado pela conexão VPN, onde deve ser encaminhado para os dispositivos de borda da sua organização, processado e enviado na Internet.</span><span class="sxs-lookup"><span data-stu-id="9aa54-120">Without split tunneling, all of your remote work traffic gets sent across the VPN connection, where it must be forwarded to your organization’s edge devices, get processed, and then sent on the Internet.</span></span>

![Tráfego de rede de clientes VPN sem túnel dividido](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-before-tunneling.png)

<span data-ttu-id="9aa54-122">O tráfego do Microsoft 365 deve seguir uma rota indireta pela organização, que pode ser encaminhada para um ponto de entrada da rede Microsoft longe do local físico do cliente VPN.</span><span class="sxs-lookup"><span data-stu-id="9aa54-122">Microsoft 365 traffic must take an indirect route through your organization, which could be the forwarded to a Microsoft network entry point far away from the VPN client’s physical location.</span></span> <span data-ttu-id="9aa54-123">Esse caminho indireto adiciona latência ao tráfego da rede e diminui o desempenho geral.</span><span class="sxs-lookup"><span data-stu-id="9aa54-123">This indirect path adds latency to the network traffic and decreases overall performance.</span></span> 

<span data-ttu-id="9aa54-124">Com o túnel dividido, você pode configurar seu cliente VPN para impedir que tipos específicos de tráfego sejam enviados à rede da organização pela conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="9aa54-124">With split tunneling, you can configure your VPN client to exclude specific types of traffic from being sent over the VPN connection to the organization network.</span></span>

<span data-ttu-id="9aa54-125">Para otimizar o acesso aos recursos de nuvem do Microsoft 365, configure seus clientes VPN de túnel dividido para excluir o tráfego nos pontos de extremidade do Microsoft 365 da categoria **Otimizar** pela conexão VPN.</span><span class="sxs-lookup"><span data-stu-id="9aa54-125">To optimize access to Microsoft 365 cloud resources, configure your split tunneling VPN clients to exclude traffic to the **Optimize** category Microsoft 365 endpoints over the VPN connection.</span></span> <span data-ttu-id="9aa54-126">Para obter mais informações, confira [Categorias de ponto de extremidade do Office 365](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span><span class="sxs-lookup"><span data-stu-id="9aa54-126">For more information, see [Office 365 endpoint categories](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-network-connectivity-principles#new-office-365-endpoint-categories).</span></span> <span data-ttu-id="9aa54-127">Veja a lista de pontos de extremidade da categoria Otimizar [aqui](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span><span class="sxs-lookup"><span data-stu-id="9aa54-127">See the list of Optimize category endpoints [here](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges).</span></span>

![Tráfego de rede de clientes VPN com túnel dividido](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-after-tunneling.png)

<span data-ttu-id="9aa54-129">Isso permite que o cliente VPN envie e receba o tráfego crucial do serviço em nuvem do Microsoft 365 diretamente pela Internet e para o ponto de entrada mais próximo da rede Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9aa54-129">This allows the VPN client to send and receive crucial Microsoft 365 cloud service traffic directly over the Internet and to the nearest entry point into the Microsoft network.</span></span>

<span data-ttu-id="9aa54-130">Para obter mais informações e orientações, confira [Otimizar a conectividade do Office 365 para usuários remotos usando o túnel dividido da VPN](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?).</span><span class="sxs-lookup"><span data-stu-id="9aa54-130">For more information and guidance, see [Optimize Office 365 connectivity for remote users using VPN split tunneling](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel?).</span></span>

## <a name="deploy-remote-access-when-all-your-apps-are-web-apps-and-you-have-hybrid-identity"></a><span data-ttu-id="9aa54-131">Implantar o acesso remoto quando todos os seus aplicativos são aplicativos Web e você tem identidade híbrida</span><span class="sxs-lookup"><span data-stu-id="9aa54-131">Deploy remote access when all your apps are web apps and you have hybrid identity</span></span>

<span data-ttu-id="9aa54-132">Se os seus funcionários remotos não estiverem usando um cliente VPN tradicional, e suas contas e grupos de usuários locais estiverem sincronizados com o Microsoft Azure Active Directory, você poderá usar o Proxy de Aplicativo do Microsoft Azure Active Directory para fornecer acesso remoto seguro a aplicativos baseados na Web hospedados em servidores da intranet.</span><span class="sxs-lookup"><span data-stu-id="9aa54-132">If your remote workers are not using a traditional VPN client and your on-premises user accounts and groups are synchronized with Azure AD, you can use Azure AD Application Proxy to provide secure remote access for web-based applications hosted on intranet servers.</span></span> <span data-ttu-id="9aa54-133">Aplicativos baseados na Web incluem sites do Microsoft Office SharePoint Online, servidores do Outlook Web Access ou qualquer outro aplicativo de linha de negócios baseado na Web.</span><span class="sxs-lookup"><span data-stu-id="9aa54-133">Web-based applications include SharePoint sites, Outlook Web Access servers, or any other web-based line of business applications.</span></span> 

<span data-ttu-id="9aa54-134">Estes são os componentes do Proxy de Aplicativo do Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9aa54-134">Here are the components of Azure AD Application Proxy.</span></span>

![Componentes do Proxy de Aplicativo do Microsoft Azure Active Directory](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-application-proxy.png)

<span data-ttu-id="9aa54-136">Para obter mais informações, confira este [Visão geral sobre o Proxy do aplicativo Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) e o vídeo da [Parte 3 sobre como usar o](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security)Proxy do aplicativo Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9aa54-136">For more information, see this [overview of Azure AD Application Proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy) and the [Part 3 video on using Azure AD Application Proxy](https://resources.techcommunity.microsoft.com/enabling-remote-work/#security).</span></span>

>[!Note]
><span data-ttu-id="9aa54-137">O Proxy do aplicativo Azure Active Directory não está incluído na assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aa54-137">Azure AD Application Proxy is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="9aa54-138">Você deve pagar por uso com uma assinatura separada do Azure.</span><span class="sxs-lookup"><span data-stu-id="9aa54-138">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-remote-access-when-not-all-your-apps-are-web-apps"></a><span data-ttu-id="9aa54-139">Implantar o acesso remoto quando nem todos os seus aplicativos são aplicativos Web</span><span class="sxs-lookup"><span data-stu-id="9aa54-139">Deploy remote access when not all your apps are web apps</span></span>

<span data-ttu-id="9aa54-140">Se os seus funcionários remotos não estiverem usando um cliente VPN tradicional, e algum de seus aplicativos não for baseado na Web, você poderá usar uma VPN Ponto a Site do Azure (P2S).</span><span class="sxs-lookup"><span data-stu-id="9aa54-140">If your remote workers are not using a traditional VPN client and any of your apps are not web-based, you can use an Azure Point-to-Site (P2S) VPN.</span></span>

<span data-ttu-id="9aa54-141">Uma conexão VPN P2S cria uma conexão segura do dispositivo de um trabalhador remoto à rede da sua organização por meio de uma rede virtual do Azure.</span><span class="sxs-lookup"><span data-stu-id="9aa54-141">A P2S VPN connection creates a secure connection from a remote worker’s device to your organization network through an Azure virtual network.</span></span> 

![Componentes da VPN P2S do Azure](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-p2s-vpn.png)

<span data-ttu-id="9aa54-143">Para mais informações, confira esta [visão geral da VPN P2S](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span><span class="sxs-lookup"><span data-stu-id="9aa54-143">For more information, see this [overview of P2S VPN](https://docs.microsoft.com/azure/vpn-gateway/point-to-site-about).</span></span>

>[!Note]
><span data-ttu-id="9aa54-144">O Azure P2P VPN não está incluído na assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aa54-144">Azure P2S VPN is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="9aa54-145">Você deve pagar por uso com uma assinatura separada do Azure.</span><span class="sxs-lookup"><span data-stu-id="9aa54-145">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="deploy-windows-virtual-desktop-to-provide-remote-access-for-remote-workers-using-personal-devices"></a><span data-ttu-id="9aa54-146">Implantar a Área de Trabalho Virtual do Windows para fornecer acesso remoto a trabalhadores remotos usando dispositivos pessoais</span><span class="sxs-lookup"><span data-stu-id="9aa54-146">Deploy Windows Virtual Desktop to provide remote access for remote workers using personal devices</span></span> 

<span data-ttu-id="9aa54-147">Para oferecer suporte a trabalhadores remotos que podem usar somente dispositivos pessoais e não gerenciados, use a Área de Trabalho Virtual do Windows no Azure para criar e alocar áreas de trabalho virtuais para seus usuários usarem em casa.</span><span class="sxs-lookup"><span data-stu-id="9aa54-147">To support remote workers who can only use their personal and unmanaged devices, use Windows Virtual Desktop in Azure to create and allocate virtual desktops for your users to use from home.</span></span> <span data-ttu-id="9aa54-148">Os computadores virtualizados podem funcionar da mesma forma que os computadores conectados à sua organização.</span><span class="sxs-lookup"><span data-stu-id="9aa54-148">Virtualized PCs can act just like PCs connected to your organization network.</span></span>

![Componentes da Área de Trabalho Virtual do Windows do Azure](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-windows-virtual-desktop.png)

<span data-ttu-id="9aa54-150">Para saber mais, confira:</span><span class="sxs-lookup"><span data-stu-id="9aa54-150">For more information, see:</span></span> 

- <span data-ttu-id="9aa54-151">[Esta visão geral da Área de Trabalho Virtual do Windows](https://docs.microsoft.com/azure/virtual-desktop/overview).</span><span class="sxs-lookup"><span data-stu-id="9aa54-151">[This overview of Windows Virtual Desktop](https://docs.microsoft.com/azure/virtual-desktop/overview).</span></span>
- <span data-ttu-id="9aa54-152">[O vídeo da parte 2 sobre o uso da Área de Trabalho Virtual do Windows para funcionários remotos](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity).</span><span class="sxs-lookup"><span data-stu-id="9aa54-152">[The Part 2 video on using Windows Virtual Desktop for remote workers](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity).</span></span>

>[!Note]
><span data-ttu-id="9aa54-153">A Área de Trabalho Virtual do Windows não está incluída na assinatura do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aa54-153">Windows Virtual Desktop is not included with a Microsoft 365 subscription.</span></span> <span data-ttu-id="9aa54-154">Você deve pagar por uso com uma assinatura separada do Azure.</span><span class="sxs-lookup"><span data-stu-id="9aa54-154">You must pay for usage with a separate Azure subscription.</span></span>
>

## <a name="protect-your-remote-desktop-services-connections-with-the-remote-desktop-services-gateway"></a><span data-ttu-id="9aa54-155">Proteja seus serviços de Área de trabalho remota com o Gateway dos serviços de área de trabalho remota.</span><span class="sxs-lookup"><span data-stu-id="9aa54-155">Protect your Remote Desktop Services connections with the Remote Desktop Services Gateway</span></span>

<span data-ttu-id="9aa54-156">Se você estiver usando os Serviços de Área de Trabalho Remota da Microsoft (RDS) para permitir que os funcionários se conectem a computadores baseados no Windows em sua rede local, você deve usar um Gateway dos serviços de área de trabalho remota da Microsoft em sua rede Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9aa54-156">If you are using Remote Desktop Services (RDS) to allow employees to connect into Windows-based computers on your on-premises network, you should use a Microsoft Remote Desktop Services gateway in your edge network.</span></span> <span data-ttu-id="9aa54-157">O gateway usa o protocolo SSL (Secure Sockets Layer) para criptografar as comunicações e impede que o sistema que hospeda o RDS seja exposto diretamente à Internet.</span><span class="sxs-lookup"><span data-stu-id="9aa54-157">The gateway uses Secure Sockets Layer (SSL) to encrypt communications and prevents the system hosting RDS from being directly exposed to the Internet.</span></span>

![Conexões dos Serviços de Área de trabalho remota com o Gateway dos serviços de área de trabalho remota.](../media/empower-people-to-work-remotely-remote-access/empower-people-to-work-remotely-remote-access-remote-desktop.png)

<span data-ttu-id="9aa54-159">Confira [este artigo](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) para saber mais.</span><span class="sxs-lookup"><span data-stu-id="9aa54-159">See [this article](https://www.microsoft.com/security/blog/2020/04/16/security-guidance-remote-desktop-adoption/) for more information.</span></span>

## <a name="admin-technical-resources-for-remote-access"></a><span data-ttu-id="9aa54-160">Recursos técnicos do administrador para acesso remoto</span><span class="sxs-lookup"><span data-stu-id="9aa54-160">Admin technical resources for remote access</span></span>

- [<span data-ttu-id="9aa54-161">Como otimizar rapidamente o tráfego do Office 365 para funcionários remotos e reduzir a carga em sua infraestrutura</span><span class="sxs-lookup"><span data-stu-id="9aa54-161">How to quickly optimize Office 365 traffic for remote staff & reduce the load on your infrastructure</span></span>](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571)
- [<span data-ttu-id="9aa54-162">Otimize a conectividade do Office 365 dos usuários remotos usando o túnel dividido da VPN</span><span class="sxs-lookup"><span data-stu-id="9aa54-162">Optimize Office 365 connectivity for remote users using VPN split tunneling</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-vpn-split-tunnel)

## <a name="results-of-step-2"></a><span data-ttu-id="9aa54-163">Resultados da Etapa 2</span><span class="sxs-lookup"><span data-stu-id="9aa54-163">Results of Step 2</span></span>

<span data-ttu-id="9aa54-164">Após a implantação de uma solução de acesso remoto para seus trabalhadores remotos:</span><span class="sxs-lookup"><span data-stu-id="9aa54-164">After deployment of a remote access solution for your remote workers:</span></span>

| <span data-ttu-id="9aa54-165">Configuração de acesso remoto</span><span class="sxs-lookup"><span data-stu-id="9aa54-165">Remote access configuration</span></span> | <span data-ttu-id="9aa54-166">Resultados</span><span class="sxs-lookup"><span data-stu-id="9aa54-166">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="9aa54-167">Existe uma solução VPN de acesso remoto instalada</span><span class="sxs-lookup"><span data-stu-id="9aa54-167">A remote access VPN solution is in place</span></span> | <span data-ttu-id="9aa54-168">Você configurou seu cliente VPN de acesso remoto para o túnel dividido e para a categoria Otimizar dos pontos de extremidade do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9aa54-168">You have configured your remote access VPN client for split tunneling and for the Optimize category of Microsoft 365 endpoints.</span></span> |
| <span data-ttu-id="9aa54-169">Não existe uma solução VPN de acesso remoto instalada e você precisa de acesso remoto somente a aplicativos locais baseados na Web</span><span class="sxs-lookup"><span data-stu-id="9aa54-169">No remote access VPN solution and you need remote access only to on-premises web-based apps</span></span> | <span data-ttu-id="9aa54-170">Você configurou o Proxy de Aplicativo do Azure.</span><span class="sxs-lookup"><span data-stu-id="9aa54-170">You have configured Azure Application Proxy.</span></span> |
| <span data-ttu-id="9aa54-171">Não existe uma solução VPN de acesso remoto instalada e você precisa acessar aplicativos locais, alguns dos quais não são baseados na Web</span><span class="sxs-lookup"><span data-stu-id="9aa54-171">No remote access VPN solution and you need access to on-premises apps, some of which are not web-based</span></span> | <span data-ttu-id="9aa54-172">Você configurou a VPN P2S do Azure.</span><span class="sxs-lookup"><span data-stu-id="9aa54-172">You have configured Azure P2S VPN.</span></span> |
| <span data-ttu-id="9aa54-173">Trabalhadores remotos estão usando seus dispositivos pessoais em casa</span><span class="sxs-lookup"><span data-stu-id="9aa54-173">Remote workers are using their personal devices from home</span></span> | <span data-ttu-id="9aa54-174">Você configurou a Área de Trabalho Virtual do Windows.</span><span class="sxs-lookup"><span data-stu-id="9aa54-174">You have configured Windows Virtual Desktop.</span></span> |
| <span data-ttu-id="9aa54-175">Os funcionários remotos estão usando as conexões de RDS para os sistemas locais</span><span class="sxs-lookup"><span data-stu-id="9aa54-175">Remote workers are using RDS connections to on-premises systems</span></span> | <span data-ttu-id="9aa54-176">Você implantou um Gateway dos Serviços de área de trabalho remota na rede Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="9aa54-176">You have deployed a Remote Desktop Services gateway in your edge network.</span></span> |
|||

## <a name="next-step"></a><span data-ttu-id="9aa54-177">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="9aa54-177">Next step</span></span>

<span data-ttu-id="9aa54-178">Prossiga com a [etapa 3](empower-people-to-work-remotely-security-compliance.md) para implantar o Centro de segurança do Microsoft 365 e serviços de conformidade para proteger seus aplicativos, dados e dispositivos.</span><span class="sxs-lookup"><span data-stu-id="9aa54-178">Continue with [Step 3](empower-people-to-work-remotely-security-compliance.md) to deploy Microsoft 365 security and compliance services to protect your apps, data, and devices.</span></span>
