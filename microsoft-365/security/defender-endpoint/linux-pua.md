---
title: Detectar e bloquear aplicativos potencialmente indesejados com o Microsoft Defender ATP para Linux
description: Detectar e bloquear Aplicativos Potencialmente Indesejados (PUA) usando o Microsoft Defender ATP para Linux.
keywords: microsoft, defender, atp, linux, pua, pus
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
ms.openlocfilehash: 40e6099349ff6c62c5e0b6c35fd9940cb9200f05
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187764"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="23f8a-104">Detectar e bloquear aplicativos potencialmente indesejados com o Microsoft Defender para Endpoint para Linux</span><span class="sxs-lookup"><span data-stu-id="23f8a-104">Detect and block potentially unwanted applications with Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="23f8a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="23f8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="23f8a-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="23f8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="23f8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="23f8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="23f8a-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="23f8a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="23f8a-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="23f8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="23f8a-110">O recurso de proteção de aplicativo potencialmente indesejado (PUA) no Defender for Endpoint para Linux pode detectar e bloquear arquivos PUA em pontos de extremidade em sua rede.</span><span class="sxs-lookup"><span data-stu-id="23f8a-110">The potentially unwanted application (PUA) protection feature in Defender for Endpoint for Linux can detect and block PUA files on endpoints in your network.</span></span>

<span data-ttu-id="23f8a-111">Esses aplicativos não são considerados vírus, malware ou outros tipos de ameaças, mas podem executar ações em pontos de extremidade que afetam adversamente seu desempenho ou uso.</span><span class="sxs-lookup"><span data-stu-id="23f8a-111">These applications are not considered viruses, malware, or other types of threats, but might perform actions on endpoints that adversely affect their performance or use.</span></span> <span data-ttu-id="23f8a-112">A PUA também pode se referir a aplicativos considerados com má reputação.</span><span class="sxs-lookup"><span data-stu-id="23f8a-112">PUA can also refer to applications that are considered to have poor reputation.</span></span>

<span data-ttu-id="23f8a-113">Esses aplicativos podem aumentar o risco de sua rede ser infectado por malware, fazer com que as infecções de malware sejam mais difíceis de identificar e podem desperdiçar recursos de IT na limpeza dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="23f8a-113">These applications can increase the risk of your network being infected with malware, cause malware infections to be harder to identify, and can waste IT resources in cleaning up the applications.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="23f8a-114">Como funciona</span><span class="sxs-lookup"><span data-stu-id="23f8a-114">How it works</span></span>

<span data-ttu-id="23f8a-115">O Defender para Ponto de Extremidade para Linux pode detectar e relatar arquivos PUA.</span><span class="sxs-lookup"><span data-stu-id="23f8a-115">Defender for Endpoint for Linux can detect and report PUA files.</span></span> <span data-ttu-id="23f8a-116">Quando configurados no modo de bloqueio, os arquivos PUA são movidos para a quarentena.</span><span class="sxs-lookup"><span data-stu-id="23f8a-116">When configured in blocking mode, PUA files are moved to the quarantine.</span></span>

<span data-ttu-id="23f8a-117">Quando um PUA é detectado em um ponto de extremidade, o Defender for Endpoint para Linux mantém um registro da infecção no histórico de ameaças.</span><span class="sxs-lookup"><span data-stu-id="23f8a-117">When a PUA is detected on an endpoint, Defender for Endpoint for Linux keeps a record of the infection in the threat history.</span></span> <span data-ttu-id="23f8a-118">O histórico pode ser visualizado no portal do Centro de Segurança do Microsoft Defender ou por meio da `mdatp` ferramenta de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="23f8a-118">The history can be visualized from the Microsoft Defender Security Center portal or through the `mdatp` command-line tool.</span></span> <span data-ttu-id="23f8a-119">O nome da ameaça conterá a palavra "Application".</span><span class="sxs-lookup"><span data-stu-id="23f8a-119">The threat name will contain the word "Application".</span></span>

