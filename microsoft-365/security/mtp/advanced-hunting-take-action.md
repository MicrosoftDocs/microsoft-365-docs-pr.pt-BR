---
title: Tomar medidas em busca avançada de resultados de consulta no Microsoft 365 Defender
description: Resolver rapidamente ameaças e ativos afetados em seus resultados de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, tomar medidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932173"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="1d7e9-104">Tomar medidas em resultados de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="1d7e9-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1d7e9-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="1d7e9-105">**Applies to:**</span></span>
- <span data-ttu-id="1d7e9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d7e9-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="1d7e9-107">Você pode rapidamente conter ameaças ou resolver ativos comprometidos que encontra na busca avançada [usando](advanced-hunting-overview.md) opções de ação avançadas e abrangentes.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="1d7e9-108">Com essas opções, você pode:</span><span class="sxs-lookup"><span data-stu-id="1d7e9-108">With these options, you can:</span></span>

- <span data-ttu-id="1d7e9-109">Tomar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="1d7e9-109">Take various actions on devices</span></span>
- <span data-ttu-id="1d7e9-110">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="1d7e9-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="1d7e9-111">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="1d7e9-111">Required permissions</span></span>
<span data-ttu-id="1d7e9-112">Para poder realizar ações por meio da busca avançada, você precisa de uma função no Microsoft Defender for Endpoint com permissões para enviar ações de correção [em dispositivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)</span><span class="sxs-lookup"><span data-stu-id="1d7e9-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="1d7e9-113">Se não for possível tomar medidas, entre em contato com um administrador global para obter a seguinte permissão:</span><span class="sxs-lookup"><span data-stu-id="1d7e9-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="1d7e9-114">*Ações de correção ativas > gerenciamento de ameaças e vulnerabilidades - Tratamento de correção*</span><span class="sxs-lookup"><span data-stu-id="1d7e9-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="1d7e9-115">Tomar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="1d7e9-115">Take various actions on devices</span></span>
<span data-ttu-id="1d7e9-116">Você pode tomar as seguintes ações em dispositivos identificados pela `DeviceId` coluna nos resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="1d7e9-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="1d7e9-117">Isolar dispositivos afetados para conter uma infecção ou impedir que ataques se movem lateralmente</span><span class="sxs-lookup"><span data-stu-id="1d7e9-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="1d7e9-118">Coletar pacote de investigação para obter mais informações forenses</span><span class="sxs-lookup"><span data-stu-id="1d7e9-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="1d7e9-119">Executar uma verificação antivírus para encontrar e remover ameaças usando as atualizações mais recentes de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="1d7e9-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="1d7e9-120">Iniciar uma investigação automatizada para verificar e remediar ameaças no dispositivo e possivelmente outros dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="1d7e9-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="1d7e9-121">Restringir a execução do aplicativo somente a arquivos executáveis assinados pela Microsoft, impedindo a atividade subsequente de ameaças por meio de malware ou outros executáveis não-confianças</span><span class="sxs-lookup"><span data-stu-id="1d7e9-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="1d7e9-122">Para saber mais sobre como essas ações de resposta são executadas por meio do Microsoft Defender para Ponto de Extremidade, [leia sobre ações de resposta em dispositivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)</span><span class="sxs-lookup"><span data-stu-id="1d7e9-122">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="1d7e9-123">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="1d7e9-123">Quarantine files</span></span>
<span data-ttu-id="1d7e9-124">Você pode implantar a *ação de* quarentena em arquivos para que eles sejam automaticamente colocados em quarentena quando encontrados.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="1d7e9-125">Ao selecionar essa ação, você pode escolher entre as seguintes colunas para identificar quais arquivos da consulta serão colocados em quarentena:</span><span class="sxs-lookup"><span data-stu-id="1d7e9-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="1d7e9-126">`SHA1` — Nas tabelas de busca mais avançadas, este é o SHA-1 do arquivo que foi afetado pela ação gravada.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="1d7e9-127">Por exemplo, se um arquivo foi copiado, esse seria o arquivo copiado.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="1d7e9-128">`InitiatingProcessSHA1` — Nas tabelas de busca mais avançadas, esse é o arquivo responsável por iniciar a ação gravada.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="1d7e9-129">Por exemplo, se um processo filho foi lançado, esse seria o processo pai.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="1d7e9-130">`SHA256` — Este é o equivalente SHA-256 do arquivo identificado pela `SHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="1d7e9-131">`InitiatingProcessSHA256` — Este é o equivalente SHA-256 do arquivo identificado pela `InitiatingProcessSHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="1d7e9-132">Para saber mais sobre como as ações de quarentena são tomadas e como os arquivos podem ser restaurados, [leia sobre ações de resposta em arquivos.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)</span><span class="sxs-lookup"><span data-stu-id="1d7e9-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="1d7e9-133">Para localizar arquivos e coloca-los em quarentena, os resultados da consulta também devem incluir `DeviceId` valores como identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="1d7e9-134">Tomar medidas</span><span class="sxs-lookup"><span data-stu-id="1d7e9-134">Take action</span></span>
<span data-ttu-id="1d7e9-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="1d7e9-136">Um assistente o orientará durante o processo de seleção e envio de suas ações preferidas.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Imagem do registro selecionado com painel para inspecionar o registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="1d7e9-138">Revisar as ações tomadas</span><span class="sxs-lookup"><span data-stu-id="1d7e9-138">Review actions taken</span></span>
<span data-ttu-id="1d7e9-139">Cada ação é registrada individualmente na central de ações [em](mtp-action-center.md) **Histórico da Central** de Ações (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="1d7e9-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="1d7e9-140">Vá para a central de ações para verificar o status de cada ação.</span><span class="sxs-lookup"><span data-stu-id="1d7e9-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="1d7e9-141">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1d7e9-141">Related topics</span></span>
- [<span data-ttu-id="1d7e9-142">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="1d7e9-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="1d7e9-143">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="1d7e9-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="1d7e9-144">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="1d7e9-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="1d7e9-145">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="1d7e9-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="1d7e9-146">Visão geral da Central de Ações</span><span class="sxs-lookup"><span data-stu-id="1d7e9-146">Action center overview</span></span>](mtp-action-center.md)
