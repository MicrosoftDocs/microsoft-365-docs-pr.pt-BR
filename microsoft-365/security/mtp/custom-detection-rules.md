---
title: Criar e gerenciar regras de detecção personalizadas no Microsoft Threat Protection
description: Saiba como criar e gerenciar regras de detecções personalizadas com base em consultas de busca avançada
keywords: caça avançada, busca de ameaças, caça à Cyber Threat, proteção contra ameaças da Microsoft, Microsoft 365, MTP, M365, pesquisa, consulta, telemetria, detecções personalizadas, regras, esquema, Kusto, Microsoft 365, proteção contra ameaças da Microsoft, RBAC, permissões, Microsoft defender ATP
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
ms.openlocfilehash: cdfc23f34d90c9d725ec6fb314728553a987c025
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034859"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="f2c53-104">Criar e gerenciar regras de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="f2c53-104">Create and manage custom detections rules</span></span>

<span data-ttu-id="f2c53-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="f2c53-105">**Applies to:**</span></span>
- <span data-ttu-id="f2c53-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="f2c53-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f2c53-107">Regras de detecção personalizadas criadas a partir de consultas de [busca avançada](advanced-hunting-overview.md) permitem monitorar proativamente vários eventos e Estados do sistema, incluindo a suspeita de falha na atividade e os pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="f2c53-107">Custom detection rules built from [Advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="f2c53-108">Você pode defini-los para executar em intervalos regulares, gerar alertas e realizar ações de resposta sempre que houver correspondências.</span><span class="sxs-lookup"><span data-stu-id="f2c53-108">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="f2c53-109">Permissões necessárias para o gerenciamento de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="f2c53-109">Required permissions for managing custom detections</span></span>