## <a name="configure-pua-protection"></a><span data-ttu-id="23f8a-120">Configurar a proteção pua</span><span class="sxs-lookup"><span data-stu-id="23f8a-120">Configure PUA protection</span></span>

<span data-ttu-id="23f8a-121">A proteção PUA no Defender para Ponto de Extremidade para Linux pode ser configurada de uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="23f8a-121">PUA protection in Defender for Endpoint for Linux can be configured in one of the following ways:</span></span>

- <span data-ttu-id="23f8a-122">**Desativado**: a proteção pua está desabilitada.</span><span class="sxs-lookup"><span data-stu-id="23f8a-122">**Off**: PUA protection is disabled.</span></span>
- <span data-ttu-id="23f8a-123">**Auditoria**: os arquivos PUA são relatados nos logs do produto, mas não no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="23f8a-123">**Audit**: PUA files are reported in the product logs, but not in Microsoft Defender Security Center.</span></span> <span data-ttu-id="23f8a-124">Nenhum registro da infecção é armazenado no histórico de ameaças e nenhuma ação é tomada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="23f8a-124">No record of the infection is stored in the threat history and no action is taken by the product.</span></span>
- <span data-ttu-id="23f8a-125">**Bloquear**: os arquivos PUA são relatados nos logs do produto e no Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="23f8a-125">**Block**: PUA files are reported in the product logs and in Microsoft Defender Security Center.</span></span> <span data-ttu-id="23f8a-126">Um registro da infecção é armazenado no histórico de ameaças e a ação é tomada pelo produto.</span><span class="sxs-lookup"><span data-stu-id="23f8a-126">A record of the infection is stored in the threat history and action is taken by the product.</span></span>

>[!WARNING]
><span data-ttu-id="23f8a-127">Por padrão, a proteção pua é configurada no **modo auditoria.**</span><span class="sxs-lookup"><span data-stu-id="23f8a-127">By default, PUA protection is configured in **Audit** mode.</span></span>

<span data-ttu-id="23f8a-128">Você pode configurar como os arquivos PUA são manipulados da linha de comando ou do console de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="23f8a-128">You can configure how PUA files are handled from the command line or from the management console.</span></span>

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a><span data-ttu-id="23f8a-129">Use a ferramenta de linha de comando para configurar a proteção PUA:</span><span class="sxs-lookup"><span data-stu-id="23f8a-129">Use the command-line tool to configure PUA protection:</span></span>

<span data-ttu-id="23f8a-130">No Terminal, execute o seguinte comando para configurar a proteção PUA:</span><span class="sxs-lookup"><span data-stu-id="23f8a-130">In Terminal, execute the following command to configure PUA protection:</span></span>

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a><span data-ttu-id="23f8a-131">Use o console de gerenciamento para configurar a proteção pua:</span><span class="sxs-lookup"><span data-stu-id="23f8a-131">Use the management console to configure PUA protection:</span></span>

<span data-ttu-id="23f8a-132">Em sua empresa, você pode configurar a proteção PUA de um console de gerenciamento, como o Puppet ou Ansible, da mesma forma como outras configurações de produto são configuradas.</span><span class="sxs-lookup"><span data-stu-id="23f8a-132">In your enterprise, you can configure PUA protection from a management console, such as Puppet or Ansible, similarly to how other product settings are configured.</span></span> <span data-ttu-id="23f8a-133">Para obter mais informações, consulte a seção [Configurações do tipo](linux-preferences.md#threat-type-settings) Ameaça do artigo [Definir preferências para Defender para Ponto de](linux-preferences.md) Extremidade para Linux.</span><span class="sxs-lookup"><span data-stu-id="23f8a-133">For more information, see the [Threat type settings](linux-preferences.md#threat-type-settings) section of the [Set preferences for Defender for Endpoint for Linux](linux-preferences.md) article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="23f8a-134">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="23f8a-134">Related articles</span></span>

- [<span data-ttu-id="23f8a-135">Definir preferências para Defender para Ponto de Extremidade para Linux</span><span class="sxs-lookup"><span data-stu-id="23f8a-135">Set preferences for Defender for Endpoint for Linux</span></span>](linux-preferences.md)
