---
title: Criar e gerenciar regras de detecção personalizadas no Microsoft 365 Defender
description: Saiba como criar e gerenciar regras de detecções personalizadas com base em consultas de busca avançadas
keywords: busca avançada, busca de ameaças, busca de ameaças cibernéticas, proteção contra ameaças da Microsoft, microsoft 365, mtp, m365, pesquisa, consulta, telemetria, detecções personalizadas, regras, esquema, kusto, microsoft 365, Microsoft Threat Protection, RBAC, permissões, Microsoft Defender ATP
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 12a35a9f80da6b401495fcae7c245436b35b991c
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51382884"
---
# <a name="create-and-manage-custom-detections-rules"></a><span data-ttu-id="4e2da-104">Criar e gerenciar regras de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="4e2da-104">Create and manage custom detections rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4e2da-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="4e2da-105">**Applies to:**</span></span>
- <span data-ttu-id="4e2da-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4e2da-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4e2da-107">Regras de detecção personalizadas são regras que você pode projetar e ajustar usando [consultas de busca](advanced-hunting-overview.md) avançadas.</span><span class="sxs-lookup"><span data-stu-id="4e2da-107">Custom detection rules are rules you can design and tweak using [advanced hunting](advanced-hunting-overview.md) queries.</span></span> <span data-ttu-id="4e2da-108">Essas regras permitem que você monitore proativamente vários eventos e estados do sistema, incluindo atividades suspeitas de violação e pontos de extremidade configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="4e2da-108">These rules let you proactively monitor various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="4e2da-109">Você pode defini-los para executar em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver corresponde.</span><span class="sxs-lookup"><span data-stu-id="4e2da-109">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

## <a name="required-permissions-for-managing-custom-detections"></a><span data-ttu-id="4e2da-110">Permissões necessárias para gerenciar detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="4e2da-110">Required permissions for managing custom detections</span></span>

<span data-ttu-id="4e2da-111">Para gerenciar detecções personalizadas, você precisa ter uma dessas funções:</span><span class="sxs-lookup"><span data-stu-id="4e2da-111">To manage custom detections, you need to be assigned one of these roles:</span></span>

