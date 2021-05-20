---
title: Lista de incidentes de API no Microsoft 365 Defender
description: Saiba como listar API incidentes no Microsoft 365 Defender
keywords: lista, incidente, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6f0c92371e7e9b7a3348f90df788ee8c3a46374b
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572148"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="6ce64-104">Lista de incidentes de API no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ce64-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="6ce64-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="6ce64-105">**Applies to:**</span></span>

- <span data-ttu-id="6ce64-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ce64-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6ce64-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="6ce64-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="6ce64-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="6ce64-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="6ce64-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="6ce64-109">API description</span></span>

<span data-ttu-id="6ce64-110">A lista de incidentes API permite que você classifique através de incidentes para criar uma resposta de segurança cibernética informada.</span><span class="sxs-lookup"><span data-stu-id="6ce64-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="6ce64-111">Ele expõe uma coleção de incidentes que foram sinalizados em sua rede, dentro do intervalo de tempo especificado na política de retenção do ambiente.</span><span class="sxs-lookup"><span data-stu-id="6ce64-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="6ce64-112">Os incidentes mais recentes são exibidos no topo da lista.</span><span class="sxs-lookup"><span data-stu-id="6ce64-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="6ce64-113">Cada incidente contém uma série de alertas relacionados, e suas entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="6ce64-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="6ce64-114">A API suporta os seguintes operadores **OData:**</span><span class="sxs-lookup"><span data-stu-id="6ce64-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="6ce64-115">`$filter` sobre `lastUpdateTime` `createdTime` , `status` , , e `assignedTo` propriedades</span><span class="sxs-lookup"><span data-stu-id="6ce64-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="6ce64-116">`$top`, com um valor máximo de **100**</span><span class="sxs-lookup"><span data-stu-id="6ce64-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="6ce64-117">Limitações</span><span class="sxs-lookup"><span data-stu-id="6ce64-117">Limitations</span></span>

1. <span data-ttu-id="6ce64-118">O tamanho máximo da página é **de 100 incidentes.**</span><span class="sxs-lookup"><span data-stu-id="6ce64-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="6ce64-119">A taxa máxima de solicitações é de **50 chamadas por minuto** e **1500 chamadas por hora.**</span><span class="sxs-lookup"><span data-stu-id="6ce64-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="6ce64-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="6ce64-120">Permissions</span></span>

<span data-ttu-id="6ce64-121">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="6ce64-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="6ce64-122">Para saber mais, incluindo como escolher permissões, consulte [APIs do Access Microsoft 365 Defender](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="6ce64-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="6ce64-123">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="6ce64-123">Permission type</span></span> | <span data-ttu-id="6ce64-124">Permissão</span><span class="sxs-lookup"><span data-stu-id="6ce64-124">Permission</span></span> | <span data-ttu-id="6ce64-125">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="6ce64-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="6ce64-126">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="6ce64-126">Application</span></span> | <span data-ttu-id="6ce64-127">Incidente.Read.Todos</span><span class="sxs-lookup"><span data-stu-id="6ce64-127">Incident.Read.All</span></span> | <span data-ttu-id="6ce64-128">Leia todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="6ce64-128">Read all incidents</span></span>
<span data-ttu-id="6ce64-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="6ce64-129">Application</span></span> | <span data-ttu-id="6ce64-130">Incidente.ReadWrite.Todos</span><span class="sxs-lookup"><span data-stu-id="6ce64-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="6ce64-131">Leia e escreva todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="6ce64-131">Read and write all incidents</span></span>
<span data-ttu-id="6ce64-132">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="6ce64-132">Delegated (work or school account)</span></span> | <span data-ttu-id="6ce64-133">Incidente.Leia</span><span class="sxs-lookup"><span data-stu-id="6ce64-133">Incident.Read</span></span> | <span data-ttu-id="6ce64-134">Leia incidentes</span><span class="sxs-lookup"><span data-stu-id="6ce64-134">Read incidents</span></span>
<span data-ttu-id="6ce64-135">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="6ce64-135">Delegated (work or school account)</span></span> | <span data-ttu-id="6ce64-136">Incidente.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="6ce64-136">Incident.ReadWrite</span></span> | <span data-ttu-id="6ce64-137">Leia e escreva incidentes</span><span class="sxs-lookup"><span data-stu-id="6ce64-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="6ce64-138">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="6ce64-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="6ce64-139">O usuário precisa ter permissão de visualização para incidentes no portal.</span><span class="sxs-lookup"><span data-stu-id="6ce64-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="6ce64-140">A resposta incluirá apenas incidentes aos que o usuário está exposto.</span><span class="sxs-lookup"><span data-stu-id="6ce64-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="6ce64-141">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="6ce64-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="6ce64-142">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="6ce64-142">Request headers</span></span>

<span data-ttu-id="6ce64-143">Nome</span><span class="sxs-lookup"><span data-stu-id="6ce64-143">Name</span></span> | <span data-ttu-id="6ce64-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="6ce64-144">Type</span></span> | <span data-ttu-id="6ce64-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ce64-145">Description</span></span>
-|-|-
<span data-ttu-id="6ce64-146">Autorização</span><span class="sxs-lookup"><span data-stu-id="6ce64-146">Authorization</span></span> | <span data-ttu-id="6ce64-147">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6ce64-147">String</span></span> | <span data-ttu-id="6ce64-148">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="6ce64-148">Bearer {token}.</span></span> <span data-ttu-id="6ce64-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="6ce64-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="6ce64-150">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="6ce64-150">Request body</span></span>

