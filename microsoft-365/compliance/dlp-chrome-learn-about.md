---
title: Saiba mais sobre a Extensão de Conformidade da Microsoft (prévia)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: A Extensão de Conformidade da Microsoft estende o monitoramento e controle de atividades de arquivo e ações de proteção para o navegador Google Chrome
ms.openlocfilehash: c8a5795b3be8b393fd3a934504449bf6db0c2f01
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113377"
---
# <a name="learn-about-the-microsoft-compliance-extension-preview"></a><span data-ttu-id="33ae6-103">Saiba mais sobre a Extensão de Conformidade da Microsoft (prévia)</span><span class="sxs-lookup"><span data-stu-id="33ae6-103">Learn about the Microsoft Compliance Extension (preview)</span></span>

<span data-ttu-id="33ae6-104">[A Prevenção contra Perda de Dados de Ponto de Extremidade (ponto de extremidade DLP)](endpoint-dlp-learn-about.md) estende os recursos de monitoramento de atividade e proteção da [prevenção contra perda de dados (DLP) do Microsoft 365](dlp-learn-about-dlp.md) para itens confidenciais que estão em dispositivos Windows 10.</span><span class="sxs-lookup"><span data-stu-id="33ae6-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="33ae6-105">Depois que os dispositivos estiverem integrados às soluções de conformidade do Microsoft 365, as informações sobre o que os usuários estão fazendo com itens confidenciais serão visíveis no [explorador de atividades](data-classification-activity-explorer.md) e você poderá aplicar ações de proteção a esses itens por meio das [políticas DLP](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="33ae6-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="33ae6-106">Depois que a Extensão de Conformidade da Microsoft é instalada em um dispositivo Windows 10, as organizações podem monitorar quando um usuário tenta acessar ou fazer upload de um item confidencial para um serviço em nuvem usando o Google Chrome e aplicar ações de proteção via DLP.</span><span class="sxs-lookup"><span data-stu-id="33ae6-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="33ae6-107">Atividades que você pode monitorar e realizar</span><span class="sxs-lookup"><span data-stu-id="33ae6-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="33ae6-108">A extensão de Conformidade da Microsoft permite que você audite e gerencie os seguintes tipos de atividades que os usuários realizam em itens confidenciais em dispositivos que executam o Windows 10.</span><span class="sxs-lookup"><span data-stu-id="33ae6-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="33ae6-109">atividade</span><span class="sxs-lookup"><span data-stu-id="33ae6-109">activity</span></span> |<span data-ttu-id="33ae6-110">descrição</span><span class="sxs-lookup"><span data-stu-id="33ae6-110">description</span></span>  | <span data-ttu-id="33ae6-111">ações de política apoiadas</span><span class="sxs-lookup"><span data-stu-id="33ae6-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="33ae6-112">arquivo copiado para nuvem</span><span class="sxs-lookup"><span data-stu-id="33ae6-112">file copied to cloud</span></span>  | <span data-ttu-id="33ae6-113">Detecta quando um usuário tenta fazer upload de um item confidencial para um domínio de serviço restrito por meio do navegador Chrome</span><span class="sxs-lookup"><span data-stu-id="33ae6-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="33ae6-114">auditoria, bloquear</span><span class="sxs-lookup"><span data-stu-id="33ae6-114">audit, block</span></span>|
|<span data-ttu-id="33ae6-115">arquivo impresso</span><span class="sxs-lookup"><span data-stu-id="33ae6-115">file printed</span></span>  |<span data-ttu-id="33ae6-116">Detecta quando um usuário tenta imprimir um item confidencial que está aberto no navegador Chrome em uma impressora local ou de rede</span><span class="sxs-lookup"><span data-stu-id="33ae6-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="33ae6-117">auditoria, bloquear com substituição, bloquear</span><span class="sxs-lookup"><span data-stu-id="33ae6-117">audit, block with override, block</span></span>|
|<span data-ttu-id="33ae6-118">O arquivo foi copiado para a área de transferência</span><span class="sxs-lookup"><span data-stu-id="33ae6-118">file copied to clipboard</span></span> |<span data-ttu-id="33ae6-119">Detecta quando um usuário tenta copiar informações de um item confidencial que está sendo visualizado no navegador Chrome e, em seguida, colá-lo em outro aplicativo, processo ou item.</span><span class="sxs-lookup"><span data-stu-id="33ae6-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="33ae6-120">auditoria, bloquear com substituição, bloquear</span><span class="sxs-lookup"><span data-stu-id="33ae6-120">audit, block with override, block</span></span>|
|<span data-ttu-id="33ae6-121">arquivo copiado para armazenamento removível</span><span class="sxs-lookup"><span data-stu-id="33ae6-121">file copied to removable storage</span></span>    | <span data-ttu-id="33ae6-122">Detecta quando um usuário tenta copiar um item confidencial ou informação de um item confidencial que está aberto no navegador Chrome para uma mídia removível ou dispositivo USB</span><span class="sxs-lookup"><span data-stu-id="33ae6-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="33ae6-123">auditoria, bloquear com substituição, bloquear</span><span class="sxs-lookup"><span data-stu-id="33ae6-123">audit, block with override, block</span></span>|
|<span data-ttu-id="33ae6-124">arquivo copiado para compartilhamento de rede</span><span class="sxs-lookup"><span data-stu-id="33ae6-124">file copied to network share</span></span>  |<span data-ttu-id="33ae6-125">Detecta quando um usuário tenta copiar um item confidencial ou informação de um item confidencial que está aberto no navegador Chrome para um compartilhamento de rede ou unidade de rede mapeada.</span><span class="sxs-lookup"><span data-stu-id="33ae6-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="33ae6-126">auditoria, bloquear com substituição, bloquear</span><span class="sxs-lookup"><span data-stu-id="33ae6-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="33ae6-127">Processo de implantação</span><span class="sxs-lookup"><span data-stu-id="33ae6-127">Deployment process</span></span>
1. [<span data-ttu-id="33ae6-128">Comece a usar a prevenção contra Perda de Dados de Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="33ae6-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="33ae6-129">Ferramentas e métodos de integração para dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="33ae6-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="33ae6-130">Instale a extensão em seus dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="33ae6-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="33ae6-131">[Crie ou edite políticas de DLP](create-test-tune-dlp-policy.md) que restrinjam o upload para o serviço em nuvem ou o acesso por meio de ações não permitidas de navegadores e aplique-as aos seus dispositivos Windows 10</span><span class="sxs-lookup"><span data-stu-id="33ae6-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="33ae6-132">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="33ae6-132">Next steps</span></span>

<span data-ttu-id="33ae6-133">Confira [Primeiros passos com a Extensão de Conformidade da Microsoft](dlp-chrome-get-started.md) para procedimentos e cenários completos de implantação.</span><span class="sxs-lookup"><span data-stu-id="33ae6-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="33ae6-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="33ae6-134">See also</span></span>

- [<span data-ttu-id="33ae6-135">Comece a usar a Extensão de Conformidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="33ae6-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="33ae6-136">Saiba mais sobre a prevenção contra Perda de Dados de Ponto de Extremidade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33ae6-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="33ae6-137">Introdução à prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="33ae6-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="33ae6-138">Usar a prevenção contra perda de dados do Ponto de extremidade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="33ae6-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="33ae6-139">Saiba mais sobre prevenção contra perda de dados</span><span class="sxs-lookup"><span data-stu-id="33ae6-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="33ae6-140">Criar, testar e ajustar uma política DLP</span><span class="sxs-lookup"><span data-stu-id="33ae6-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="33ae6-141">Começar a usar o Explorador de atividades</span><span class="sxs-lookup"><span data-stu-id="33ae6-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="33ae6-142">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="33ae6-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="33ae6-143">Gerenciamento de risco interno</span><span class="sxs-lookup"><span data-stu-id="33ae6-143">Insider Risk management</span></span>](insider-risk-management.md)
