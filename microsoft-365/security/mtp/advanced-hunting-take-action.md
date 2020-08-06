---
title: Executar ações na busca avançada de resultados de consulta na proteção contra ameaças da Microsoft
description: Resolver rapidamente as ameaças e os ativos afetados nos resultados da consulta de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção de ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, executar ação
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4ebf220472db69d48127b805256e15246bd400cb
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552723"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="e9b80-104">Executar ações nos resultados da consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="e9b80-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="e9b80-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e9b80-105">**Applies to:**</span></span>
- <span data-ttu-id="e9b80-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e9b80-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e9b80-107">Você pode facilmente conter ameaças ou lidar com os ativos comprometidos encontrados em [busca avançada](advanced-hunting-overview.md) usando opções de ações poderosas e abrangentes.</span><span class="sxs-lookup"><span data-stu-id="e9b80-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="e9b80-108">Com essas opções, você pode:</span><span class="sxs-lookup"><span data-stu-id="e9b80-108">With these options, you can:</span></span>

- <span data-ttu-id="e9b80-109">Executar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="e9b80-109">Take various actions on devices</span></span>
- <span data-ttu-id="e9b80-110">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="e9b80-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="e9b80-111">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="e9b80-111">Required permissions</span></span>
<span data-ttu-id="e9b80-112">Para executar ações por meio de busca avançada, você precisa de uma função no Microsoft defender ATP com [permissões para enviar ações de correção em dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="e9b80-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="e9b80-113">Se você não puder executar uma ação, entre em contato com um administrador global para obter a seguinte permissão:</span><span class="sxs-lookup"><span data-stu-id="e9b80-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="e9b80-114">*Ações de correção ativas > gerenciamento de vulnerabilidades e ameaças-tratamento de correção*</span><span class="sxs-lookup"><span data-stu-id="e9b80-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="e9b80-115">Executar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="e9b80-115">Take various actions on devices</span></span>
<span data-ttu-id="e9b80-116">Você pode executar as seguintes ações nos dispositivos identificados pela `DeviceId` coluna nos resultados de consulta:</span><span class="sxs-lookup"><span data-stu-id="e9b80-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="e9b80-117">Isolar dispositivos afetados para que contenham uma infecção ou impedir que ataques sejam movidos de forma mais tarde</span><span class="sxs-lookup"><span data-stu-id="e9b80-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="e9b80-118">Coletar pacote de investigação para obter informações mais legais</span><span class="sxs-lookup"><span data-stu-id="e9b80-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="e9b80-119">Execute uma verificação antivírus para encontrar e remover ameaças usando as atualizações de inteligência de segurança mais recentes</span><span class="sxs-lookup"><span data-stu-id="e9b80-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="e9b80-120">Iniciar uma investigação automatizada para verificar e corrigir ameaças no dispositivo e possivelmente outros dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="e9b80-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="e9b80-121">Restringir a execução do aplicativo apenas a arquivos executáveis assinados pela Microsoft, impedindo a atividade de ameaça subsequente por malware ou outros executáveis não confiáveis</span><span class="sxs-lookup"><span data-stu-id="e9b80-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="e9b80-122">Para saber mais sobre como essas ações de resposta são executadas por meio do Microsoft defender ATP, [Leia sobre as ações de resposta nos dispositivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="e9b80-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="e9b80-123">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="e9b80-123">Quarantine files</span></span>
<span data-ttu-id="e9b80-124">Você pode implantar a ação de *quarentena* nos arquivos para que eles sejam automaticamente colocados em quarentena quando encontrados.</span><span class="sxs-lookup"><span data-stu-id="e9b80-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="e9b80-125">Ao selecionar essa ação, você pode escolher entre as seguintes colunas para identificar quais arquivos da sua consulta resultam em quarentena:</span><span class="sxs-lookup"><span data-stu-id="e9b80-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="e9b80-126">`SHA1`— Na maioria das tabelas de caça avançadas, este é o SHA-1 do arquivo que foi afetado pela ação gravada.</span><span class="sxs-lookup"><span data-stu-id="e9b80-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="e9b80-127">Por exemplo, se um arquivo foi copiado, esse será o arquivo copiado.</span><span class="sxs-lookup"><span data-stu-id="e9b80-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="e9b80-128">`InitiatingProcessSHA1`— Na maioria das tabelas de busca avançada, este é o arquivo responsável por iniciar a ação gravada.</span><span class="sxs-lookup"><span data-stu-id="e9b80-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="e9b80-129">Por exemplo, se um processo filho foi iniciado, esse seria o processo pai.</span><span class="sxs-lookup"><span data-stu-id="e9b80-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="e9b80-130">`SHA256`— Este é o equivalente SHA-256 do arquivo identificado pela `SHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="e9b80-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="e9b80-131">`InitiatingProcessSHA256`— Este é o equivalente SHA-256 do arquivo identificado pela `InitiatingProcessSHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="e9b80-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="e9b80-132">Para saber mais sobre como as ações de quarentena são tomadas e como os arquivos podem ser restaurados, [Leia sobre as ações de resposta nos arquivos](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="e9b80-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="e9b80-133">Para localizar arquivos e Quarantine-los, os resultados da consulta também devem incluir `DeviceId` valores como identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e9b80-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="e9b80-134">Executar ação</span><span class="sxs-lookup"><span data-stu-id="e9b80-134">Take action</span></span>
<span data-ttu-id="e9b80-135">Para executar qualquer uma das ações descritas, selecione um ou mais registros nos resultados da consulta e selecione **executar ações**.</span><span class="sxs-lookup"><span data-stu-id="e9b80-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="e9b80-136">Um assistente orientará você pelo processo de seleção e envio de suas ações preferidas.</span><span class="sxs-lookup"><span data-stu-id="e9b80-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Imagem do registro selecionado com painel para inspecionar o registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="e9b80-138">Revisar ações executadas</span><span class="sxs-lookup"><span data-stu-id="e9b80-138">Review actions taken</span></span>
<span data-ttu-id="e9b80-139">Cada ação é registrada individualmente na [central de ações](mtp-action-center.md) , em histórico da **central de ações**  >  **History** ([Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="e9b80-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="e9b80-140">Vá para a central de ações para verificar o status de cada ação.</span><span class="sxs-lookup"><span data-stu-id="e9b80-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="e9b80-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e9b80-141">Related topics</span></span>
- [<span data-ttu-id="e9b80-142">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="e9b80-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9b80-143">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="e9b80-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e9b80-144">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="e9b80-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="e9b80-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="e9b80-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="e9b80-146">Visão geral da central de ações</span><span class="sxs-lookup"><span data-stu-id="e9b80-146">Action center overview</span></span>](mtp-action-center.md)