<span data-ttu-id="6ce64-151">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6ce64-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="6ce64-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="6ce64-152">Response</span></span>

<span data-ttu-id="6ce64-153">Se for bem sucedido, este método retorna `200 OK` , e uma lista de [incidentes](api-incident.md) no corpo de resposta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="6ce64-154">Mapeamento de esquemas</span><span class="sxs-lookup"><span data-stu-id="6ce64-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="6ce64-155">Metadados incidentes</span><span class="sxs-lookup"><span data-stu-id="6ce64-155">Incident metadata</span></span>

<span data-ttu-id="6ce64-156">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="6ce64-156">Field name</span></span> | <span data-ttu-id="6ce64-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ce64-157">Description</span></span> | <span data-ttu-id="6ce64-158">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="6ce64-158">Example value</span></span>
-|-|-
<span data-ttu-id="6ce64-159">incidenteId</span><span class="sxs-lookup"><span data-stu-id="6ce64-159">incidentId</span></span> | <span data-ttu-id="6ce64-160">Identificador único para representar o incidente</span><span class="sxs-lookup"><span data-stu-id="6ce64-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="6ce64-161">924565</span><span class="sxs-lookup"><span data-stu-id="6ce64-161">924565</span></span>
<span data-ttu-id="6ce64-162">redirecionarIncidentId</span><span class="sxs-lookup"><span data-stu-id="6ce64-162">redirectIncidentId</span></span> | <span data-ttu-id="6ce64-163">Só povoado no caso de um incidente estiver sendo agrupado com outro incidente, como parte da lógica de processamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="6ce64-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="6ce64-164">924569</span><span class="sxs-lookup"><span data-stu-id="6ce64-164">924569</span></span>
<span data-ttu-id="6ce64-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="6ce64-165">incidentName</span></span> | <span data-ttu-id="6ce64-166">Valor de sequência disponível para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="6ce64-166">String value available for every incident.</span></span> | <span data-ttu-id="6ce64-167">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="6ce64-167">Ransomware activity</span></span>
<span data-ttu-id="6ce64-168">criadoTime</span><span class="sxs-lookup"><span data-stu-id="6ce64-168">createdTime</span></span> | <span data-ttu-id="6ce64-169">Tempo em que o incidente foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="6ce64-169">Time when incident was first created.</span></span> | <span data-ttu-id="6ce64-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="6ce64-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="6ce64-171">lastUpdateTime</span></span> | <span data-ttu-id="6ce64-172">Tempo quando o incidente foi atualizado pela última vez no backend.</span><span class="sxs-lookup"><span data-stu-id="6ce64-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="6ce64-173">Este campo pode ser usado quando você está definindo o parâmetro de solicitação para o intervalo de tempo que os incidentes são recuperados.</span><span class="sxs-lookup"><span data-stu-id="6ce64-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="6ce64-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="6ce64-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6ce64-175">assignedTo</span></span> | <span data-ttu-id="6ce64-176">Dono do incidente, ou *nulo* se nenhum proprietário for designado.</span><span class="sxs-lookup"><span data-stu-id="6ce64-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="6ce64-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ce64-177">secop2@contoso.com</span></span>
<span data-ttu-id="6ce64-178">classificação</span><span class="sxs-lookup"><span data-stu-id="6ce64-178">classification</span></span> | <span data-ttu-id="6ce64-179">A especificação para o incidente.</span><span class="sxs-lookup"><span data-stu-id="6ce64-179">The specification for the incident.</span></span> <span data-ttu-id="6ce64-180">Os valores da propriedade são: *Desconhecido,* *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="6ce64-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="6ce64-181">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="6ce64-181">Unknown</span></span>
<span data-ttu-id="6ce64-182">determinação</span><span class="sxs-lookup"><span data-stu-id="6ce64-182">determination</span></span> | <span data-ttu-id="6ce64-183">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="6ce64-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="6ce64-184">Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware,* *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Outros*</span><span class="sxs-lookup"><span data-stu-id="6ce64-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="6ce64-185">Não disponível</span><span class="sxs-lookup"><span data-stu-id="6ce64-185">NotAvailable</span></span>
<span data-ttu-id="6ce64-186">status</span><span class="sxs-lookup"><span data-stu-id="6ce64-186">status</span></span> | <span data-ttu-id="6ce64-187">Categorizar incidentes (como *Ativo*, ou *Resolvido*).</span><span class="sxs-lookup"><span data-stu-id="6ce64-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="6ce64-188">Ele pode ajudá-lo a organizar e gerenciar sua resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="6ce64-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="6ce64-189">Ativa</span><span class="sxs-lookup"><span data-stu-id="6ce64-189">Active</span></span>
<span data-ttu-id="6ce64-190">severity</span><span class="sxs-lookup"><span data-stu-id="6ce64-190">severity</span></span> | <span data-ttu-id="6ce64-191">Indica o possível impacto sobre os ativos.</span><span class="sxs-lookup"><span data-stu-id="6ce64-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="6ce64-192">Quanto maior a gravidade, maior o impacto.</span><span class="sxs-lookup"><span data-stu-id="6ce64-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="6ce64-193">Normalmente, itens de maior gravidade requerem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="6ce64-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="6ce64-194">Um dos seguintes valores: *Informativo,* *Baixo*, \*Médio e *Alto*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="6ce64-195">Médio</span><span class="sxs-lookup"><span data-stu-id="6ce64-195">Medium</span></span>
<span data-ttu-id="6ce64-196">tags</span><span class="sxs-lookup"><span data-stu-id="6ce64-196">tags</span></span> | <span data-ttu-id="6ce64-197">Matriz de etiquetas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.</span><span class="sxs-lookup"><span data-stu-id="6ce64-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="6ce64-198">comentários</span><span class="sxs-lookup"><span data-stu-id="6ce64-198">comments</span></span> | <span data-ttu-id="6ce64-199">Conjunto de comentários criados por secops ao gerenciar o incidente, por exemplo, informações adicionais sobre a seleção de classificação.</span><span class="sxs-lookup"><span data-stu-id="6ce64-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="6ce64-200">alerts</span><span class="sxs-lookup"><span data-stu-id="6ce64-200">alerts</span></span> | <span data-ttu-id="6ce64-201">Matriz contendo todos os alertas relacionados ao incidente, além de outras informações, como gravidade, entidades envolvidas no alerta e a origem dos alertas.</span><span class="sxs-lookup"><span data-stu-id="6ce64-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="6ce64-202">\[\] (veja detalhes sobre os campos de alerta abaixo)</span><span class="sxs-lookup"><span data-stu-id="6ce64-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="6ce64-203">Alertas de metadados</span><span class="sxs-lookup"><span data-stu-id="6ce64-203">Alerts metadata</span></span>

