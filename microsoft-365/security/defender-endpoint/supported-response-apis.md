---
title: APIs de resposta avançada contra ameaças do Microsoft Defender com suporte
description: Saiba mais sobre as chamadas específicas da API de Proteção Avançada contra Ameaças do Microsoft Defender.
keywords: apis de resposta, api gráfica, apis com suporte, ator, alertas, dispositivo, usuário, domínio, ip, arquivo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: a290c431f6d81b23896ddf77e7c7a47de378de22
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185546"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="3727e-104">APIs de consulta com suporte do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3727e-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="3727e-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="3727e-105">**Applies to:**</span></span>
- [<span data-ttu-id="3727e-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="3727e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="3727e-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="3727e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="3727e-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="3727e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="3727e-109">Saiba mais sobre as chamadas de API relacionadas à resposta com suporte que você pode executar e detalhes como os headers de solicitação necessários e a resposta esperada das chamadas.</span><span class="sxs-lookup"><span data-stu-id="3727e-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="3727e-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3727e-110">In this section</span></span>
<span data-ttu-id="3727e-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="3727e-111">Topic</span></span> | <span data-ttu-id="3727e-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="3727e-112">Description</span></span>
:---|:---
<span data-ttu-id="3727e-113">Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="3727e-113">Collect investigation package</span></span> | <span data-ttu-id="3727e-114">Execute essa API para coletar um pacote de investigação de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3727e-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="3727e-115">Isolar dispositivo</span><span class="sxs-lookup"><span data-stu-id="3727e-115">Isolate device</span></span> | <span data-ttu-id="3727e-116">Execute essa API para isolar um dispositivo da rede.</span><span class="sxs-lookup"><span data-stu-id="3727e-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="3727e-117">Dispositivo unisolado</span><span class="sxs-lookup"><span data-stu-id="3727e-117">Unisolate device</span></span> | <span data-ttu-id="3727e-118">Remova um dispositivo do isolamento.</span><span class="sxs-lookup"><span data-stu-id="3727e-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="3727e-119">Restringir a execução de código</span><span class="sxs-lookup"><span data-stu-id="3727e-119">Restrict code execution</span></span> | <span data-ttu-id="3727e-120">Execute essa API para conter um ataque interrompendo processos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="3727e-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="3727e-121">Você também pode bloquear um dispositivo e impedir a execução de tentativas subsequentes de programas potencialmente mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="3727e-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="3727e-122">Execução de código desconsumentado</span><span class="sxs-lookup"><span data-stu-id="3727e-122">Unrestrict code execution</span></span> | <span data-ttu-id="3727e-123">Execute isso para reverter a restrição da política de aplicativos depois de verificar se o dispositivo comprometido foi remediado.</span><span class="sxs-lookup"><span data-stu-id="3727e-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="3727e-124">Executar verificação antivírus</span><span class="sxs-lookup"><span data-stu-id="3727e-124">Run antivirus scan</span></span> | <span data-ttu-id="3727e-125">Inicie remotamente uma verificação antivírus para ajudar a identificar e correção de malware que pode estar presente em um dispositivo comprometido.</span><span class="sxs-lookup"><span data-stu-id="3727e-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="3727e-126">Arquivo stop and quarantine</span><span class="sxs-lookup"><span data-stu-id="3727e-126">Stop and quarantine file</span></span> |  <span data-ttu-id="3727e-127">Execute essa chamada para interromper a execução de processos, arquivos de quarentena e excluir a persistência, como chaves do Registro.</span><span class="sxs-lookup"><span data-stu-id="3727e-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="3727e-128">Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="3727e-128">Request sample</span></span> | <span data-ttu-id="3727e-129">Execute essa chamada para solicitar um exemplo de um arquivo de um dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="3727e-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="3727e-130">O arquivo será coletado do dispositivo e carregado em um armazenamento seguro.</span><span class="sxs-lookup"><span data-stu-id="3727e-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="3727e-131">Bloquear arquivo</span><span class="sxs-lookup"><span data-stu-id="3727e-131">Block file</span></span> | <span data-ttu-id="3727e-132">Execute essa API para evitar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou suspeitas de malware.</span><span class="sxs-lookup"><span data-stu-id="3727e-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="3727e-133">Desbloquear arquivo</span><span class="sxs-lookup"><span data-stu-id="3727e-133">Unblock file</span></span> | <span data-ttu-id="3727e-134">Permitir que um arquivo seja executado na organização usando o Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="3727e-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="3727e-135">Obter URI do SAS do pacote</span><span class="sxs-lookup"><span data-stu-id="3727e-135">Get package SAS URI</span></span> | <span data-ttu-id="3727e-136">Execute essa API para obter um URI que permita baixar um pacote de investigação.</span><span class="sxs-lookup"><span data-stu-id="3727e-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="3727e-137">Obter objeto MachineAction</span><span class="sxs-lookup"><span data-stu-id="3727e-137">Get MachineAction object</span></span> | <span data-ttu-id="3727e-138">Execute essa API para obter o objeto MachineAction.</span><span class="sxs-lookup"><span data-stu-id="3727e-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="3727e-139">Obter coleção MachineActions</span><span class="sxs-lookup"><span data-stu-id="3727e-139">Get MachineActions collection</span></span> | <span data-ttu-id="3727e-140">Execute isso para obter a coleção MachineAction.</span><span class="sxs-lookup"><span data-stu-id="3727e-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="3727e-141">Obter coleção FileActions</span><span class="sxs-lookup"><span data-stu-id="3727e-141">Get FileActions collection</span></span> | <span data-ttu-id="3727e-142">Execute essa API para obter a coleção FileActions.</span><span class="sxs-lookup"><span data-stu-id="3727e-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="3727e-143">Obter objeto FileMachineAction</span><span class="sxs-lookup"><span data-stu-id="3727e-143">Get FileMachineAction object</span></span> | <span data-ttu-id="3727e-144">Execute essa API para obter o objeto FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="3727e-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="3727e-145">Obter coleção FileMachineActions</span><span class="sxs-lookup"><span data-stu-id="3727e-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="3727e-146">Execute essa API para obter a coleção FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="3727e-146">Run this API to get FileMachineAction collection.</span></span>
