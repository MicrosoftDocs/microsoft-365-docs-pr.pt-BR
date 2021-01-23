---
title: Usar o Microsoft Defender para Office 365 em conjunto com o Microsoft Defender para Ponto de Extremidade
f1.keywords:
- NOCSH
keywords: integrar, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use o Microsoft Defender para Office 365 em conjunto com o Microsoft Defender for Endpoint para obter informações mais detalhadas sobre ameaças contra seus dispositivos e conteúdo de email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24b81bb4c445c44d7c0228fa1c4440faff642816
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939327"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="3f3df-104">Usar o Microsoft Defender para Office 365 em conjunto com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3f3df-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="3f3df-105">[O Microsoft Defender para Office 365](office-365-atp.md) pode ser configurado para funcionar com [o Microsoft Defender para Ponto de Extremidade.](https://docs.microsoft.com/windows/security/threat-protection)</span><span class="sxs-lookup"><span data-stu-id="3f3df-105">[Microsoft Defender for Office 365](office-365-atp.md) can be configured to work with [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection).</span></span>

<span data-ttu-id="3f3df-106">A integração do Microsoft Defender para Office 365 com o Microsoft Defender for Endpoint pode ajudar a equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estão em risco.</span><span class="sxs-lookup"><span data-stu-id="3f3df-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="3f3df-107">Por exemplo, depois que a integração for habilitada, sua equipe de operações de segurança poderá ver os dispositivos potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="3f3df-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="3f3df-108">A imagem a seguir ilustra a aparência da guia **Dispositivos** com a integração do Microsoft Defender for Endpoint habilitada:</span><span class="sxs-lookup"><span data-stu-id="3f3df-108">The following image depicts what the **Devices** tab looks like have Microsoft Defender for Endpoint integration enabled:</span></span>

![Quando o Microsoft Defender para Ponto de Extremidade está habilitado, você pode ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="3f3df-110">Neste exemplo, você pode ver que os destinatários da mensagem de email detectada têm quatro dispositivos e um tem um alerta.</span><span class="sxs-lookup"><span data-stu-id="3f3df-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="3f3df-111">Clicar no link para um dispositivo abre sua página na Central de Segurança do Microsoft Defender ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="3f3df-111">Clicking the link for a device opens its page in the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

> [!TIP]
> <span data-ttu-id="3f3df-112">**[Saiba mais sobre a Central de Segurança do Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (também conhecida como portal de ponto de extremidade do Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="3f3df-112">**[Learn more about the Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (also referred to as the Microsoft Defender for Endpoint portal.)</span></span>

## <a name="requirements"></a><span data-ttu-id="3f3df-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3f3df-113">Requirements</span></span>

- <span data-ttu-id="3f3df-114">Sua organização deve ter o Microsoft Defender para Office 365 (ou Office 365 E5) e o Microsoft Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="3f3df-114">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="3f3df-115">Você deve ser um administrador global ou ter uma função de administrador de segurança (como o Administrador de Segurança) atribuída no Centro de [& Conformidade](https://protection.office.com)e Segurança.</span><span class="sxs-lookup"><span data-stu-id="3f3df-115">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="3f3df-116">(Consulte [Permissões no Centro de Conformidade e & Segurança)](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="3f3df-116">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="3f3df-117">Você deve ter acesso ao [Explorer (ou](threat-explorer.md) detecções em tempo real) no Centro de Conformidade & segurança e na Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3f3df-117">You must have access to both [Explorer (or real-time detections)](threat-explorer.md) in the Security & Compliance Center and the Microsoft Defender Security Center.</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="3f3df-118">Para integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3f3df-118">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="3f3df-119">A integração do Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade é configurada usando o Centro de Conformidade & Segurança e a Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="3f3df-119">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up by using both the Security & Compliance Center AND the Microsoft Defender Security Center.</span></span>

1. <span data-ttu-id="3f3df-120">Como administrador global ou administrador de segurança, acesse <https://protection.office.com> e entre.</span><span class="sxs-lookup"><span data-stu-id="3f3df-120">As a global administrator or a security administrator, go to <https://protection.office.com> and sign in.</span></span> <span data-ttu-id="3f3df-121">(Isso leva você ao Centro de Conformidade e Segurança & do Office 365.)</span><span class="sxs-lookup"><span data-stu-id="3f3df-121">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="3f3df-122">No painel de navegação, escolha Explorador **de gerenciamento de** \> **ameaças.**</span><span class="sxs-lookup"><span data-stu-id="3f3df-122">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Explorer in Threat Management menu](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="3f3df-124">No canto superior direito da tela, escolha Defender para Configurações de Ponto de Extremidade **(Configurações MDE).**</span><span class="sxs-lookup"><span data-stu-id="3f3df-124">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="3f3df-125">Na caixa de diálogo Conexão do Microsoft Defender para Ponto de Extremidade, a ligue **Conectar-se ao Microsoft Defender para Ponto de Extremidade.**</span><span class="sxs-lookup"><span data-stu-id="3f3df-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Conexão do Microsoft Defender para Ponto de Extremidade](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="3f3df-127">Vá para a Central de Segurança do Microsoft Defender ( <https://securitycenter.windows.com> ).</span><span class="sxs-lookup"><span data-stu-id="3f3df-127">Go to the Microsoft Defender Security Center (<https://securitycenter.windows.com>).</span></span>

6. <span data-ttu-id="3f3df-128">Na barra de navegação, escolha **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="3f3df-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="3f3df-129">Em seguida, em **Geral,** escolha **Recursos avançados.**</span><span class="sxs-lookup"><span data-stu-id="3f3df-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="3f3df-130">Role para baixo até a conexão de Inteligência contra Ameaças do **Office 365** e a ligue.</span><span class="sxs-lookup"><span data-stu-id="3f3df-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Conexão de inteligência contra ameaças do Office 365](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="3f3df-132">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="3f3df-132">Related articles</span></span>

[<span data-ttu-id="3f3df-133">Recursos de investigação e resposta a ameaças no Office 365</span><span class="sxs-lookup"><span data-stu-id="3f3df-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="3f3df-134">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="3f3df-134">Microsoft Defender for Office 365</span></span>](office-365-atp.md)

[<span data-ttu-id="3f3df-135">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3f3df-135">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection)