<span data-ttu-id="6ce64-204">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="6ce64-204">Field name</span></span> | <span data-ttu-id="6ce64-205">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ce64-205">Description</span></span> | <span data-ttu-id="6ce64-206">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="6ce64-206">Example value</span></span>
-|-|-
<span data-ttu-id="6ce64-207">alertId</span><span class="sxs-lookup"><span data-stu-id="6ce64-207">alertId</span></span> | <span data-ttu-id="6ce64-208">Identificador único para representar o alerta</span><span class="sxs-lookup"><span data-stu-id="6ce64-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="6ce64-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="6ce64-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="6ce64-210">incidenteId</span><span class="sxs-lookup"><span data-stu-id="6ce64-210">incidentId</span></span> | <span data-ttu-id="6ce64-211">Identificador único para representar o incidente este alerta está associado a</span><span class="sxs-lookup"><span data-stu-id="6ce64-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="6ce64-212">924565</span><span class="sxs-lookup"><span data-stu-id="6ce64-212">924565</span></span>
<span data-ttu-id="6ce64-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="6ce64-213">serviceSource</span></span> | <span data-ttu-id="6ce64-214">Serviço do que o alerta se origina, como Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity ou Microsoft Defender for Office 365.</span><span class="sxs-lookup"><span data-stu-id="6ce64-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="6ce64-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="6ce64-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="6ce64-216">criaçãoTime</span><span class="sxs-lookup"><span data-stu-id="6ce64-216">creationTime</span></span> | <span data-ttu-id="6ce64-217">Tempo em que o alerta foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="6ce64-217">Time when alert was first created.</span></span> | <span data-ttu-id="6ce64-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="6ce64-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="6ce64-219">lastUpdatedTime</span></span> | <span data-ttu-id="6ce64-220">Tempo em que o alerta foi atualizado pela última vez no backend.</span><span class="sxs-lookup"><span data-stu-id="6ce64-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="6ce64-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="6ce64-222">tempo resolvido</span><span class="sxs-lookup"><span data-stu-id="6ce64-222">resolvedTime</span></span> | <span data-ttu-id="6ce64-223">Tempo em que o alerta foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="6ce64-223">Time when alert was resolved.</span></span> | <span data-ttu-id="6ce64-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="6ce64-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="6ce64-225">firstActivity</span></span> | <span data-ttu-id="6ce64-226">Tempo em que o alerta informou pela primeira vez que a atividade foi atualizada no backend.</span><span class="sxs-lookup"><span data-stu-id="6ce64-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="6ce64-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="6ce64-228">title</span><span class="sxs-lookup"><span data-stu-id="6ce64-228">title</span></span> | <span data-ttu-id="6ce64-229">Breve identifique o valor da sequência disponível para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="6ce64-230">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="6ce64-230">Ransomware activity</span></span>
<span data-ttu-id="6ce64-231">descrição</span><span class="sxs-lookup"><span data-stu-id="6ce64-231">description</span></span> | <span data-ttu-id="6ce64-232">Valor de sequência descrevendo cada alerta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-232">String value describing each alert.</span></span> | <span data-ttu-id="6ce64-233">O usuário Test User2 (testUser2@contoso.com) manipulou 99 arquivos com várias extensões terminando com a extensão incomum *herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="6ce64-234">Este é um número incomum de manipulações de arquivos e é um indicativo de um potencial ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="6ce64-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="6ce64-235">category</span><span class="sxs-lookup"><span data-stu-id="6ce64-235">category</span></span> | <span data-ttu-id="6ce64-236">Visão visual e numérica de quão longe o ataque progrediu ao longo da cadeia de morte.</span><span class="sxs-lookup"><span data-stu-id="6ce64-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="6ce64-237">Alinhado ao [quadro mitre ATT&CK™](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="6ce64-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="6ce64-238">Impacto</span><span class="sxs-lookup"><span data-stu-id="6ce64-238">Impact</span></span>
<span data-ttu-id="6ce64-239">status</span><span class="sxs-lookup"><span data-stu-id="6ce64-239">status</span></span> | <span data-ttu-id="6ce64-240">Classificar alertas (como *Novo,* *Ativo* ou *Resolvido*).</span><span class="sxs-lookup"><span data-stu-id="6ce64-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="6ce64-241">Ele pode ajudá-lo a organizar e gerenciar sua resposta aos alertas.</span><span class="sxs-lookup"><span data-stu-id="6ce64-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="6ce64-242">Novo</span><span class="sxs-lookup"><span data-stu-id="6ce64-242">New</span></span>
<span data-ttu-id="6ce64-243">severity</span><span class="sxs-lookup"><span data-stu-id="6ce64-243">severity</span></span> | <span data-ttu-id="6ce64-244">Indica o possível impacto sobre os ativos.</span><span class="sxs-lookup"><span data-stu-id="6ce64-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="6ce64-245">Quanto maior a gravidade, maior o impacto.</span><span class="sxs-lookup"><span data-stu-id="6ce64-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="6ce64-246">Normalmente, itens de maior gravidade requerem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="6ce64-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="6ce64-247">Um dos seguintes valores: *Informativo,* *Baixo*, \*Médio e *Alto*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="6ce64-248">Médio</span><span class="sxs-lookup"><span data-stu-id="6ce64-248">Medium</span></span>
<span data-ttu-id="6ce64-249">investigaçãoId</span><span class="sxs-lookup"><span data-stu-id="6ce64-249">investigationId</span></span> | <span data-ttu-id="6ce64-250">A ID de investigação automatizada desencadeada por este alerta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="6ce64-251">1234</span><span class="sxs-lookup"><span data-stu-id="6ce64-251">1234</span></span>
<span data-ttu-id="6ce64-252">investigaçãoEstia</span><span class="sxs-lookup"><span data-stu-id="6ce64-252">investigationState</span></span> | <span data-ttu-id="6ce64-253">Informações sobre o estado atual da investigação.</span><span class="sxs-lookup"><span data-stu-id="6ce64-253">Information on the investigation's current status.</span></span> <span data-ttu-id="6ce64-254">Um dos seguintes valores: *Desconhecido*, *Encerrado*, *Com sucesso, Remediado*, *Benigno*, *Falho*, *Parcialmente Remediado*, *Execução*, *Pendentes,* *PendentesResource*, *Parcialmente Investigado*, *EncerradoByUser*, *EncerradoBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnupportedAlertType*, *SuppressedAlert*. </span><span class="sxs-lookup"><span data-stu-id="6ce64-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="6ce64-255">Sem suporteAlertType</span><span class="sxs-lookup"><span data-stu-id="6ce64-255">UnsupportedAlertType</span></span>
<span data-ttu-id="6ce64-256">classificação</span><span class="sxs-lookup"><span data-stu-id="6ce64-256">classification</span></span> | <span data-ttu-id="6ce64-257">A especificação para o incidente.</span><span class="sxs-lookup"><span data-stu-id="6ce64-257">The specification for the incident.</span></span> <span data-ttu-id="6ce64-258">Os valores da propriedade são: *Desconhecido,* *FalsoPositivo,* *TruePositive* ou *nulo*</span><span class="sxs-lookup"><span data-stu-id="6ce64-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="6ce64-259">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="6ce64-259">Unknown</span></span>
<span data-ttu-id="6ce64-260">determinação</span><span class="sxs-lookup"><span data-stu-id="6ce64-260">determination</span></span> | <span data-ttu-id="6ce64-261">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="6ce64-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="6ce64-262">Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware,* *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Outros* ou  *nulos*</span><span class="sxs-lookup"><span data-stu-id="6ce64-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="6ce64-263">apto</span><span class="sxs-lookup"><span data-stu-id="6ce64-263">Apt</span></span>
<span data-ttu-id="6ce64-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="6ce64-264">assignedTo</span></span> | <span data-ttu-id="6ce64-265">Dono do incidente, ou *nulo* se nenhum proprietário for designado.</span><span class="sxs-lookup"><span data-stu-id="6ce64-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="6ce64-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ce64-266">secop2@contoso.com</span></span>
<span data-ttu-id="6ce64-267">nome do ator</span><span class="sxs-lookup"><span data-stu-id="6ce64-267">actorName</span></span> | <span data-ttu-id="6ce64-268">O grupo de atividades, se houver, está associado a este alerta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="6ce64-269">boro</span><span class="sxs-lookup"><span data-stu-id="6ce64-269">BORON</span></span>
<span data-ttu-id="6ce64-270">ameaçaFamilyName</span><span class="sxs-lookup"><span data-stu-id="6ce64-270">threatFamilyName</span></span> | <span data-ttu-id="6ce64-271">Família de ameaças associada a este alerta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="6ce64-272">null</span><span class="sxs-lookup"><span data-stu-id="6ce64-272">null</span></span>
<span data-ttu-id="6ce64-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="6ce64-273">mitreTechniques</span></span> | <span data-ttu-id="6ce64-274">As técnicas de ataque, alinhadas com a estrutura [de ™ MITRE ATT&CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="6ce64-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="6ce64-275">Dispositivos</span><span class="sxs-lookup"><span data-stu-id="6ce64-275">devices</span></span> | <span data-ttu-id="6ce64-276">Todos os dispositivos para onde foram enviados alertas relacionados ao incidente.</span><span class="sxs-lookup"><span data-stu-id="6ce64-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="6ce64-277">\[\] (veja detalhes sobre os campos da entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="6ce64-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="6ce64-278">Formato do dispositivo</span><span class="sxs-lookup"><span data-stu-id="6ce64-278">Device format</span></span>

