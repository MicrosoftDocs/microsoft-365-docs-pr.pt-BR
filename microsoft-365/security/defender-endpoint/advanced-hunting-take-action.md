---
title: Tomar medidas em resultados avançados de consulta de busca na Proteção contra Ameaças da Microsoft
description: Resolver rapidamente ameaças e ativos afetados em seus resultados de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, mdatp, microsoft defender atp, pesquisa wdatp, consulta, telemetria, detecções personalizadas, esquema, kusto, evitar tempo de espera, linhas de comando, id de processo
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
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51054198"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="ff79f-104">Tomar medidas nos resultados avançados da consulta de busca</span><span class="sxs-lookup"><span data-stu-id="ff79f-104">Take action on advanced hunting query results</span></span>

<span data-ttu-id="ff79f-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="ff79f-105">**Applies to:**</span></span>
- [<span data-ttu-id="ff79f-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="ff79f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> <span data-ttu-id="ff79f-107">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="ff79f-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="ff79f-108">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="ff79f-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="ff79f-109">Você pode conter rapidamente ameaças ou resolver ativos comprometidos que você encontra na busca [avançada](advanced-hunting-overview.md) usando opções de ação avançadas e abrangentes.</span><span class="sxs-lookup"><span data-stu-id="ff79f-109">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="ff79f-110">Com essas opções, você pode:</span><span class="sxs-lookup"><span data-stu-id="ff79f-110">With these options, you can:</span></span>

- <span data-ttu-id="ff79f-111">Tomar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="ff79f-111">Take various actions on devices</span></span>
- <span data-ttu-id="ff79f-112">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="ff79f-112">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="ff79f-113">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="ff79f-113">Required permissions</span></span>

<span data-ttu-id="ff79f-114">Para poder realizar ações por meio da busca avançada, você precisa de uma função no Defender para Ponto de Extremidade com permissões para enviar ações de [correção em dispositivos](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="ff79f-114">To be able to take action through advanced hunting, you need a role in Defender for Endpoint with [permissions to submit remediation actions on devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options).</span></span> <span data-ttu-id="ff79f-115">Se você não puder tomar uma ação, contate um administrador global sobre como obter a seguinte permissão:</span><span class="sxs-lookup"><span data-stu-id="ff79f-115">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="ff79f-116">*Ações de correção ativas > gerenciamento de ameaças e vulnerabilidades - Tratamento de correção*</span><span class="sxs-lookup"><span data-stu-id="ff79f-116">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="ff79f-117">Tomar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="ff79f-117">Take various actions on devices</span></span>

<span data-ttu-id="ff79f-118">Você pode tomar as seguintes ações em dispositivos identificados pela `DeviceId` coluna nos resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="ff79f-118">You can take the following actions on devices identified by the `DeviceId` column in your query results:</span></span>

- <span data-ttu-id="ff79f-119">Isolar dispositivos afetados para conter uma infecção ou impedir que os ataques se movem lateralmente</span><span class="sxs-lookup"><span data-stu-id="ff79f-119">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="ff79f-120">Coletar pacote de investigação para obter mais informações forenses</span><span class="sxs-lookup"><span data-stu-id="ff79f-120">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="ff79f-121">Executar uma verificação antivírus para encontrar e remover ameaças usando as atualizações mais recentes de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="ff79f-121">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="ff79f-122">Inicie uma investigação automatizada para verificar e remediar ameaças no dispositivo e, possivelmente, em outros dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="ff79f-122">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="ff79f-123">Restringir a execução de aplicativos somente a arquivos executáveis assinados pela Microsoft, impedindo atividades de ameaças subsequentes por meio de malware ou outros executáveis não-confiança</span><span class="sxs-lookup"><span data-stu-id="ff79f-123">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="ff79f-124">Para saber mais sobre como essas ações de resposta são executadas por meio do Defender for Endpoint, [leia sobre ações de resposta em dispositivos](respond-machine-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="ff79f-124">To learn more about how these response actions are performed through Defender for Endpoint, [read about response actions on devices](respond-machine-alerts.md).</span></span>

## <a name="quarantine-files"></a><span data-ttu-id="ff79f-125">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="ff79f-125">Quarantine files</span></span>

<span data-ttu-id="ff79f-126">Você pode implantar a *ação de* quarentena em arquivos para que eles sejam automaticamente colocados em quarentena quando encontrados.</span><span class="sxs-lookup"><span data-stu-id="ff79f-126">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="ff79f-127">Ao selecionar essa ação, você pode escolher entre as seguintes colunas para identificar quais arquivos em sua consulta resulta em quarentena:</span><span class="sxs-lookup"><span data-stu-id="ff79f-127">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="ff79f-128">`SHA1` — Nas tabelas de busca mais avançadas, este é o SHA-1 do arquivo que foi afetado pela ação gravada.</span><span class="sxs-lookup"><span data-stu-id="ff79f-128">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="ff79f-129">Por exemplo, se um arquivo foi copiado, esse seria o arquivo copiado.</span><span class="sxs-lookup"><span data-stu-id="ff79f-129">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="ff79f-130">`InitiatingProcessSHA1` — Nas tabelas de busca mais avançadas, esse é o arquivo responsável por iniciar a ação gravada.</span><span class="sxs-lookup"><span data-stu-id="ff79f-130">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="ff79f-131">Por exemplo, se um processo filho foi lançado, esse seria o processo pai.</span><span class="sxs-lookup"><span data-stu-id="ff79f-131">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="ff79f-132">`SHA256` — Esse é o equivalente sha-256 do arquivo identificado pela `SHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="ff79f-132">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="ff79f-133">`InitiatingProcessSHA256` — Esse é o equivalente sha-256 do arquivo identificado pela `InitiatingProcessSHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="ff79f-133">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="ff79f-134">Para saber mais sobre como as ações de quarentena são tomadas e como os arquivos podem ser restaurados, [leia sobre ações de resposta em arquivos](respond-file-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="ff79f-134">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](respond-file-alerts.md).</span></span>

>[!NOTE]
><span data-ttu-id="ff79f-135">Para localizar arquivos e colocar em quarentena, os resultados da consulta também devem incluir `DeviceId` valores como identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ff79f-135">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="ff79f-136">Tomar uma ação</span><span class="sxs-lookup"><span data-stu-id="ff79f-136">Take action</span></span>

<span data-ttu-id="ff79f-137">Para tomar qualquer uma das ações descritas, selecione um ou mais registros nos resultados da consulta e selecione **Tomar ações**.</span><span class="sxs-lookup"><span data-stu-id="ff79f-137">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="ff79f-138">Um assistente o guiará pelo processo de seleção e, em seguida, enviará suas ações preferenciais.</span><span class="sxs-lookup"><span data-stu-id="ff79f-138">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Imagem do registro selecionado com painel para inspecionar o registro](images/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="ff79f-140">Revisar ações realizadas</span><span class="sxs-lookup"><span data-stu-id="ff79f-140">Review actions taken</span></span>

<span data-ttu-id="ff79f-141">Cada ação é registrada individualmente no centro de ações, em **Histórico do Centro de** Ações (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="ff79f-141">Each action is individually recorded in the action center, under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="ff79f-142">Vá para o centro de ações para verificar o status de cada ação.</span><span class="sxs-lookup"><span data-stu-id="ff79f-142">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="ff79f-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ff79f-143">Related topics</span></span>

- [<span data-ttu-id="ff79f-144">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="ff79f-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ff79f-145">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="ff79f-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ff79f-146">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="ff79f-146">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="ff79f-147">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="ff79f-147">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ff79f-148">Aplicar práticas recomendadas de consulta</span><span class="sxs-lookup"><span data-stu-id="ff79f-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ff79f-149">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="ff79f-149">Custom detections overview</span></span>](overview-custom-detections.md)
