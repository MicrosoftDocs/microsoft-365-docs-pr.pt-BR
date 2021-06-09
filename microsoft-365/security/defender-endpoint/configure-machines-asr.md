---
title: Otimizar a implantação e as detecções de regras ASR
description: Otimize suas regras de redução de superfície de ataque (ASR) para identificar e impedir explorações típicas de malware.
keywords: onboard, gerenciamento do Intune, Microsoft Defender para Ponto de Extremidade, Microsoft Defender, Windows Defender, redução de superfície de ataque, ASR, linha de base de segurança
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a5590e62e7838bb9f611320b6d0e5c573b2be084
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841553"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="32209-104">Otimizar a implantação e as detecções de regras ASR</span><span class="sxs-lookup"><span data-stu-id="32209-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="32209-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="32209-105">**Applies to:**</span></span>
- [<span data-ttu-id="32209-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="32209-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="32209-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="32209-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="32209-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="32209-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="32209-109">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="32209-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="32209-110">As regras de redução de superfície de ataque [(ASR)](./attack-surface-reduction.md) identificam e impedem explorações típicas de malware.</span><span class="sxs-lookup"><span data-stu-id="32209-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="32209-111">Eles controlam quando e como um código potencialmente mal-intencionado pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="32209-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="32209-112">Por exemplo, eles podem impedir que JavaScript ou VBScript iniciar um executável baixado, bloquear chamadas de API Win32 de macros Office e bloquear processos executados a partir de unidades USB.</span><span class="sxs-lookup"><span data-stu-id="32209-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="32209-113">![Cartão de gerenciamento de superfície de ataque](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="32209-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="32209-114">*Cartão de gerenciamento de superfície de ataque*</span><span class="sxs-lookup"><span data-stu-id="32209-114">*Attack surface management card*</span></span>

<span data-ttu-id="32209-115">O *cartão de gerenciamento de* superfície de ataque é um ponto de entrada para ferramentas no Microsoft 365 de segurança que você pode usar para:</span><span class="sxs-lookup"><span data-stu-id="32209-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="32209-116">Entenda como as regras ASR são implantadas atualmente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="32209-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="32209-117">Revise as detecções asR e identifique possíveis detecções incorretas.</span><span class="sxs-lookup"><span data-stu-id="32209-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="32209-118">Analise o impacto das exclusões e gere a lista de caminhos de arquivo a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="32209-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="32209-119">Selecione **Ir para atacar o gerenciamento** de superfície Monitoramento & relatórios > regras de redução de superfície de ataque > Adicionar  >  **exclusões**.</span><span class="sxs-lookup"><span data-stu-id="32209-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="32209-120">A partir daí, você pode navegar até outras seções do Microsoft 365 de segurança.</span><span class="sxs-lookup"><span data-stu-id="32209-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="32209-121">![Adicionar a guia exclusões na página Regras de redução de superfície de ataque no centro Microsoft 365 segurança](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="32209-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="32209-122">A ***guia Adicionar exclusões** na página Regras de redução de superfície de ataque no centro Microsoft 365 segurança*</span><span class="sxs-lookup"><span data-stu-id="32209-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="32209-123">Para acessar Microsoft 365 central de segurança, você precisa de uma licença Microsoft 365 E3 ou E5 e uma conta que tenha determinadas funções no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32209-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="32209-124">[Leia sobre licenças e permissões necessárias.](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="32209-124">[Read about required licenses and permissions](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="32209-125">Para obter mais informações sobre a implantação de regras ASR no centro de segurança Microsoft 365, consulte [Monitor and manage ASR rule deployment and detections](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span><span class="sxs-lookup"><span data-stu-id="32209-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="32209-126">**Tópicos relacionados**</span><span class="sxs-lookup"><span data-stu-id="32209-126">**Related topics**</span></span>

* [<span data-ttu-id="32209-127">Verificar se os dispositivos estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="32209-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="32209-128">Obter dispositivos conectados ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="32209-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="32209-129">Monitorar a conformidade com a linha de base de segurança do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="32209-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