<span data-ttu-id="6ce64-279">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="6ce64-279">Field name</span></span> | <span data-ttu-id="6ce64-280">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ce64-280">Description</span></span> | <span data-ttu-id="6ce64-281">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="6ce64-281">Example value</span></span>
-|-|-
<span data-ttu-id="6ce64-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="6ce64-282">DeviceId</span></span> | <span data-ttu-id="6ce64-283">O ID do dispositivo como designado no Microsoft Defender para Endpoint.</span><span class="sxs-lookup"><span data-stu-id="6ce64-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="6ce64-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="6ce64-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="6ce64-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="6ce64-285">aadDeviceId</span></span> |  <span data-ttu-id="6ce64-286">O ID do dispositivo como designado em [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="6ce64-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="6ce64-287">Disponível apenas para dispositivos de domínio.</span><span class="sxs-lookup"><span data-stu-id="6ce64-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="6ce64-288">null</span><span class="sxs-lookup"><span data-stu-id="6ce64-288">null</span></span>
<span data-ttu-id="6ce64-289">dispositivoDnsName</span><span class="sxs-lookup"><span data-stu-id="6ce64-289">deviceDnsName</span></span> | <span data-ttu-id="6ce64-290">O nome de domínio totalmente qualificado para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ce64-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="6ce64-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ce64-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="6ce64-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="6ce64-292">osPlatform</span></span> | <span data-ttu-id="6ce64-293">A plataforma operacional que o dispositivo está executando.</span><span class="sxs-lookup"><span data-stu-id="6ce64-293">The OS platform the device is running.</span></span>| <span data-ttu-id="6ce64-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="6ce64-294">WindowsServer2016</span></span>
<span data-ttu-id="6ce64-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="6ce64-295">osBuild</span></span> | <span data-ttu-id="6ce64-296">A versão de compilação para o SISTEMA OPERACIONAL o dispositivo está em execução.</span><span class="sxs-lookup"><span data-stu-id="6ce64-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="6ce64-297">14393</span><span class="sxs-lookup"><span data-stu-id="6ce64-297">14393</span></span>
<span data-ttu-id="6ce64-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="6ce64-298">rbacGroupName</span></span> | <span data-ttu-id="6ce64-299">O grupo [de controle de acesso baseado em papel](/azure/role-based-access-control/overview) (RBAC) associado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ce64-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="6ce64-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="6ce64-300">WDATP-Ring0</span></span>
<span data-ttu-id="6ce64-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="6ce64-301">firstSeen</span></span> | <span data-ttu-id="6ce64-302">Tempo em que o dispositivo foi visto pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="6ce64-302">Time when device was first seen.</span></span> | <span data-ttu-id="6ce64-303">020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="6ce64-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="6ce64-304">healthStatus</span></span> | <span data-ttu-id="6ce64-305">O estado de saúde do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ce64-305">The health state of the device.</span></span> | <span data-ttu-id="6ce64-306">Ativa</span><span class="sxs-lookup"><span data-stu-id="6ce64-306">Active</span></span>
<span data-ttu-id="6ce64-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="6ce64-307">riskScore</span></span> | <span data-ttu-id="6ce64-308">A pontuação de risco para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6ce64-308">The risk score for the  device.</span></span> | <span data-ttu-id="6ce64-309">Alto</span><span class="sxs-lookup"><span data-stu-id="6ce64-309">High</span></span>
<span data-ttu-id="6ce64-310">Entidades</span><span class="sxs-lookup"><span data-stu-id="6ce64-310">entities</span></span> | <span data-ttu-id="6ce64-311">Todas as entidades identificadas fazem parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="6ce64-312">\[\] (veja detalhes sobre os campos da entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="6ce64-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="6ce64-313">Formato da entidade</span><span class="sxs-lookup"><span data-stu-id="6ce64-313">Entity Format</span></span>

<span data-ttu-id="6ce64-314">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="6ce64-314">Field name</span></span> | <span data-ttu-id="6ce64-315">Descrição</span><span class="sxs-lookup"><span data-stu-id="6ce64-315">Description</span></span> | <span data-ttu-id="6ce64-316">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="6ce64-316">Example value</span></span>
-|-|-
<span data-ttu-id="6ce64-317">entidadeType</span><span class="sxs-lookup"><span data-stu-id="6ce64-317">entityType</span></span> | <span data-ttu-id="6ce64-318">Entidades identificadas como parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="6ce64-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="6ce64-319">Os valores das propriedades são: *Usuário*, *Ip,* *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registro*</span><span class="sxs-lookup"><span data-stu-id="6ce64-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="6ce64-320">Usuário</span><span class="sxs-lookup"><span data-stu-id="6ce64-320">User</span></span>
<span data-ttu-id="6ce64-321">sha1</span><span class="sxs-lookup"><span data-stu-id="6ce64-321">sha1</span></span> | <span data-ttu-id="6ce64-322">Disponível se a entidadeType for *File*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="6ce64-323">O hash do arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="6ce64-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="6ce64-324">5de83918691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="6ce64-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="6ce64-325">sha256</span><span class="sxs-lookup"><span data-stu-id="6ce64-325">sha256</span></span> | <span data-ttu-id="6ce64-326">Disponível se a entidadeType for *File*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="6ce64-327">O hash do arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="6ce64-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="6ce64-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="6ce64-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="6ce64-329">fileName</span><span class="sxs-lookup"><span data-stu-id="6ce64-329">fileName</span></span> | <span data-ttu-id="6ce64-330">Disponível se a entidadeType for *File*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="6ce64-331">O nome do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="6ce64-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="6ce64-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="6ce64-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="6ce64-333">filePath</span><span class="sxs-lookup"><span data-stu-id="6ce64-333">filePath</span></span> | <span data-ttu-id="6ce64-334">Disponível se a entidadeType for *File*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="6ce64-335">O caminho do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="6ce64-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="6ce64-336">C: \\ \agent_work_temp\Implantar\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="6ce64-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="6ce64-337">processId</span><span class="sxs-lookup"><span data-stu-id="6ce64-337">processId</span></span> | <span data-ttu-id="6ce64-338">Disponível se a entidadeType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6ce64-339">24348</span><span class="sxs-lookup"><span data-stu-id="6ce64-339">24348</span></span>
<span data-ttu-id="6ce64-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="6ce64-340">processCommandLine</span></span> | <span data-ttu-id="6ce64-341">Disponível se a entidadeType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6ce64-342">"Seu arquivo está pronto para baixar \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="6ce64-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="6ce64-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="6ce64-343">processCreationTime</span></span> | <span data-ttu-id="6ce64-344">Disponível se a entidadeType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6ce64-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="6ce64-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="6ce64-346">parentProcessId</span></span> | <span data-ttu-id="6ce64-347">Disponível se a entidadeType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6ce64-348">16840</span><span class="sxs-lookup"><span data-stu-id="6ce64-348">16840</span></span>
<span data-ttu-id="6ce64-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="6ce64-349">parentProcessCreationTime</span></span> | <span data-ttu-id="6ce64-350">Disponível se a entidadeType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="6ce64-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="6ce64-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="6ce64-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="6ce64-352">ipAddress</span></span> | <span data-ttu-id="6ce64-353">Disponível se a entidadeType for *Ip*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="6ce64-354">Endereço IP para alertas associados a eventos de rede, como *comunicação a um destino de rede malicioso*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="6ce64-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="6ce64-355">62.216.203.204</span></span>
<span data-ttu-id="6ce64-356">url</span><span class="sxs-lookup"><span data-stu-id="6ce64-356">url</span></span> | <span data-ttu-id="6ce64-357">Disponível se a entidadeType é *Url*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="6ce64-358">URL para alertas associados a eventos de rede, como, *Comunicação para um destino de rede malicioso*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="6ce64-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="6ce64-359">down.esales360.cn</span></span>
<span data-ttu-id="6ce64-360">accountName</span><span class="sxs-lookup"><span data-stu-id="6ce64-360">accountName</span></span> | <span data-ttu-id="6ce64-361">Disponível se a entidadeType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="6ce64-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="6ce64-362">testUser2</span></span>
<span data-ttu-id="6ce64-363">domainName</span><span class="sxs-lookup"><span data-stu-id="6ce64-363">domainName</span></span> | <span data-ttu-id="6ce64-364">Disponível se a entidadeType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="6ce64-365">europa.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="6ce64-365">europe.corp.contoso</span></span>
<span data-ttu-id="6ce64-366">userSid</span><span class="sxs-lookup"><span data-stu-id="6ce64-366">userSid</span></span> | <span data-ttu-id="6ce64-367">Disponível se a entidadeType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="6ce64-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="6ce64-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="6ce64-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="6ce64-369">aadUserId</span></span> | <span data-ttu-id="6ce64-370">Disponível se a entidadeType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="6ce64-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="6ce64-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="6ce64-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="6ce64-372">userPrincipalName</span></span> | <span data-ttu-id="6ce64-373">Disponível se a entidadeType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6ce64-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ce64-374">testUser2@contoso.com</span></span>
<span data-ttu-id="6ce64-375">caixa de correioDisplayName</span><span class="sxs-lookup"><span data-stu-id="6ce64-375">mailboxDisplayName</span></span> | <span data-ttu-id="6ce64-376">Disponível se a entidadeType for *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="6ce64-377">teste Usuário2</span><span class="sxs-lookup"><span data-stu-id="6ce64-377">test User2</span></span>
<span data-ttu-id="6ce64-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="6ce64-378">mailboxAddress</span></span> | <span data-ttu-id="6ce64-379">Disponível se a entidadeType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6ce64-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ce64-380">testUser2@contoso.com</span></span>
<span data-ttu-id="6ce64-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="6ce64-381">clusterBy</span></span> | <span data-ttu-id="6ce64-382">Disponível se a entidadeType for  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="6ce64-383">Assunto; P2SenderDomain; Tipo de conteúdo</span><span class="sxs-lookup"><span data-stu-id="6ce64-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="6ce64-384">remetente</span><span class="sxs-lookup"><span data-stu-id="6ce64-384">sender</span></span> | <span data-ttu-id="6ce64-385">Disponível se a entidadeType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="6ce64-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="6ce64-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="6ce64-387">destinatário</span><span class="sxs-lookup"><span data-stu-id="6ce64-387">recipient</span></span> | <span data-ttu-id="6ce64-388">Disponível se a entidadeType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6ce64-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="6ce64-389">testUser2@contoso.com</span></span>
<span data-ttu-id="6ce64-390">Assunto</span><span class="sxs-lookup"><span data-stu-id="6ce64-390">subject</span></span> | <span data-ttu-id="6ce64-391">Disponível se a entidadeType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6ce64-392">\[Atenção EXTERNA \]</span><span class="sxs-lookup"><span data-stu-id="6ce64-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="6ce64-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="6ce64-393">deliveryAction</span></span> | <span data-ttu-id="6ce64-394">Disponível se a entidadeType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="6ce64-395">Entregue</span><span class="sxs-lookup"><span data-stu-id="6ce64-395">Delivered</span></span>
<span data-ttu-id="6ce64-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="6ce64-396">securityGroupId</span></span> | <span data-ttu-id="6ce64-397">Disponível se a entidadeType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="6ce64-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="6ce64-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="6ce64-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="6ce64-399">securityGroupName</span></span> | <span data-ttu-id="6ce64-400">Disponível se a entidadeType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="6ce64-401">Operadores de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="6ce64-401">Network Configuration Operators</span></span>
<span data-ttu-id="6ce64-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="6ce64-402">registryHive</span></span> | <span data-ttu-id="6ce64-403">Disponível se a entidadeType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6ce64-404">MÁQUINA LOCAL HKEY \_ \_</span><span class="sxs-lookup"><span data-stu-id="6ce64-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="6ce64-405">registroKey</span><span class="sxs-lookup"><span data-stu-id="6ce64-405">registryKey</span></span> | <span data-ttu-id="6ce64-406">Disponível se a entidadeType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6ce64-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="6ce64-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="6ce64-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="6ce64-408">registryValueType</span></span> | <span data-ttu-id="6ce64-409">Disponível se a entidadeType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6ce64-410">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="6ce64-410">String</span></span>
<span data-ttu-id="6ce64-411">registroVasse</span><span class="sxs-lookup"><span data-stu-id="6ce64-411">registryValue</span></span> | <span data-ttu-id="6ce64-412">Disponível se a entidadeType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="6ce64-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="6ce64-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="6ce64-413">31-00-00-00</span></span>
<span data-ttu-id="6ce64-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="6ce64-414">deviceId</span></span> | <span data-ttu-id="6ce64-415">O ID, se houver, do dispositivo relacionado à entidade.</span><span class="sxs-lookup"><span data-stu-id="6ce64-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="6ce64-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="6ce64-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="6ce64-417">Exemplo</span><span class="sxs-lookup"><span data-stu-id="6ce64-417">Example</span></span>

<span data-ttu-id="6ce64-418">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="6ce64-418">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="6ce64-419">**Response**</span><span class="sxs-lookup"><span data-stu-id="6ce64-419">**Response**</span></span>

```json
{
    "@odata.context": "https://api.security.microsoft.com/api/$metadata#Incidents",
    "value": [
            {
            "incidentId": 924565,
            "redirectIncidentId": null,
            "incidentName": "Ransomware activity",
            "createdTime": "2020-09-06T14:46:57.0733333Z",
            "lastUpdateTime": "2020-09-06T14:46:57.29Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Medium",
            "tags": [],
            "comments": [
                {
                    "comment": "test comment for docs",
                    "createdBy": "secop123@contoso.com",
                    "createdTime": "2021-01-26T01:00:37.8404534Z"
                }
            ],
            "alerts": [
                {
                    "alertId": "caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC",
                    "incidentId": 924565,
                    "serviceSource": "MicrosoftCloudAppSecurity",
                    "creationTime": "2020-09-06T14:46:55.7182276Z",
                    "lastUpdatedTime": "2020-09-06T14:46:57.2433333Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-04T05:22:59Z",
                    "lastActivity": "2020-09-04T05:22:59Z",
                    "title": "Ransomware activity",
                    "description": "The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension herunterladen. This is an unusual number of file manipulations and is indicative of a potential ransomware attack.",
                    "category": "Impact",
                    "status": "New",
                    "severity": "Medium",
                    "investigationId": null,
                    "investigationState": "UnsupportedAlertType",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "MCAS",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "User",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": "testUser2",
                            "domainName": "europe.corp.contoso",
                            "userSid": "S-1-5-21-1721254763-462695806-1538882281-4156657",
                            "aadUserId": "fc8f7484-f813-4db2-afab-bc1507913fb6",
                            "userPrincipalName": "testUser2@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "62.216.203.204",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924521,
            "redirectIncidentId": null,
            "incidentName": "'Mimikatz' hacktool was detected on one endpoint",
            "createdTime": "2020-09-06T12:18:03.6266667Z",
            "lastUpdateTime": "2020-09-06T12:18:03.81Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Low",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "da637349914833441527_393341063",
                    "incidentId": 924521,
                    "serviceSource": "MicrosoftDefenderATP",
                    "creationTime": "2020-09-06T12:18:03.3285366Z",
                    "lastUpdatedTime": "2020-09-06T12:18:04.2566667Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:15:07.7272048Z",
                    "lastActivity": "2020-09-06T12:15:07.7272048Z",
                    "title": "'Mimikatz' hacktool was detected",
                    "description": "Readily available tools, such as hacking programs, can be used by unauthorized individuals to spy on users. When used by attackers, these tools are often installed without authorization and used to compromise targeted machines.\n\nThese tools are often used to collect personal information from browser records, record key presses, access email and instant messages, record voice and video conversations, and take screenshots.\n\nThis detection might indicate that Windows Defender Antivirus has stopped the tool from being installed and used effectively. However, it is prudent to check the machine for the files and processes associated with the detected tool.",
                    "category": "Malware",
                    "status": "New",
                    "severity": "Low",
                    "investigationId": null,
                    "investigationState": "UnsupportedOs",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "WindowsDefenderAv",
                    "assignedTo": null,
                    "actorName": null,
                    "threatFamilyName": "Mimikatz",
                    "mitreTechniques": [],
                    "devices": [
                        {
                            "mdatpDeviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491",
                            "aadDeviceId": null,
                            "deviceDnsName": "user5cx.middleeast.corp.contoso.com",
                            "osPlatform": "WindowsServer2016",
                            "version": "1607",
                            "osProcessor": "x64",
                            "osBuild": 14393,
                            "healthStatus": "Active",
                            "riskScore": "High",
                            "rbacGroupName": "WDATP-Ring0",
                            "rbacGroupId": 9,
                            "firstSeen": "2020-02-06T14:16:01.9330135Z"
                        }
                    ],
                    "entities": [
                        {
                            "entityType": "File",
                            "sha1": "5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd",
                            "sha256": null,
                            "fileName": "Detector.UnitTests.dll",
                            "filePath": "C:\\Agent\\_work\\_temp\\Deploy_SYSTEM 2020-09-06 12_14_54\\Out",
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": "24c222b0b60fe148eeece49ac83910cc6a7ef491"
                        }
                    ]
                }
            ]
        },
        {
            "incidentId": 924518,
            "redirectIncidentId": null,
            "incidentName": "Email reported by user as malware or phish",
            "createdTime": "2020-09-06T12:07:55.1366667Z",
            "lastUpdateTime": "2020-09-06T12:07:55.32Z",
            "assignedTo": null,
            "classification": "Unknown",
            "determination": "NotAvailable",
            "status": "Active",
            "severity": "Informational",
            "tags": [],
            "comments": [],
            "alerts": [
                {
                    "alertId": "faf8edc936-85f8-a603-b800-08d8525cf099",
                    "incidentId": 924518,
                    "serviceSource": "OfficeATP",
                    "creationTime": "2020-09-06T12:07:54.3716642Z",
                    "lastUpdatedTime": "2020-09-06T12:37:40.88Z",
                    "resolvedTime": null,
                    "firstActivity": "2020-09-06T12:04:00Z",
                    "lastActivity": "2020-09-06T12:04:00Z",
                    "title": "Email reported by user as malware or phish",
                    "description": "This alert is triggered when any email message is reported as malware or phish by users -V1.0.0.2",
                    "category": "InitialAccess",
                    "status": "InProgress",
                    "severity": "Informational",
                    "investigationId": null,
                    "investigationState": "Queued",
                    "classification": null,
                    "determination": null,
                    "detectionSource": "OfficeATP",
                    "assignedTo": "Automation",
                    "actorName": null,
                    "threatFamilyName": null,
                    "mitreTechniques": [],
                    "devices": [],
                    "entities": [
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser3@contoso.com",
                            "mailboxDisplayName": "test User3",
                            "mailboxAddress": "testUser3@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailBox",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "testUser4@contoso.com",
                            "mailboxDisplayName": "test User4",
                            "mailboxAddress": "test.User4@contoso.com",
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailMessage",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": "test.User4@contoso.com",
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": "user.abc@mail.contoso.co.in",
                            "recipient": "test.User4@contoso.com",
                            "subject": "[EXTERNAL] Attention",
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "Subject;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;P2SenderDomain;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "MailCluster",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": null,
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": "BodyFingerprintBin1;SenderIp;ContentType",
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        },
                        {
                            "entityType": "Ip",
                            "sha1": null,
                            "sha256": null,
                            "fileName": null,
                            "filePath": null,
                            "processId": null,
                            "processCommandLine": null,
                            "processCreationTime": null,
                            "parentProcessId": null,
                            "parentProcessCreationTime": null,
                            "ipAddress": "49.50.81.121",
                            "url": null,
                            "accountName": null,
                            "domainName": null,
                            "userSid": null,
                            "aadUserId": null,
                            "userPrincipalName": null,
                            "mailboxDisplayName": null,
                            "mailboxAddress": null,
                            "clusterBy": null,
                            "sender": null,
                            "recipient": null,
                            "subject": null,
                            "deliveryAction": null,
                            "securityGroupId": null,
                            "securityGroupName": null,
                            "registryHive": null,
                            "registryKey": null,
                            "registryValueType": null,
                            "registryValue": null,
                            "deviceId": null
                        }
                    ]
                }
            ]
        },
        ...
    ]
}
```

## <a name="related-articles"></a><span data-ttu-id="6ce64-420">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="6ce64-420">Related articles</span></span>

- [<span data-ttu-id="6ce64-421">Acesse as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6ce64-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="6ce64-422">Conheça os limites e licenciamento da API</span><span class="sxs-lookup"><span data-stu-id="6ce64-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="6ce64-423">Entenda códigos de erro</span><span class="sxs-lookup"><span data-stu-id="6ce64-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="6ce64-424">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="6ce64-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6ce64-425">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="6ce64-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="6ce64-426">Atualizar a API incidente</span><span class="sxs-lookup"><span data-stu-id="6ce64-426">Update incident API</span></span>](api-update-incidents.md)
