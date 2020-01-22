---
title: Como relatar falsos positivos ou falsos negativos no AIR na proteção contra ameaças da Microsoft
description: Algo estava perdido ou foi detectado incorretamente pelo ar na proteção contra ameaças da Microsoft? Saiba como enviar falsos positivos ou falsos negativos para a Microsoft para análise.
keywords: automatizado, investigação, alerta, gatilho, ação, correção, falso positivo, falso negativo
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260189"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="72d45-105">Como relatar falsos positivos/negativos em recursos de investigação e resposta automatizados</span><span class="sxs-lookup"><span data-stu-id="72d45-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="72d45-106">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="72d45-106">**Applies to:**</span></span>
- <span data-ttu-id="72d45-107">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="72d45-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="72d45-108">Os [recursos de investigação e resposta automatizados](mtp-autoir.md) na proteção contra ameaças da Microsoft perdem ou detectam incorretamente algo?</span><span class="sxs-lookup"><span data-stu-id="72d45-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="72d45-109">Você pode relatá-la à Microsoft ou ajustar seus alertas (se necessário).</span><span class="sxs-lookup"><span data-stu-id="72d45-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="72d45-110">Use a tabela a seguir como uma guia:</span><span class="sxs-lookup"><span data-stu-id="72d45-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="72d45-111">Item</span><span class="sxs-lookup"><span data-stu-id="72d45-111">Item</span></span>  |<span data-ttu-id="72d45-112">Detectado por</span><span class="sxs-lookup"><span data-stu-id="72d45-112">Detected by</span></span>  |<span data-ttu-id="72d45-113">Como relatá-lo</span><span class="sxs-lookup"><span data-stu-id="72d45-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="72d45-114">Mensagem de email</span><span class="sxs-lookup"><span data-stu-id="72d45-114">Email message</span></span> <br/><span data-ttu-id="72d45-115">Anexo de email</span><span class="sxs-lookup"><span data-stu-id="72d45-115">Email attachment</span></span> <br/><span data-ttu-id="72d45-116">URL em uma mensagem de email ou em um arquivo do Office</span><span class="sxs-lookup"><span data-stu-id="72d45-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="72d45-117">Proteção Avançada contra Ameaças do Office 365</span><span class="sxs-lookup"><span data-stu-id="72d45-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="72d45-118">Enviar spam, phishing, URLs e arquivos suspeitos à Microsoft para a verificação do Office 365</span><span class="sxs-lookup"><span data-stu-id="72d45-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="72d45-119">Arquivo ou aplicativo em um dispositivo</span><span class="sxs-lookup"><span data-stu-id="72d45-119">File or app on a device</span></span>    |[<span data-ttu-id="72d45-120">Proteção Avançada contra Ameaças do Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="72d45-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="72d45-121">Enviar um arquivo para a Microsoft para análise de malware</span><span class="sxs-lookup"><span data-stu-id="72d45-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="72d45-122">Alerta disparado por uso legítimo</span><span class="sxs-lookup"><span data-stu-id="72d45-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="72d45-123">Alerta incorreto</span><span class="sxs-lookup"><span data-stu-id="72d45-123">Inaccurate alert</span></span>    |[<span data-ttu-id="72d45-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="72d45-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="72d45-125">ou</span><span class="sxs-lookup"><span data-stu-id="72d45-125">or</span></span> <br/>[<span data-ttu-id="72d45-126">Detecção avançada de ameaças do Azure</span><span class="sxs-lookup"><span data-stu-id="72d45-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="72d45-127">Gerenciar alertas no portal do Cloud app Security</span><span class="sxs-lookup"><span data-stu-id="72d45-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="72d45-128">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="72d45-128">Next steps</span></span>

- [<span data-ttu-id="72d45-129">Aprovar ou rejeitar ações relacionadas a investigações e respostas automatizadas</span><span class="sxs-lookup"><span data-stu-id="72d45-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="72d45-130">Saiba mais sobre a Central de Ações</span><span class="sxs-lookup"><span data-stu-id="72d45-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="72d45-131">Faça buscas proativas por ameaças com a busca avançada da Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="72d45-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