- <span data-ttu-id="4e2da-112">**Administrador de** segurança — os usuários com essa função do [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar configurações de segurança no Centro de segurança do Microsoft 365 e em outros portais e serviços.</span><span class="sxs-lookup"><span data-stu-id="4e2da-112">**Security administrator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage security settings in Microsoft 365 security center and other portals and services.</span></span>

- <span data-ttu-id="4e2da-113">**Operador de** segurança — os usuários com essa função do [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) podem gerenciar alertas e ter acesso global somente leitura a recursos relacionados à segurança, incluindo todas as informações no Centro de segurança do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e2da-113">**Security operator**—Users with this [Azure Active Directory role](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) can manage alerts and have global read-only access to security-related features, including all information in Microsoft 365 security center.</span></span> <span data-ttu-id="4e2da-114">Essa função é suficiente para gerenciar detecções personalizadas somente se o controle de acesso baseado em função (RBAC) estiver desligado no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4e2da-114">This role is sufficient for managing custom detections only if role-based access control (RBAC) is turned off in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="4e2da-115">Se você tiver o RBAC configurado, também precisará da permissão gerenciar configurações **de segurança** para o Defender para o Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="4e2da-115">If you have RBAC configured, you also need the **manage security settings** permission for Defender for Endpoint.</span></span>

<span data-ttu-id="4e2da-116">Para gerenciar permissões necessárias, um **administrador global** pode:</span><span class="sxs-lookup"><span data-stu-id="4e2da-116">To manage required permissions, a **global administrator** can:</span></span>

- <span data-ttu-id="4e2da-117">Atribua **a função de administrador de** segurança ou operador **de** segurança no Centro de administração do [Microsoft 365](https://admin.microsoft.com/) em **Roles**  >  **Security admin**.</span><span class="sxs-lookup"><span data-stu-id="4e2da-117">Assign the **security administrator** or **security operator** role in [Microsoft 365 admin center](https://admin.microsoft.com/) under **Roles** > **Security admin**.</span></span>
- <span data-ttu-id="4e2da-118">Verifique as configurações do RBAC para o Microsoft Defender para Ponto de Extremidade no Centro de Segurança do [Microsoft Defender](https://securitycenter.windows.com/) em **Funções de** Permissões  >  **de**  >  **Configurações.**</span><span class="sxs-lookup"><span data-stu-id="4e2da-118">Check RBAC settings for Microsoft Defender for Endpoint in [Microsoft Defender Security Center](https://securitycenter.windows.com/) under **Settings** > **Permissions** > **Roles**.</span></span> <span data-ttu-id="4e2da-119">Selecione a função correspondente para atribuir a **permissão gerenciar configurações de** segurança.</span><span class="sxs-lookup"><span data-stu-id="4e2da-119">Select the corresponding role to assign the **manage security settings** permission.</span></span>

> [!NOTE]
> <span data-ttu-id="4e2da-120">Para gerenciar detecções **personalizadas,** os operadores de segurança precisarão da permissão gerenciar configurações de **segurança** no Microsoft Defender para Ponto de Extremidade se o RBAC estiver ligado.</span><span class="sxs-lookup"><span data-stu-id="4e2da-120">To manage custom detections, **security operators** will need the **manage security settings** permission in Microsoft Defender for Endpoint if RBAC is turned on.</span></span>

## <a name="create-a-custom-detection-rule"></a><span data-ttu-id="4e2da-121">Criar uma regra de detecção personalizada</span><span class="sxs-lookup"><span data-stu-id="4e2da-121">Create a custom detection rule</span></span>
### <a name="1-prepare-the-query"></a><span data-ttu-id="4e2da-122">1. Preparar a consulta.</span><span class="sxs-lookup"><span data-stu-id="4e2da-122">1. Prepare the query.</span></span>

<span data-ttu-id="4e2da-123">No Centro de segurança do Microsoft 365, vá para **Busca** Avançada e selecione uma consulta existente ou crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="4e2da-123">In Microsoft 365 security center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="4e2da-124">Ao usar uma nova consulta, execute a consulta para identificar erros e compreender possíveis resultados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-124">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="4e2da-125">Para impedir que o serviço retorne alertas demais, cada regra é limitada à geração de apenas 100 alertas sempre que ele é executado.</span><span class="sxs-lookup"><span data-stu-id="4e2da-125">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="4e2da-126">Antes de criar uma regra, ajuste sua consulta para evitar alertas para atividades normais do dia a dia.</span><span class="sxs-lookup"><span data-stu-id="4e2da-126">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>


#### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="4e2da-127">Colunas necessárias nos resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="4e2da-127">Required columns in the query results</span></span>
<span data-ttu-id="4e2da-128">Para criar uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="4e2da-128">To create a custom detection rule, the query must return the following columns:</span></span>

- <span data-ttu-id="4e2da-129">`Timestamp`— usado para definir o data/hora dos alertas gerados</span><span class="sxs-lookup"><span data-stu-id="4e2da-129">`Timestamp`—used to set the timestamp for generated alerts</span></span>
- <span data-ttu-id="4e2da-130">`ReportId`— habilita as buscas para os registros originais</span><span class="sxs-lookup"><span data-stu-id="4e2da-130">`ReportId`—enables lookups for the original records</span></span>
- <span data-ttu-id="4e2da-131">Uma das seguintes colunas que identificam dispositivos, usuários ou caixas de correio específicas:</span><span class="sxs-lookup"><span data-stu-id="4e2da-131">One of the following columns that identify specific devices, users, or mailboxes:</span></span>
    - `DeviceId`
    - `DeviceName`
    - `RemoteDeviceName`
    - `RecipientEmailAddress`
    - <span data-ttu-id="4e2da-132">`SenderFromAddress` (remetente de envelope ou Return-Path endereço)</span><span class="sxs-lookup"><span data-stu-id="4e2da-132">`SenderFromAddress` (envelope sender or Return-Path address)</span></span>
    - <span data-ttu-id="4e2da-133">`SenderMailFromAddress` (endereço do remetente exibido pelo cliente de email)</span><span class="sxs-lookup"><span data-stu-id="4e2da-133">`SenderMailFromAddress` (sender address displayed by email client)</span></span>
    - `RecipientObjectId`
    - `AccountObjectId`
    - `AccountSid`
    - `AccountUpn`
    - `InitiatingProcessAccountSid`
    - `InitiatingProcessAccountUpn`
    - `InitiatingProcessAccountObjectId`

>[!NOTE]
><span data-ttu-id="4e2da-134">O suporte para entidades adicionais será adicionado à medida que novas tabelas são adicionadas ao [esquema avançado de busca.](advanced-hunting-schema-tables.md)</span><span class="sxs-lookup"><span data-stu-id="4e2da-134">Support for additional entities will be added as new tables are added to the [advanced hunting schema](advanced-hunting-schema-tables.md).</span></span>

<span data-ttu-id="4e2da-135">Consultas simples, como aquelas que não usam o operador ou para personalizar ou agregar resultados, normalmente `project` `summarize` retornam essas colunas comuns.</span><span class="sxs-lookup"><span data-stu-id="4e2da-135">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="4e2da-136">Há várias maneiras de garantir que consultas mais complexas retornem essas colunas.</span><span class="sxs-lookup"><span data-stu-id="4e2da-136">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="4e2da-137">Por exemplo, se você preferir agregar e contar por entidade em uma coluna como , você ainda pode retornar e conseguindo-o do evento mais recente envolvendo `DeviceId` `Timestamp` cada exclusivo `ReportId` `DeviceId` .</span><span class="sxs-lookup"><span data-stu-id="4e2da-137">For example, if you prefer to aggregate and count by entity under a column such as `DeviceId`, you can still return `Timestamp` and `ReportId` by getting it from the most recent event involving each unique `DeviceId`.</span></span>

<span data-ttu-id="4e2da-138">A consulta de exemplo abaixo conta o número de dispositivos exclusivos ( ) com detecções antivírus e usa essa contagem para encontrar apenas os dispositivos com mais de `DeviceId` cinco detecções.</span><span class="sxs-lookup"><span data-stu-id="4e2da-138">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this count to find only the devices with more than five detections.</span></span> <span data-ttu-id="4e2da-139">Para retornar o mais `Timestamp` recente e o correspondente , ele usa o operador com a `ReportId` `summarize` `arg_max` função.</span><span class="sxs-lookup"><span data-stu-id="4e2da-139">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(1d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="4e2da-140">Para melhorar o desempenho da consulta, de definir um filtro de tempo que corresponde à frequência de execução pretendido para a regra.</span><span class="sxs-lookup"><span data-stu-id="4e2da-140">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="4e2da-141">Como a duração menos frequente é a cada _24 horas,_ a filtragem do último dia abrangerá todos os novos dados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-141">Since the least frequent run is _every 24 hours_, filtering for the past day will cover all new data.</span></span>

### <a name="2-create-new-rule-and-provide-alert-details"></a><span data-ttu-id="4e2da-142">2. Crie nova regra e forneça detalhes de alerta.</span><span class="sxs-lookup"><span data-stu-id="4e2da-142">2. Create new rule and provide alert details.</span></span>

<span data-ttu-id="4e2da-143">Com a consulta no editor de consulta, selecione **Criar regra de** detecção e especifique os seguintes detalhes de alerta:</span><span class="sxs-lookup"><span data-stu-id="4e2da-143">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="4e2da-144">**Nome da detecção**— nome da regra de detecção</span><span class="sxs-lookup"><span data-stu-id="4e2da-144">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="4e2da-145">**Frequência**— intervalo para executar a consulta e executar a ação.</span><span class="sxs-lookup"><span data-stu-id="4e2da-145">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="4e2da-146">Consulte orientações adicionais abaixo</span><span class="sxs-lookup"><span data-stu-id="4e2da-146">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="4e2da-147">**Título do** alerta — título exibido com alertas disparados pela regra</span><span class="sxs-lookup"><span data-stu-id="4e2da-147">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="4e2da-148">**Severidade**— risco potencial do componente ou atividade identificado pela regra</span><span class="sxs-lookup"><span data-stu-id="4e2da-148">**Severity**—potential risk of the component or activity identified by the rule</span></span>
- <span data-ttu-id="4e2da-149">**Categoria**— componente de ameaça ou atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="4e2da-149">**Category**—threat component or activity identified by the rule</span></span>
- <span data-ttu-id="4e2da-150">**MITRE ATT&técnicas de CK**— uma ou mais técnicas de ataque identificadas pela regra como documentadas na estrutura CK do [MITRE ATT&CK](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="4e2da-150">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the [MITRE ATT&CK framework](https://attack.mitre.org/).</span></span> <span data-ttu-id="4e2da-151">Esta seção está oculta para determinadas categorias de alerta, incluindo malware, ransomware, atividade suspeita e software indesejado</span><span class="sxs-lookup"><span data-stu-id="4e2da-151">This section is hidden for certain alert categories, including malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="4e2da-152">**Descrição**— mais informações sobre o componente ou atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="4e2da-152">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="4e2da-153">**Ações recomendadas**— ações adicionais que os respondentes podem tomar em resposta a um alerta</span><span class="sxs-lookup"><span data-stu-id="4e2da-153">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

#### <a name="rule-frequency"></a><span data-ttu-id="4e2da-154">Frequência de regra</span><span class="sxs-lookup"><span data-stu-id="4e2da-154">Rule frequency</span></span>
<span data-ttu-id="4e2da-155">Quando você salva uma nova regra, ela é executado e verifica se há combinações dos últimos 30 dias de dados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-155">When you save a new rule, it runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="4e2da-156">Em seguida, a regra é executado novamente em intervalos fixos, aplicando uma duração de retorno com base na frequência escolhida:</span><span class="sxs-lookup"><span data-stu-id="4e2da-156">The rule then runs again at fixed intervals, applying a lookback duration based on the frequency you choose:</span></span>

- <span data-ttu-id="4e2da-157">**A cada 24 horas**— é executado a cada 24 horas, verificando dados dos últimos 30 dias</span><span class="sxs-lookup"><span data-stu-id="4e2da-157">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="4e2da-158">**A cada 12 horas**— é executado a cada 12 horas, verificando dados das últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="4e2da-158">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="4e2da-159">**A cada 3 horas**— é executado a cada 3 horas, verificando dados das últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="4e2da-159">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="4e2da-160">**A cada hora**— é executado por hora, verificando dados das últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="4e2da-160">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="4e2da-161">Quando você editar uma regra, ela será executado com as alterações aplicadas no próximo tempo de executar agendado de acordo com a frequência definida.</span><span class="sxs-lookup"><span data-stu-id="4e2da-161">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>



>[!TIP]
> <span data-ttu-id="4e2da-162">Match the time filters in your query with the lookback duration.</span><span class="sxs-lookup"><span data-stu-id="4e2da-162">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="4e2da-163">Os resultados fora da duração do retorno de pesquisa são ignorados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-163">Results outside of the lookback duration are ignored.</span></span>  

<span data-ttu-id="4e2da-164">Selecione a frequência que corresponde à proximidade com que você deseja monitorar detecções.</span><span class="sxs-lookup"><span data-stu-id="4e2da-164">Select the frequency that matches how closely you want to monitor detections.</span></span> <span data-ttu-id="4e2da-165">Considere a capacidade da sua organização de responder aos alertas.</span><span class="sxs-lookup"><span data-stu-id="4e2da-165">Consider your organization's capacity to respond to the alerts.</span></span>

### <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="4e2da-166">3. Escolha as entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="4e2da-166">3. Choose the impacted entities.</span></span>
<span data-ttu-id="4e2da-167">Identifique as colunas nos resultados da consulta onde você espera encontrar a entidade principal afetada ou afetada.</span><span class="sxs-lookup"><span data-stu-id="4e2da-167">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="4e2da-168">Por exemplo, uma consulta pode retornar endereços de remetente ( `SenderFromAddress` ou ) e destinatário ( `SenderMailFromAddress` `RecipientEmailAddress` ).</span><span class="sxs-lookup"><span data-stu-id="4e2da-168">For example, a query might return sender (`SenderFromAddress` or `SenderMailFromAddress`) and recipient (`RecipientEmailAddress`) addresses.</span></span> <span data-ttu-id="4e2da-169">Identificar qual dessas colunas representa a entidade principal impactada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.</span><span class="sxs-lookup"><span data-stu-id="4e2da-169">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="4e2da-170">Você pode selecionar apenas uma coluna para cada tipo de entidade (caixa de correio, usuário ou dispositivo).</span><span class="sxs-lookup"><span data-stu-id="4e2da-170">You can select only one column for each entity type (mailbox, user, or device).</span></span> <span data-ttu-id="4e2da-171">As colunas que não são retornadas pela consulta não podem ser selecionadas.</span><span class="sxs-lookup"><span data-stu-id="4e2da-171">Columns that are not returned by your query can't be selected.</span></span>

### <a name="4-specify-actions"></a><span data-ttu-id="4e2da-172">4. Especifique ações.</span><span class="sxs-lookup"><span data-stu-id="4e2da-172">4. Specify actions.</span></span>
<span data-ttu-id="4e2da-173">Sua regra de detecção personalizada pode tomar ações automaticamente em dispositivos, arquivos ou usuários retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="4e2da-173">Your custom detection rule can automatically take actions on devices, files, or users that are returned by the query.</span></span>

#### <a name="actions-on-devices"></a><span data-ttu-id="4e2da-174">Ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="4e2da-174">Actions on devices</span></span>
<span data-ttu-id="4e2da-175">Essas ações são aplicadas a dispositivos na `DeviceId` coluna dos resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="4e2da-175">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>
- <span data-ttu-id="4e2da-176">**Isolar dispositivo** usa o Microsoft Defender para Endpoint para aplicar isolamento total de rede, impedindo que o dispositivo se conecte a qualquer aplicativo ou serviço.</span><span class="sxs-lookup"><span data-stu-id="4e2da-176">**Isolate device**—uses Microsoft Defender for Endpoint to apply full network isolation, preventing the device from connecting to any application or service.</span></span> [<span data-ttu-id="4e2da-177">Saiba mais sobre o isolamento de máquina do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4e2da-177">Learn more about Microsoft Defender for Endpoint machine isolation</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#isolate-devices-from-the-network)
- <span data-ttu-id="4e2da-178">**Coletar pacote de investigação**— coleta informações do dispositivo em um arquivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="4e2da-178">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="4e2da-179">Saiba mais sobre o pacote de investigação do Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4e2da-179">Learn more about the Microsoft Defender for Endpoint investigation package</span></span>](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts#collect-investigation-package-from-devices)
- <span data-ttu-id="4e2da-180">**Executar a verificação antivírus**— executa uma verificação completa Windows Defender antivírus no dispositivo</span><span class="sxs-lookup"><span data-stu-id="4e2da-180">**Run antivirus scan**—performs a full Windows Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="4e2da-181">**Iniciar investigação**— inicia uma investigação [automatizada](m365d-autoir.md) no dispositivo</span><span class="sxs-lookup"><span data-stu-id="4e2da-181">**Initiate investigation**—initiates an [automated investigation](m365d-autoir.md) on the device</span></span>
- <span data-ttu-id="4e2da-182">**Restringir a execução de** aplicativos define restrições no dispositivo para permitir que apenas arquivos assinados com um certificado emitido pela Microsoft sejam executados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-182">**Restrict app execution**—sets restrictions on device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="4e2da-183">Saiba mais sobre restrições de aplicativo com o Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4e2da-183">Learn more about app restrictions with Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/respond-machine-alerts#restrict-app-execution)

#### <a name="actions-on-files"></a><span data-ttu-id="4e2da-184">Ações em arquivos</span><span class="sxs-lookup"><span data-stu-id="4e2da-184">Actions on files</span></span>
<span data-ttu-id="4e2da-185">Quando selecionado, você pode  optar por aplicar a ação de arquivo de quarentena em arquivos na coluna , , ou nos `SHA1` resultados da `InitiatingProcessSHA1` `SHA256` `InitiatingProcessSHA256` consulta.</span><span class="sxs-lookup"><span data-stu-id="4e2da-185">When selected, you can choose to apply the **Quarantine file** action on files in the `SHA1`, `InitiatingProcessSHA1`, `SHA256`, or `InitiatingProcessSHA256` column of the query results.</span></span> <span data-ttu-id="4e2da-186">Essa ação exclui o arquivo de seu local atual e coloca uma cópia em quarentena.</span><span class="sxs-lookup"><span data-stu-id="4e2da-186">This action deletes the file from its current location and places a copy in quarantine.</span></span>

#### <a name="actions-on-users"></a><span data-ttu-id="4e2da-187">Ações em usuários</span><span class="sxs-lookup"><span data-stu-id="4e2da-187">Actions on users</span></span>
<span data-ttu-id="4e2da-188">Quando selecionado, o **usuário Mark como ação** comprometida é tomada em usuários na coluna , ou nos resultados da `AccountObjectId` `InitiatingProcessAccountObjectId` `RecipientObjectId` consulta.</span><span class="sxs-lookup"><span data-stu-id="4e2da-188">When selected, the **Mark user as compromised** action is taken on users in the `AccountObjectId`, `InitiatingProcessAccountObjectId`, or `RecipientObjectId` column of the query results.</span></span> <span data-ttu-id="4e2da-189">Essa ação define o nível de risco dos usuários como "alto" no Azure Active Directory, disparando as políticas de proteção [de identidade correspondentes.](/azure/active-directory/identity-protection/overview-identity-protection)</span><span class="sxs-lookup"><span data-stu-id="4e2da-189">This action sets the users risk level to "high" in Azure Active Directory, triggering corresponding [identity protection policies](/azure/active-directory/identity-protection/overview-identity-protection).</span></span>

> [!NOTE]
> <span data-ttu-id="4e2da-190">No momento, a ação permitir ou bloquear regras de detecção personalizadas não é suportada no Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="4e2da-190">The allow or block action for custom detection rules is currently not supported on Microsoft 365 Defender.</span></span>

### <a name="5-set-the-rule-scope"></a><span data-ttu-id="4e2da-191">5. De definir o escopo da regra.</span><span class="sxs-lookup"><span data-stu-id="4e2da-191">5. Set the rule scope.</span></span>
<span data-ttu-id="4e2da-192">De definir o escopo para especificar quais dispositivos são cobertos pela regra.</span><span class="sxs-lookup"><span data-stu-id="4e2da-192">Set the scope to specify which devices are covered by the rule.</span></span> <span data-ttu-id="4e2da-193">O escopo influencia regras que verificam dispositivos e não afetam regras que verificam apenas caixas de correio e contas de usuário ou identidades.</span><span class="sxs-lookup"><span data-stu-id="4e2da-193">The scope influences rules that check devices and doesn't affect rules that check only mailboxes and user accounts or identities.</span></span>

<span data-ttu-id="4e2da-194">Ao definir o escopo, você pode selecionar:</span><span class="sxs-lookup"><span data-stu-id="4e2da-194">When setting the scope, you can select:</span></span>

- <span data-ttu-id="4e2da-195">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="4e2da-195">All devices</span></span>
- <span data-ttu-id="4e2da-196">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="4e2da-196">Specific device groups</span></span>

<span data-ttu-id="4e2da-197">Somente os dados de dispositivos no escopo serão consultados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-197">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="4e2da-198">Além disso, as ações serão realizadas somente nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="4e2da-198">Also, actions will be taken only on those devices.</span></span>

### <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="4e2da-199">6. Revise e a turn on the rule.</span><span class="sxs-lookup"><span data-stu-id="4e2da-199">6. Review and turn on the rule.</span></span>
<span data-ttu-id="4e2da-200">Depois de revisar a regra, selecione **Criar** para salvá-la.</span><span class="sxs-lookup"><span data-stu-id="4e2da-200">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="4e2da-201">A regra de detecção personalizada é imediatamente executado.</span><span class="sxs-lookup"><span data-stu-id="4e2da-201">The custom detection rule immediately runs.</span></span> <span data-ttu-id="4e2da-202">Ele é executado novamente com base na frequência configurada para verificar se há resultados, gerar alertas e tomar ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="4e2da-202">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>


>[!Important] 
><span data-ttu-id="4e2da-203">As detecções personalizadas devem ser regularmente revisadas para eficiência e eficácia.</span><span class="sxs-lookup"><span data-stu-id="4e2da-203">Custom detections should be regularly reviewed for efficiency and effectiveness.</span></span> <span data-ttu-id="4e2da-204">Para garantir que você está criando detecções que disparam alertas verdadeiros, desdove para revisar suas detecções personalizadas existentes seguindo as etapas em Gerenciar regras de detecção [personalizadas existentes.](#manage-existing-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="4e2da-204">To make sure you are creating detections that trigger true alerts, take time to review your existing custom detections by following the steps in [Manage existing custom detection rules](#manage-existing-custom-detection-rules).</span></span> <br>  
<span data-ttu-id="4e2da-205">Você mantém o controle sobre a ampla ou a especificidade de suas detecções personalizadas para que quaisquer alertas falsos gerados por detecções personalizadas possam indicar a necessidade de modificar determinados parâmetros das regras.</span><span class="sxs-lookup"><span data-stu-id="4e2da-205">You maintain control over the broadness or specificity of your custom detections so any false alerts generated by custom detections might indicate a need to modify certain parameters of the rules.</span></span>


## <a name="manage-existing-custom-detection-rules"></a><span data-ttu-id="4e2da-206">Gerenciar regras de detecção personalizadas existentes</span><span class="sxs-lookup"><span data-stu-id="4e2da-206">Manage existing custom detection rules</span></span>
<span data-ttu-id="4e2da-207">Você pode exibir a lista de regras de detecção personalizadas existentes, verificar suas versões anteriores e revisar os alertas disparados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-207">You can view the list of existing custom detection rules, check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="4e2da-208">Você também pode executar uma regra sob demanda e modificá-la.</span><span class="sxs-lookup"><span data-stu-id="4e2da-208">You can also run a rule on demand and modify it.</span></span>

### <a name="view-existing-rules"></a><span data-ttu-id="4e2da-209">Exibir regras existentes</span><span class="sxs-lookup"><span data-stu-id="4e2da-209">View existing rules</span></span>

<span data-ttu-id="4e2da-210">Para exibir todas as regras de detecção personalizadas existentes, navegue até **Hunting**  >  **Custom detections**.</span><span class="sxs-lookup"><span data-stu-id="4e2da-210">To view all existing custom detection rules, navigate to **Hunting** > **Custom detections**.</span></span> <span data-ttu-id="4e2da-211">A página lista todas as regras com as seguintes informações de executar:</span><span class="sxs-lookup"><span data-stu-id="4e2da-211">The page lists all the rules with the following run information:</span></span>

- <span data-ttu-id="4e2da-212">**Última executar**— quando uma regra foi executado pela última vez para verificar se há verificações de consultas e gerar alertas</span><span class="sxs-lookup"><span data-stu-id="4e2da-212">**Last run**—when a rule was last run to check for query matches and generate alerts</span></span>
- <span data-ttu-id="4e2da-213">**Status da última executar**— se uma regra foi realizada com êxito</span><span class="sxs-lookup"><span data-stu-id="4e2da-213">**Last run status**—whether a rule ran successfully</span></span>
- <span data-ttu-id="4e2da-214">**Próxima executar**— a próxima sequência agendada</span><span class="sxs-lookup"><span data-stu-id="4e2da-214">**Next run**—the next scheduled run</span></span>
- <span data-ttu-id="4e2da-215">**Status**— se uma regra foi 1ada ou desligada</span><span class="sxs-lookup"><span data-stu-id="4e2da-215">**Status**—whether a rule has been turned on or off</span></span>

### <a name="view-rule-details-modify-rule-and-run-rule"></a><span data-ttu-id="4e2da-216">Exibir detalhes da regra, modificar regra e executar regra</span><span class="sxs-lookup"><span data-stu-id="4e2da-216">View rule details, modify rule, and run rule</span></span>

<span data-ttu-id="4e2da-217">Para exibir informações abrangentes sobre uma regra de detecção personalizada, acesse **Hunting**  >  **Custom detections** e selecione o nome da regra.</span><span class="sxs-lookup"><span data-stu-id="4e2da-217">To view comprehensive information about a custom detection rule, go to **Hunting** > **Custom detections** and then select the name of rule.</span></span> <span data-ttu-id="4e2da-218">Em seguida, você pode exibir informações gerais sobre a regra, incluindo informações sobre seu status e escopo de executar.</span><span class="sxs-lookup"><span data-stu-id="4e2da-218">You can then view general information about the rule, including information its run status and scope.</span></span> <span data-ttu-id="4e2da-219">A página também fornece a lista de alertas e ações disparados.</span><span class="sxs-lookup"><span data-stu-id="4e2da-219">The page also provides the list of triggered alerts and actions.</span></span>

<span data-ttu-id="4e2da-220">![Página de detalhes da regra de detecção personalizada](../../media/custom-detection-details.png)</span><span class="sxs-lookup"><span data-stu-id="4e2da-220">![Custom detection rule details page](../../media/custom-detection-details.png)</span></span><br>
<span data-ttu-id="4e2da-221">*Detalhes da regra de detecção personalizada*</span><span class="sxs-lookup"><span data-stu-id="4e2da-221">*Custom detection rule details*</span></span>

<span data-ttu-id="4e2da-222">Você também pode tomar as seguintes ações na regra nesta página:</span><span class="sxs-lookup"><span data-stu-id="4e2da-222">You can also take the following actions on the rule from this page:</span></span>

- <span data-ttu-id="4e2da-223">**Executar**— execute a regra imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4e2da-223">**Run**—run the rule immediately.</span></span> <span data-ttu-id="4e2da-224">Isso também redefine o intervalo para a próxima executar.</span><span class="sxs-lookup"><span data-stu-id="4e2da-224">This also resets the interval for the next run.</span></span>
- <span data-ttu-id="4e2da-225">**Editar**— modificar a regra sem alterar a consulta</span><span class="sxs-lookup"><span data-stu-id="4e2da-225">**Edit**—modify the rule without changing the query</span></span>
- <span data-ttu-id="4e2da-226">**Modificar consulta —** editar a consulta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="4e2da-226">**Modify query**—edit the query in advanced hunting</span></span>
- <span data-ttu-id="4e2da-227">**Ativar**  /  **Desativar —** habilitar a regra ou impedi-la de executar</span><span class="sxs-lookup"><span data-stu-id="4e2da-227">**Turn on** / **Turn off**—enable the rule or stop it from running</span></span>
- <span data-ttu-id="4e2da-228">**Excluir**— desativar a regra e removê-la</span><span class="sxs-lookup"><span data-stu-id="4e2da-228">**Delete**—turn off the rule and remove it</span></span>

### <a name="view-and-manage-triggered-alerts"></a><span data-ttu-id="4e2da-229">Exibir e gerenciar alertas disparados</span><span class="sxs-lookup"><span data-stu-id="4e2da-229">View and manage triggered alerts</span></span>

<span data-ttu-id="4e2da-230">Na tela de detalhes da regra (**Hunting**  >  **Custom detections**  >  **[Nome** da regra] ), vá para **Alertas disparados**, que lista os alertas gerados por corresponde à regra.</span><span class="sxs-lookup"><span data-stu-id="4e2da-230">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to  **Triggered alerts**, which lists the alerts generated by matches to the rule.</span></span> <span data-ttu-id="4e2da-231">Selecione um alerta para exibir informações detalhadas sobre ele e tome as seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="4e2da-231">Select an alert to view detailed information about it and take the following actions:</span></span>

- <span data-ttu-id="4e2da-232">Gerencie o alerta definindo seu status e classificação (alerta verdadeiro ou falso)</span><span class="sxs-lookup"><span data-stu-id="4e2da-232">Manage the alert by setting its status and classification (true or false alert)</span></span>
- <span data-ttu-id="4e2da-233">Vincular o alerta a um incidente</span><span class="sxs-lookup"><span data-stu-id="4e2da-233">Link the alert to an incident</span></span>
- <span data-ttu-id="4e2da-234">Execute a consulta que disparou o alerta na busca avançada</span><span class="sxs-lookup"><span data-stu-id="4e2da-234">Run the query that triggered the alert on advanced hunting</span></span>

### <a name="review-actions"></a><span data-ttu-id="4e2da-235">Revisar ações</span><span class="sxs-lookup"><span data-stu-id="4e2da-235">Review actions</span></span>
<span data-ttu-id="4e2da-236">Na tela de detalhes da regra (**Hunting**  >  **Custom detections**  >  **[Nome** da regra] ), vá para **Ações** disparadas , que lista as ações realizadas com base em corresponde à regra.</span><span class="sxs-lookup"><span data-stu-id="4e2da-236">In the rule details screen (**Hunting** > **Custom detections** > **[Rule name]**), go to **Triggered actions**, which lists the actions taken based on matches to the rule.</span></span>

>[!TIP]
><span data-ttu-id="4e2da-237">Para exibir rapidamente informações e tomar medidas em um item em uma tabela, use a coluna de seleção [&#10003;] à esquerda da tabela.</span><span class="sxs-lookup"><span data-stu-id="4e2da-237">To quickly view information and take action on an item in a table, use the selection column [&#10003;] at the left of the table.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e2da-238">Confira também</span><span class="sxs-lookup"><span data-stu-id="4e2da-238">See also</span></span>
- [<span data-ttu-id="4e2da-239">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="4e2da-239">Custom detections overview</span></span>](custom-detections-overview.md)
- [<span data-ttu-id="4e2da-240">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="4e2da-240">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4e2da-241">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="4e2da-241">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4e2da-242">Migrar consultas de busca avançadas do Microsoft Defender para o Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="4e2da-242">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>](advanced-hunting-migrate-from-mde.md)
