---
title: Solucionar problemas de desempenho do Microsoft Defender ATP para Mac
description: Solucionar problemas de desempenho no Microsoft Defender ATP para Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: f6dd5681dfafd069a4c52f72e1dc1733584283a2
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185904"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="44b0d-104">Solucionar problemas de desempenho do Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="44b0d-104">Troubleshoot performance issues for Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="44b0d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="44b0d-105">**Applies to:**</span></span>

- [<span data-ttu-id="44b0d-106">Microsoft Defender para Ponto de Extremidade para Mac</span><span class="sxs-lookup"><span data-stu-id="44b0d-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="44b0d-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="44b0d-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="44b0d-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="44b0d-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="44b0d-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="44b0d-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="44b0d-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="44b0d-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="44b0d-111">Este tópico fornece algumas etapas gerais que podem ser usadas para reduzir os problemas de desempenho relacionados ao Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="44b0d-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="44b0d-112">A proteção em tempo real (RTP) é um recurso do Microsoft Defender para Ponto de Extremidade para Mac que monitora e protege continuamente seu dispositivo contra ameaças.</span><span class="sxs-lookup"><span data-stu-id="44b0d-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint for Mac that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="44b0d-113">Ele consiste no monitoramento de arquivos e processos e outras heurísticas.</span><span class="sxs-lookup"><span data-stu-id="44b0d-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="44b0d-114">Dependendo dos aplicativos que você está executando e suas características de dispositivo, você pode ter um desempenho suboptimal ao executar o Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="44b0d-114">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint for Mac.</span></span> <span data-ttu-id="44b0d-115">Em particular, aplicativos ou processos do sistema que acessam muitos recursos em um curto período de tempo podem levar a problemas de desempenho no Microsoft Defender para Ponto de Extremidade para Mac.</span><span class="sxs-lookup"><span data-stu-id="44b0d-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="44b0d-116">As etapas a seguir podem ser usadas para solucionar problemas e atenuar esses problemas:</span><span class="sxs-lookup"><span data-stu-id="44b0d-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="44b0d-117">Desabilite a proteção em tempo real usando um dos métodos a seguir e observe se o desempenho melhora.</span><span class="sxs-lookup"><span data-stu-id="44b0d-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="44b0d-118">Essa abordagem ajuda a restringir se o Microsoft Defender para Ponto de Extremidade para Mac está contribuindo para os problemas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="44b0d-118">This approach helps narrow down whether Microsoft Defender for Endpoint for Mac is contributing to the performance issues.</span></span>

    <span data-ttu-id="44b0d-119">Se o dispositivo não for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada usando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="44b0d-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="44b0d-120">Na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="44b0d-120">From the user interface.</span></span> <span data-ttu-id="44b0d-121">Abra o Microsoft Defender para Ponto de Extremidade para Mac e navegue até **Gerenciar configurações**.</span><span class="sxs-lookup"><span data-stu-id="44b0d-121">Open Microsoft Defender for Endpoint for Mac and navigate to **Manage settings**.</span></span>

      ![Gerenciar captura de tela de proteção em tempo real](/windows/security/threat-protection/microsoft-defender-antivirus/images/mdatp-36-rtp)

    - <span data-ttu-id="44b0d-123">Do Terminal.</span><span class="sxs-lookup"><span data-stu-id="44b0d-123">From the Terminal.</span></span> <span data-ttu-id="44b0d-124">Para fins de segurança, essa operação requer elevação.</span><span class="sxs-lookup"><span data-stu-id="44b0d-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

    <span data-ttu-id="44b0d-125">Se seu dispositivo for gerenciado pela sua organização, a proteção em tempo real poderá ser desabilitada pelo administrador usando as instruções em Definir [preferências](mac-preferences.md)do Microsoft Defender para Ponto de Extremidade para Mac .</span><span class="sxs-lookup"><span data-stu-id="44b0d-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint for Mac](mac-preferences.md).</span></span>

2. <span data-ttu-id="44b0d-126">Abra o Finder e navegue até  >  **Utilitários de Aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="44b0d-126">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="44b0d-127">Abra **o Monitor de Atividades** e analise quais aplicativos estão usando os recursos em seu sistema.</span><span class="sxs-lookup"><span data-stu-id="44b0d-127">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="44b0d-128">Exemplos típicos incluem atualizadores e compiladores de software.</span><span class="sxs-lookup"><span data-stu-id="44b0d-128">Typical examples include software updaters and compilers.</span></span>

3. <span data-ttu-id="44b0d-129">Configure o Microsoft Defender para Ponto de Extremidade para Mac com exclusões para os processos ou locais de disco que contribuem para os problemas de desempenho e rehabilitam a proteção em tempo real.</span><span class="sxs-lookup"><span data-stu-id="44b0d-129">Configure Microsoft Defender for Endpoint for Mac with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="44b0d-130">Consulte [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac para](mac-exclusions.md) obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="44b0d-130">See [Configure and validate exclusions for Microsoft Defender for Endpoint for Mac](mac-exclusions.md) for details.</span></span>
