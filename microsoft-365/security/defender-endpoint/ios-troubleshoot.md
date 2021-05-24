---
title: Solucionar problemas e encontrar respostas sobre perguntas frequentes relacionadas ao Microsoft Defender para Ponto de Extremidade no iOS
description: Solução de problemas e perguntas frequentes - Microsoft Defender para Ponto de Extremidade no iOS
keywords: microsoft, defender, Microsoft Defender para Endpoint, ios, solução de problemas, perguntas frequentes, como
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13c0a575fd2614f58eb6a2163cda04118c2a391d
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636273"
---
# <a name="troubleshoot-issues-and-find-answers-to-faqs-on-microsoft-defender-for-endpoint-on-ios"></a><span data-ttu-id="d53fc-104">Solucionar problemas e encontrar respostas para perguntas frequentes no Microsoft Defender para Endpoint no iOS</span><span class="sxs-lookup"><span data-stu-id="d53fc-104">Troubleshoot issues and find answers to FAQs on Microsoft Defender for Endpoint on iOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d53fc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d53fc-105">**Applies to:**</span></span>
- [<span data-ttu-id="d53fc-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d53fc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d53fc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d53fc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d53fc-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="d53fc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d53fc-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="d53fc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="d53fc-110">Este tópico fornece informações de solução de problemas para ajudá-lo a resolver problemas que podem surgir à medida que você usa o Microsoft Defender para Ponto de Extremidade no iOS.</span><span class="sxs-lookup"><span data-stu-id="d53fc-110">This topic provides troubleshooting information to help you address issues that may arise as you use Microsoft Defender for Endpoint on iOS.</span></span>



> [!NOTE]
> <span data-ttu-id="d53fc-111">O Defender for Endpoint no iOS usaria uma VPN para fornecer o recurso de Proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="d53fc-111">Defender for Endpoint on iOS would use a VPN in order to provide the Web Protection feature.</span></span> <span data-ttu-id="d53fc-112">Esta não é uma VPN regular e é uma VPN local/auto-loop que não faz o tráfego fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53fc-112">This is not a regular VPN and is a local/self-looping VPN that does not take traffic outside the device.</span></span>

## <a name="apps-dont-work-when-vpn-is-turned-on"></a><span data-ttu-id="d53fc-113">Os aplicativos não funcionam quando a VPN está conexões</span><span class="sxs-lookup"><span data-stu-id="d53fc-113">Apps don't work when VPN is turned on</span></span>
<span data-ttu-id="d53fc-114">Há alguns aplicativos que param de funcionar quando uma VPN ativa é detectada.</span><span class="sxs-lookup"><span data-stu-id="d53fc-114">There are some apps that stop functioning when an active VPN is detected.</span></span> <span data-ttu-id="d53fc-115">Você pode desabilitar a VPN durante o tempo em que está usando esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d53fc-115">You can disable the VPN during the time you are using such apps.</span></span> 

<span data-ttu-id="d53fc-116">Por padrão, o Defender para Ponto de Extremidade no iOS inclui e habilita o recurso de proteção da Web.</span><span class="sxs-lookup"><span data-stu-id="d53fc-116">By default, Defender for Endpoint on iOS includes and enables the web protection feature.</span></span> <span data-ttu-id="d53fc-117">[A proteção da Web](web-protection-overview.md) ajuda a proteger dispositivos contra ameaças da Web e proteger os usuários contra ataques de phishing.</span><span class="sxs-lookup"><span data-stu-id="d53fc-117">[Web protection](web-protection-overview.md) helps to secure devices against web threats and protect users from phishing attacks.</span></span> <span data-ttu-id="d53fc-118">O Defender for Endpoint no iOS usa uma VPN para fornecer essa proteção.</span><span class="sxs-lookup"><span data-stu-id="d53fc-118">Defender for Endpoint on iOS uses a VPN in order to provide this protection.</span></span> <span data-ttu-id="d53fc-119">Observe que esta é uma VPN local e, ao contrário da VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53fc-119">Please note this is a local VPN and unlike traditional VPN, network traffic is not sent outside the device.</span></span>

<span data-ttu-id="d53fc-120">Embora habilitada por padrão, pode haver alguns casos que exigem que você desabilite a VPN.</span><span class="sxs-lookup"><span data-stu-id="d53fc-120">While enabled by default, there might be some cases that require you to disable VPN.</span></span> <span data-ttu-id="d53fc-121">Por exemplo, você deseja executar alguns aplicativos que não funcionam quando uma VPN está configurada.</span><span class="sxs-lookup"><span data-stu-id="d53fc-121">For example, you want to run some apps that do not work when a VPN is configured.</span></span> <span data-ttu-id="d53fc-122">Nesses casos, você pode optar por desabilitar a VPN do aplicativo no dispositivo seguindo as etapas abaixo:</span><span class="sxs-lookup"><span data-stu-id="d53fc-122">In such cases, you can choose to disable VPN from the app on the device by following the steps below:</span></span>

1. <span data-ttu-id="d53fc-123">Em seu dispositivo iOS, abra o aplicativo **Configurações,** clique ou toque em **Geral** **e,** em seguida, VPN .</span><span class="sxs-lookup"><span data-stu-id="d53fc-123">On your iOS device, open the **Settings** app, click or tap **General** and then **VPN**.</span></span>
1. <span data-ttu-id="d53fc-124">Clique ou toque no botão "i" do Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="d53fc-124">Click or tap the "i" button for Microsoft Defender for Endpoint.</span></span>
1. <span data-ttu-id="d53fc-125">Desative o **Conexão Sob Demanda para** desabilitar a VPN.</span><span class="sxs-lookup"><span data-stu-id="d53fc-125">Toggle off **Connect On Demand** to disable VPN.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d53fc-126">![Vpn config connect on demand](images/ios-vpn-config.png)</span><span class="sxs-lookup"><span data-stu-id="d53fc-126">![VPN config connect on demand](images/ios-vpn-config.png)</span></span>

> [!NOTE]
> <span data-ttu-id="d53fc-127">A Proteção da Web não estará disponível quando a VPN estiver desabilitada.</span><span class="sxs-lookup"><span data-stu-id="d53fc-127">Web Protection will not be available when VPN is disabled.</span></span> <span data-ttu-id="d53fc-128">Para habilitar a Proteção Web de novo, abra o aplicativo Microsoft Defender para Ponto de Extremidade no dispositivo e clique ou toque em **Iniciar VPN**.</span><span class="sxs-lookup"><span data-stu-id="d53fc-128">To re-enable Web Protection, open the Microsoft Defender for Endpoint app on the device and click or tap **Start VPN**.</span></span>

## <a name="issues-with-multiple-vpn-profiles"></a><span data-ttu-id="d53fc-129">Problemas com vários perfis VPN</span><span class="sxs-lookup"><span data-stu-id="d53fc-129">Issues with multiple VPN profiles</span></span>

<span data-ttu-id="d53fc-130">O iOS da Apple não dá suporte a várias VPNs em todo o dispositivo para serem ativas simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="d53fc-130">Apple iOS does not support multiple device-wide VPNs to be active simultaneously.</span></span> <span data-ttu-id="d53fc-131">Embora vários perfis VPN possam existir no dispositivo, apenas uma VPN pode estar ativa por vez.</span><span class="sxs-lookup"><span data-stu-id="d53fc-131">While multiple VPN profiles can exist on the device, only one VPN can be active at a time.</span></span>


## <a name="battery-consumption"></a><span data-ttu-id="d53fc-132">Consumo de bateria</span><span class="sxs-lookup"><span data-stu-id="d53fc-132">Battery consumption</span></span>

<span data-ttu-id="d53fc-133">O uso da bateria por um aplicativo é calculado pela Apple com base em uma infinidade de fatores, incluindo o uso da CPU e da rede.</span><span class="sxs-lookup"><span data-stu-id="d53fc-133">The battery usage by an app is computed by Apple based on a multitude of factors including CPU and Network usage.</span></span> <span data-ttu-id="d53fc-134">O Microsoft Defender para Ponto de Extremidade usa uma VPN local/loop-back em segundo plano para verificar o tráfego da Web em busca de sites ou conexões mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="d53fc-134">Microsoft Defender for Endpoint uses a local/loop-back VPN in the background to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="d53fc-135">Os pacotes de rede de qualquer aplicativo passam por essa verificação e isso faz com que o uso da bateria do Microsoft Defender para o Ponto de Extremidade seja calculado de forma impreciso.</span><span class="sxs-lookup"><span data-stu-id="d53fc-135">Network packets from any app go through this check and that causes the battery usage of Microsoft Defender for Endpoint to be computed inaccurately.</span></span> <span data-ttu-id="d53fc-136">Isso dá uma falsa impressão ao usuário.</span><span class="sxs-lookup"><span data-stu-id="d53fc-136">This gives a false impression to the user.</span></span> <span data-ttu-id="d53fc-137">O consumo real de bateria do Microsoft Defender para Ponto de Extremidade é menor do que o mostrado na página Bateria Configurações no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53fc-137">The actual battery consumption of Microsoft Defender for Endpoint is lesser than what is shown on the Battery Settings page on the device.</span></span> <span data-ttu-id="d53fc-138">Isso se baseia em testes realizados no aplicativo Microsoft Defender para Ponto de Extremidade para entender o consumo de bateria.</span><span class="sxs-lookup"><span data-stu-id="d53fc-138">This is based on conducted tests done on the Microsoft Defender for Endpoint app to understand battery consumption.</span></span>

<span data-ttu-id="d53fc-139">Além disso, a VPN usada é uma VPN local e, ao contrário de uma VPN tradicional, o tráfego de rede não é enviado fora do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53fc-139">Also the VPN used is a local VPN and unlike a traditional VPN, network traffic is not sent outside the device.</span></span>

## <a name="data-usage"></a><span data-ttu-id="d53fc-140">Uso de dados</span><span class="sxs-lookup"><span data-stu-id="d53fc-140">Data usage</span></span>

<span data-ttu-id="d53fc-141">O Microsoft Defender para Ponto de Extremidade usa uma VPN local/loopback para verificar o tráfego da Web em busca de sites ou conexões mal-intencionadas.</span><span class="sxs-lookup"><span data-stu-id="d53fc-141">Microsoft Defender for Endpoint uses a local/loopback VPN to check web traffic for any malicious websites or connections.</span></span> <span data-ttu-id="d53fc-142">Devido a esse motivo, a Apple conta o uso de dados para o Microsoft Defender para o Ponto de Extremidade de forma impreciso.</span><span class="sxs-lookup"><span data-stu-id="d53fc-142">Due to this reason Apple accounts data usage to Microsoft Defender for Endpoint inaccurately.</span></span> <span data-ttu-id="d53fc-143">O uso real de dados pelo Microsoft Defender para Ponto de Extremidade não é significativo e muito menos do que o mostrado no data Usage Configurações no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53fc-143">The actual data usage by Microsoft Defender for Endpoint is not significant and much less than what is shown on the Data Usage Settings on the device.</span></span>

## <a name="report-unsafe-site"></a><span data-ttu-id="d53fc-144">Relatar site não seguro</span><span class="sxs-lookup"><span data-stu-id="d53fc-144">Report unsafe site</span></span>

<span data-ttu-id="d53fc-145">Sites de phishing personificam sites confiáveis com o objetivo de obter suas informações pessoais ou financeiras.</span><span class="sxs-lookup"><span data-stu-id="d53fc-145">Phishing websites impersonate trustworthy websites for the purpose of obtaining your personal or financial information.</span></span> <span data-ttu-id="d53fc-146">Visite a [página Fornecer comentários sobre proteção de rede](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) para relatar um site que pode ser um site de phishing.</span><span class="sxs-lookup"><span data-stu-id="d53fc-146">Visit the [Provide feedback about network protection](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) page to report a website that could be a phishing site.</span></span>

## <a name="malicious-site-detected"></a><span data-ttu-id="d53fc-147">Site mal-intencionado detectado</span><span class="sxs-lookup"><span data-stu-id="d53fc-147">Malicious site detected</span></span>

<span data-ttu-id="d53fc-148">O Microsoft Defender para Ponto de Extremidade protege você contra phishing ou outros ataques baseados na Web.</span><span class="sxs-lookup"><span data-stu-id="d53fc-148">Microsoft Defender for Endpoint protects you against phishing or other web-based attacks.</span></span> <span data-ttu-id="d53fc-149">Se um site mal-intencionado for detectado, a conexão será bloqueada e um alerta será enviado para o portal da Central de Segurança da organização.</span><span class="sxs-lookup"><span data-stu-id="d53fc-149">If a malicious site is detected, the connection is blocked and an alert is sent to the organization's Security Center portal.</span></span> <span data-ttu-id="d53fc-150">O alerta inclui o nome de domínio da conexão, o endereço IP remoto e os detalhes do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d53fc-150">The alert includes the domain name of the connection, remote IP address and the device details.</span></span>

<span data-ttu-id="d53fc-151">Além disso, uma notificação é mostrada no dispositivo iOS.</span><span class="sxs-lookup"><span data-stu-id="d53fc-151">In addition, a notification is shown on the iOS device.</span></span> <span data-ttu-id="d53fc-152">Tocar na notificação abre a tela a seguir para que o usuário revise os detalhes.</span><span class="sxs-lookup"><span data-stu-id="d53fc-152">Tapping on the notification opens the following screen for the user to review the details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d53fc-153">![Imagem do site relatada como notificação não segura](images/ios-phish-alert.png)</span><span class="sxs-lookup"><span data-stu-id="d53fc-153">![Image of site reported as unsafe notification](images/ios-phish-alert.png)</span></span>

## <a name="data-and-privacy"></a><span data-ttu-id="d53fc-154">Dados e Privacidade</span><span class="sxs-lookup"><span data-stu-id="d53fc-154">Data and Privacy</span></span>

<span data-ttu-id="d53fc-155">Para obter detalhes sobre dados coletados e privacidade, consulte Informações de Privacidade [- Microsoft Defender para Ponto de Extremidade no iOS](ios-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="d53fc-155">For details about data collected and privacy, see [Privacy Information - Microsoft Defender for Endpoint on iOS](ios-privacy.md).</span></span>

