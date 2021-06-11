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
ms.openlocfilehash: 63ae9f8c1136a973e4fccb63ecfbaee2639c3f6f
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904075"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="d41e3-104">Usar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d41e3-104">Use Microsoft Defender for Office 365 together with Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="d41e3-105">[O Microsoft Defender para Office 365](defender-for-office-365.md) pode ser configurado para trabalhar com o Microsoft Defender para Ponto de [Extremidade](/windows/security/threat-protection).</span><span class="sxs-lookup"><span data-stu-id="d41e3-105">[Microsoft Defender for Office 365](defender-for-office-365.md) can be configured to work with [Microsoft Defender for Endpoint](/windows/security/threat-protection).</span></span>

<span data-ttu-id="d41e3-106">A integração do Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade pode ajudar sua equipe de operações de segurança a monitorar e tomar medidas rapidamente se os dispositivos dos usuários estão em risco.</span><span class="sxs-lookup"><span data-stu-id="d41e3-106">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint can help your security operations team monitor and take action quickly if users' devices are at risk.</span></span> <span data-ttu-id="d41e3-107">Por exemplo, depois que a integração for habilitada, sua equipe de operações de segurança poderá ver os dispositivos que são potencialmente afetados por uma mensagem de email detectada, bem como quantos alertas recentes foram gerados para esses dispositivos no Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="d41e3-107">For example, once integration is enabled, your security operations team will be able to see the devices that are potentially affected by a detected email message, as well as how many recent alerts were generated for those devices in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="d41e3-108">A imagem a seguir mostra a aparência da guia **Dispositivos** quando você tem a integração do Microsoft Defender for Endpoint habilitada:</span><span class="sxs-lookup"><span data-stu-id="d41e3-108">The following image depicts what the **Devices** tab looks like when you have Microsoft Defender for Endpoint integration enabled:</span></span>

![Quando o Microsoft Defender for Endpoint está habilitado, você pode ver uma lista de dispositivos com alertas.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

<span data-ttu-id="d41e3-110">Neste exemplo, você pode ver que os destinatários da mensagem de email detectada têm quatro dispositivos e um tem um alerta.</span><span class="sxs-lookup"><span data-stu-id="d41e3-110">In this example, you can see that the recipients of the detected email message have four devices and one has an alert.</span></span> <span data-ttu-id="d41e3-111">Clicar no link de um dispositivo abre sua página [no Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (anteriormente o Central de Segurança do Microsoft Defender).</span><span class="sxs-lookup"><span data-stu-id="d41e3-111">Clicking the link for a device opens its page in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center).</span></span>

> [!TIP]
> <span data-ttu-id="d41e3-112">O Microsoft 365 portal do Defender substitui o Central de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d41e3-112">The Microsoft 365 Defender portal replaces the Microsoft Defender Security Center.</span></span> <span data-ttu-id="d41e3-113">Consulte [Microsoft Defender for Endpoint no Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="d41e3-113">See [Microsoft Defender for Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).</span></span>

## <a name="requirements"></a><span data-ttu-id="d41e3-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d41e3-114">Requirements</span></span>

- <span data-ttu-id="d41e3-115">Sua organização deve ter o Microsoft Defender para Office 365 (ou Office 365 E5) e o Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="d41e3-115">Your organization must have Microsoft Defender for Office 365 (or Office 365 E5) and Microsoft Defender for Endpoint.</span></span>

- <span data-ttu-id="d41e3-116">Você deve ser um administrador global ou ter uma função de administrador de segurança (como Administrador de Segurança) atribuída Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d41e3-116">You must be a global administrator or have a security administrator role (such as Security Administrator) assigned in Microsoft 365.</span></span> <span data-ttu-id="d41e3-117">(Consulte Permissões no Centro de [Conformidade & Segurança](permissions-in-the-security-and-compliance-center.md))</span><span class="sxs-lookup"><span data-stu-id="d41e3-117">(See [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))</span></span>

- <span data-ttu-id="d41e3-118">Você deve ter acesso ao [Explorer (ou detecções em tempo real)](threat-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="d41e3-118">You must have access to [Explorer (or real-time detections)](threat-explorer.md).</span></span>

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a><span data-ttu-id="d41e3-119">Para integrar o Microsoft Defender para Office 365 com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d41e3-119">To integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d41e3-120">A integração do Microsoft Defender para Office 365 com o Microsoft Defender for Endpoint está configurada no Defender para Ponto de Extremidade e no Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="d41e3-120">Integrating Microsoft Defender for Office 365 with Microsoft Defender for Endpoint is set up in both Defender for Endpoint and Defender for Office 365.</span></span>

1. <span data-ttu-id="d41e3-121">Como administrador global ou administrador de segurança, acesse [https://protection.office.com](https://protection.office.com) e entre.</span><span class="sxs-lookup"><span data-stu-id="d41e3-121">As a global administrator or a security administrator, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="d41e3-122">(Isso o leva ao Centro Office 365 Segurança & Conformidade.)</span><span class="sxs-lookup"><span data-stu-id="d41e3-122">(This takes you to the Office 365 Security & Compliance Center.)</span></span>

2. <span data-ttu-id="d41e3-123">No painel de navegação, escolha **Explorador de gerenciamento de** \> **ameaças.**</span><span class="sxs-lookup"><span data-stu-id="d41e3-123">In the navigation pane, choose **Threat management** \> **Explorer**.</span></span>

   ![Menu Explorer in Threat Management](../../media/ThreatMgmt-Explorer-nav.png)

3. <span data-ttu-id="d41e3-125">No canto superior direito da tela, escolha **Defender for Endpoint Configurações (MDE Configurações)**.</span><span class="sxs-lookup"><span data-stu-id="d41e3-125">In the upper right corner of the screen, choose **Defender for Endpoint Settings (MDE Settings)**.</span></span>

4. <span data-ttu-id="d41e3-126">Na caixa de diálogo Conexão do Microsoft Defender para Ponto de Extremidade, a Conexão **para o Microsoft Defender para Ponto de Extremidade**.</span><span class="sxs-lookup"><span data-stu-id="d41e3-126">In the Microsoft Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

   ![Conexão do Microsoft Defender para Ponto de Extremidade](../../media/Explorer-WDATPConnection-dialog.png)

5. <span data-ttu-id="d41e3-128">Vá para o portal Microsoft 365 Defender ( [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="d41e3-128">Go to the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com).</span></span>

6. <span data-ttu-id="d41e3-129">Na barra de navegação, escolha **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="d41e3-129">In the navigation bar, choose **Settings**.</span></span> <span data-ttu-id="d41e3-130">Em **Geral,** escolha **Recursos avançados.**</span><span class="sxs-lookup"><span data-stu-id="d41e3-130">Then, under **General**, choose **Advanced features**.</span></span>

7. <span data-ttu-id="d41e3-131">Role para baixo **Office 365 conexão de Inteligência contra Ameaças** e a ligue.</span><span class="sxs-lookup"><span data-stu-id="d41e3-131">Scroll down to **Office 365 Threat Intelligence connection**, and turn the connection on.</span></span>

   ![Office 365 de inteligência contra ameaças](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a><span data-ttu-id="d41e3-133">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d41e3-133">Related articles</span></span>

[<span data-ttu-id="d41e3-134">Recursos de investigação e resposta contra ameaças Office 365</span><span class="sxs-lookup"><span data-stu-id="d41e3-134">Threat investigation and response capabilities in Office 365</span></span>](office-365-ti.md)

[<span data-ttu-id="d41e3-135">Obter o Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="d41e3-135">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)

[<span data-ttu-id="d41e3-136">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="d41e3-136">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)
