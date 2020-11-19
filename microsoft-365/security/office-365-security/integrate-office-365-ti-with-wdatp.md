---
title: Usar o Microsoft defender para Office 365 junto com o Microsoft defender para ponto de extremidade
f1.keywords:
- NOCSH
keywords: integrar, Microsoft defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 09/29/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use o Microsoft defender para Office 365 junto com o Microsoft defender para ponto de extremidade para obter informações mais detalhadas sobre as ameaças contra seus dispositivos e conteúdo de email.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7f668aa1234509789dacd2b018b94f1bfbc79e2c
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357774"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="48e31-104">Usar o Microsoft defender para Office 365 junto com o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="48e31-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="48e31-105">[O Microsoft defender para Office 365](office-365-atp.md) pode ser configurado para trabalhar com [o Microsoft defender para ponto de extremidade](https://docs.microsoft.com/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="48e31-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="48e31-106">A integração do Microsoft defender para Office 365 com o Microsoft defender para o ponto de extremidade pode ajudar sua equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estiverem em risco.</span><span class="sxs-lookup"><span data-stu-id="48e31-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="48e31-107">Por exemplo, depois que a integração estiver habilitada, sua equipe de operações de segurança poderá ver os dispositivos potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="48e31-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span> 

<span data-ttu-id="48e31-108">A imagem a seguir mostra a aparência da guia **dispositivos** para que a integração do Microsoft defender para ponto de extremidade seja habilitada:</span><span class="sxs-lookup"><span data-stu-id="48e31-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>
  
![Quando o Microsoft defender para ponto de extremidade estiver habilitado, você poderá ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="48e31-110">Neste exemplo, você pode ver que os destinatários da mensagem de email detectado têm quatro dispositivos e um tem um alerta.</span><span class="sxs-lookup"><span data-stu-id="48e31-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="48e31-111">Clicar no link de um dispositivo abre sua página no centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="48e31-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="48e31-112">**[Saiba mais sobre a central de segurança do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (também conhecida como Microsoft defender para o portal de ponto de extremidade).</span><span class="sxs-lookup"><span data-stu-id="48e31-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="48e31-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48e31-113">Requirements</span></span>

- <span data-ttu-id="48e31-114">Sua organização deve ter o Microsoft defender para Office 365 (ou o Office 365 E5) e o Microsoft defender para ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="48e31-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>
    
- <span data-ttu-id="48e31-115">Você deve ser um administrador global ou ter uma função de administrador de segurança (como administrador de segurança) atribuída [no &amp; centro de conformidade de segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="48e31-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="48e31-116">(Consulte [permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="48e31-116">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="48e31-117">Você deve ter acesso ao [Explorer (ou às detecções em tempo real)](threat-explorer.md) no centro de segurança & conformidade e no centro de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="48e31-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="48e31-118">Para integrar o Microsoft defender para Office 365 com o Microsoft defender para ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="48e31-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="48e31-119">A integração do Microsoft defender para Office 365 com o Microsoft defender para ponto de extremidade é configurada usando o centro de segurança & conformidade e a central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="48e31-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="48e31-120">Como administrador global ou administrador de segurança, acesse [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="48e31-120">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="48e31-121">(Isso leva você para o centro de conformidade & segurança do Office 365.)</span><span class="sxs-lookup"><span data-stu-id="48e31-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="48e31-122">No painel de navegação, escolha Gerenciador de **Gerenciamento de ameaças**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="48e31-122">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="48e31-123">![Gerenciador no menu de gerenciamento de ameaças](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="48e31-123">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="48e31-124">No canto superior direito da tela, escolha **defender para configurações de ponto de extremidade**.</span><span class="sxs-lookup"><span data-stu-id="48e31-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings**.</span></span>
    
4. <span data-ttu-id="48e31-125">Na caixa de diálogo conexão do Microsoft defender para ponto de extremidade, ative **conectar ao Microsoft defender para ponto de extremidade**.</span><span class="sxs-lookup"><span data-stu-id="48e31-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span><br><span data-ttu-id="48e31-126">![Conexão de ponto de extremidade do Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="48e31-126">![Microsoft Defender for Endpoint connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="48e31-127">Vá para o centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="48e31-127">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="48e31-128">Na barra de navegação, escolha **configurações**.</span><span class="sxs-lookup"><span data-stu-id="48e31-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="48e31-129">Em seguida, em **geral**, escolha **recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="48e31-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="48e31-130">Role para baixo até a **conexão do Office 365 Threat Intelligence** e ative a conexão.</span><span class="sxs-lookup"><span data-stu-id="48e31-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="48e31-131">![Conexão do Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="48e31-131">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="48e31-132">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="48e31-132">Related articles</span></span>

[<span data-ttu-id="48e31-133">Recursos de investigação e resposta contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="48e31-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="48e31-134">Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="48e31-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
  
[<span data-ttu-id="48e31-135">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="48e31-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
