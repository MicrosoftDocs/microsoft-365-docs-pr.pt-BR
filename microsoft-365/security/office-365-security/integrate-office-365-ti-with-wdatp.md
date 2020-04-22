---
title: Integrar a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 04/13/2020
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
ms.openlocfilehash: e416d70baf7498b0163d5bd8aa8e923585a5e5a4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633804"
---
# <a name="integrate-office-365-advanced-threat-protection-with-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="a5d33-103">Integrar a proteção avançada contra ameaças do Office 365 com a proteção avançada contra ameaças do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="a5d33-103">Integrate Office 365 Advanced Threat Protection with Microsoft Defender Advanced Threat Protection</span></span>

<span data-ttu-id="a5d33-104">Se você fizer parte da equipe de segurança da sua organização, poderá integrar a [proteção avançada contra ameaças do Office 365](office-365-atp.md) e os recursos de investigação e resposta relacionados à [proteção avançada contra ameaças do Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span><span class="sxs-lookup"><span data-stu-id="a5d33-104">If you are part of your organization's security team, you can integrate [Office 365 Advanced Threat Protection](office-365-atp.md) and related investigation and response features with [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection).</span></span> <span data-ttu-id="a5d33-105">Isso pode ajudá-lo a entender rapidamente se as máquinas dos usuários estão em risco quando você está investigando ameaças no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a5d33-105">This can help you quickly understand if users' machines are at risk when you are investigating threats in Office 365.</span></span> <span data-ttu-id="a5d33-106">Por exemplo, depois que a integração estiver habilitada, você poderá ver uma lista de máquinas que são usadas pelos destinatários de uma mensagem de email detectada, bem como os alertas recentes que essas máquinas têm na proteção avançada contra ameaças do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a5d33-106">For example, once integration is enabled, you will be able to see a list of machines that are used by the recipients of a detected email message, as well as how many recent alerts those machines have in Microsoft Defender Advanced Threat Protection.</span></span>
  
<span data-ttu-id="a5d33-107">A imagem a seguir mostra a guia **dispositivos** que você verá quando tiver a integração do Microsoft defender ATP habilitada:</span><span class="sxs-lookup"><span data-stu-id="a5d33-107">The following image shows the **Devices** tab that you'll see when have Microsoft Defender ATP integration enabled:</span></span>
  
![Quando o Microsoft defender ATP estiver habilitado, você poderá ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)
  
<span data-ttu-id="a5d33-109">Neste exemplo, você pode ver que os destinatários da mensagem de email têm quatro dispositivos e um tem um alerta.</span><span class="sxs-lookup"><span data-stu-id="a5d33-109">In this example, you can see that the recipients of the email message have four devices and one has an alert.</span></span> <span data-ttu-id="a5d33-110">Clicar no link de um dispositivo abre sua página na central de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a5d33-110">Clicking the link for a device opens its page in the Microsoft Defender Security Center.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="a5d33-111">Requirements</span><span class="sxs-lookup"><span data-stu-id="a5d33-111">Requirements</span></span>

- <span data-ttu-id="a5d33-112">Sua organização deve ter o Office 365 ATP Plan 2 (ou o Office 365 E5) e o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="a5d33-112">Your organization must have Office 365 ATP Plan 2 (or Office 365 E5) and Microsoft Defender ATP.</span></span>
    
- <span data-ttu-id="a5d33-113">Você deve ser um administrador global ou ter uma função de administrador de segurança (como administrador de segurança) atribuída [no &amp; centro de conformidade de segurança](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="a5d33-113">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security &amp; Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="a5d33-114">(Consulte [permissões no centro de &amp; conformidade de segurança](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="a5d33-114">(See [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>
    
- <span data-ttu-id="a5d33-115">Você deve ter acesso ao [Explorer (ou às detecções em tempo real)](threat-explorer.md) no centro de segurança & conformidade e no centro de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a5d33-115">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>
    
## <a name="to-integrate-office-365-atp-with-microsoft-defender-atp"></a><span data-ttu-id="a5d33-116">Para integrar o Office 365 ATP com o Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="a5d33-116">To integrate Office 365 ATP with Microsoft Defender ATP</span></span>

<span data-ttu-id="a5d33-117">A integração do Office 365 ATP com o Microsoft defender ATP é configurada usando o centro de conformidade & segurança e o centro de segurança do Microsoft defender.</span><span class="sxs-lookup"><span data-stu-id="a5d33-117">Integrating Office 365 ATP with Microsoft Defender ATP is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>
  
1. <span data-ttu-id="a5d33-118">Como administrador global ou administrador de segurança, acesse [https://protection.office.com](https://protection.office.com) e entre com sua conta corporativa ou de estudante.</span><span class="sxs-lookup"><span data-stu-id="a5d33-118">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="a5d33-119">Escolha **Threat management** \> **Gerenciador**de gerenciamento de ameaças.</span><span class="sxs-lookup"><span data-stu-id="a5d33-119">Choose **Threat management** \> **Explorer**.</span></span><br><span data-ttu-id="a5d33-120">![Gerenciador no menu de gerenciamento de ameaças](../../media/ThreatMgmt-Explorer-nav.png)</span><span class="sxs-lookup"><span data-stu-id="a5d33-120">![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)</span></span><br>
    
3. <span data-ttu-id="a5d33-121">No canto superior direito da tela, escolha configurações de **WDATP**.</span><span class="sxs-lookup"><span data-stu-id="a5d33-121">In the upper right corner of the screen, choose **WDATP Settings**.</span></span>
    
4. <span data-ttu-id="a5d33-122">Na caixa de diálogo conexão ATP do Microsoft defender, ative **conectar ao Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="a5d33-122">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span><br><span data-ttu-id="a5d33-123">![Conexão ATP do Microsoft defender](../../media/Explorer-WDATPConnection-dialog.png)</span><span class="sxs-lookup"><span data-stu-id="a5d33-123">![Microsoft Defender ATP connection](../../media/Explorer-WDATPConnection-dialog.png)</span></span><br>
    
5. <span data-ttu-id="a5d33-124">Habilite a conexão no centro de segurança do Microsoft[https://securitycenter.windows.com](https://securitycenter.windows.com)defender ().</span><span class="sxs-lookup"><span data-stu-id="a5d33-124">Enable the connection in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a5d33-125">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a5d33-125">Related topics</span></span>

[<span data-ttu-id="a5d33-126">Recursos de investigação e resposta contra ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="a5d33-126">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)
  
[<span data-ttu-id="a5d33-127">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="a5d33-127">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  

