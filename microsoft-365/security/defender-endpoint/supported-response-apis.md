---
title: APIs de resposta do Microsoft Defender para Ponto de Extremidade com suporte
description: Saiba mais sobre as chamadas de API específicas relacionadas à resposta do Microsoft Defender para Endpoint.
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
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933764"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="c15da-104">APIs de consulta com suporte do Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c15da-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c15da-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c15da-105">**Applies to:**</span></span>
- [<span data-ttu-id="c15da-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="c15da-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="c15da-107">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="c15da-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c15da-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="c15da-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="c15da-109">Saiba mais sobre as chamadas de API relacionadas à resposta com suporte que você pode executar e detalhes como os headers de solicitação necessários e a resposta esperada das chamadas.</span><span class="sxs-lookup"><span data-stu-id="c15da-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="c15da-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c15da-110">In this section</span></span>
<span data-ttu-id="c15da-111">Tópico</span><span class="sxs-lookup"><span data-stu-id="c15da-111">Topic</span></span> | <span data-ttu-id="c15da-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="c15da-112">Description</span></span>
:---|:---
<span data-ttu-id="c15da-113">Coletar pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="c15da-113">Collect investigation package</span></span> | <span data-ttu-id="c15da-114">Execute essa API para coletar um pacote de investigação de um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c15da-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="c15da-115">Isolar dispositivo</span><span class="sxs-lookup"><span data-stu-id="c15da-115">Isolate device</span></span> | <span data-ttu-id="c15da-116">Execute essa API para isolar um dispositivo da rede.</span><span class="sxs-lookup"><span data-stu-id="c15da-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="c15da-117">Dispositivo unisolado</span><span class="sxs-lookup"><span data-stu-id="c15da-117">Unisolate device</span></span> | <span data-ttu-id="c15da-118">Remova um dispositivo do isolamento.</span><span class="sxs-lookup"><span data-stu-id="c15da-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="c15da-119">Restringir a execução de código</span><span class="sxs-lookup"><span data-stu-id="c15da-119">Restrict code execution</span></span> | <span data-ttu-id="c15da-120">Execute essa API para conter um ataque interrompendo processos mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="c15da-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="c15da-121">Você também pode bloquear um dispositivo e impedir a execução de tentativas subsequentes de programas potencialmente mal-intencionados.</span><span class="sxs-lookup"><span data-stu-id="c15da-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="c15da-122">Execução de código desconsumentado</span><span class="sxs-lookup"><span data-stu-id="c15da-122">Unrestrict code execution</span></span> | <span data-ttu-id="c15da-123">Execute isso para reverter a restrição da política de aplicativos depois de verificar se o dispositivo comprometido foi remediado.</span><span class="sxs-lookup"><span data-stu-id="c15da-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="c15da-124">Executar verificação de antivírus</span><span class="sxs-lookup"><span data-stu-id="c15da-124">Run antivirus scan</span></span> | <span data-ttu-id="c15da-125">Inicie remotamente uma verificação antivírus para ajudar a identificar e correção de malware que pode estar presente em um dispositivo comprometido.</span><span class="sxs-lookup"><span data-stu-id="c15da-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="c15da-126">Interromper e colocar o arquivo em quarentena</span><span class="sxs-lookup"><span data-stu-id="c15da-126">Stop and quarantine file</span></span> |  <span data-ttu-id="c15da-127">Execute essa chamada para interromper a execução de processos, arquivos de quarentena e excluir a persistência, como chaves do Registro.</span><span class="sxs-lookup"><span data-stu-id="c15da-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="c15da-128">Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="c15da-128">Request sample</span></span> | <span data-ttu-id="c15da-129">Execute essa chamada para solicitar um exemplo de um arquivo de um dispositivo específico.</span><span class="sxs-lookup"><span data-stu-id="c15da-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="c15da-130">O arquivo será coletado do dispositivo e carregado em um armazenamento seguro.</span><span class="sxs-lookup"><span data-stu-id="c15da-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="c15da-131">Bloquear arquivo</span><span class="sxs-lookup"><span data-stu-id="c15da-131">Block file</span></span> | <span data-ttu-id="c15da-132">Execute essa API para evitar a propagação de um ataque em sua organização, proibindo arquivos potencialmente mal-intencionados ou suspeitas de malware.</span><span class="sxs-lookup"><span data-stu-id="c15da-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="c15da-133">Desbloquear arquivo</span><span class="sxs-lookup"><span data-stu-id="c15da-133">Unblock file</span></span> | <span data-ttu-id="c15da-134">Permitir que um arquivo seja executado na organização usando Microsoft Defender Antivírus.</span><span class="sxs-lookup"><span data-stu-id="c15da-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="c15da-135">Obter URI do SAS do pacote</span><span class="sxs-lookup"><span data-stu-id="c15da-135">Get package SAS URI</span></span> | <span data-ttu-id="c15da-136">Execute essa API para obter um URI que permita baixar um pacote de investigação.</span><span class="sxs-lookup"><span data-stu-id="c15da-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="c15da-137">Obter objeto MachineAction</span><span class="sxs-lookup"><span data-stu-id="c15da-137">Get MachineAction object</span></span> | <span data-ttu-id="c15da-138">Execute essa API para obter o objeto MachineAction.</span><span class="sxs-lookup"><span data-stu-id="c15da-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="c15da-139">Obter coleção MachineActions</span><span class="sxs-lookup"><span data-stu-id="c15da-139">Get MachineActions collection</span></span> | <span data-ttu-id="c15da-140">Execute isso para obter a coleção MachineAction.</span><span class="sxs-lookup"><span data-stu-id="c15da-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="c15da-141">Obter coleção FileActions</span><span class="sxs-lookup"><span data-stu-id="c15da-141">Get FileActions collection</span></span> | <span data-ttu-id="c15da-142">Execute essa API para obter a coleção FileActions.</span><span class="sxs-lookup"><span data-stu-id="c15da-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="c15da-143">Obter objeto FileMachineAction</span><span class="sxs-lookup"><span data-stu-id="c15da-143">Get FileMachineAction object</span></span> | <span data-ttu-id="c15da-144">Execute essa API para obter o objeto FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="c15da-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="c15da-145">Obter coleção FileMachineActions</span><span class="sxs-lookup"><span data-stu-id="c15da-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="c15da-146">Execute essa API para obter a coleção FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="c15da-146">Run this API to get FileMachineAction collection.</span></span>
