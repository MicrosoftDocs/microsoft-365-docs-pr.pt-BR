---
title: Detectar e bloquear aplicativos potencialmente indesejados com o Microsoft Defender ATP para Mac
description: Detectar e bloquear Aplicativos Potencialmente Indesejados (PUA) usando o Microsoft Defender ATP para Mac.
keywords: microsoft, defender, atp, mac, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6e65e847403160d24eac04a553ca16a46314e33d
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187416"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="169a2-104">Detectar e bloquear aplicativos potencialmente indesejados com o Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="169a2-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="169a2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="169a2-105">**Applies to:**</span></span>
- [<span data-ttu-id="169a2-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="169a2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="169a2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="169a2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="169a2-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="169a2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="169a2-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="169a2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


<span data-ttu-id="169a2-110">O recurso de proteção de aplicativo potencialmente indesejado (PUA) no Microsoft Defender para Ponto de Extremidade para Mac pode detectar e bloquear arquivos PUA em pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="169a2-110">The potentially unwanted application (PUA) protection feature in Microsoft Defender for Endpoint for Mac can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="169a2-111">Esses aplicativos não são considerados vírus, malware ou outros tipos de ameaças, mas podem executar ações em pontos de extremidade que afetam adversamente seu desempenho ou uso.</span><span class="sxs-lookup"><span data-stu-id="169a2-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="169a2-112">A PUA também pode se referir a aplicativos considerados com má reputação.</span><span class="sxs-lookup"><span data-stu-id="169a2-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="169a2-113">Esses aplicativos podem aumentar o risco de sua rede ser infectado por malware, fazer com que as infecções de malware sejam mais difíceis de identificar e podem desperdiçar recursos de IT na limpeza dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="169a2-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="169a2-114">Como funciona</span><span class="sxs-lookup"><span data-stu-id="169a2-114">How it works</span></span>

<span data-ttu-id="169a2-115">O Microsoft Defender para Ponto de Extremidade para Mac pode detectar e relatar arquivos PUA.</span><span class="sxs-lookup"><span data-stu-id="169a2-115">Microsoft Defender for Endpoint for Mac can detect and report PUA files.</span></span> <span data-ttu-id="169a2-116">Quando configurados no modo de bloqueio, os arquivos PUA são movidos para a quarentena.</span><span class="sxs-lookup"><span data-stu-id="169a2-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="169a2-117">Quando um PUA é detectado em um ponto de extremidade, o Microsoft Defender para Ponto de Extremidade para Mac apresenta uma notificação para o usuário, a menos que as notificações tenham sido desabilitadas.</span><span class="sxs-lookup"><span data-stu-id="169a2-117">When a PUA is detected on an endpoint, Microsoft Defender for Endpoint for Mac presents a notification to the user, unless notifications have been disabled.</span></span> <span data-ttu-id="169a2-118">O nome da ameaça conterá a palavra "Application".</span><span class="sxs-lookup"><span data-stu-id="169a2-118">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="169a2-119">Configurar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="169a2-119">Configure PUA protection</span></span>

<span data-ttu-id="169a2-120">A proteção PUA no Microsoft Defender para Ponto de Extremidade para Mac pode ser configurada de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="169a2-120">PUA protection in Microsoft Defender for Endpoint for Mac can be configured in one of the following ways:</span></span>

- <span data-ttu-id="169a2-121">**Desativado**: a proteção pua está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="169a2-121">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="169a2-122">**Auditoria**: os arquivos PUA são relatados nos logs do produto, mas não no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="169a2-122">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="169a2-123">Nenhuma notificação é apresentada ao usuário e nenhuma ação é tomada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="169a2-123">No notification is presented to the user and no action is taken by the product.</span></span>
- <span data-ttu-id="169a2-124">**Bloquear**: os arquivos PUA são relatados nos logs do produto e no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="169a2-124">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="169a2-125">O usuário recebe uma notificação e a ação é tomada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="169a2-125">The user is presented with a notification and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="169a2-126">Por padrão, a proteção pua é configurada no **modo auditoria.**</span><span class="sxs-lookup"><span data-stu-id="169a2-126">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="169a2-127">Você pode configurar como os arquivos PUA são manipulados da linha de comando ou do console de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="169a2-127">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="169a2-128">Use a ferramenta de linha de comando para configurar a proteção PUA:</span><span class="sxs-lookup"><span data-stu-id="169a2-128">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="169a2-129">No Terminal, execute o seguinte comando para configurar a proteção PUA:</span><span class="sxs-lookup"><span data-stu-id="169a2-129">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="169a2-130">Use o console de gerenciamento para configurar a proteção pua:</span><span class="sxs-lookup"><span data-stu-id="169a2-130">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="169a2-131">Em sua empresa, você pode configurar a proteção pua de um console de gerenciamento, como JAMF ou Intune, da mesma forma como outras configurações de produto são configuradas.</span><span class="sxs-lookup"><span data-stu-id="169a2-131">In your enterprise, you can configure PUA protection from a management console, such as JAMF or Intune, similarly to how other product settings are configured.</span></span> <span data-ttu-id="169a2-132">Para obter mais informações, consulte a seção [Configurações do](mac-preferences.md#threat-type-settings) tipo Ameaça do [tópico Definir preferências](mac-preferences.md) do Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="169a2-132">For more information, see the [Threat type settings](mac-preferences.md#threat-type-settings) section of the [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md) topic.</span></span>

## <a name="related-topics"></a><span data-ttu-id="169a2-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="169a2-133">Related topics</span></span>

- [<span data-ttu-id="169a2-134">Definir preferências do Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="169a2-134">Set preferences for Microsoft Defender for Endpoint for Mac</span></span>](mac-preferences.md)