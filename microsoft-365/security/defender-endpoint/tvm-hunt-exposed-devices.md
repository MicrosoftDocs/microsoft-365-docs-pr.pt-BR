---
title: Buscar por dispositivos expostos
description: Saiba como o gerenciamento de ameaças e vulnerabilidades pode ser usado para ajudar administradores de segurança, administradores de IT e SecOps a colaborar.
keywords: Cenários do Microsoft Defender para Endpoint-tvm, Microsoft Defender para Ponto de Extremidade, TVM, cenários de TVM, redução da exposição de vulnerabilidades de ameaça &, redução de ameaças e vulnerabilidades, melhoria da configuração de segurança, aumento da Pontuação Segura da Microsoft para Dispositivos, aumento da vulnerabilidade de & da Microsoft Secure Score for Devices, Pontuação Segura da Microsoft para Dispositivos, pontuação de exposição, controles de segurança
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a9a8ebcc89c3009cd93fbb42f2a74bbb9ffcc31b
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934088"
---
# <a name="hunt-for-exposed-devices---threat-and-vulnerability-management"></a><span data-ttu-id="a2d07-104">Busca por dispositivos expostos - gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a2d07-104">Hunt for exposed devices - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a2d07-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="a2d07-105">**Applies to:**</span></span>

- [<span data-ttu-id="a2d07-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="a2d07-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a2d07-107">Gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a2d07-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a2d07-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a2d07-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="a2d07-109">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="a2d07-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="a2d07-110">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="a2d07-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

## <a name="use-advanced-hunting-to-find-devices-with-vulnerabilities"></a><span data-ttu-id="a2d07-111">Usar a busca avançada para encontrar dispositivos com vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a2d07-111">Use advanced hunting to find devices with vulnerabilities</span></span>

<span data-ttu-id="a2d07-112">A busca avançada é uma ferramenta de busca de ameaças baseada em consultas que permite explorar até 30 dias de dados brutos.</span><span class="sxs-lookup"><span data-stu-id="a2d07-112">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span> <span data-ttu-id="a2d07-113">Você pode inspecionar proativamente eventos em sua rede para localizar indicadores e entidades de ameaça.</span><span class="sxs-lookup"><span data-stu-id="a2d07-113">You can proactively inspect events in your network to locate threat indicators and entities.</span></span> <span data-ttu-id="a2d07-114">O acesso flexível aos dados permite a busca não restrita por ameaças conhecidas e potenciais.</span><span class="sxs-lookup"><span data-stu-id="a2d07-114">The flexible access to data enables unconstrained hunting for both known and potential threats.</span></span> [<span data-ttu-id="a2d07-115">Saiba mais sobre a busca avançada</span><span class="sxs-lookup"><span data-stu-id="a2d07-115">Learn more about advanced hunting</span></span>](advanced-hunting-overview.md)

### <a name="schema-tables"></a><span data-ttu-id="a2d07-116">Tabelas de esquema</span><span class="sxs-lookup"><span data-stu-id="a2d07-116">Schema tables</span></span>

- <span data-ttu-id="a2d07-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventário de software instalado em dispositivos, incluindo suas informações de versão e status de fim de suporte.</span><span class="sxs-lookup"><span data-stu-id="a2d07-117">[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md) - Inventory of software installed on devices, including their version information and end-of-support status.</span></span>

- <span data-ttu-id="a2d07-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Vulnerabilidades de software encontradas em dispositivos e a lista de atualizações de segurança disponíveis que abordam cada vulnerabilidade.</span><span class="sxs-lookup"><span data-stu-id="a2d07-118">[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md) - Software vulnerabilities found on devices and the list of available security updates that address each vulnerability.</span></span>

- <span data-ttu-id="a2d07-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Base de conhecimento de vulnerabilidades publicamente divulgadas, incluindo se o código de exploração está disponível publicamente.</span><span class="sxs-lookup"><span data-stu-id="a2d07-119">[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md) - Knowledge base of publicly disclosed vulnerabilities, including whether exploit code is publicly available.</span></span>

- <span data-ttu-id="a2d07-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Eventos de avaliação de gerenciamento de ameaças e vulnerabilidades, indicando o status de várias configurações de segurança em dispositivos.</span><span class="sxs-lookup"><span data-stu-id="a2d07-120">[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md) - Threat and vulnerability management assessment events, indicating the status of various security configurations on devices.</span></span>

- <span data-ttu-id="a2d07-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Base de conhecimento de várias configurações de segurança usadas pelo Gerenciamento de Vulnerabilidades & Ameaças para avaliar dispositivos; inclui mapeamentos para vários padrões e parâmetros de referência</span><span class="sxs-lookup"><span data-stu-id="a2d07-121">[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md) - Knowledge base of various security configurations used by Threat & Vulnerability Management to assess devices; includes mappings to various standards and benchmarks</span></span>

## <a name="check-which-devices-are-involved-in-high-severity-alerts"></a><span data-ttu-id="a2d07-122">Verificar quais dispositivos estão envolvidos em alertas de alta gravidade</span><span class="sxs-lookup"><span data-stu-id="a2d07-122">Check which devices are involved in high severity alerts</span></span>

1. <span data-ttu-id="a2d07-123">Vá para **a busca avançada** no painel de navegação à esquerda do Centro de Segurança do Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="a2d07-123">Go to **Advanced hunting** from the left-hand navigation pane of the Microsoft Defender Security Center.</span></span>

2. <span data-ttu-id="a2d07-124">Role para baixo até os esquemas de busca avançada da TVM para se familiarizar com os nomes das colunas.</span><span class="sxs-lookup"><span data-stu-id="a2d07-124">Scroll down to the TVM advanced hunting schemas to familiarize yourself with the column names.</span></span>

3. <span data-ttu-id="a2d07-125">Insira as seguintes consultas:</span><span class="sxs-lookup"><span data-stu-id="a2d07-125">Enter the following queries:</span></span>

```kusto
// Search for devices with High active alerts or Critical CVE public exploit
DeviceTvmSoftwareVulnerabilities
| join kind=inner(DeviceTvmSoftwareVulnerabilitiesKB) on CveId
| where IsExploitAvailable == 1 and CvssScore >= 7
| summarize NumOfVulnerabilities=dcount(CveId),
DeviceName=any(DeviceName) by DeviceId
| join kind =inner(DeviceAlertEvents) on DeviceId  
| summarize NumOfVulnerabilities=any(NumOfVulnerabilities),
DeviceName=any(DeviceName) by DeviceId, AlertId
| project DeviceName, NumOfVulnerabilities, AlertId  
| order by NumOfVulnerabilities desc
```

## <a name="related-topics"></a><span data-ttu-id="a2d07-126">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="a2d07-126">Related topics</span></span>

- [<span data-ttu-id="a2d07-127">Visão geral do gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a2d07-127">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="a2d07-128">Recomendações de segurança</span><span class="sxs-lookup"><span data-stu-id="a2d07-128">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="a2d07-129">APIs</span><span class="sxs-lookup"><span data-stu-id="a2d07-129">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)
- [<span data-ttu-id="a2d07-130">Configurar o acesso a dados para funções de gerenciamento de ameaças e vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="a2d07-130">Configure data access for threat and vulnerability management roles</span></span>](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group)
- [<span data-ttu-id="a2d07-131">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="a2d07-131">Advanced hunting overview</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [<span data-ttu-id="a2d07-132">Todas as tabelas avançadas de busca</span><span class="sxs-lookup"><span data-stu-id="a2d07-132">All advanced hunting tables</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference.md)
