---
title: Tomar medidas em resultados de consulta de busca avançada no Microsoft 365 Defender
description: Resolver rapidamente ameaças e ativos afetados em seus resultados de consulta de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, Microsoft 365 Defender, microsoft 365, m365, pesquisa, consulta, telemetria, tomar medidas
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 15eebbba102640a92f9c7712194aaef685a96cfb
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952603"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="6fea2-104">Tomar medidas nos resultados avançados da consulta de busca</span><span class="sxs-lookup"><span data-stu-id="6fea2-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6fea2-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6fea2-105">**Applies to:**</span></span>
- <span data-ttu-id="6fea2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6fea2-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="6fea2-107">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="6fea2-107">Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="6fea2-108">Você pode conter rapidamente ameaças ou resolver ativos comprometidos que você encontra na busca [avançada](advanced-hunting-overview.md) usando opções de ação avançadas e abrangentes.</span><span class="sxs-lookup"><span data-stu-id="6fea2-108">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="6fea2-109">Com essas opções, você pode:</span><span class="sxs-lookup"><span data-stu-id="6fea2-109">With these options, you can:</span></span>

- <span data-ttu-id="6fea2-110">Tomar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="6fea2-110">Take various actions on devices</span></span>
- <span data-ttu-id="6fea2-111">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="6fea2-111">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="6fea2-112">Permissões obrigatórias</span><span class="sxs-lookup"><span data-stu-id="6fea2-112">Required permissions</span></span>
<span data-ttu-id="6fea2-113">Para poder realizar ações por meio da busca avançada, você precisa de uma função no Microsoft Defender para Ponto de Extremidade com permissões para enviar ações de [correção em dispositivos](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span><span class="sxs-lookup"><span data-stu-id="6fea2-113">To be able to take action through advanced hunting, you need a role in Microsoft Defender for Endpoint with [permissions to submit remediation actions on devices](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="6fea2-114">Se você não puder tomar uma ação, contate um administrador global sobre como obter a seguinte permissão:</span><span class="sxs-lookup"><span data-stu-id="6fea2-114">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="6fea2-115">*Ações de correção ativas > Ameaças e Gerenciamento de Vulnerabilidades - Tratamento de correção*</span><span class="sxs-lookup"><span data-stu-id="6fea2-115">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="6fea2-116">Tomar várias ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="6fea2-116">Take various actions on devices</span></span>
<span data-ttu-id="6fea2-117">Você pode tomar as seguintes ações em dispositivos identificados pela `DeviceId` coluna em seus resultados de consulta:</span><span class="sxs-lookup"><span data-stu-id="6fea2-117">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="6fea2-118">Isolar dispositivos afetados para conter uma infecção ou impedir que os ataques se movem lateralmente</span><span class="sxs-lookup"><span data-stu-id="6fea2-118">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="6fea2-119">Coletar pacote de investigação para obter mais informações forenses</span><span class="sxs-lookup"><span data-stu-id="6fea2-119">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="6fea2-120">Executar uma verificação antivírus para encontrar e remover ameaças usando as atualizações mais recentes de inteligência de segurança</span><span class="sxs-lookup"><span data-stu-id="6fea2-120">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="6fea2-121">Inicie uma investigação automatizada para verificar e remediar ameaças no dispositivo e, possivelmente, em outros dispositivos afetados</span><span class="sxs-lookup"><span data-stu-id="6fea2-121">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="6fea2-122">Restringir a execução de aplicativos somente a arquivos executáveis assinados pela Microsoft, impedindo atividades de ameaças subsequentes por meio de malware ou outros executáveis não-confiança</span><span class="sxs-lookup"><span data-stu-id="6fea2-122">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="6fea2-123">Para saber mais sobre como essas ações de resposta são executadas por meio do Microsoft Defender para Ponto de Extremidade, [leia sobre ações de resposta em dispositivos](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span><span class="sxs-lookup"><span data-stu-id="6fea2-123">To learn more about how these response actions are performed through Microsoft Defender for Endpoint, [read about response actions on devices](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="6fea2-124">Arquivos de quarentena</span><span class="sxs-lookup"><span data-stu-id="6fea2-124">Quarantine files</span></span>
<span data-ttu-id="6fea2-125">Você pode implantar a *ação de* quarentena em arquivos para que eles sejam automaticamente colocados em quarentena quando encontrados.</span><span class="sxs-lookup"><span data-stu-id="6fea2-125">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="6fea2-126">Ao selecionar essa ação, você pode escolher entre as seguintes colunas para identificar quais arquivos em sua consulta resulta em quarentena:</span><span class="sxs-lookup"><span data-stu-id="6fea2-126">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="6fea2-127">`SHA1` — Nas tabelas de busca mais avançadas, este é o SHA-1 do arquivo que foi afetado pela ação gravada.</span><span class="sxs-lookup"><span data-stu-id="6fea2-127">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="6fea2-128">Por exemplo, se um arquivo foi copiado, esse seria o arquivo copiado.</span><span class="sxs-lookup"><span data-stu-id="6fea2-128">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="6fea2-129">`InitiatingProcessSHA1` — Nas tabelas de busca mais avançadas, esse é o arquivo responsável por iniciar a ação gravada.</span><span class="sxs-lookup"><span data-stu-id="6fea2-129">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="6fea2-130">Por exemplo, se um processo filho foi lançado, esse seria o processo pai.</span><span class="sxs-lookup"><span data-stu-id="6fea2-130">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="6fea2-131">`SHA256` — Esse é o equivalente sha-256 do arquivo identificado pela `SHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="6fea2-131">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="6fea2-132">`InitiatingProcessSHA256` — Esse é o equivalente sha-256 do arquivo identificado pela `InitiatingProcessSHA1` coluna.</span><span class="sxs-lookup"><span data-stu-id="6fea2-132">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="6fea2-133">Para saber mais sobre como as ações de quarentena são tomadas e como os arquivos podem ser restaurados, [leia sobre ações de resposta em arquivos](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span><span class="sxs-lookup"><span data-stu-id="6fea2-133">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="6fea2-134">Para localizar arquivos e colocar em quarentena, os resultados da consulta também devem incluir `DeviceId` valores como identificadores de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6fea2-134">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="6fea2-135">Tomar medidas</span><span class="sxs-lookup"><span data-stu-id="6fea2-135">Take action</span></span>
<span data-ttu-id="6fea2-136">Para tomar qualquer uma das ações descritas, selecione um ou mais registros nos resultados da consulta e selecione **Tomar ações**.</span><span class="sxs-lookup"><span data-stu-id="6fea2-136">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="6fea2-137">Um assistente o guiará pelo processo de seleção e, em seguida, enviará suas ações preferenciais.</span><span class="sxs-lookup"><span data-stu-id="6fea2-137">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![Imagem do registro selecionado com painel para inspecionar o registro](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="6fea2-139">Revisar ações realizadas</span><span class="sxs-lookup"><span data-stu-id="6fea2-139">Review actions taken</span></span>
<span data-ttu-id="6fea2-140">Cada ação é registrada individualmente no centro [de](m365d-action-center.md) ações em **Histórico do Centro** de Ações (  >   [security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span><span class="sxs-lookup"><span data-stu-id="6fea2-140">Each action is individually recorded in the [action center](m365d-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="6fea2-141">Vá para o centro de ações para verificar o status de cada ação.</span><span class="sxs-lookup"><span data-stu-id="6fea2-141">Go to the action center to check the status of each action.</span></span>
 
>[!NOTE]
><span data-ttu-id="6fea2-142">Algumas tabelas neste artigo podem não estar disponíveis no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="6fea2-142">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="6fea2-143">[A Microsoft 365 Defender para](m365d-enable.md) procurar ameaças usando mais fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="6fea2-143">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="6fea2-144">Você pode mover seus fluxos de trabalho de busca avançados do Microsoft Defender para o Endpoint para o Microsoft 365 Defender seguindo as etapas em Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de [Extremidade.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="6fea2-144">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6fea2-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6fea2-145">Related topics</span></span>
- [<span data-ttu-id="6fea2-146">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="6fea2-146">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="6fea2-147">Aprender a linguagem de consulta</span><span class="sxs-lookup"><span data-stu-id="6fea2-147">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="6fea2-148">Trabalhar com os resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="6fea2-148">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="6fea2-149">Compreender o esquema</span><span class="sxs-lookup"><span data-stu-id="6fea2-149">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="6fea2-150">Visão geral do Centro de Ações</span><span class="sxs-lookup"><span data-stu-id="6fea2-150">Action center overview</span></span>](m365d-action-center.md)
