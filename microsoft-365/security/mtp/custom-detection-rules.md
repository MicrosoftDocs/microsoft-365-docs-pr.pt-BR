---
title: Criar e gerenciar regras de detecção personalizadas no Microsoft 365 Defender
description: Saiba como criar e gerenciar regras de detecções personalizadas com base em consultas de busca avançada
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, detecções personalizadas, regras, esquema, kusto, microsoft 365, Proteção contra Ameaças da Microsoft, RBAC, permissões, Microsoft Defender ATP
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
ms.openlocfilehash: d58292f658446259bfab5b1b55c8b462d081421c
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080618"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="e9d9b-104">Criar e gerenciar regras de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="e9d9b-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="e9d9b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e9d9b-105">**Applies to:**</span></span>
- <span data-ttu-id="e9d9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e9d9b-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="e9d9b-107">Regras de detecção personalizadas são regras que você pode projetar e ajustar usando [consultas de busca](advanced-hunting-overview.md) avançada.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="e9d9b-108">Essas regras permitem monitorar proativamente vários eventos e estados do sistema, incluindo atividades suspeitas de violação e pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="e9d9b-109">Você pode defini-los para executar em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver resultados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="e9d9b-110">Permissões necessárias para gerenciar detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="e9d9b-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="e9d9b-111">Para gerenciar detecções personalizadas, você precisa ter uma destas funções atribuídas:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="e9d9b-112">**Administrador de** segurança — os usuários com essa função [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar as configurações de segurança no centro de segurança do Microsoft 365 e em outros portais e serviços.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-112">**Security administrator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="e9d9b-113">**Operador** de segurança — Os usuários com essa função [do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar alertas e ter acesso global somente leitura a recursos relacionados à segurança, incluindo todas as informações na central de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-113">**Security operator**—Users with this [Azure Active Directory role](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="e9d9b-114">Essa função é suficiente para gerenciar detecções personalizadas somente se o controle de acesso baseado em função (RBAC) estiver desligado no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="e9d9b-115">Se o RBAC estiver configurado, você também precisará da permissão gerenciar configurações **de** segurança do Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="e9d9b-116">Para gerenciar as permissões necessárias, um **administrador global** pode:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="e9d9b-117">Atribua **a função de administrador de** segurança **ou** operador de segurança no centro de administração do [Microsoft 365](https://admin.microsoft.com/) sob **o administrador de Segurança** de  >  **Funções.**</span><span class="sxs-lookup"><span data-stu-id="e9d9b-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="e9d9b-118">Verifique as configurações do RBAC para o Microsoft Defender para o ponto de extremidade na Central de Segurança do [Microsoft Defender](https://securitycenter.windows.com/) em **Funções** de  >  **Permissões de**  >  **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="e9d9b-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="e9d9b-119">Selecione a função correspondente para atribuir a **permissão gerenciar configurações de** segurança.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="e9d9b-120">Para gerenciar detecções personalizadas,   os operadores de segurança precisarão da permissão gerenciar configurações de segurança no Microsoft Defender para Ponto de Extremidade se o RBAC estiver ligado.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="e9d9b-121">Criar uma regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="e9d9b-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="e9d9b-122">1. Prepare a consulta.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-122">1. Prepare the query.</span></span>

<span data-ttu-id="e9d9b-123">No centro de segurança do Microsoft  365, vá para a Busca Avançada e selecione uma consulta existente ou crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="e9d9b-124">Ao usar uma nova consulta, execute a consulta para identificar erros e entender os possíveis resultados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e9d9b-125">Para impedir que o serviço retorne muitos alertas, cada regra está limitada a gerar apenas 100 alertas sempre que for executado.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="e9d9b-126">Antes de criar uma regra, ajuste sua consulta para evitar alertas para atividades normais do dia a dia.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="e9d9b-127">Colunas necessárias nos resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="e9d9b-127">Required columns in the query results</span></span>
<span data-ttu-id="e9d9b-128">Para criar uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="e9d9b-129">`Timestamp`— usado para definir o timestamp para alertas gerados</span><span class="sxs-lookup"><span data-stu-id="e9d9b-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="e9d9b-130">`ReportId`— habilita as buscas para os registros originais</span><span class="sxs-lookup"><span data-stu-id="e9d9b-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="e9d9b-131">Uma das seguintes colunas que identificam dispositivos, usuários ou caixas de correio específicos:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="e9d9b-132">`SenderFromAddress` (remetente de envelope ou Return-Path endereço)</span><span class="sxs-lookup"><span data-stu-id="e9d9b-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="e9d9b-133">`SenderMailFromAddress` (endereço do remetente exibido pelo cliente de email)</span><span class="sxs-lookup"><span data-stu-id="e9d9b-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="e9d9b-134">O suporte para entidades adicionais será adicionado à medida que novas tabelas são adicionadas ao [esquema de busca avançada.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="e9d9b-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="e9d9b-135">Consultas simples, como aquelas que não usam o operador ou para personalizar ou agregar resultados, normalmente `project` `summarize` retornam essas colunas comuns.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="e9d9b-136">Há várias maneiras de garantir que consultas mais complexas retornem essas colunas.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="e9d9b-137">Por exemplo, se você preferir agregar e contar por entidade sob uma coluna, como , você ainda pode retornar e recebendo-o do evento mais recente envolvendo `DeviceId` `Timestamp` cada exclusivo `ReportId` `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="e9d9b-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="e9d9b-138">A consulta de exemplo abaixo conta o número de dispositivos exclusivos ( ) com detecções antivírus e usa essa contagem para encontrar apenas os dispositivos com mais de `DeviceId` cinco detecções.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="e9d9b-139">Para retornar o mais `Timestamp` recente e o `ReportId` correspondente, ele usa o operador com `summarize` a `arg_max` função.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="e9d9b-140">Para melhorar o desempenho da consulta, de definir um filtro de tempo que corresponde à frequência de execução pretendido para a regra.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="e9d9b-141">Como a menor frequência de run é _a cada 24 horas,_ a filtragem do dia anterior abrangerá todos os novos dados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="e9d9b-142">2. Crie uma nova regra e forneça detalhes de alerta.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="e9d9b-143">Com a consulta no editor de consulta, selecione **Criar regra de** detecção e especifique os seguintes detalhes de alerta:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="e9d9b-144">**Nome da detecção**— nome da regra de detecção</span><span class="sxs-lookup"><span data-stu-id="e9d9b-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="e9d9b-145">**Frequência**— intervalo para executar a consulta e executar uma ação.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="e9d9b-146">Consulte as diretrizes adicionais abaixo</span><span class="sxs-lookup"><span data-stu-id="e9d9b-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="e9d9b-147">**Título do** alerta – título exibido com alertas disparados pela regra</span><span class="sxs-lookup"><span data-stu-id="e9d9b-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="e9d9b-148">**Gravidade —** risco potencial do componente ou da atividade identificado pela regra</span><span class="sxs-lookup"><span data-stu-id="e9d9b-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="e9d9b-149">**Categoria**— componente de ameaça ou atividade identificado pela regra</span><span class="sxs-lookup"><span data-stu-id="e9d9b-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="e9d9b-150">**TÉCNICAS CK mitRE ATT&** uma ou mais técnicas de ataque identificadas pela regra, conforme documentado na estrutura [MITRE ATT&CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="e9d9b-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="e9d9b-151">Esta seção está oculta para determinadas categorias de alerta, incluindo malware, ransomware, atividade suspeita e software indesejado</span><span class="sxs-lookup"><span data-stu-id="e9d9b-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="e9d9b-152">**Descrição**– mais informações sobre o componente ou a atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="e9d9b-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="e9d9b-153">**Ações recomendadas**— ações adicionais que os respondentes podem tomar em resposta a um alerta</span><span class="sxs-lookup"><span data-stu-id="e9d9b-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="e9d9b-154">Frequência de regra</span><span class="sxs-lookup"><span data-stu-id="e9d9b-154">Rule frequency</span></span>
<span data-ttu-id="e9d9b-155">Quando você salva ou edita uma nova regra, ela é executado e verifica se há combinações dos últimos 30 dias de dados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-155">When you save or edit a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="e9d9b-156">Em seguida, a regra é executado novamente em intervalos fixos, aplicando uma duração de retorno com base na frequência escolhida:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="e9d9b-157">**A cada 24 horas**— é executado a cada 24 horas, verificando dados dos últimos 30 dias</span><span class="sxs-lookup"><span data-stu-id="e9d9b-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="e9d9b-158">**A cada 12 horas**— é executado a cada 12 horas, verificando dados das últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="e9d9b-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="e9d9b-159">**A cada 3 horas**— é executado a cada 3 horas, verificando dados das últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="e9d9b-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="e9d9b-160">**A cada hora**— é executado a cada hora, verificando dados das últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="e9d9b-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

>[!TIP]
> <span data-ttu-id="e9d9b-161">Corresponder os filtros de tempo em sua consulta com a duração de retorno.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-161">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="e9d9b-162">Os resultados fora da duração de pesquisa são ignorados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-162">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="e9d9b-163">Selecione a frequência que corresponde à proximidade com que você deseja monitorar detecções.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-163">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="e9d9b-164">Considere a capacidade da sua organização de responder aos alertas.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-164">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="e9d9b-165">3. Escolha as entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-165">3. Choose the impacted entities.</span></span>
<span data-ttu-id="e9d9b-166">Identifique as colunas nos resultados da consulta onde você espera encontrar a entidade principal afetada ou afetada.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-166">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="e9d9b-167">Por exemplo, uma consulta pode retornar endereços de remetente ( `SenderFromAddress` ou ) e de destinatário ( `SenderMailFromAddress` `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="e9d9b-167">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="e9d9b-168">Identificar quais dessas colunas representam a entidade principal impactada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-168">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="e9d9b-169">Você pode selecionar apenas uma coluna para cada tipo de entidade (caixa de correio, usuário ou dispositivo).</span><span class="sxs-lookup"><span data-stu-id="e9d9b-169">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="e9d9b-170">Colunas que não são retornadas por sua consulta não podem ser selecionadas.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-170">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="e9d9b-171">4. Especifique as ações.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-171">4. Specify actions.</span></span>
<span data-ttu-id="e9d9b-172">Sua regra de detecção personalizada pode automaticamente tomar ações em dispositivos, arquivos ou usuários retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-172">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="e9d9b-173">Ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="e9d9b-173">Actions on devices</span></span>
<span data-ttu-id="e9d9b-174">Essas ações são aplicadas a dispositivos na `DeviceId` coluna dos resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-174">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="e9d9b-175">**Isole o** dispositivo — usa o Microsoft Defender para o Ponto de Extremidade para aplicar o isolamento de rede completo, impedindo que o dispositivo se conecte a qualquer aplicativo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-175">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="e9d9b-176">Saiba mais sobre o Microsoft Defender para isolamento de máquina de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="e9d9b-176">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="e9d9b-177">**Coletar pacote de investigação**— coleta informações do dispositivo em um arquivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-177">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="e9d9b-178">Saiba mais sobre o pacote de investigação do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e9d9b-178">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="e9d9b-179">**Executar a verificação antivírus**— executa uma verificação completa do Windows Defender Antivírus no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9d9b-179">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="e9d9b-180">**Iniciar investigação**— inicia uma [investigação automatizada](mtp-autoir.md) no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e9d9b-180">**Initiate investigation**—initiates an [automated investigation](mtp-autoir.md) on the device</span></span>
- <span data-ttu-id="e9d9b-181">**Restringir a execução do** aplicativo — define restrições no dispositivo para permitir que somente arquivos assinados com um certificado emitido pela Microsoft sejam executados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-181">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="e9d9b-182">Saiba mais sobre restrições de aplicativos com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e9d9b-182">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="e9d9b-183">Ações em arquivos</span><span class="sxs-lookup"><span data-stu-id="e9d9b-183">Actions on files</span></span>
<span data-ttu-id="e9d9b-184">Quando selecionado, você pode optar por aplicar a ação **de** arquivo de quarentena em arquivos na coluna , ou nos `SHA1` resultados da `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` consulta.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-184">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="e9d9b-185">Essa ação exclui o arquivo de seu local atual e coloca uma cópia em quarentena.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-185">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="e9d9b-186">Ações em usuários</span><span class="sxs-lookup"><span data-stu-id="e9d9b-186">Actions on users</span></span>
<span data-ttu-id="e9d9b-187">Quando selecionado, a **ação marcar o usuário** como comprometida é realizada para os usuários na coluna , ou nos resultados da `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` consulta.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-187">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="e9d9b-188">Essa ação define o nível de risco dos usuários como "alto" no Azure Active Directory, disparando as políticas de [proteção de identidade correspondentes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="e9d9b-188">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="e9d9b-189">No momento, a ação de permitir ou bloquear regras de detecção personalizadas não é suportada no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-189">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="e9d9b-190">5. Definir o escopo da regra.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-190">5. Set the rule scope.</span></span>
<span data-ttu-id="e9d9b-191">Definir o escopo para especificar quais dispositivos são cobertos pela regra.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-191">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="e9d9b-192">O escopo influencia regras que verificam dispositivos e não afeta regras que verificam apenas caixas de correio e contas de usuário ou identidades.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-192">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="e9d9b-193">Ao definir o escopo, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-193">When setting the scope, you can select:</span></span>

- <span data-ttu-id="e9d9b-194">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="e9d9b-194">All devices</span></span>
- <span data-ttu-id="e9d9b-195">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="e9d9b-195">Specific device groups</span></span>

<span data-ttu-id="e9d9b-196">Somente os dados de dispositivos no escopo serão consultados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-196">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="e9d9b-197">Além disso, as ações serão realizadas apenas nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-197">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="e9d9b-198">6. Revise e a a turn on the rule.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-198">6. Review and turn on the rule.</span></span>
<span data-ttu-id="e9d9b-199">Depois de analisar a regra, selecione **Criar** para salvá-la.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-199">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="e9d9b-200">A regra de detecção personalizada é imediatamente executado.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-200">The custom detection rule immediately runs.</span></span> <span data-ttu-id="e9d9b-201">Ele é executado novamente com base na frequência configurada para verificar se há resultados, gerar alertas e tomar ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-201">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="e9d9b-202">Gerenciar regras de detecção personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="e9d9b-202">Manage existing custom detection rules</span></span>
<span data-ttu-id="e9d9b-203">Você pode exibir a lista de regras de detecção personalizadas existentes, verificar suas versões anteriores e analisar os alertas disparados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-203">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="e9d9b-204">Você também pode executar uma regra sob demanda e modificá-la.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-204">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="e9d9b-205">Exibir regras existentes</span><span class="sxs-lookup"><span data-stu-id="e9d9b-205">View existing rules</span></span>

<span data-ttu-id="e9d9b-206">Para exibir todas as regras de detecção personalizadas existentes, navegue até  >  **Detecções personalizadas de Busca.**</span><span class="sxs-lookup"><span data-stu-id="e9d9b-206">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="e9d9b-207">A página lista todas as regras com as seguintes informações de executar:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-207">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="e9d9b-208">**Última vez —** quando uma regra foi executado pela última vez para verificar se há consultas e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="e9d9b-208">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="e9d9b-209">**Status da última vez**— se uma regra foi executado com êxito</span><span class="sxs-lookup"><span data-stu-id="e9d9b-209">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="e9d9b-210">**Próxima sequência —** a próxima sequência agendada</span><span class="sxs-lookup"><span data-stu-id="e9d9b-210">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="e9d9b-211">**Status**— se uma regra foi 2013 ou não</span><span class="sxs-lookup"><span data-stu-id="e9d9b-211">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="e9d9b-212">Exibir detalhes da regra, modificar regra e executar regra</span><span class="sxs-lookup"><span data-stu-id="e9d9b-212">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="e9d9b-213">Para exibir informações abrangentes sobre uma regra de detecção personalizada, vá para **Detecções** de Busca Personalizada  >  **e** selecione o nome da regra.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-213">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="e9d9b-214">Em seguida, você pode exibir informações gerais sobre a regra, incluindo informações sobre seu status de executar e escopo.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-214">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="e9d9b-215">A página também fornece a lista de alertas e ações disparados.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-215">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="e9d9b-216">![Página de detalhes da regra de detecção personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="e9d9b-216">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="e9d9b-217">*Detalhes da regra de detecção personalizada*</span><span class="sxs-lookup"><span data-stu-id="e9d9b-217">*Custom detection rule details*</span></span>

<span data-ttu-id="e9d9b-218">Você também pode tomar as seguintes ações na regra desta página:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-218">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="e9d9b-219">**Executar**— execute a regra imediatamente.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-219">**Run**—run the rule immediately.</span></span> <span data-ttu-id="e9d9b-220">Isso também redefine o intervalo para a próxima sequência.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-220">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="e9d9b-221">**Editar**— modifique a regra sem alterar a consulta</span><span class="sxs-lookup"><span data-stu-id="e9d9b-221">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="e9d9b-222">**Modificar consulta —** editar a consulta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="e9d9b-222">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="e9d9b-223">**Ativar**  /  **Desativar — habilitar** a regra ou impedi-la de ser executado</span><span class="sxs-lookup"><span data-stu-id="e9d9b-223">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="e9d9b-224">**Excluir**— desativar a regra e removê-la</span><span class="sxs-lookup"><span data-stu-id="e9d9b-224">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="e9d9b-225">Exibir e gerenciar alertas disparados</span><span class="sxs-lookup"><span data-stu-id="e9d9b-225">View and manage triggered alerts</span></span>

<span data-ttu-id="e9d9b-226">Na tela de detalhes da regra (**Detecções** personalizadas de busca [nome da regra] ), vá para  >    >   **alertas disparados,** que lista os alertas gerados por corresponde à regra.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-226">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="e9d9b-227">Selecione um alerta para exibir informações detalhadas sobre ele e tomar as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="e9d9b-227">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="e9d9b-228">Gerenciar o alerta definindo seu status e classificação (alerta verdadeiro ou falso)</span><span class="sxs-lookup"><span data-stu-id="e9d9b-228">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="e9d9b-229">Vincular o alerta a um incidente</span><span class="sxs-lookup"><span data-stu-id="e9d9b-229">Link the alert to an incident</span></span>
- <span data-ttu-id="e9d9b-230">Executar a consulta que disparou o alerta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="e9d9b-230">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="e9d9b-231">Revisar ações</span><span class="sxs-lookup"><span data-stu-id="e9d9b-231">Review actions</span></span>
<span data-ttu-id="e9d9b-232">Na tela de detalhes da regra **(** Detecções personalizadas de busca [nome da regra] ), vá para ações disparadas, que lista as ações tomadas com base  >    >  nas combinações com a regra.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-232">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="e9d9b-233">Para exibir rapidamente informações e tomar medidas em um item em uma tabela, use a coluna de seleção [&#10003;] à esquerda da tabela.</span><span class="sxs-lookup"><span data-stu-id="e9d9b-233">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9d9b-234">Confira também</span><span class="sxs-lookup"><span data-stu-id="e9d9b-234">See also</span></span>
- [<span data-ttu-id="e9d9b-235">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="e9d9b-235">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="e9d9b-236">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="e9d9b-236">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e9d9b-237">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="e9d9b-237">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e9d9b-238">Migrar consultas de busca avançada do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e9d9b-238">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mdatp.md)
