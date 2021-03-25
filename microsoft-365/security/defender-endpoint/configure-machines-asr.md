---
title: Otimizar a implantação e as detecções de regras ASR
description: Otimize suas regras de redução de superfície de ataque (ASR) para identificar e impedir explorações típicas de malware.
keywords: onboard, Gerenciamento do Intune, MDATP, WDATP, Microsoft Defender, Windows Defender, proteção avançada contra ameaças, redução de superfície de ataque, ASR, linha de base de segurança
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
ms.openlocfilehash: a5ce39bb3ff0bf3eea4ac4e89c554de43499b15f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165472"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a><span data-ttu-id="65ee8-104">Otimizar a implantação e as detecções de regras ASR</span><span class="sxs-lookup"><span data-stu-id="65ee8-104">Optimize ASR rule deployment and detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="65ee8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="65ee8-105">**Applies to:**</span></span>
- [<span data-ttu-id="65ee8-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65ee8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65ee8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65ee8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="65ee8-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="65ee8-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="65ee8-109">[Inscreva-se para uma avaliação gratuita](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span><span class="sxs-lookup"><span data-stu-id="65ee8-109">[Sign up for a free trial](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink).</span></span>

<span data-ttu-id="65ee8-110">As regras de redução de superfície de ataque [(ASR)](./attack-surface-reduction.md) identificam e impedem explorações típicas de malware.</span><span class="sxs-lookup"><span data-stu-id="65ee8-110">[Attack surface reduction (ASR) rules](./attack-surface-reduction.md) identify and prevent typical malware exploits.</span></span> <span data-ttu-id="65ee8-111">Eles controlam quando e como um código potencialmente mal-intencionado pode ser executado.</span><span class="sxs-lookup"><span data-stu-id="65ee8-111">They control when and how potentially malicious code can run.</span></span> <span data-ttu-id="65ee8-112">Por exemplo, eles podem impedir que JavaScript ou VBScript iniciar um executável baixado, bloquear chamadas de API Win32 de macros do Office e bloquear processos executados a partir de unidades USB.</span><span class="sxs-lookup"><span data-stu-id="65ee8-112">For example, they can prevent JavaScript or VBScript from launching a downloaded executable, block Win32 API calls from Office macros, and block processes that run from USB drives.</span></span>

<span data-ttu-id="65ee8-113">![Cartão de gerenciamento de superfície de ataque](images/secconmgmt_asr_card.png)</span><span class="sxs-lookup"><span data-stu-id="65ee8-113">![Attack surface management card](images/secconmgmt_asr_card.png)</span></span><br>
<span data-ttu-id="65ee8-114">*Cartão de gerenciamento de superfície de ataque*</span><span class="sxs-lookup"><span data-stu-id="65ee8-114">*Attack surface management card*</span></span>

<span data-ttu-id="65ee8-115">O *cartão de gerenciamento de* superfície de ataque é um ponto de entrada para ferramentas no Centro de segurança do Microsoft 365 que você pode usar para:</span><span class="sxs-lookup"><span data-stu-id="65ee8-115">The *Attack surface management card* is an entry point to tools in Microsoft 365 security center that you can use to:</span></span>

* <span data-ttu-id="65ee8-116">Entenda como as regras ASR são implantadas atualmente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="65ee8-116">Understand how ASR rules are currently deployed in your organization.</span></span>
* <span data-ttu-id="65ee8-117">Revise as detecções asR e identifique possíveis detecções incorretas.</span><span class="sxs-lookup"><span data-stu-id="65ee8-117">Review ASR detections and identify possible incorrect detections.</span></span>
* <span data-ttu-id="65ee8-118">Analise o impacto das exclusões e gere a lista de caminhos de arquivo a ser excluído.</span><span class="sxs-lookup"><span data-stu-id="65ee8-118">Analyze the impact of exclusions and generate the list of file paths to exclude.</span></span>

<span data-ttu-id="65ee8-119">Selecione **Ir para atacar o gerenciamento** de superfície Monitoramento & relatórios > regras de redução de superfície de ataque > Adicionar  >  **exclusões**.</span><span class="sxs-lookup"><span data-stu-id="65ee8-119">Select **Go to attack surface management** > **Monitoring & reports > Attack surface reduction rules > Add exclusions**.</span></span> <span data-ttu-id="65ee8-120">A partir daí, você pode navegar até outras seções do Centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="65ee8-120">From there, you can navigate to other sections of Microsoft 365 security center.</span></span>

<span data-ttu-id="65ee8-121">![Adicionar a guia exclusões na página Regras de redução de superfície de ataque no Centro de segurança do Microsoft 365](images/secconmgmt_asr_m365exlusions.png)</span><span class="sxs-lookup"><span data-stu-id="65ee8-121">![Add exclusions tab in the Attack surface reduction rules page in Microsoft 365 security center](images/secconmgmt_asr_m365exlusions.png)</span></span><br>
<span data-ttu-id="65ee8-122">A guia Adicionar exclusões na página Regras de redução de superfície de ataque no Centro de *segurança do Microsoft 365*</span><span class="sxs-lookup"><span data-stu-id="65ee8-122">The ***Add exclusions** tab in the Attack surface reduction rules page in Microsoft 365 security center*</span></span>

> [!NOTE]
> <span data-ttu-id="65ee8-123">Para acessar o Centro de segurança do Microsoft 365, você precisa de uma licença do Microsoft 365 E3 ou E5 e uma conta que tenha determinadas funções no Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="65ee8-123">To access Microsoft 365 security center, you need a Microsoft 365 E3 or E5 license and an account that has certain roles on Azure Active Directory.</span></span> <span data-ttu-id="65ee8-124">[Leia sobre licenças e permissões necessárias.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="65ee8-124">[Read about required licenses and permissions](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions).</span></span>

<span data-ttu-id="65ee8-125">Para obter mais informações sobre a implantação de regras ASR no Centro de segurança do Microsoft 365, consulte [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span><span class="sxs-lookup"><span data-stu-id="65ee8-125">For more information about ASR rule deployment in Microsoft 365 security center, see [Monitor and manage ASR rule deployment and detections](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections).</span></span>

<span data-ttu-id="65ee8-126">**Tópicos relacionados**</span><span class="sxs-lookup"><span data-stu-id="65ee8-126">**Related topics**</span></span>

* [<span data-ttu-id="65ee8-127">Verifique se seus dispositivos estão configurados corretamente</span><span class="sxs-lookup"><span data-stu-id="65ee8-127">Ensure your devices are configured properly</span></span>](configure-machines.md)
* [<span data-ttu-id="65ee8-128">Obter dispositivos conectados ao Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="65ee8-128">Get devices onboarded to Microsoft Defender for Endpoint</span></span>](configure-machines-onboarding.md)
* [<span data-ttu-id="65ee8-129">Monitorar a conformidade com a linha de base de segurança do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="65ee8-129">Monitor compliance to the Microsoft Defender for Endpoint security baseline</span></span>](configure-machines-security-baseline.md)
