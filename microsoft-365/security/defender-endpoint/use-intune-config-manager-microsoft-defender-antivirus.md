---
title: Configurar Microsoft Defender Antivírus usando Microsoft Endpoint Manager
description: Use Microsoft Endpoint Manager e Microsoft Intune configurar o Microsoft Defender AV e Endpoint Protection
keywords: scep, intune, proteção de ponto de extremidade, configuração
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683746"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="97971-104">Use Microsoft Endpoint Manager para configurar e gerenciar Microsoft Defender Antivírus</span><span class="sxs-lookup"><span data-stu-id="97971-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="97971-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="97971-105">**Applies to:**</span></span>

- [<span data-ttu-id="97971-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="97971-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="97971-107">Você pode usar [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) para configurar Microsoft Defender Antivírus verificações.</span><span class="sxs-lookup"><span data-stu-id="97971-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="97971-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) e [o Configuration Manager](/mem/configmgr/core/understand/introduction) agora fazem parte Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="97971-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="97971-109">Configurar Microsoft Defender Antivírus verificações em Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="97971-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="97971-110">Vá para o Microsoft Endpoint Manager de administração ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ), e entre.</span><span class="sxs-lookup"><span data-stu-id="97971-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="97971-111">Navegue até **Endpoint Security**.</span><span class="sxs-lookup"><span data-stu-id="97971-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="97971-112">Em **Gerenciar**, escolha **Antivírus**.</span><span class="sxs-lookup"><span data-stu-id="97971-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="97971-113">Selecione sua Microsoft Defender Antivírus de segurança.</span><span class="sxs-lookup"><span data-stu-id="97971-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="97971-114">Em **Gerenciar**, escolha **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="97971-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="97971-115">Ao lado de **Definições de configuração**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="97971-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="97971-116">Expanda **a seção Examinar** e revise ou edite suas configurações de verificação.</span><span class="sxs-lookup"><span data-stu-id="97971-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="97971-117">Escolha **Revisar + salvar**</span><span class="sxs-lookup"><span data-stu-id="97971-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="97971-118">Precisa de ajuda?</span><span class="sxs-lookup"><span data-stu-id="97971-118">Need help?</span></span> <span data-ttu-id="97971-119">Consulte [Gerenciar a segurança do ponto de extremidade Microsoft Intune](/mem/intune/protect/endpoint-security).</span><span class="sxs-lookup"><span data-stu-id="97971-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="97971-120">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="97971-120">Related articles</span></span>

- [<span data-ttu-id="97971-121">Artigos de referência para ferramentas de gerenciamento e configuração</span><span class="sxs-lookup"><span data-stu-id="97971-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="97971-122">Microsoft Defender Antivirus no Windows 10</span><span class="sxs-lookup"><span data-stu-id="97971-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)