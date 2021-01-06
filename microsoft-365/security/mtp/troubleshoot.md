---
title: Solucionar problemas do Microsoft 365 defender Service
description: Encontre soluções e contornos para problemas conhecidos do Microsoft 365 defender
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760453"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a><span data-ttu-id="f3a74-104">Solucionar problemas do Microsoft 365 defender Service</span><span class="sxs-lookup"><span data-stu-id="f3a74-104">Troubleshoot Microsoft 365 Defender service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f3a74-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f3a74-105">**Applies to:**</span></span>
- <span data-ttu-id="f3a74-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3a74-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f3a74-107">Esta seção aborda os problemas que podem surgir quando você usa o serviço Microsoft 365 defender.</span><span class="sxs-lookup"><span data-stu-id="f3a74-107">This section addresses issues that might arise as you use the Microsoft 365 Defender service.</span></span>

## <a name="i-dont-see-microsoft-365-defender-content"></a><span data-ttu-id="f3a74-108">Não vejo o conteúdo do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f3a74-108">I don't see Microsoft 365 Defender content</span></span>

<span data-ttu-id="f3a74-109">Se você não vir recursos no painel de navegação, como incidentes, central de ações ou busca em seu portal, você precisará verificar se o seu locatário tem as licenças apropriadas.</span><span class="sxs-lookup"><span data-stu-id="f3a74-109">If you don't see capabilities on the navigation pane such as the Incidents, Action Center, or Hunting in your portal, you'll need to verify that your tenant has the appropriate licenses.</span></span>

<span data-ttu-id="f3a74-110">Para obter mais informações, confira [Pré-requisitos](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f3a74-110">For more information, see [Prerequisites](prerequisites.md).</span></span>

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a><span data-ttu-id="f3a74-111">Os alertas do Microsoft defender for Identity não estão aparecendo nos incidentes do Microsoft 365 defender</span><span class="sxs-lookup"><span data-stu-id="f3a74-111">Microsoft Defender for Identity alerts are not showing up in the Microsoft 365 Defender incidents</span></span>

<span data-ttu-id="f3a74-112">Se você tiver o Microsoft defender para identidade implantado em seu ambiente, mas não estiver vendo o defender para alertas de identidade como parte dos incidentes do Microsoft 365 defender, será necessário garantir que o Microsoft Cloud app Security e o defender para integração de identidade estejam habilitados.</span><span class="sxs-lookup"><span data-stu-id="f3a74-112">If you have Microsoft Defender for Identity deployed in your environment but you're not seeing Defender for Identity alerts as part of Microsoft 365 Defender incidents, you'll need to ensure that the Microsoft Cloud App Security and Defender for Identity integration is enabled.</span></span>

<span data-ttu-id="f3a74-113">Para obter mais informações, consulte [Microsoft defender para integração de identidades](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span><span class="sxs-lookup"><span data-stu-id="f3a74-113">For more information, see [Microsoft Defender for Identity integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).</span></span>

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a><span data-ttu-id="f3a74-114">Onde está a página de configurações para ativar o serviço?</span><span class="sxs-lookup"><span data-stu-id="f3a74-114">Where is the settings page for turning the service on?</span></span>

<span data-ttu-id="f3a74-115">Para ativar o Microsoft 365 defender, acesse **configurações** do painel de navegação na central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3a74-115">To turn on Microsoft 365 Defender, access **Settings** from the navigation pane in the Microsoft 365 security center.</span></span> <span data-ttu-id="f3a74-116">Esse item de navegação só será visível se você tiver as [permissões e as licenças de pré-requisito](mtp-enable.md#check-license-eligibility-and-required-permissions).</span><span class="sxs-lookup"><span data-stu-id="f3a74-116">This navigation item is visible only if you have the [prerequisite permissions and licenses](mtp-enable.md#check-license-eligibility-and-required-permissions).</span></span>
