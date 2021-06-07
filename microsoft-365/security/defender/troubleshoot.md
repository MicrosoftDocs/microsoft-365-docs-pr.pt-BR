---
title: Solucionar Microsoft 365 problemas de serviço do Defender
description: Encontre soluções e soluções alternativas para problemas conhecidos Microsoft 365 Defender
keywords: solução Microsoft 365 Defender, solução de problemas, Microsoft Defender para Identidade, problemas, complemento, página de configurações
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 81da6c6ef46798ac656e7d5f0f374bf2c722583d
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782736"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="f83fc-104">Solucionar Microsoft 365 problemas de serviço do Defender</span><span class="sxs-lookup"><span data-stu-id="f83fc-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f83fc-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f83fc-105">**Applies to:**</span></span>
- <span data-ttu-id="f83fc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f83fc-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f83fc-107">Esta seção aborda problemas que podem surgir à medida que você usa o serviço Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f83fc-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="f83fc-108">Não vejo o conteúdo Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f83fc-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="f83fc-109">Se você não vir recursos no painel de navegação, como Incidentes, Centro de Ações ou Busca em seu portal, precisará verificar se seu locatário tem as licenças apropriadas.</span><span class="sxs-lookup"><span data-stu-id="f83fc-109">If you don't see capabilities on the navigation pane such as the Incidents, Action center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="f83fc-110">Para obter mais informações, confira [Pré-requisitos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f83fc-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="f83fc-111">Os alertas do Microsoft Defender para Identidade não estão sendo exibidos nos incidentes Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f83fc-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="f83fc-112">Se você tiver o Microsoft Defender for Identity implantado em seu ambiente, mas não estiver vendo alertas do Defender para Identidade como parte de incidentes do Microsoft 365 Defender, você precisará garantir que a integração do Microsoft Cloud App Security e do Defender for Identity esteja habilitada.</span><span class="sxs-lookup"><span data-stu-id="f83fc-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="f83fc-113">Para obter mais informações, consulte [Integração do Microsoft Defender for Identity](/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="f83fc-113">For more information, see [Microsoft Defender for Identity integration](/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a><span data-ttu-id="f83fc-114">Onde está a página de configurações para ligar o serviço?</span><span class="sxs-lookup"><span data-stu-id="f83fc-114">Where is the settings page for turning on the service?</span></span>

<span data-ttu-id="f83fc-115">Para ativar o Microsoft 365 Defender, acesse **Configurações** do painel de navegação no centro Microsoft 365 segurança.</span><span class="sxs-lookup"><span data-stu-id="f83fc-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="f83fc-116">Esse item de navegação só será visível se você tiver as permissões e licenças de [pré-requisito.](m365d-enable.md#check-license-eligibility-and-required-permissions)</span><span class="sxs-lookup"><span data-stu-id="f83fc-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](m365d-enable.md#check-license-eligibility-and-required-permissions).</span></span>

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a><span data-ttu-id="f83fc-117">Como criar uma exceção para meu arquivo/URL?</span><span class="sxs-lookup"><span data-stu-id="f83fc-117">How do I create an exception for my file/URL?</span></span>

<span data-ttu-id="f83fc-118">Um falso positivo é um arquivo ou URL que é detectado como mal-intencionado, mas não é uma ameaça.</span><span class="sxs-lookup"><span data-stu-id="f83fc-118">A false positive is a file or URL that is detected as malicious but is not a threat.</span></span> <span data-ttu-id="f83fc-119">Você pode criar indicadores e definir exclusões para desbloquear e permitir determinados arquivos/URLs.</span><span class="sxs-lookup"><span data-stu-id="f83fc-119">You can create indicators and define exclusions to unblock and allow certain files/URLs.</span></span> <span data-ttu-id="f83fc-120">Consulte [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span><span class="sxs-lookup"><span data-stu-id="f83fc-120">See [Address false positives/negatives in Defender for Endpoint](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives).</span></span>


