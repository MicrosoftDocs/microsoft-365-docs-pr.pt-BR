---
title: Integrar o ATP do Office 365 com o ATP do Microsoft Defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 07/08/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 414fa693-d7b7-4a1d-a387-ebc3b6a52889
ms.collection:
- M365-security-compliance
description: Integre a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender para ver informações mais detalhadas sobre o gerenciamento de ameaças.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906b8b44922084a65999dd9ab10a09c827605c2
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201966"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="d8c9d-103">Integrar a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="d8c9d-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d8c9d-104">A [proteção avançada contra ameaças do office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) pode ser configurada para funcionar com a [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft defender ATP).</span><span class="sxs-lookup"><span data-stu-id="d8c9d-104">[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) (Office 365 ATP) can be configured to work with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) (Microsoft Defender ATP).</span></span>

<span data-ttu-id="d8c9d-105">Integrar o Office 365 ATP com o Microsoft defender ATP pode ajudar sua equipe de operações de segurança a monitorar e tomar ações rapidamente se os dispositivos dos usuários estiverem em risco.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-105">Integrating Office 365 ATP with Microsoft Defender ATP can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="d8c9d-106">Por exemplo, depois que a integração estiver habilitada, sua equipe de operações de segurança poderá ver os dispositivos potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes esses dispositivos têm no Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-106">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts those devices have in Microsoft Defender ATP.</span></span> 

<span data-ttu-id="d8c9d-107">A imagem a seguir representa a aparência da guia **dispositivos** como a integração do Microsoft defender ATP está habilitada:</span><span class="sxs-lookup"><span data-stu-id="d8c9d-107">The following image depicts what the **Devices** tab looks like have Microsoft Defender ATP integration enabled:</span></span>
  
![Quando o Microsoft defender ATP estiver habilitado, você poderá ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="d8c9d-109">Neste exemplo, você pode ver que os destinatários da mensagem de email detectado têm quatro dispositivos e um tem um alerta.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-109">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="d8c9d-110">Clicar no link de um dispositivo abre sua página no centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="d8c9d-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

> [!TIP]
> <span data-ttu-id="d8c9d-111">**[Saiba mais sobre o centro de segurança do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (também mencionado como o portal ATP do Microsoft defender).</span><span class="sxs-lookup"><span data-stu-id="d8c9d-111">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender ATP portal.)</span></span>
  
## <a name="requirements"></a><span data-ttu-id="d8c9d-112">Requirements</span><span class="sxs-lookup"><span data-stu-id="d8c9d-112">Requirements</span></span>

- <span data-ttu-id="d8c9d-113">Sua organização deve ter o Office 365 ATP Plan 2 (ou o Office 365 E5) e o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-113">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="d8c9d-114">Você deve ser um administrador global ou ter uma função de administrador de segurança (como administrador de segurança) atribuída [no &amp; centro de conformidade de segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="d8c9d-114">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="d8c9d-115">(Consulte [permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="d8c9d-115">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="d8c9d-116">Você deve ter acesso ao [Explorer (ou às detecções em tempo real)](threat-explorer.md) no centro de segurança & conformidade e no centro de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-116">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="d8c9d-117">Para integrar o Office 365 ATP com o Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="d8c9d-117">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="d8c9d-118">A integração do Office 365 ATP com o Microsoft defender ATP é configurada usando o centro de conformidade & segurança e o centro de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-118">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="d8c9d-119">Como administrador global ou administrador de segurança, acesse [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-119">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="d8c9d-120">(Isso leva você para o centro de conformidade & segurança do Office 365.)</span><span class="sxs-lookup"><span data-stu-id="d8c9d-120">(This takes you to the Office 365 Security & Compliance Center.)</span></span>
    
2. <span data-ttu-id="d8c9d-121">No painel de navegação, escolha Gerenciador de **Gerenciamento de ameaças**  >  **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-121">In the navigation pane, choose **Threat management** > **Explorer**.</span></span><br><span data-ttu-id="d8c9d-122">![Gerenciador no menu de gerenciamento de ameaças](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="d8c9d-122">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="d8c9d-123">No canto superior direito da tela, escolha configurações de **WDATP**.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-123">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="d8c9d-124">Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-124">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="d8c9d-125">![Conexão ATP do Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="d8c9d-125">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="d8c9d-126">Vá para o centro de segurança do Microsoft defender ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).</span><span class="sxs-lookup"><span data-stu-id="d8c9d-126">Go to the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

6. <span data-ttu-id="d8c9d-127">Na barra de navegação, escolha **configurações**.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-127">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="d8c9d-128">Em seguida, em **geral**, escolha **recursos avançados**.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-128">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="d8c9d-129">Role para baixo até a **conexão do Office 365 Threat Intelligence**e ative a conexão.</span><span class="sxs-lookup"><span data-stu-id="d8c9d-129">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span><br/><span data-ttu-id="d8c9d-130">![Conexão do Office 365 Threat Intelligence](../../media/mdatp-oatptoggle.png)</span><span class="sxs-lookup"><span data-stu-id="d8c9d-130">![Office 365 threat intelligence connection](../../media/mdatp-oatptoggle.png)</span></span><br>

## <a name="related-articles"></a><span data-ttu-id="d8c9d-131">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d8c9d-131">Related articles</span></span>

[<span data-ttu-id="d8c9d-132">Recursos de investigação e resposta contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="d8c9d-132">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="d8c9d-133">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="d8c9d-133">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="d8c9d-134">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="d8c9d-134">Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
