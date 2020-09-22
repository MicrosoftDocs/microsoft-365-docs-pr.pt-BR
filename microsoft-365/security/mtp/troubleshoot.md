---
title: À procura de soluções para os problemas de serviço da Proteção contra Ameaças da Microsoft
description: Encontre soluções e contorne problemas conhecidos da Proteção contra Ameaças da Microsoft
keywords: solução de problemas da proteção contra ameaças da Microsoft, solução de problemas, ATP, problemas, complemento, página de configurações do Azure
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201281"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a><span data-ttu-id="64f39-104">À procura de soluções para os problemas de serviço da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="64f39-104">Troubleshoot Microsoft Threat Protection service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="64f39-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="64f39-105">**Applies to:**</span></span>
- <span data-ttu-id="64f39-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="64f39-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="64f39-107">Esta seção aborda os problemas que podem surgir quando você usa o serviço de Proteção contra Ameaças da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="64f39-107">This section addresses issues that might arise as you use the Microsoft Threat Protection service.</span></span>


## <a name="i-dont-see-microsoft-threat-protection-content"></a><span data-ttu-id="64f39-108">Não vejo o conteúdo da proteção contra ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="64f39-108">I don't see Microsoft Threat Protection content</span></span>
<span data-ttu-id="64f39-109">Se você não vir recursos no painel de navegação, como incidentes, central de ações ou busca em seu portal, você precisará verificar se o seu locatário tem as licenças apropriadas.</span><span class="sxs-lookup"><span data-stu-id="64f39-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span> 

<span data-ttu-id="64f39-110">Para obter mais informações, confira [Pré-requisitos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="64f39-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a><span data-ttu-id="64f39-111">Os alertas ATP do Azure não estão aparecendo nos incidentes da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="64f39-111">Azure ATP alerts are not showing up in the Microsoft Threat Protection incidents</span></span>
<span data-ttu-id="64f39-112">Se você tiver o Azure ATP implantado em seu ambiente, mas não estiver vendo os alertas ATP do Azure como parte dos incidentes de Proteção contra Ameaças da Microsoft, você precisará verificar se o Microsoft Cloud app Security e a integração ATP do Azure estão habilitados.</span><span class="sxs-lookup"><span data-stu-id="64f39-112">If you have Azure ATP deployed in your environment but you're not seeing Azure ATP alerts as part of Microsoft Threat Protection incidents, you'll need to ensure that the Microsoft Cloud App Security and Azure ATP integration is enabled.</span></span> 

<span data-ttu-id="64f39-113">Para obter mais informações, consulte [ integração da ATP do Azure](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span><span class="sxs-lookup"><span data-stu-id="64f39-113">For more information, see [Azure ATP integration](https://docs.microsoft.com/cloud-app-security/aatp-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="64f39-114">Onde está a página de configurações para ativar o serviço?</span><span class="sxs-lookup"><span data-stu-id="64f39-114">Where is the settings page for turning the service on?</span></span>
<span data-ttu-id="64f39-115">Para ativar a proteção contra ameaças da Microsoft, acesse **configurações** do painel de navegação na central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="64f39-115">To turn on Microsoft Threat Protection, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="64f39-116">Esse item de navegação só será visível se você tiver as [permissões e as licenças de pré-requisito](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="64f39-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
 