<span data-ttu-id="f2c53-110">Para gerenciar detecções personalizadas, você precisa ter uma destas funções:</span><span class="sxs-lookup"><span data-stu-id="f2c53-110">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="f2c53-111">**Administrador** de segurança — a função Administrador de segurança ou administrador de segurança é uma [função do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para gerenciar várias configurações de segurança no centro de segurança do Microsoft 365 e vários portais e serviços.</span><span class="sxs-lookup"><span data-stu-id="f2c53-111">**Security administrator** — the security administrator or security admin role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing various security settings in Microsoft 365 security center and various portals and services.</span></span>

- <span data-ttu-id="f2c53-112">**Operador de segurança** — a função do operador de segurança é uma [função do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) para gerenciar alertas e tem acesso global somente leitura em recursos relacionados à segurança, incluindo todas as informações no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f2c53-112">**Security operator** —  the security operator role is an [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) for managing alerts and has global read-only access on security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="f2c53-113">Essa função é suficiente para gerenciar detecções personalizadas somente se o controle de acesso baseado em função (RBAC) estiver desativado no Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f2c53-113">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="f2c53-114">Se o RBAC estiver configurado, você também precisará da permissão **gerenciar configurações de segurança** para o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="f2c53-114">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="f2c53-115">Para gerenciar as permissões necessárias, um **administrador global** pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f2c53-115">To manage required permissions, a **global administrator** can do the following:</span></span>

- <span data-ttu-id="f2c53-116">Atribua a função de **administrador de segurança** ou **operador de segurança** no [centro de administração do Microsoft 365](https://admin.microsoft.com/) em **funções** > **administrador de segurança**.</span><span class="sxs-lookup"><span data-stu-id="f2c53-116">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="f2c53-117">Verifique as configurações RBAC do Microsoft defender ATP [na central de segurança do Microsoft defender](https://securitycenter.windows.com/) em**funções**de**permissões** > de **configurações** > .</span><span class="sxs-lookup"><span data-stu-id="f2c53-117">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="f2c53-118">Selecione a função correspondente para atribuir a permissão **gerenciar configurações de segurança** .</span><span class="sxs-lookup"><span data-stu-id="f2c53-118">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="f2c53-119">Para gerenciar detecções personalizadas, os **operadores de segurança** precisarão da permissão **gerenciar configurações de segurança** no Microsoft defender ATP se o RBAC estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="f2c53-119">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="f2c53-120">Criar uma regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="f2c53-120">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="f2c53-121">1. Prepare a consulta.</span><span class="sxs-lookup"><span data-stu-id="f2c53-121">1. Prepare the query.</span></span>

<span data-ttu-id="f2c53-122">No centro de segurança do Microsoft 365, vá para a **busca avançada** e selecione uma consulta existente ou crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="f2c53-122">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="f2c53-123">Ao usar uma nova consulta, execute a consulta para identificar erros e compreender possíveis resultados.</span><span class="sxs-lookup"><span data-stu-id="f2c53-123">When using a new query, run the query to identify errors and understand possible results.</span></span>

#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="f2c53-124">Colunas obrigatórias nos resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="f2c53-124">Required columns in the query results</span></span>
<span data-ttu-id="f2c53-125">Para criar uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="f2c53-125">To create a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- <span data-ttu-id="f2c53-126">Uma das seguintes colunas de dispositivo, usuário ou caixa de correio:</span><span class="sxs-lookup"><span data-stu-id="f2c53-126">One of the following device, user, or mailbox columns:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="f2c53-127">`SenderFromAddress`(remetente de envelope ou endereço do caminho de retorno)</span><span class="sxs-lookup"><span data-stu-id="f2c53-127">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="f2c53-128">`SenderMailFromAddress`(endereço do remetente exibido pelo cliente de email)</span><span class="sxs-lookup"><span data-stu-id="f2c53-128">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountSid`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`
>[!NOTE]
><span data-ttu-id="f2c53-129">O suporte para entidades adicionais será adicionado à medida que novas tabelas forem adicionadas ao [esquema de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f2c53-129">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="f2c53-130">Consultas simples, como as que não usam o `project` operador or `summarize` para personalizar ou agregar resultados, normalmente retornam essas colunas comuns.</span><span class="sxs-lookup"><span data-stu-id="f2c53-130">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="f2c53-131">Há várias maneiras de garantir que consultas mais complexas retornem essas colunas.</span><span class="sxs-lookup"><span data-stu-id="f2c53-131">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="f2c53-132">Por exemplo, se você preferir agregar e contar por entidade em uma coluna como `DeviceId`, você ainda pode retornar `Timestamp` ao obtê-lo do evento mais recente envolvendo cada exclusivo. `DeviceId`</span><span class="sxs-lookup"><span data-stu-id="f2c53-132">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="f2c53-133">A consulta de exemplo abaixo conta o número de máquinas exclusivas (`DeviceId`) com detecções de antivírus e usa essa contagem para localizar apenas as máquinas com mais de cinco detecções.</span><span class="sxs-lookup"><span data-stu-id="f2c53-133">The sample query below counts the number of unique machines (`DeviceId`) with antivirus detections and uses this count to find only the machines with more than five detections.</span></span> <span data-ttu-id="f2c53-134">Para retornar o mais `Timestamp`recente, ele usa `summarize` o operador com `arg_max` a função.</span><span class="sxs-lookup"><span data-stu-id="f2c53-134">To return the latest `Timestamp`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize Timestamp = max(Timestamp), count() by DeviceId
| where count_ > 5
```
### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="f2c53-135">2. Crie uma nova regra e forneça detalhes do alerta.</span><span class="sxs-lookup"><span data-stu-id="f2c53-135">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="f2c53-136">Com a consulta no editor de consultas, selecione **criar regra de detecção** e especifique os seguintes detalhes de alerta:</span><span class="sxs-lookup"><span data-stu-id="f2c53-136">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="f2c53-137">**Nome da detecção** — nome da regra de detecção</span><span class="sxs-lookup"><span data-stu-id="f2c53-137">**Detection name** — name of the detection rule</span></span>
- <span data-ttu-id="f2c53-138">**Frequência** – intervalo para executar a consulta e executar a ação.</span><span class="sxs-lookup"><span data-stu-id="f2c53-138">**Frequency** — interval for running the query and taking action.</span></span> [<span data-ttu-id="f2c53-139">Veja orientações adicionais abaixo</span><span class="sxs-lookup"><span data-stu-id="f2c53-139">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="f2c53-140">**Título do alerta** — título exibido com alertas disparados pela regra</span><span class="sxs-lookup"><span data-stu-id="f2c53-140">**Alert title** — title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="f2c53-141">**Severidade** — risco potencial do componente ou atividade identificado pela regra</span><span class="sxs-lookup"><span data-stu-id="f2c53-141">**Severity** — potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="f2c53-142">**Categoria** — componente de ameaça ou atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="f2c53-142">**Category** — threat component or activity identified by the rule</span></span>
- <span data-ttu-id="f2c53-143">**Mitre ATT&Reck Techniques** — uma ou mais técnicas de ataque identificadas pela regra conforme documentadas na [estrutura Mitre ATT&CK](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="f2c53-143">**MITRE ATT&CK techniques** — one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/)</span></span>
- <span data-ttu-id="f2c53-144">**Descrição** — mais informações sobre o componente ou atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="f2c53-144">**Description** — more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="f2c53-145">**Ações recomendadas** — ações adicionais que os respondentes podem executar em resposta a um alerta</span><span class="sxs-lookup"><span data-stu-id="f2c53-145">**Recommended actions** — additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="f2c53-146">Frequência da regra</span><span class="sxs-lookup"><span data-stu-id="f2c53-146">Rule frequency</span></span>
<span data-ttu-id="f2c53-147">Quando salvo, uma regra de detecção personalizada nova ou editada é executada imediatamente e verifica se há correspondências dos últimos 30 dias de dados.</span><span class="sxs-lookup"><span data-stu-id="f2c53-147">When saved, a new or edited custom detection rule immediately runs and checks for matches from  the past 30 days of data.</span></span> <span data-ttu-id="f2c53-148">A regra então é executada novamente em intervalos fixos e durações de lookback com base na frequência que você escolher:</span><span class="sxs-lookup"><span data-stu-id="f2c53-148">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="f2c53-149">A **cada 24 horas** — é executado a cada 24 horas, verificando os dados dos últimos 30 dias</span><span class="sxs-lookup"><span data-stu-id="f2c53-149">**Every 24 hours** — runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="f2c53-150">A **cada 12 horas** — é executado a cada 12 horas, verificando os dados das últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="f2c53-150">**Every 12 hours** — runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="f2c53-151">A **cada 3 horas** — é executado a cada 3 horas, verificando os dados das últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="f2c53-151">**Every 3 hours** — runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="f2c53-152">A **cada hora** — é executado a cada hora, verificando os dados das últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="f2c53-152">**Every hour** — runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="f2c53-153">Selecione a frequência que corresponde à aparência que você deseja monitorar as detecções e considere a capacidade da sua organização para responder aos alertas.</span><span class="sxs-lookup"><span data-stu-id="f2c53-153">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="f2c53-154">3. escolha as entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="f2c53-154">3. Choose the impacted entities.</span></span>
<span data-ttu-id="f2c53-155">Identifique as colunas nos resultados de consulta onde você espera encontrar a entidade principal afetada ou afetada.</span><span class="sxs-lookup"><span data-stu-id="f2c53-155">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="f2c53-156">Por exemplo, uma consulta pode retornar endereços de`SenderFromAddress` remetente `SenderMailFromAddress`(ou) e`RecipientEmailAddress`destinatário ().</span><span class="sxs-lookup"><span data-stu-id="f2c53-156">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="f2c53-157">Identificar quais dessas colunas representam a principal entidade afetada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.</span><span class="sxs-lookup"><span data-stu-id="f2c53-157">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="f2c53-158">Você pode selecionar apenas uma coluna para cada tipo de entidade (caixa de correio, usuário ou dispositivo).</span><span class="sxs-lookup"><span data-stu-id="f2c53-158">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="f2c53-159">As colunas que não são retornadas pela consulta não podem ser selecionadas.</span><span class="sxs-lookup"><span data-stu-id="f2c53-159">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions-on-files-or-machines"></a><span data-ttu-id="f2c53-160">4. Especifique ações em arquivos ou máquinas.</span><span class="sxs-lookup"><span data-stu-id="f2c53-160">4. Specify actions on files or machines.</span></span>
<span data-ttu-id="f2c53-161">Sua regra de detecção personalizada pode executar automaticamente ações em arquivos ou máquinas que são retornadas pela consulta.</span><span class="sxs-lookup"><span data-stu-id="f2c53-161">Your custom detection rule can automatically take actions on files or machines that are returned by the query.</span></span>

#### <a name="actions-on-machines"></a><span data-ttu-id="f2c53-162">Ações em máquinas</span><span class="sxs-lookup"><span data-stu-id="f2c53-162">Actions on machines</span></span>
<span data-ttu-id="f2c53-163">Essas ações são aplicadas às máquinas na `DeviceId` coluna dos resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="f2c53-163">These actions are applied to machines in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="f2c53-164">**Isolate Machine** — usa o Microsoft defender ATP para aplicar o isolamento completo da rede, impedindo o computador de se conectar a qualquer aplicativo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="f2c53-164">**Isolate machine** — uses Microsoft Defender ATP to apply full network isolation, preventing the machine from connecting to any application or service.</span></span> [<span data-ttu-id="f2c53-165">Saiba mais sobre o isolamento de máquina ATP do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="f2c53-165">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-machines-from-the-network)
- <span data-ttu-id="f2c53-166">**Coletar pacote de investigação** — coleta informações de máquina em um arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="f2c53-166">**Collect investigation package** — collects machine information in a ZIP file.</span></span> [<span data-ttu-id="f2c53-167">Saiba mais sobre o pacote de investigação ATP do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="f2c53-167">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-machines)
- <span data-ttu-id="f2c53-168">**Executar verificação antivírus** — realiza uma verificação completa do Windows Defender antivírus na máquina</span><span class="sxs-lookup"><span data-stu-id="f2c53-168">**Run antivirus scan** — performs a full Windows Defender Antivirus scan on the machine</span></span>
- <span data-ttu-id="f2c53-169">**Iniciar investigação** — inicia uma [investigação automatizada](mtp-autoir.md) no computador</span><span class="sxs-lookup"><span data-stu-id="f2c53-169">**Initiate investigation** — initiates an [automated investigation](mtp-autoir.md) on the machine</span></span>

#### <a name="actions-on-files"></a><span data-ttu-id="f2c53-170">Ações em arquivos</span><span class="sxs-lookup"><span data-stu-id="f2c53-170">Actions on files</span></span>
<span data-ttu-id="f2c53-171">Quando selecionada, a ação de **arquivo de quarentena** é executada nos arquivos da `SHA1`coluna `InitiatingProcessSHA1`, `SHA256`, ou `InitiatingProcessSHA256` dos resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="f2c53-171">When selected, the **Quarantine file** action is taken on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="f2c53-172">Esta ação exclui o arquivo de seu local atual e coloca uma cópia em quarentena.</span><span class="sxs-lookup"><span data-stu-id="f2c53-172">This action deletes the file from its current location and places a copy in quarantine.</span></span>

> [!NOTE]
> <span data-ttu-id="f2c53-173">A ação de permissão ou bloqueio para regras de detecção personalizada atualmente não é suportada no Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="f2c53-173">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="f2c53-174">5. defina o escopo da regra.</span><span class="sxs-lookup"><span data-stu-id="f2c53-174">5. Set the rule scope.</span></span>
<span data-ttu-id="f2c53-175">Defina o escopo para especificar quais dispositivos são cobertos pela regra.</span><span class="sxs-lookup"><span data-stu-id="f2c53-175">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="f2c53-176">O escopo influencia as regras que verificam dispositivos e não afetam as regras que verificam apenas caixas de correio e contas de usuário e identidades.</span><span class="sxs-lookup"><span data-stu-id="f2c53-176">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="f2c53-177">Ao configurar o escopo, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="f2c53-177">When setting the scope, you can select:</span></span>

- <span data-ttu-id="f2c53-178">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="f2c53-178">All devices</span></span>
- <span data-ttu-id="f2c53-179">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="f2c53-179">Specific device groups</span></span>

<span data-ttu-id="f2c53-180">Somente os dados de dispositivos no escopo serão consultados.</span><span class="sxs-lookup"><span data-stu-id="f2c53-180">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="f2c53-181">Além disso, as ações serão executadas apenas nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="f2c53-181">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="f2c53-182">6. revise e ative a regra.</span><span class="sxs-lookup"><span data-stu-id="f2c53-182">6. Review and turn on the rule.</span></span>
<span data-ttu-id="f2c53-183">Após a revisão da regra, clique em **criar** para salvá-la.</span><span class="sxs-lookup"><span data-stu-id="f2c53-183">After reviewing the rule, click **Create** to save it.</span></span> <span data-ttu-id="f2c53-184">A regra de detecção personalizada é executada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f2c53-184">The custom detection rule immediately runs.</span></span> <span data-ttu-id="f2c53-185">Ele é executado novamente com base na frequência configurada para verificar correspondências, gerar alertas e realizar ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="f2c53-185">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="f2c53-186">Gerenciar regras de detecção personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="f2c53-186">Manage existing custom detection rules</span></span>
<span data-ttu-id="f2c53-187">Você pode exibir a lista de regras de detecção personalizadas existentes, verificar suas execuções anteriores e revisar os alertas que eles acionaram.</span><span class="sxs-lookup"><span data-stu-id="f2c53-187">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="f2c53-188">Você também pode executar uma regra por demanda e modificá-la.</span><span class="sxs-lookup"><span data-stu-id="f2c53-188">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="f2c53-189">Exibir regras existentes</span><span class="sxs-lookup"><span data-stu-id="f2c53-189">View existing rules</span></span>

<span data-ttu-id="f2c53-190">Para exibir todas as regras de detecção personalizadas existentes, navegue até **buscar** > **detecções personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="f2c53-190">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="f2c53-191">A página lista todas as regras com as seguintes informações de execução:</span><span class="sxs-lookup"><span data-stu-id="f2c53-191">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="f2c53-192">**Última execução** — quando uma regra foi executada pela última vez para verificar correspondências de consulta e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="f2c53-192">**Last run** — when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="f2c53-193">**Status da última execução** — se uma regra foi executada com êxito</span><span class="sxs-lookup"><span data-stu-id="f2c53-193">**Last run status** — whether a rule ran successfully</span></span>
- <span data-ttu-id="f2c53-194">**Próxima execução** : a próxima execução agendada</span><span class="sxs-lookup"><span data-stu-id="f2c53-194">**Next run** — the next scheduled run</span></span>
- <span data-ttu-id="f2c53-195">**Status** — se uma regra foi ativada ou desativada</span><span class="sxs-lookup"><span data-stu-id="f2c53-195">**Status** — whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="f2c53-196">Exibir detalhes da regra, modificar regra e executar regra</span><span class="sxs-lookup"><span data-stu-id="f2c53-196">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="f2c53-197">Para exibir informações abrangentes sobre uma regra de detecção personalizada, selecione o nome da regra na lista de regras em**detecções personalizadas**de **busca** > .</span><span class="sxs-lookup"><span data-stu-id="f2c53-197">To view comprehensive information about a custom detection rule, select the name of rule from the list of rules in **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="f2c53-198">Isso abre uma página sobre a regra de detecção personalizada com informações gerais sobre a regra, incluindo os detalhes do alerta, o status de execução e o escopo.</span><span class="sxs-lookup"><span data-stu-id="f2c53-198">This opens a page about the custom detection rule with general information about the rule, including the details of the alert, run status, and scope.</span></span> <span data-ttu-id="f2c53-199">Também fornece a lista de alertas disparados e ações disparadas.</span><span class="sxs-lookup"><span data-stu-id="f2c53-199">It also provides the list of triggered alerts and triggered actions.</span></span>

<span data-ttu-id="f2c53-200">![Página de detalhes da regra de detecção personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="f2c53-200">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="f2c53-201">*Detalhes da regra de detecção personalizada*</span><span class="sxs-lookup"><span data-stu-id="f2c53-201">*Custom detection rule details*</span></span>

<span data-ttu-id="f2c53-202">Você também pode executar as seguintes ações na regra nesta página:</span><span class="sxs-lookup"><span data-stu-id="f2c53-202">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="f2c53-203">**Executar** — execute a regra imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f2c53-203">**Run** — run the rule immediately.</span></span> <span data-ttu-id="f2c53-204">Isso também redefine o intervalo para a próxima execução.</span><span class="sxs-lookup"><span data-stu-id="f2c53-204">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="f2c53-205">**Editar** — modificar a regra sem alterar a consulta</span><span class="sxs-lookup"><span data-stu-id="f2c53-205">**Edit** — modify the rule without changing the query</span></span>
- <span data-ttu-id="f2c53-206">**Modificar consulta** — editar a consulta em busca avançada</span><span class="sxs-lookup"><span data-stu-id="f2c53-206">**Modify query** — edit the query in advanced hunting</span></span>
- <span data-ttu-id="f2c53-207">**Ativar**desativar, habilitar a regra ou impedir que ela seja executada**Turn off**  / </span><span class="sxs-lookup"><span data-stu-id="f2c53-207">**Turn on** / **Turn off** — enable the rule or stop it from running</span></span>
- <span data-ttu-id="f2c53-208">**Excluir** — desativar a regra e removê-la</span><span class="sxs-lookup"><span data-stu-id="f2c53-208">**Delete** — turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="f2c53-209">Exibir e gerenciar alertas disparados</span><span class="sxs-lookup"><span data-stu-id="f2c53-209">View and manage triggered alerts</span></span>

<span data-ttu-id="f2c53-210">Na tela detalhes da regra (**busca** > de**detecções** > personalizadas **[nome da regra]**), acesse **alertas** disparados para exibir a lista de alertas gerados por correspondências com a regra.</span><span class="sxs-lookup"><span data-stu-id="f2c53-210">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered alerts** to view the list of alerts generated by matches to the rule.</span></span> <span data-ttu-id="f2c53-211">Selecione um alerta para exibir informações detalhadas sobre esse alerta e realizar as seguintes ações no alerta:</span><span class="sxs-lookup"><span data-stu-id="f2c53-211">Select an alert to view detailed information about that alert and take the following actions on that alert:</span></span>

- <span data-ttu-id="f2c53-212">Gerenciar o alerta definindo seu status e classificação (alerta verdadeiro ou falso)</span><span class="sxs-lookup"><span data-stu-id="f2c53-212">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="f2c53-213">Vincular o alerta a um incidente</span><span class="sxs-lookup"><span data-stu-id="f2c53-213">Link the alert to an incident</span></span>
- <span data-ttu-id="f2c53-214">Executar a consulta que disparou o alerta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="f2c53-214">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="f2c53-215">Ações de revisão</span><span class="sxs-lookup"><span data-stu-id="f2c53-215">Review actions</span></span>
<span data-ttu-id="f2c53-216">Na tela detalhes da regra (**busca** > de**detecções** > personalizadas **[nome da regra]**), vá para **ações** disparadas para exibir a lista de ações executadas com base em correspondências com a regra.</span><span class="sxs-lookup"><span data-stu-id="f2c53-216">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions** to view the list of actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="f2c53-217">Para exibir rapidamente as informações e executar ações em um item em uma tabela, use a coluna seleção [&#10003;] à esquerda da tabela.</span><span class="sxs-lookup"><span data-stu-id="f2c53-217">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="f2c53-218">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="f2c53-218">Related topic</span></span>
- [<span data-ttu-id="f2c53-219">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="f2c53-219">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="f2c53-220">Visão geral da caça avançada</span><span class="sxs-lookup"><span data-stu-id="f2c53-220">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f2c53-221">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="f2c53-221">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
