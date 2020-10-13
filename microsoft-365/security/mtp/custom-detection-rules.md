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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 85bf980f87b640df0f3767294b3c5f2059ba0ac6
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430854"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="c645d-104">Criar e gerenciar regras de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="c645d-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c645d-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c645d-105">**Applies to:**</span></span>
- <span data-ttu-id="c645d-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c645d-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c645d-107">Regras de detecção personalizadas são regras que você pode projetar e ajustar usando consultas de [busca avançada](advanced-hunting-overview.md) .</span><span class="sxs-lookup"><span data-stu-id="c645d-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="c645d-108">Essas regras permitem monitorar de forma proativa vários eventos e Estados do sistema, incluindo a suspeita de atividade e os pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="c645d-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="c645d-109">Você pode defini-los para executar em intervalos regulares, gerar alertas e realizar ações de resposta sempre que houver correspondências.</span><span class="sxs-lookup"><span data-stu-id="c645d-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="c645d-110">Permissões necessárias para o gerenciamento de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="c645d-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="c645d-111">Para gerenciar detecções personalizadas, você precisa ter uma destas funções:</span><span class="sxs-lookup"><span data-stu-id="c645d-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="c645d-112">**Administrador de segurança**— os usuários com essa [função do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar configurações de segurança no centro de segurança do Microsoft 365 e outros portais e serviços.</span><span class="sxs-lookup"><span data-stu-id="c645d-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="c645d-113">**Operador de segurança**— os usuários com essa [função do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar alertas e ter acesso somente leitura global a recursos relacionados à segurança, incluindo todas as informações no centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c645d-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="c645d-114">Essa função é suficiente para gerenciar detecções personalizadas somente se o controle de acesso baseado em função (RBAC) estiver desativado no Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c645d-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender ATP.</span></span> <span data-ttu-id="c645d-115">Se o RBAC estiver configurado, você também precisará da permissão **gerenciar configurações de segurança** para o Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c645d-115">If you have RBAC configured, you also need the **manage security settings** permission for Microsoft Defender ATP.</span></span>

<span data-ttu-id="c645d-116">Para gerenciar as permissões necessárias, um **administrador global** pode:</span><span class="sxs-lookup"><span data-stu-id="c645d-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="c645d-117">Atribua a função de **administrador de segurança** ou **operador de segurança** no centro de [Administração do Microsoft 365](https://admin.microsoft.com/) em **funções**  >  **administrador de segurança**.</span><span class="sxs-lookup"><span data-stu-id="c645d-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="c645d-118">Verifique as configurações RBAC do Microsoft defender ATP na [central de segurança do Microsoft defender](https://securitycenter.windows.com/) em funções de permissões de **configurações**  >  **Permissions**  >  **Roles**.</span><span class="sxs-lookup"><span data-stu-id="c645d-118">Check RBAC settings for Microsoft Defender ATP in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="c645d-119">Selecione a função correspondente para atribuir a permissão **gerenciar configurações de segurança** .</span><span class="sxs-lookup"><span data-stu-id="c645d-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="c645d-120">Para gerenciar detecções personalizadas, os **operadores de segurança** precisarão da permissão **gerenciar configurações de segurança** no Microsoft defender ATP se o RBAC estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="c645d-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender ATP if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="c645d-121">Criar uma regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="c645d-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="c645d-122">1. Prepare a consulta.</span><span class="sxs-lookup"><span data-stu-id="c645d-122">1. Prepare the query.</span></span>

<span data-ttu-id="c645d-123">No centro de segurança do Microsoft 365, vá para a **busca avançada** e selecione uma consulta existente ou crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="c645d-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="c645d-124">Ao usar uma nova consulta, execute a consulta para identificar erros e compreender possíveis resultados.</span><span class="sxs-lookup"><span data-stu-id="c645d-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c645d-125">Para impedir que o serviço retorne muitos alertas, cada regra é limitada a gerar apenas 100 alertas sempre que ele é executado.</span><span class="sxs-lookup"><span data-stu-id="c645d-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="c645d-126">Antes de criar uma regra, ajuste sua consulta para evitar o alerta de atividade normal e diária.</span><span class="sxs-lookup"><span data-stu-id="c645d-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="c645d-127">Colunas obrigatórias nos resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="c645d-127">Required columns in the query results</span></span>
<span data-ttu-id="c645d-128">Para criar uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="c645d-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="c645d-129">`Timestamp`– usado para definir o carimbo de data/hora para alertas gerados</span><span class="sxs-lookup"><span data-stu-id="c645d-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="c645d-130">`ReportId`— permite pesquisas para os registros originais</span><span class="sxs-lookup"><span data-stu-id="c645d-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="c645d-131">Uma das seguintes colunas que identificam dispositivos, usuários ou caixas de correio específicas:</span><span class="sxs-lookup"><span data-stu-id="c645d-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="c645d-132">`SenderFromAddress` (endereço de remetente ou Return-Path)</span><span class="sxs-lookup"><span data-stu-id="c645d-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="c645d-133">`SenderMailFromAddress` (endereço do remetente exibido pelo cliente de email)</span><span class="sxs-lookup"><span data-stu-id="c645d-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="c645d-134">O suporte para entidades adicionais será adicionado à medida que novas tabelas forem adicionadas ao [esquema de busca avançada](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c645d-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="c645d-135">Consultas simples, como as que não usam o `project` operador or `summarize` para personalizar ou agregar resultados, normalmente retornam essas colunas comuns.</span><span class="sxs-lookup"><span data-stu-id="c645d-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="c645d-136">Há várias maneiras de garantir que consultas mais complexas retornem essas colunas.</span><span class="sxs-lookup"><span data-stu-id="c645d-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="c645d-137">Por exemplo, se você preferir agregar e contar por entidade em uma coluna como `DeviceId` , você ainda pode retornar `Timestamp` e `ReportId` obtendo-o do evento mais recente envolvendo cada exclusivo `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="c645d-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="c645d-138">A consulta de exemplo abaixo conta o número de dispositivos exclusivos ( `DeviceId` ) com detecções de antivírus e usa essa contagem para localizar apenas os dispositivos com mais de cinco detecções.</span><span class="sxs-lookup"><span data-stu-id="c645d-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="c645d-139">Para retornar o mais recente `Timestamp` e o correspondente `ReportId` , ele usa o `summarize` operador com a `arg_max` função.</span><span class="sxs-lookup"><span data-stu-id="c645d-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="c645d-140">Para obter um melhor desempenho de consulta, defina um filtro de tempo que corresponda à sua frequência de execução pretendida para a regra.</span><span class="sxs-lookup"><span data-stu-id="c645d-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="c645d-141">Como a execução menos frequente é a _cada 24 horas_, a filtragem do dia passado abrange todos os novos dados.</span><span class="sxs-lookup"><span data-stu-id="c645d-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="c645d-142">2. Crie uma nova regra e forneça detalhes do alerta.</span><span class="sxs-lookup"><span data-stu-id="c645d-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="c645d-143">Com a consulta no editor de consultas, selecione **criar regra de detecção** e especifique os seguintes detalhes de alerta:</span><span class="sxs-lookup"><span data-stu-id="c645d-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="c645d-144">**Nome da detecção**— nome da regra de detecção</span><span class="sxs-lookup"><span data-stu-id="c645d-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="c645d-145">**Frequência**– intervalo para executar a consulta e executar a ação.</span><span class="sxs-lookup"><span data-stu-id="c645d-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="c645d-146">Veja orientações adicionais abaixo</span><span class="sxs-lookup"><span data-stu-id="c645d-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="c645d-147">**Título do alerta**— título exibido com alertas disparados pela regra</span><span class="sxs-lookup"><span data-stu-id="c645d-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="c645d-148">**Severidade**— risco potencial do componente ou atividade identificado pela regra</span><span class="sxs-lookup"><span data-stu-id="c645d-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="c645d-149">**Categoria**— componente de ameaça ou atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="c645d-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="c645d-150">**Mitre ATT&Reck Techniques**— uma ou mais técnicas de ataque identificadas pela regra conforme documentadas na [estrutura Mitre ATT&CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="c645d-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="c645d-151">Esta seção está oculta para determinadas categorias de alerta, incluindo malware, ransomware, atividade suspeita e software indesejado</span><span class="sxs-lookup"><span data-stu-id="c645d-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="c645d-152">**Descrição**— mais informações sobre o componente ou atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="c645d-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="c645d-153">**Ações recomendadas**— ações adicionais que os respondentes podem executar em resposta a um alerta</span><span class="sxs-lookup"><span data-stu-id="c645d-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="c645d-154">Frequência da regra</span><span class="sxs-lookup"><span data-stu-id="c645d-154">Rule frequency</span></span>
<span data-ttu-id="c645d-155">Quando você salva ou edita uma nova regra, ela é executada e verifica se há correspondências dos últimos 30 dias de dados.</span><span class="sxs-lookup"><span data-stu-id="c645d-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="c645d-156">A regra então é executada novamente em intervalos fixos, aplicando uma duração de lookback com base na frequência que você escolher:</span><span class="sxs-lookup"><span data-stu-id="c645d-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="c645d-157">A **cada 24 horas**— é executado a cada 24 horas, verificando os dados dos últimos 30 dias</span><span class="sxs-lookup"><span data-stu-id="c645d-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="c645d-158">A **cada 12 horas**— é executado a cada 12 horas, verificando os dados das últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="c645d-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="c645d-159">A **cada 3 horas**— é executado a cada 3 horas, verificando os dados das últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="c645d-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="c645d-160">A **cada hora**— é executado a cada hora, verificando os dados das últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="c645d-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="c645d-161">Relacione os filtros de tempo em sua consulta com a duração lookback.</span><span class="sxs-lookup"><span data-stu-id="c645d-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="c645d-162">Os resultados fora da duração do lookback são ignorados.</span><span class="sxs-lookup"><span data-stu-id="c645d-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="c645d-163">Selecione a frequência que corresponde à aparência que você deseja monitorar as detecções.</span><span class="sxs-lookup"><span data-stu-id="c645d-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="c645d-164">Considere a capacidade da sua organização para responder aos alertas.</span><span class="sxs-lookup"><span data-stu-id="c645d-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="c645d-165">3. escolha as entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="c645d-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="c645d-166">Identifique as colunas nos resultados de consulta onde você espera encontrar a entidade principal afetada ou afetada.</span><span class="sxs-lookup"><span data-stu-id="c645d-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="c645d-167">Por exemplo, uma consulta pode retornar endereços de remetente ( `SenderFromAddress` ou `SenderMailFromAddress` ) e destinatário ( `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="c645d-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="c645d-168">Identificar quais dessas colunas representam a principal entidade afetada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.</span><span class="sxs-lookup"><span data-stu-id="c645d-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="c645d-169">Você pode selecionar apenas uma coluna para cada tipo de entidade (caixa de correio, usuário ou dispositivo).</span><span class="sxs-lookup"><span data-stu-id="c645d-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="c645d-170">As colunas que não são retornadas pela consulta não podem ser selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c645d-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="c645d-171">4. Especifique ações.</span><span class="sxs-lookup"><span data-stu-id="c645d-171">4. Specify actions.</span></span>
<span data-ttu-id="c645d-172">Sua regra de detecção personalizada pode realizar ações automaticamente em dispositivos, arquivos ou usuários retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="c645d-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="c645d-173">Ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="c645d-173">Actions on devices</span></span>
<span data-ttu-id="c645d-174">Essas ações são aplicadas a dispositivos na `DeviceId` coluna dos resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="c645d-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="c645d-175">**Isolate Device**— usa o Microsoft defender ATP para aplicar o isolamento completo da rede, impedindo o dispositivo de se conectar a qualquer aplicativo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="c645d-175">**Isolate device**—uses Microsoft Defender ATP to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="c645d-176">Saiba mais sobre o isolamento de máquina ATP do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="c645d-176">Learn more about Microsoft Defender ATP machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="c645d-177">**Coletar pacote de investigação**— coleta informações de dispositivo em um arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="c645d-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="c645d-178">Saiba mais sobre o pacote de investigação ATP do Microsoft defender</span><span class="sxs-lookup"><span data-stu-id="c645d-178">Learn more about the Microsoft Defender ATP investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="c645d-179">**Executar verificação antivírus**— realiza uma verificação completa do Windows Defender antivírus no dispositivo</span><span class="sxs-lookup"><span data-stu-id="c645d-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="c645d-180">**Iniciar investigação**— inicia uma [investigação automatizada](mtp-autoir.md) no dispositivo</span><span class="sxs-lookup"><span data-stu-id="c645d-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="c645d-181">**Restringir a execução do aplicativo**— define restrições no dispositivo para permitir que somente os arquivos assinados com um certificado emitido pela Microsoft sejam executados.</span><span class="sxs-lookup"><span data-stu-id="c645d-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="c645d-182">Saiba mais sobre as restrições de aplicativo com o Microsoft defender ATP</span><span class="sxs-lookup"><span data-stu-id="c645d-182">Learn more about app restrictions with Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="c645d-183">Ações em arquivos</span><span class="sxs-lookup"><span data-stu-id="c645d-183">Actions on files</span></span>
<span data-ttu-id="c645d-184">Quando selecionado, você pode optar por aplicar a ação de **arquivo de quarentena** nos arquivos na `SHA1` coluna,, `InitiatingProcessSHA1` ou nos `SHA256` `InitiatingProcessSHA256` resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="c645d-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="c645d-185">Esta ação exclui o arquivo de seu local atual e coloca uma cópia em quarentena.</span><span class="sxs-lookup"><span data-stu-id="c645d-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="c645d-186">Ações em usuários</span><span class="sxs-lookup"><span data-stu-id="c645d-186">Actions on users</span></span>
<span data-ttu-id="c645d-187">Quando selecionada, a ação **Marcar usuário como comprometido** é executada nos usuários na `AccountObjectId` `InitiatingProcessAccountObjectId` coluna,, ou nos `RecipientObjectId` resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="c645d-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="c645d-188">Esta ação define o nível de risco dos usuários como "alto" no Azure Active Directory, disparando [as políticas de proteção de identidade](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)correspondentes.</span><span class="sxs-lookup"><span data-stu-id="c645d-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="c645d-189">A ação de permissão ou bloqueio para regras de detecção personalizada atualmente não é suportada no Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="c645d-189">The allow or block action for custom detection rules is currently not supported on Microsoft Threat Protection.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="c645d-190">5. defina o escopo da regra.</span><span class="sxs-lookup"><span data-stu-id="c645d-190">5. Set the rule scope.</span></span>
<span data-ttu-id="c645d-191">Defina o escopo para especificar quais dispositivos são cobertos pela regra.</span><span class="sxs-lookup"><span data-stu-id="c645d-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="c645d-192">O escopo influencia as regras que verificam dispositivos e não afetam as regras que verificam apenas caixas de correio e contas de usuário e identidades.</span><span class="sxs-lookup"><span data-stu-id="c645d-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="c645d-193">Ao configurar o escopo, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="c645d-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="c645d-194">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="c645d-194">All devices</span></span>
- <span data-ttu-id="c645d-195">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="c645d-195">Specific device groups</span></span>

<span data-ttu-id="c645d-196">Somente os dados de dispositivos no escopo serão consultados.</span><span class="sxs-lookup"><span data-stu-id="c645d-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="c645d-197">Além disso, as ações serão executadas apenas nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="c645d-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="c645d-198">6. revise e ative a regra.</span><span class="sxs-lookup"><span data-stu-id="c645d-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="c645d-199">Após a revisão da regra, selecione **criar** para salvá-la.</span><span class="sxs-lookup"><span data-stu-id="c645d-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="c645d-200">A regra de detecção personalizada é executada imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c645d-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="c645d-201">Ele é executado novamente com base na frequência configurada para verificar correspondências, gerar alertas e realizar ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="c645d-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="c645d-202">Gerenciar regras de detecção personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="c645d-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="c645d-203">Você pode exibir a lista de regras de detecção personalizadas existentes, verificar suas execuções anteriores e revisar os alertas que eles acionaram.</span><span class="sxs-lookup"><span data-stu-id="c645d-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="c645d-204">Você também pode executar uma regra por demanda e modificá-la.</span><span class="sxs-lookup"><span data-stu-id="c645d-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="c645d-205">Exibir regras existentes</span><span class="sxs-lookup"><span data-stu-id="c645d-205">View existing rules</span></span>

<span data-ttu-id="c645d-206">Para exibir todas as regras de detecção personalizadas existentes, navegue até **buscar**  >  **detecções personalizadas**.</span><span class="sxs-lookup"><span data-stu-id="c645d-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="c645d-207">A página lista todas as regras com as seguintes informações de execução:</span><span class="sxs-lookup"><span data-stu-id="c645d-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="c645d-208">**Última execução**— quando uma regra foi executada pela última vez para verificar correspondências de consulta e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="c645d-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="c645d-209">**Status da última execução**— se uma regra foi executada com êxito</span><span class="sxs-lookup"><span data-stu-id="c645d-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="c645d-210">**Próxima execução**: a próxima execução agendada</span><span class="sxs-lookup"><span data-stu-id="c645d-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="c645d-211">**Status**— se uma regra foi ativada ou desativada</span><span class="sxs-lookup"><span data-stu-id="c645d-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="c645d-212">Exibir detalhes da regra, modificar regra e executar regra</span><span class="sxs-lookup"><span data-stu-id="c645d-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="c645d-213">Para exibir informações abrangentes sobre uma regra de detecção personalizada, **Hunting**vá para  >  **detecções personalizadas** de busca e selecione o nome da regra.</span><span class="sxs-lookup"><span data-stu-id="c645d-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="c645d-214">Em seguida, você pode exibir informações gerais sobre a regra, incluindo o status e o escopo de sua execução.</span><span class="sxs-lookup"><span data-stu-id="c645d-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="c645d-215">A página também fornece a lista de alertas e ações disparadas.</span><span class="sxs-lookup"><span data-stu-id="c645d-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="c645d-216">![Página de detalhes da regra de detecção personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="c645d-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="c645d-217">*Detalhes da regra de detecção personalizada*</span><span class="sxs-lookup"><span data-stu-id="c645d-217">*Custom detection rule details*</span></span>

<span data-ttu-id="c645d-218">Você também pode executar as seguintes ações na regra nesta página:</span><span class="sxs-lookup"><span data-stu-id="c645d-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="c645d-219">**Executar**— execute a regra imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c645d-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="c645d-220">Isso também redefine o intervalo para a próxima execução.</span><span class="sxs-lookup"><span data-stu-id="c645d-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="c645d-221">**Editar**— modificar a regra sem alterar a consulta</span><span class="sxs-lookup"><span data-stu-id="c645d-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="c645d-222">**Modificar consulta**— editar a consulta em busca avançada</span><span class="sxs-lookup"><span data-stu-id="c645d-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="c645d-223">**Ativar o**  /  **Desativar**— habilitar a regra ou impedir que ela seja executada</span><span class="sxs-lookup"><span data-stu-id="c645d-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="c645d-224">**Excluir**— desativar a regra e removê-la</span><span class="sxs-lookup"><span data-stu-id="c645d-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="c645d-225">Exibir e gerenciar alertas disparados</span><span class="sxs-lookup"><span data-stu-id="c645d-225">View and manage triggered alerts</span></span>

<span data-ttu-id="c645d-226">Na tela detalhes da regra (**busca**de  >  **detecções personalizadas**  >  **[nome da regra]**), acesse **alertas disparados**, que lista os alertas gerados por correspondências com a regra.</span><span class="sxs-lookup"><span data-stu-id="c645d-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="c645d-227">Selecione um alerta para exibir informações detalhadas sobre ele e realizar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="c645d-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="c645d-228">Gerenciar o alerta definindo seu status e classificação (alerta verdadeiro ou falso)</span><span class="sxs-lookup"><span data-stu-id="c645d-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="c645d-229">Vincular o alerta a um incidente</span><span class="sxs-lookup"><span data-stu-id="c645d-229">Link the alert to an incident</span></span>
- <span data-ttu-id="c645d-230">Executar a consulta que disparou o alerta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="c645d-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="c645d-231">Ações de revisão</span><span class="sxs-lookup"><span data-stu-id="c645d-231">Review actions</span></span>
<span data-ttu-id="c645d-232">Na tela detalhes da regra (**busca**de  >  **detecções personalizadas**  >  **[nome da regra]**), vá para **ações disparadas**, que lista as ações executadas com base em correspondências com a regra.</span><span class="sxs-lookup"><span data-stu-id="c645d-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="c645d-233">Para exibir rapidamente as informações e executar ações em um item em uma tabela, use a coluna seleção [&#10003;] à esquerda da tabela.</span><span class="sxs-lookup"><span data-stu-id="c645d-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="related-topic"></a><span data-ttu-id="c645d-234">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="c645d-234">Related topic</span></span>
- [<span data-ttu-id="c645d-235">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="c645d-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="c645d-236">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="c645d-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c645d-237">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="c645d-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
