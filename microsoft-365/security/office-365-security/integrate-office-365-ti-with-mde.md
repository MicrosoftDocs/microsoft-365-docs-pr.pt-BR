---
title: Usar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade
f1.keywords:
- NOCSH
keywords: integre, Microsoft Defender, Microsoft Defender for Endpoint
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Use o Microsoft Defender para Office 365 com o Microsoft Defender para Endpoint para obter informações mais detalhadas sobre ameaças contra seus dispositivos e conteúdo de email.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e59f608a6f732f58002dfd2ff34666865ab23f3d
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028866"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e580a-104">Usar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e580a-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="e580a-105">[O Microsoft Defender para Office 365](defender-for-office-365.md) pode ser configurado para trabalhar com o Microsoft Defender para Ponto de [Extremidade](/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="e580a-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="e580a-106">A integração do Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade pode ajudar sua equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estão em risco.</span><span class="sxs-lookup"><span data-stu-id="e580a-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="e580a-107">Por exemplo, depois que a integração for habilitada, sua equipe de operações de segurança poderá ver os dispositivos que são potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="e580a-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="e580a-108">A imagem a seguir mostra a aparência da guia **Dispositivos** quando você tem a integração do Microsoft Defender for Endpoint habilitada:</span><span class="sxs-lookup"><span data-stu-id="e580a-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Quando o Microsoft Defender for Endpoint está habilitado, você pode ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="e580a-110">Neste exemplo, você pode ver que os destinatários da mensagem de email detectada têm quatro dispositivos e um tem um alerta.</span><span class="sxs-lookup"><span data-stu-id="e580a-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="e580a-111">Clicar no link de um dispositivo abre sua página em [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (anteriormente o Central de Segurança do Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="e580a-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="e580a-112">O Microsoft 365 Defender portal substitui o Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e580a-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="e580a-113">Consulte [Microsoft Defender for Endpoint no Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="e580a-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="e580a-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="e580a-114">Requirements</span></span>

- <span data-ttu-id="e580a-115">Sua organização deve ter o Microsoft Defender para Office 365 (ou Office 365 E5) e o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e580a-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="e580a-116">Você deve ser um administrador global ou ter uma função de administrador de segurança (como Administrador de Segurança) atribuída Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e580a-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="e580a-117">(Consulte [Permissões no Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="e580a-117">(See [Permissions in the Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="e580a-118">Você deve ter acesso ao [Explorer (ou detecções em tempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="e580a-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="e580a-119">Para integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e580a-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="e580a-120">A integração do Microsoft Defender para Office 365 com o Microsoft Defender for Endpoint está configurada no Defender para Ponto de Extremidade e no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="e580a-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="e580a-121">Como administrador global ou administrador de segurança, acesse [https://security.microsoft.com](https://security.microsoft.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="e580a-121">As a global administrator or a security administrator, go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> <span data-ttu-id="e580a-122">(Isso o leva ao portal Microsoft 365 Defender.)</span><span class="sxs-lookup"><span data-stu-id="e580a-122">(This takes you to the Microsoft 365 Defender portal.)</span></span>

2. <span data-ttu-id="e580a-123">No painel de navegação, escolha **Email & colaboração** \> **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e580a-123">In the navigation pane, choose **Email & collaboration** \> **Explorer**.</span></span>

3. <span data-ttu-id="e580a-124">No canto superior direito da tela, clique em **MDE Configurações**.</span><span class="sxs-lookup"><span data-stu-id="e580a-124">In the upper right corner of the screen, click **MDE Settings**.</span></span>

4. <span data-ttu-id="e580a-125">Na caixa de diálogo Conexão do Microsoft Defender para Ponto de Extremidade, a Conexão **para o Microsoft Defender para Ponto de Extremidade**.</span><span class="sxs-lookup"><span data-stu-id="e580a-125">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="Conexão MDE":::

5. <span data-ttu-id="e580a-127">Vá para o Microsoft 365 Defender portal ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="e580a-127">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="e580a-128">Na barra de navegação, escolha **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="e580a-128">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="e580a-129">Em **Geral,** escolha **Recursos avançados.**</span><span class="sxs-lookup"><span data-stu-id="e580a-129">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="e580a-130">Role para baixo **Office 365 conexão de Inteligência contra Ameaças** e a ligue.</span><span class="sxs-lookup"><span data-stu-id="e580a-130">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 de inteligência contra ameaças](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="e580a-132">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="e580a-132">Related articles</span></span>

[<span data-ttu-id="e580a-133">Recursos de investigação e resposta contra ameaças Office 365</span><span class="sxs-lookup"><span data-stu-id="e580a-133">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="e580a-134">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="e580a-134">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="e580a-135">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e580a-135">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
