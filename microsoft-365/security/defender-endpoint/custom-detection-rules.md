---
title: Criar regras de detecção personalizadas no Microsoft Defender ATP
ms.reviewer: ''
description: Saiba como criar regras de detecção personalizadas com base em consultas de busca avançadas
keywords: detecções personalizadas, criar, gerenciar, alertas, editar, executar sob demanda, frequência, intervalo, regras de detecção, busca avançada, busca, consulta, ações de resposta, mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 15dec5396a5ba95fe3ec7af5f9a72bbf15e07140
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500491"
---
# <a name="create-custom-detection-rules"></a><span data-ttu-id="e7dc0-104">Criar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="e7dc0-104">Create custom detection rules</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e7dc0-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="e7dc0-105">**Applies to:**</span></span>
- [<span data-ttu-id="e7dc0-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="e7dc0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e7dc0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e7dc0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="e7dc0-108">Deseja experimentar o Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="e7dc0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="e7dc0-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="e7dc0-110">As regras de [](advanced-hunting-overview.md) detecção personalizadas criadas a partir de consultas avançadas de busca permitem monitorar proativamente vários eventos e estados do sistema, incluindo atividades suspeitas de violação e dispositivos configurados incorretamente.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-110">Custom detection rules built from [advanced hunting](advanced-hunting-overview.md) queries let you proactively monitor various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="e7dc0-111">Você pode defini-los para executar em intervalos regulares, gerando alertas e tomando ações de resposta sempre que houver corresponde.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-111">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="e7dc0-112">Leia este artigo para saber como criar novas regras de detecção personalizadas.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-112">Read this article to learn how to create new custom detection rules.</span></span> <span data-ttu-id="e7dc0-113">Ou [consulte exibindo e gerenciando regras existentes.](custom-detections-manage.md)</span><span class="sxs-lookup"><span data-stu-id="e7dc0-113">Or [see viewing and managing existing rules](custom-detections-manage.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e7dc0-114">Para criar ou gerenciar detecções personalizadas, [sua função](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) precisa ter a permissão **gerenciar configurações de** segurança.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-114">To create or manage custom detections, [your role](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) needs to have the **manage security settings** permission.</span></span>

## <a name="1-prepare-the-query"></a><span data-ttu-id="e7dc0-115">1. Preparar a consulta.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-115">1. Prepare the query.</span></span>

<span data-ttu-id="e7dc0-116">No Centro de Segurança do Microsoft Defender, vá para **Busca** Avançada e selecione uma consulta existente ou crie uma nova consulta.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-116">In Microsoft Defender Security Center, go to **Advanced hunting** and select an existing query or create a new query.</span></span> <span data-ttu-id="e7dc0-117">Ao usar uma nova consulta, execute a consulta para identificar erros e compreender possíveis resultados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-117">When using a new query, run the query to identify errors and understand possible results.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e7dc0-118">Para impedir que o serviço retorne alertas demais, cada regra é limitada à geração de apenas 100 alertas sempre que ele é executado.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-118">To prevent the service from returning too many alerts, each rule is limited to generating only 100 alerts whenever it runs.</span></span> <span data-ttu-id="e7dc0-119">Antes de criar uma regra, ajuste sua consulta para evitar alertas para atividades normais do dia a dia.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-119">Before creating a rule, tweak your query to avoid alerting for normal, day-to-day activity.</span></span>

### <a name="required-columns-in-the-query-results"></a><span data-ttu-id="e7dc0-120">Colunas necessárias nos resultados da consulta</span><span class="sxs-lookup"><span data-stu-id="e7dc0-120">Required columns in the query results</span></span>

<span data-ttu-id="e7dc0-121">Para usar uma consulta para uma regra de detecção personalizada, a consulta deve retornar as seguintes colunas:</span><span class="sxs-lookup"><span data-stu-id="e7dc0-121">To use a query for a custom detection rule, the query must return the following columns:</span></span>

- `Timestamp`
- `DeviceId`
- `ReportId`

<span data-ttu-id="e7dc0-122">Consultas simples, como aquelas que não usam o operador ou para personalizar ou agregar resultados, normalmente `project` `summarize` retornam essas colunas comuns.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-122">Simple queries, such as those that don't use the `project` or `summarize` operator to customize or aggregate results, typically return these common columns.</span></span>

<span data-ttu-id="e7dc0-123">Há várias maneiras de garantir que consultas mais complexas retornem essas colunas.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-123">There are various ways to ensure more complex queries return these columns.</span></span> <span data-ttu-id="e7dc0-124">Por exemplo, se você preferir agregar e contar por , ainda poderá retornar e consegui-los do evento mais recente envolvendo `DeviceId` `Timestamp` cada `ReportId` dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-124">For example, if you prefer to aggregate and count by `DeviceId`, you can still return `Timestamp` and `ReportId` by getting them from the most recent event involving each device.</span></span>

<span data-ttu-id="e7dc0-125">A consulta de exemplo a seguir conta o número de dispositivos exclusivos ( ) com detecções antivírus e usa isso para encontrar apenas os dispositivos com mais de `DeviceId` cinco detecções.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-125">The sample query below counts the number of unique devices (`DeviceId`) with antivirus detections and uses this to find only those devices with more than five detections.</span></span> <span data-ttu-id="e7dc0-126">Para retornar o mais `Timestamp` recente e o correspondente , ele usa o operador com a `ReportId` `summarize` `arg_max` função.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-126">To return the latest `Timestamp` and the corresponding `ReportId`, it uses the `summarize` operator with the `arg_max` function.</span></span>

```kusto
DeviceEvents
| where Timestamp > ago(7d)
| where ActionType == "AntivirusDetection"
| summarize (Timestamp, ReportId)=arg_max(Timestamp, ReportId), count() by DeviceId
| where count_ > 5
```

> [!TIP]
> <span data-ttu-id="e7dc0-127">Para melhorar o desempenho da consulta, de definir um filtro de tempo que corresponde à frequência de execução pretendido para a regra.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-127">For better query performance, set a time filter that matches your intended run frequency for the rule.</span></span> <span data-ttu-id="e7dc0-128">Como a duração menos frequente é a cada 24 horas, a filtragem do último dia abrangerá todos os novos dados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-128">Since the least frequent run is every 24 hours, filtering for the past day will cover all new data.</span></span>

## <a name="2-create-a-new-rule-and-provide-alert-details"></a><span data-ttu-id="e7dc0-129">2. Crie uma nova regra e forneça detalhes de alerta.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-129">2. Create a new rule and provide alert details.</span></span>

<span data-ttu-id="e7dc0-130">Com a consulta no editor de consulta, selecione **Criar regra de** detecção e especifique os seguintes detalhes de alerta:</span><span class="sxs-lookup"><span data-stu-id="e7dc0-130">With the query in the query editor, select **Create detection rule** and specify the following alert details:</span></span>

- <span data-ttu-id="e7dc0-131">**Nome da detecção**— nome da regra de detecção</span><span class="sxs-lookup"><span data-stu-id="e7dc0-131">**Detection name**—name of the detection rule</span></span>
- <span data-ttu-id="e7dc0-132">**Frequência**— intervalo para executar a consulta e executar a ação.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-132">**Frequency**—interval for running the query and taking action.</span></span> [<span data-ttu-id="e7dc0-133">Consulte orientações adicionais abaixo</span><span class="sxs-lookup"><span data-stu-id="e7dc0-133">See additional guidance below</span></span>](#rule-frequency)
- <span data-ttu-id="e7dc0-134">**Título do** alerta — título exibido com alertas disparados pela regra</span><span class="sxs-lookup"><span data-stu-id="e7dc0-134">**Alert title**—title displayed with alerts triggered by the rule</span></span>
- <span data-ttu-id="e7dc0-135">**Severidade**— risco potencial do componente ou atividade identificado pela regra.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-135">**Severity**—potential risk of the component or activity identified by the rule.</span></span> [<span data-ttu-id="e7dc0-136">Ler sobre gravidades de alerta</span><span class="sxs-lookup"><span data-stu-id="e7dc0-136">Read about alert severities</span></span>](alerts-queue.md#severity)
- <span data-ttu-id="e7dc0-137">**Categoria**— tipo de componente ou atividade de ameaça, se for o caso.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-137">**Category**—type of threat component or activity, if any.</span></span> [<span data-ttu-id="e7dc0-138">Ler sobre categorias de alerta</span><span class="sxs-lookup"><span data-stu-id="e7dc0-138">Read about alert categories</span></span>](alerts-queue.md#understanding-alert-categories)
- <span data-ttu-id="e7dc0-139">**O MITRE ATT&** técnicas de CK — uma ou mais técnicas de ataque identificadas pela regra como documentadas na estrutura de CK do MITRE ATT&CK.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-139">**MITRE ATT&CK techniques**—one or more attack techniques identified by the rule as documented in the MITRE ATT&CK framework.</span></span> <span data-ttu-id="e7dc0-140">Esta seção não está disponível com determinadas categorias de alerta, como malware, ransomware, atividade suspeita e software indesejado</span><span class="sxs-lookup"><span data-stu-id="e7dc0-140">This section is not available with certain alert categories, such as malware, ransomware, suspicious activity, and unwanted software</span></span>
- <span data-ttu-id="e7dc0-141">**Descrição**— mais informações sobre o componente ou atividade identificada pela regra</span><span class="sxs-lookup"><span data-stu-id="e7dc0-141">**Description**—more information about the component or activity identified by the rule</span></span> 
- <span data-ttu-id="e7dc0-142">**Ações recomendadas**— ações adicionais que os respondentes podem tomar em resposta a um alerta</span><span class="sxs-lookup"><span data-stu-id="e7dc0-142">**Recommended actions**—additional actions that responders might take in response to an alert</span></span>

<span data-ttu-id="e7dc0-143">Para obter mais informações sobre como os detalhes do alerta são exibidos, [leia sobre a fila de alertas](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="e7dc0-143">For more information about how alert details are displayed, [read about the alert queue](alerts-queue.md).</span></span>

### <a name="rule-frequency"></a><span data-ttu-id="e7dc0-144">Frequência de regra</span><span class="sxs-lookup"><span data-stu-id="e7dc0-144">Rule frequency</span></span>

<span data-ttu-id="e7dc0-145">Quando salva, uma nova regra de detecção personalizada é imediatamente executado e verifica se há combinações dos últimos 30 dias de dados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-145">When saved, a new custom detection rule immediately runs and checks for matches from the past 30 days of data.</span></span> <span data-ttu-id="e7dc0-146">Em seguida, a regra é executado novamente em intervalos fixos e durações de retorno com base na frequência escolhida:</span><span class="sxs-lookup"><span data-stu-id="e7dc0-146">The rule then runs again at fixed intervals and lookback durations based on the frequency you choose:</span></span>

- <span data-ttu-id="e7dc0-147">**A cada 24 horas**— é executado a cada 24 horas, verificando dados dos últimos 30 dias</span><span class="sxs-lookup"><span data-stu-id="e7dc0-147">**Every 24 hours**—runs every 24 hours, checking data from the past 30 days</span></span>
- <span data-ttu-id="e7dc0-148">**A cada 12 horas**— é executado a cada 12 horas, verificando dados das últimas 24 horas</span><span class="sxs-lookup"><span data-stu-id="e7dc0-148">**Every 12 hours**—runs every 12 hours, checking data from the past 24 hours</span></span>
- <span data-ttu-id="e7dc0-149">**A cada 3 horas**— é executado a cada 3 horas, verificando dados das últimas 6 horas</span><span class="sxs-lookup"><span data-stu-id="e7dc0-149">**Every 3 hours**—runs every 3 hours, checking data from the past 6 hours</span></span>
- <span data-ttu-id="e7dc0-150">**A cada hora**— é executado por hora, verificando dados das últimas 2 horas</span><span class="sxs-lookup"><span data-stu-id="e7dc0-150">**Every hour**—runs hourly, checking data from the past 2 hours</span></span>

<span data-ttu-id="e7dc0-151">Quando você editar uma regra, ela será executado com as alterações aplicadas no próximo tempo de executar agendado de acordo com a frequência definida.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-151">When you edit a rule, it will run with the applied changes in the next run time scheduled according to the frequency you set.</span></span>


> [!TIP]
> <span data-ttu-id="e7dc0-152">Match the time filters in your query with the lookback duration.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-152">Match the time filters in your query with the lookback duration.</span></span> <span data-ttu-id="e7dc0-153">Os resultados fora da duração do retorno de pesquisa são ignorados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-153">Results outside of the lookback duration are ignored.</span></span>

<span data-ttu-id="e7dc0-154">Selecione a frequência que corresponde à proximidade com que você deseja monitorar detecções e considere a capacidade da sua organização de responder aos alertas.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-154">Select the frequency that matches how closely you want to monitor detections, and consider your organization's capacity to respond to the alerts.</span></span>

## <a name="3-choose-the-impacted-entities"></a><span data-ttu-id="e7dc0-155">3. Escolha as entidades impactadas.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-155">3. Choose the impacted entities.</span></span>

<span data-ttu-id="e7dc0-156">Identifique as colunas nos resultados da consulta onde você espera encontrar a entidade principal afetada ou afetada.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-156">Identify the columns in your query results where you expect to find the main affected or impacted entity.</span></span> <span data-ttu-id="e7dc0-157">Por exemplo, uma consulta pode retornar IDs de dispositivo e de usuário.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-157">For example, a query might return both device and user IDs.</span></span> <span data-ttu-id="e7dc0-158">Identificar qual dessas colunas representa a entidade principal impactada ajuda o serviço a agregar alertas relevantes, correlacionar incidentes e ações de resposta de destino.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-158">Identifying which of these columns represent the main impacted entity helps the service aggregate relevant alerts, correlate incidents, and target response actions.</span></span>

<span data-ttu-id="e7dc0-159">Você pode selecionar apenas uma coluna para cada tipo de entidade.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-159">You can select only one column for each entity type.</span></span> <span data-ttu-id="e7dc0-160">As colunas que não são retornadas pela consulta não podem ser selecionadas.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-160">Columns that are not returned by your query can't be selected.</span></span>

## <a name="4-specify-actions"></a><span data-ttu-id="e7dc0-161">4. Especifique ações.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-161">4. Specify actions.</span></span>

<span data-ttu-id="e7dc0-162">Sua regra de detecção personalizada pode tomar ações automaticamente em arquivos ou dispositivos retornados pela consulta.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-162">Your custom detection rule can automatically take actions on files or devices that are returned by the query.</span></span>

### <a name="actions-on-devices"></a><span data-ttu-id="e7dc0-163">Ações em dispositivos</span><span class="sxs-lookup"><span data-stu-id="e7dc0-163">Actions on devices</span></span>

<span data-ttu-id="e7dc0-164">Essas ações são aplicadas a dispositivos na `DeviceId` coluna dos resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="e7dc0-164">These actions are applied to devices in the `DeviceId` column of the query results:</span></span>

- <span data-ttu-id="e7dc0-165">**Isolar dispositivo** aplica isolamento total de rede, impedindo que o dispositivo se conecte a qualquer aplicativo ou serviço, exceto para o serviço Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-165">**Isolate device**—applies full network isolation, preventing the device from connecting to any application or service, except for the Defender for Endpoint service.</span></span> [<span data-ttu-id="e7dc0-166">Saiba mais sobre isolamento de dispositivos</span><span class="sxs-lookup"><span data-stu-id="e7dc0-166">Learn more about device isolation</span></span>](respond-machine-alerts.md#isolate-devices-from-the-network)
- <span data-ttu-id="e7dc0-167">**Coletar pacote de investigação**— coleta informações do dispositivo em um arquivo ZIP.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-167">**Collect investigation package**—collects device information in a ZIP file.</span></span> [<span data-ttu-id="e7dc0-168">Saiba mais sobre o pacote de investigação</span><span class="sxs-lookup"><span data-stu-id="e7dc0-168">Learn more about the investigation package</span></span>](respond-machine-alerts.md#collect-investigation-package-from-devices)
- <span data-ttu-id="e7dc0-169">**Executar a verificação antivírus** executa uma verificação completa do Microsoft Defender Antivírus no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e7dc0-169">**Run antivirus scan**—performs a full Microsoft Defender Antivirus scan on the device</span></span>
- <span data-ttu-id="e7dc0-170">**Iniciar investigação**— inicia [uma investigação](automated-investigations.md) automatizada no dispositivo</span><span class="sxs-lookup"><span data-stu-id="e7dc0-170">**Initiate investigation**—starts an [automated investigation](automated-investigations.md) on the device</span></span>
- <span data-ttu-id="e7dc0-171">**Restringir a execução de** aplicativos define restrições no dispositivo para permitir que apenas arquivos assinados com um certificado emitido pela Microsoft sejam executados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-171">**Restrict app execution**—sets restrictions on the device to allow only files that are signed with a Microsoft-issued certificate to run.</span></span> [<span data-ttu-id="e7dc0-172">Saiba mais sobre como restringir a execução de aplicativos</span><span class="sxs-lookup"><span data-stu-id="e7dc0-172">Learn more about restricting app execution</span></span>](respond-machine-alerts.md#restrict-app-execution)

### <a name="actions-on-files"></a><span data-ttu-id="e7dc0-173">Ações em arquivos</span><span class="sxs-lookup"><span data-stu-id="e7dc0-173">Actions on files</span></span>

<span data-ttu-id="e7dc0-174">Essas ações são aplicadas a arquivos na coluna ou nos `SHA1` `InitiatingProcessSHA1` resultados da consulta:</span><span class="sxs-lookup"><span data-stu-id="e7dc0-174">These actions are applied to files in the `SHA1` or the `InitiatingProcessSHA1` column of the query results:</span></span>

- <span data-ttu-id="e7dc0-175">**Allow/Block**— adiciona automaticamente [](manage-indicators.md) o arquivo à sua lista de indicadores personalizados para que ele sempre seja permitido para ser executado ou impedido de ser executado.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-175">**Allow/Block**—automatically adds the file to your [custom indicator list](manage-indicators.md) so that it is always allowed to run or blocked from running.</span></span> <span data-ttu-id="e7dc0-176">Você pode definir o escopo dessa ação para que ela seja tomada somente em grupos de dispositivos selecionados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-176">You can set the scope of this action so that it is taken only on selected device groups.</span></span> <span data-ttu-id="e7dc0-177">Esse escopo é independente do escopo da regra.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-177">This scope is independent of the scope of the rule.</span></span>
- <span data-ttu-id="e7dc0-178">**Arquivo de quarentena**— exclui o arquivo de seu local atual e coloca uma cópia em quarentena</span><span class="sxs-lookup"><span data-stu-id="e7dc0-178">**Quarantine file**—deletes the file from its current location and places a copy in quarantine</span></span>

### <a name="actions-on-users"></a><span data-ttu-id="e7dc0-179">Ações em usuários</span><span class="sxs-lookup"><span data-stu-id="e7dc0-179">Actions on users</span></span>

- <span data-ttu-id="e7dc0-180">**Marcar o usuário como comprometido** define o nível de risco do usuário como "alto" no Azure Active Directory, disparando as políticas de proteção de identidade [correspondentes.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels)</span><span class="sxs-lookup"><span data-stu-id="e7dc0-180">**Mark user as compromised**—sets the user's risk level to "high" in Azure Active Directory, triggering the corresponding [identity protection policies](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection#risk-levels).</span></span>

## <a name="5-set-the-rule-scope"></a><span data-ttu-id="e7dc0-181">5. De definir o escopo da regra.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-181">5. Set the rule scope.</span></span>

<span data-ttu-id="e7dc0-182">De definir o escopo para especificar quais dispositivos são abordados pela regra:</span><span class="sxs-lookup"><span data-stu-id="e7dc0-182">Set the scope to specify which devices are covered by the rule:</span></span>

- <span data-ttu-id="e7dc0-183">Todos os dispositivos</span><span class="sxs-lookup"><span data-stu-id="e7dc0-183">All devices</span></span>
- <span data-ttu-id="e7dc0-184">Grupos de dispositivos específicos</span><span class="sxs-lookup"><span data-stu-id="e7dc0-184">Specific device groups</span></span>

<span data-ttu-id="e7dc0-185">Somente os dados de dispositivos no escopo serão consultados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-185">Only data from devices in scope will be queried.</span></span> <span data-ttu-id="e7dc0-186">Além disso, as ações serão realizadas somente nesses dispositivos.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-186">Also, actions will be taken only on those devices.</span></span>

## <a name="6-review-and-turn-on-the-rule"></a><span data-ttu-id="e7dc0-187">6. Revise e a turn on the rule.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-187">6. Review and turn on the rule.</span></span>

<span data-ttu-id="e7dc0-188">Depois de revisar a regra, selecione **Criar** para salvá-la.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-188">After reviewing the rule, select **Create** to save it.</span></span> <span data-ttu-id="e7dc0-189">A regra de detecção personalizada é imediatamente executado.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-189">The custom detection rule immediately runs.</span></span> <span data-ttu-id="e7dc0-190">Ele é executado novamente com base na frequência configurada para verificar se há resultados, gerar alertas e tomar ações de resposta.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-190">It runs again based on configured frequency to check for matches, generate alerts, and take response actions.</span></span>

<span data-ttu-id="e7dc0-191">Você pode [exibir e gerenciar regras de detecção personalizadas,](custom-detections-manage.md)verificar suas versões anteriores e revisar os alertas disparados.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-191">You can [view and manage custom detection rules](custom-detections-manage.md), check their previous runs, and review the alerts they have triggered.</span></span> <span data-ttu-id="e7dc0-192">Você também pode executar uma regra sob demanda e modificá-la.</span><span class="sxs-lookup"><span data-stu-id="e7dc0-192">You can also run a rule on demand and modify it.</span></span>

## <a name="related-topics"></a><span data-ttu-id="e7dc0-193">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7dc0-193">Related topics</span></span>

- [<span data-ttu-id="e7dc0-194">Exibir e gerenciar regras de detecção personalizadas</span><span class="sxs-lookup"><span data-stu-id="e7dc0-194">View and manage custom detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="e7dc0-195">Visão geral de detecções personalizadas</span><span class="sxs-lookup"><span data-stu-id="e7dc0-195">Custom detections overview</span></span>](overview-custom-detections.md)
- [<span data-ttu-id="e7dc0-196">Visão geral da busca avançada</span><span class="sxs-lookup"><span data-stu-id="e7dc0-196">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="e7dc0-197">Conhecer a linguagem de consulta de busca avançada</span><span class="sxs-lookup"><span data-stu-id="e7dc0-197">Learn the advanced hunting query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="e7dc0-198">Exibir e organizar alertas</span><span class="sxs-lookup"><span data-stu-id="e7dc0-198">View and organize alerts</span></span>](alerts-queue.md)
