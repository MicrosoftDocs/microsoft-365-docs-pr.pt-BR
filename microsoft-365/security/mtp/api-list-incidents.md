---
title: Listar a API de incidentes no Microsoft 365 Defender
description: Saiba como listar a API de incidentes no Microsoft 365 Defender
keywords: lista, incidentes, incidentes, api
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 39a170a1845ab33f67d77b2de3d5f298f67fdc99
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932065"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="d7a9a-104">Listar a API de incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7a9a-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d7a9a-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-105">**Applies to:**</span></span>

- <span data-ttu-id="d7a9a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7a9a-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d7a9a-107">Algumas informações estão relacionadas a produtos de pré-lançamento que podem ser substancialmente modificados antes de serem lançadas comercialmente.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="d7a9a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="d7a9a-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="d7a9a-109">API description</span></span>

<span data-ttu-id="d7a9a-110">A API de incidentes de lista permite classificar por incidentes para criar uma resposta de segurança cibernética informada.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="d7a9a-111">Ele expõe uma coleção de incidentes que foram sinalizados em sua rede, dentro do intervalo de tempo especificado na política de retenção do ambiente.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="d7a9a-112">Os incidentes mais recentes são exibidos na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="d7a9a-113">Cada incidente contém uma matriz de alertas relacionados e suas entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="d7a9a-114">A API dá suporte aos seguintes **operadores OData:**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="d7a9a-115">`$filter`na `lastUpdateTime` propriedade `createdTime` , `status` e `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="d7a9a-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="d7a9a-116">`$top`, com um valor máximo **de 100**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="d7a9a-117">Limitações</span><span class="sxs-lookup"><span data-stu-id="d7a9a-117">Limitations</span></span>

1. <span data-ttu-id="d7a9a-118">O tamanho máximo da página **é de 100 incidentes.**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="d7a9a-119">A taxa máxima de solicitações **é de 50 chamadas por minuto** e **1500 chamadas por hora.**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="d7a9a-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="d7a9a-120">Permissions</span></span>

<span data-ttu-id="d7a9a-121">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="d7a9a-122">Para saber mais, incluindo como escolher permissões, confira As APIs do [Microsoft 365 Defender](api-access.md) do Access</span><span class="sxs-lookup"><span data-stu-id="d7a9a-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="d7a9a-123">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="d7a9a-123">Permission type</span></span> | <span data-ttu-id="d7a9a-124">Permissão</span><span class="sxs-lookup"><span data-stu-id="d7a9a-124">Permission</span></span> | <span data-ttu-id="d7a9a-125">Nome de exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="d7a9a-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="d7a9a-126">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-126">Application</span></span> | <span data-ttu-id="d7a9a-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="d7a9a-127">Incident.Read.All</span></span> | <span data-ttu-id="d7a9a-128">Ler todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="d7a9a-128">Read all incidents</span></span>
<span data-ttu-id="d7a9a-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-129">Application</span></span> | <span data-ttu-id="d7a9a-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="d7a9a-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="d7a9a-131">Ler e gravar todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="d7a9a-131">Read and write all incidents</span></span>
<span data-ttu-id="d7a9a-132">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="d7a9a-132">Delegated (work or school account)</span></span> | <span data-ttu-id="d7a9a-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="d7a9a-133">Incident.Read</span></span> | <span data-ttu-id="d7a9a-134">Ler incidentes</span><span class="sxs-lookup"><span data-stu-id="d7a9a-134">Read incidents</span></span>
<span data-ttu-id="d7a9a-135">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="d7a9a-135">Delegated (work or school account)</span></span> | <span data-ttu-id="d7a9a-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="d7a9a-136">Incident.ReadWrite</span></span> | <span data-ttu-id="d7a9a-137">Ler e gravar incidentes</span><span class="sxs-lookup"><span data-stu-id="d7a9a-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="d7a9a-138">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="d7a9a-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="d7a9a-139">O usuário precisa ter permissão de exibição para incidentes no portal.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="d7a9a-140">A resposta incluirá apenas incidentes aos que o usuário está exposto.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="d7a9a-141">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="d7a9a-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="d7a9a-142">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="d7a9a-142">Request headers</span></span>

<span data-ttu-id="d7a9a-143">Nome</span><span class="sxs-lookup"><span data-stu-id="d7a9a-143">Name</span></span> | <span data-ttu-id="d7a9a-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-144">Type</span></span> | <span data-ttu-id="d7a9a-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7a9a-145">Description</span></span>
-|-|-
<span data-ttu-id="d7a9a-146">Autorização</span><span class="sxs-lookup"><span data-stu-id="d7a9a-146">Authorization</span></span> | <span data-ttu-id="d7a9a-147">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d7a9a-147">String</span></span> | <span data-ttu-id="d7a9a-148">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-148">Bearer {token}.</span></span> <span data-ttu-id="d7a9a-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="d7a9a-150">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="d7a9a-150">Request body</span></span>

<span data-ttu-id="d7a9a-151">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="d7a9a-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="d7a9a-152">Response</span></span>

<span data-ttu-id="d7a9a-153">Se bem-sucedido, este `200 OK` método retorna e uma lista de [incidentes](api-incident.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="d7a9a-154">Mapeamento de esquema</span><span class="sxs-lookup"><span data-stu-id="d7a9a-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="d7a9a-155">Metadados de incidente</span><span class="sxs-lookup"><span data-stu-id="d7a9a-155">Incident metadata</span></span>

<span data-ttu-id="d7a9a-156">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-156">Field name</span></span> | <span data-ttu-id="d7a9a-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7a9a-157">Description</span></span> | <span data-ttu-id="d7a9a-158">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-158">Example value</span></span>
-|-|-
<span data-ttu-id="d7a9a-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-159">incidentId</span></span> | <span data-ttu-id="d7a9a-160">Identificador exclusivo para representar o incidente</span><span class="sxs-lookup"><span data-stu-id="d7a9a-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="d7a9a-161">924565</span><span class="sxs-lookup"><span data-stu-id="d7a9a-161">924565</span></span>
<span data-ttu-id="d7a9a-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-162">redirectIncidentId</span></span> | <span data-ttu-id="d7a9a-163">Preenchido somente no caso de um incidente estar sendo agrupado com outro incidente, como parte da lógica de processamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="d7a9a-164">924569</span><span class="sxs-lookup"><span data-stu-id="d7a9a-164">924569</span></span>
<span data-ttu-id="d7a9a-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-165">incidentName</span></span> | <span data-ttu-id="d7a9a-166">Valor de cadeia de caracteres disponível para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-166">String value available for every incident.</span></span> | <span data-ttu-id="d7a9a-167">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="d7a9a-167">Ransomware activity</span></span>
<span data-ttu-id="d7a9a-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="d7a9a-168">createdTime</span></span> | <span data-ttu-id="d7a9a-169">Hora em que o incidente foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-169">Time when incident was first created.</span></span> | <span data-ttu-id="d7a9a-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="d7a9a-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="d7a9a-171">lastUpdateTime</span></span> | <span data-ttu-id="d7a9a-172">Hora em que o incidente foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="d7a9a-173">Esse campo pode ser usado quando você estiver definindo o parâmetro de solicitação para o intervalo de tempo em que os incidentes são recuperados.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="d7a9a-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="d7a9a-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-175">assignedTo</span></span> | <span data-ttu-id="d7a9a-176">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="d7a9a-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d7a9a-177">secop2@contoso.com</span></span>
<span data-ttu-id="d7a9a-178">classificação</span><span class="sxs-lookup"><span data-stu-id="d7a9a-178">classification</span></span> | <span data-ttu-id="d7a9a-179">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-179">The specification for the incident.</span></span> <span data-ttu-id="d7a9a-180">Os valores de propriedade são: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="d7a9a-181">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="d7a9a-181">Unknown</span></span>
<span data-ttu-id="d7a9a-182">determinação</span><span class="sxs-lookup"><span data-stu-id="d7a9a-182">determination</span></span> | <span data-ttu-id="d7a9a-183">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="d7a9a-184">Os valores de propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="d7a9a-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="d7a9a-185">NotAvailable</span></span>
<span data-ttu-id="d7a9a-186">status</span><span class="sxs-lookup"><span data-stu-id="d7a9a-186">status</span></span> | <span data-ttu-id="d7a9a-187">Categorizar incidentes (como *Ativo* ou *Resolvido).*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="d7a9a-188">Ele pode ajudá-lo a organizar e gerenciar sua resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="d7a9a-189">Ativo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-189">Active</span></span>
<span data-ttu-id="d7a9a-190">severity</span><span class="sxs-lookup"><span data-stu-id="d7a9a-190">severity</span></span> | <span data-ttu-id="d7a9a-191">Indica o possível impacto sobre os ativos.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="d7a9a-192">Quanto maior a gravidade, maior o impacto.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="d7a9a-193">Normalmente, os itens de gravidade mais alta exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="d7a9a-194">Um dos seguintes valores: *Informacional*, *Baixo*, \*Médio e *Alto*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="d7a9a-195">Médio</span><span class="sxs-lookup"><span data-stu-id="d7a9a-195">Medium</span></span>
<span data-ttu-id="d7a9a-196">tags</span><span class="sxs-lookup"><span data-stu-id="d7a9a-196">tags</span></span> | <span data-ttu-id="d7a9a-197">Matriz de marcas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="d7a9a-198">alerts</span><span class="sxs-lookup"><span data-stu-id="d7a9a-198">alerts</span></span> | <span data-ttu-id="d7a9a-199">Matriz contendo todos os alertas relacionados ao incidente, além de outras informações, como gravidade, entidades envolvidas no alerta e a origem dos alertas.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="d7a9a-200">\[\] (veja detalhes sobre campos de alerta abaixo)</span><span class="sxs-lookup"><span data-stu-id="d7a9a-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="d7a9a-201">Metadados de alertas</span><span class="sxs-lookup"><span data-stu-id="d7a9a-201">Alerts metadata</span></span>

<span data-ttu-id="d7a9a-202">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-202">Field name</span></span> | <span data-ttu-id="d7a9a-203">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7a9a-203">Description</span></span> | <span data-ttu-id="d7a9a-204">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-204">Example value</span></span>
-|-|-
<span data-ttu-id="d7a9a-205">alertId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-205">alertId</span></span> | <span data-ttu-id="d7a9a-206">Identificador exclusivo para representar o alerta</span><span class="sxs-lookup"><span data-stu-id="d7a9a-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="d7a9a-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="d7a9a-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="d7a9a-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-208">incidentId</span></span> | <span data-ttu-id="d7a9a-209">Identificador exclusivo para representar o incidente ao que esse alerta está associado</span><span class="sxs-lookup"><span data-stu-id="d7a9a-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="d7a9a-210">924565</span><span class="sxs-lookup"><span data-stu-id="d7a9a-210">924565</span></span>
<span data-ttu-id="d7a9a-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="d7a9a-211">serviceSource</span></span> | <span data-ttu-id="d7a9a-212">Serviço de origem do alerta, como o Microsoft Defender para Ponto de Extremidade, o Microsoft Cloud App Security, o Microsoft Defender for Identity ou o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="d7a9a-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="d7a9a-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="d7a9a-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="d7a9a-214">creationTime</span></span> | <span data-ttu-id="d7a9a-215">Hora em que o alerta foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-215">Time when alert was first created.</span></span> | <span data-ttu-id="d7a9a-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="d7a9a-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="d7a9a-217">lastUpdatedTime</span></span> | <span data-ttu-id="d7a9a-218">Hora em que o alerta foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="d7a9a-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="d7a9a-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="d7a9a-220">resolvedTime</span></span> | <span data-ttu-id="d7a9a-221">Hora em que o alerta foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-221">Time when alert was resolved.</span></span> | <span data-ttu-id="d7a9a-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="d7a9a-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="d7a9a-223">firstActivity</span></span> | <span data-ttu-id="d7a9a-224">Hora em que o alerta relatou pela primeira vez que a atividade foi atualizada no back-end.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="d7a9a-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="d7a9a-226">Título</span><span class="sxs-lookup"><span data-stu-id="d7a9a-226">title</span></span> | <span data-ttu-id="d7a9a-227">Breve valor de cadeia de caracteres de identificação disponível para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="d7a9a-228">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="d7a9a-228">Ransomware activity</span></span>
<span data-ttu-id="d7a9a-229">description</span><span class="sxs-lookup"><span data-stu-id="d7a9a-229">description</span></span> | <span data-ttu-id="d7a9a-230">Valor de cadeia de caracteres que descreve cada alerta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-230">String value describing each alert.</span></span> | <span data-ttu-id="d7a9a-231">O usuário Test User2 (testUser2@contoso.com) manipulou 99 arquivos com várias extensões terminando com a extensão incomum *herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="d7a9a-232">Esse é um número incomum de manipulações de arquivos e indica um possível ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="d7a9a-233">category</span><span class="sxs-lookup"><span data-stu-id="d7a9a-233">category</span></span> | <span data-ttu-id="d7a9a-234">Exibição visual e numérica de até que ponto o ataque avançou ao longo do kill chain.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="d7a9a-235">Alinhado à estrutura [MITRE ATT&CK™ CK.](https://attack.mitre.org/)</span><span class="sxs-lookup"><span data-stu-id="d7a9a-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="d7a9a-236">Impacto</span><span class="sxs-lookup"><span data-stu-id="d7a9a-236">Impact</span></span>
<span data-ttu-id="d7a9a-237">status</span><span class="sxs-lookup"><span data-stu-id="d7a9a-237">status</span></span> | <span data-ttu-id="d7a9a-238">Categorizar alertas (como *Novo,* *Ativo* ou *Resolvido).*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="d7a9a-239">Ele pode ajudá-lo a organizar e gerenciar sua resposta a alertas.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="d7a9a-240">Novo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-240">New</span></span>
<span data-ttu-id="d7a9a-241">severity</span><span class="sxs-lookup"><span data-stu-id="d7a9a-241">severity</span></span> | <span data-ttu-id="d7a9a-242">Indica o possível impacto sobre os ativos.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="d7a9a-243">Quanto maior a gravidade, maior o impacto.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="d7a9a-244">Normalmente, os itens de gravidade mais alta exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="d7a9a-245">Um dos seguintes valores: *Informacional*, *Baixo*, \*Médio e *Alto*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="d7a9a-246">Médio</span><span class="sxs-lookup"><span data-stu-id="d7a9a-246">Medium</span></span>
<span data-ttu-id="d7a9a-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-247">investigationId</span></span> | <span data-ttu-id="d7a9a-248">A ID de investigação automatizada disparada por esse alerta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="d7a9a-249">1234</span><span class="sxs-lookup"><span data-stu-id="d7a9a-249">1234</span></span>
<span data-ttu-id="d7a9a-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="d7a9a-250">investigationState</span></span> | <span data-ttu-id="d7a9a-251">Informações sobre o status atual da investigação.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-251">Information on the investigation's current status.</span></span> <span data-ttu-id="d7a9a-252">Um dos seguintes valores: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="d7a9a-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="d7a9a-253">UnsupportedAlertType</span></span>
<span data-ttu-id="d7a9a-254">classificação</span><span class="sxs-lookup"><span data-stu-id="d7a9a-254">classification</span></span> | <span data-ttu-id="d7a9a-255">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-255">The specification for the incident.</span></span> <span data-ttu-id="d7a9a-256">Os valores de propriedade são: *Unknown*, *FalsePositive*, *TruePositive* ou *null*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="d7a9a-257">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="d7a9a-257">Unknown</span></span>
<span data-ttu-id="d7a9a-258">determinação</span><span class="sxs-lookup"><span data-stu-id="d7a9a-258">determination</span></span> | <span data-ttu-id="d7a9a-259">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="d7a9a-260">Os valores de propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* ou  *null*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="d7a9a-261">Apt</span><span class="sxs-lookup"><span data-stu-id="d7a9a-261">Apt</span></span>
<span data-ttu-id="d7a9a-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-262">assignedTo</span></span> | <span data-ttu-id="d7a9a-263">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="d7a9a-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d7a9a-264">secop2@contoso.com</span></span>
<span data-ttu-id="d7a9a-265">actorName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-265">actorName</span></span> | <span data-ttu-id="d7a9a-266">O grupo de atividades, se for o caso, o associado a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="d7a9a-267">BORON</span><span class="sxs-lookup"><span data-stu-id="d7a9a-267">BORON</span></span>
<span data-ttu-id="d7a9a-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-268">threatFamilyName</span></span> | <span data-ttu-id="d7a9a-269">Família de ameaças associada a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="d7a9a-270">null</span><span class="sxs-lookup"><span data-stu-id="d7a9a-270">null</span></span>
<span data-ttu-id="d7a9a-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="d7a9a-271">mitreTechniques</span></span> | <span data-ttu-id="d7a9a-272">As técnicas de ataque, conforme alinhadas com o [MITRE ATT&CK](https://attack.mitre.org/)™ estrutura.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="d7a9a-273">devices</span><span class="sxs-lookup"><span data-stu-id="d7a9a-273">devices</span></span> | <span data-ttu-id="d7a9a-274">Todos os dispositivos em que os alertas relacionados ao incidente foram enviados.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="d7a9a-275">\[\] (veja os detalhes sobre os campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="d7a9a-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="d7a9a-276">Formato do dispositivo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-276">Device format</span></span>

<span data-ttu-id="d7a9a-277">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-277">Field name</span></span> | <span data-ttu-id="d7a9a-278">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7a9a-278">Description</span></span> | <span data-ttu-id="d7a9a-279">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-279">Example value</span></span>
-|-|-
<span data-ttu-id="d7a9a-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-280">DeviceId</span></span> | <span data-ttu-id="d7a9a-281">A ID do dispositivo conforme designado no Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="d7a9a-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="d7a9a-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="d7a9a-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-283">aadDeviceId</span></span> |  <span data-ttu-id="d7a9a-284">A ID do dispositivo conforme designado no [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="d7a9a-284">The device ID as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="d7a9a-285">Disponível somente para dispositivos ingressados no domínio.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="d7a9a-286">null</span><span class="sxs-lookup"><span data-stu-id="d7a9a-286">null</span></span>
<span data-ttu-id="d7a9a-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-287">deviceDnsName</span></span> | <span data-ttu-id="d7a9a-288">O nome de domínio totalmente qualificado para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="d7a9a-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="d7a9a-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="d7a9a-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="d7a9a-290">osPlatform</span></span> | <span data-ttu-id="d7a9a-291">A plataforma do sistema operacional em execução pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-291">The OS platform the device is running.</span></span>| <span data-ttu-id="d7a9a-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="d7a9a-292">WindowsServer2016</span></span>
<span data-ttu-id="d7a9a-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="d7a9a-293">osBuild</span></span> | <span data-ttu-id="d7a9a-294">A versão de com build do sistema operacional em execução pelo dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="d7a9a-295">14393</span><span class="sxs-lookup"><span data-stu-id="d7a9a-295">14393</span></span>
<span data-ttu-id="d7a9a-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-296">rbacGroupName</span></span> | <span data-ttu-id="d7a9a-297">O [grupo de controle de](https://docs.microsoft.com/azure/role-based-access-control/overview) acesso baseado em função (RBAC) associado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-297">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="d7a9a-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="d7a9a-298">WDATP-Ring0</span></span>
<span data-ttu-id="d7a9a-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="d7a9a-299">firstSeen</span></span> | <span data-ttu-id="d7a9a-300">Hora em que o dispositivo foi visto pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-300">Time when device was first seen.</span></span> | <span data-ttu-id="d7a9a-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="d7a9a-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="d7a9a-302">healthStatus</span></span> | <span data-ttu-id="d7a9a-303">O estado de saúde do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-303">The health state of the device.</span></span> | <span data-ttu-id="d7a9a-304">Ativo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-304">Active</span></span>
<span data-ttu-id="d7a9a-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="d7a9a-305">riskScore</span></span> | <span data-ttu-id="d7a9a-306">A pontuação de risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-306">The risk score for the  device.</span></span> | <span data-ttu-id="d7a9a-307">Alto</span><span class="sxs-lookup"><span data-stu-id="d7a9a-307">High</span></span>
<span data-ttu-id="d7a9a-308">entidades</span><span class="sxs-lookup"><span data-stu-id="d7a9a-308">entities</span></span> | <span data-ttu-id="d7a9a-309">Todas as entidades que foram identificadas como parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="d7a9a-310">\[\] (veja os detalhes sobre os campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="d7a9a-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="d7a9a-311">Entity Format</span><span class="sxs-lookup"><span data-stu-id="d7a9a-311">Entity Format</span></span>

<span data-ttu-id="d7a9a-312">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-312">Field name</span></span> | <span data-ttu-id="d7a9a-313">Descrição</span><span class="sxs-lookup"><span data-stu-id="d7a9a-313">Description</span></span> | <span data-ttu-id="d7a9a-314">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-314">Example value</span></span>
-|-|-
<span data-ttu-id="d7a9a-315">entityType</span><span class="sxs-lookup"><span data-stu-id="d7a9a-315">entityType</span></span> | <span data-ttu-id="d7a9a-316">Entidades que foram identificadas como parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="d7a9a-317">Os valores das propriedades são: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="d7a9a-318">Usuário</span><span class="sxs-lookup"><span data-stu-id="d7a9a-318">User</span></span>
<span data-ttu-id="d7a9a-319">sha1</span><span class="sxs-lookup"><span data-stu-id="d7a9a-319">sha1</span></span> | <span data-ttu-id="d7a9a-320">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="d7a9a-321">O hash do arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="d7a9a-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="d7a9a-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="d7a9a-323">sha256</span><span class="sxs-lookup"><span data-stu-id="d7a9a-323">sha256</span></span> | <span data-ttu-id="d7a9a-324">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="d7a9a-325">O hash do arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="d7a9a-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="d7a9a-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="d7a9a-327">fileName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-327">fileName</span></span> | <span data-ttu-id="d7a9a-328">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="d7a9a-329">O nome do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="d7a9a-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="d7a9a-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="d7a9a-331">filePath</span><span class="sxs-lookup"><span data-stu-id="d7a9a-331">filePath</span></span> | <span data-ttu-id="d7a9a-332">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="d7a9a-333">O caminho do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="d7a9a-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="d7a9a-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="d7a9a-335">processId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-335">processId</span></span> | <span data-ttu-id="d7a9a-336">Disponível se entityType for *Processo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d7a9a-337">24348</span><span class="sxs-lookup"><span data-stu-id="d7a9a-337">24348</span></span>
<span data-ttu-id="d7a9a-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="d7a9a-338">processCommandLine</span></span> | <span data-ttu-id="d7a9a-339">Disponível se entityType for *Processo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d7a9a-340">"Seu arquivo está pronto para baixar \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="d7a9a-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="d7a9a-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="d7a9a-341">processCreationTime</span></span> | <span data-ttu-id="d7a9a-342">Disponível se entityType for *Processo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d7a9a-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="d7a9a-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-344">parentProcessId</span></span> | <span data-ttu-id="d7a9a-345">Disponível se entityType for *Processo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d7a9a-346">16840</span><span class="sxs-lookup"><span data-stu-id="d7a9a-346">16840</span></span>
<span data-ttu-id="d7a9a-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="d7a9a-347">parentProcessCreationTime</span></span> | <span data-ttu-id="d7a9a-348">Disponível se entityType for *Processo*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="d7a9a-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="d7a9a-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="d7a9a-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="d7a9a-350">ipAddress</span></span> | <span data-ttu-id="d7a9a-351">Disponível se entityType for *Ip*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="d7a9a-352">Endereço IP para alertas associados a eventos de rede, como Comunicação *a um destino de rede mal-intencionado.*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="d7a9a-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="d7a9a-353">62.216.203.204</span></span>
<span data-ttu-id="d7a9a-354">url</span><span class="sxs-lookup"><span data-stu-id="d7a9a-354">url</span></span> | <span data-ttu-id="d7a9a-355">Disponível se entityType for *URL*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="d7a9a-356">URL para alertas associados a eventos de rede, como Comunicação *a um destino de rede mal-intencionado.*</span><span class="sxs-lookup"><span data-stu-id="d7a9a-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="d7a9a-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="d7a9a-357">down.esales360.cn</span></span>
<span data-ttu-id="d7a9a-358">accountName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-358">accountName</span></span> | <span data-ttu-id="d7a9a-359">Disponível se entityType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="d7a9a-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="d7a9a-360">testUser2</span></span>
<span data-ttu-id="d7a9a-361">domainName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-361">domainName</span></span> | <span data-ttu-id="d7a9a-362">Disponível se entityType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="d7a9a-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="d7a9a-363">europe.corp.contoso</span></span>
<span data-ttu-id="d7a9a-364">userSid</span><span class="sxs-lookup"><span data-stu-id="d7a9a-364">userSid</span></span> | <span data-ttu-id="d7a9a-365">Disponível se entityType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="d7a9a-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="d7a9a-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="d7a9a-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-367">aadUserId</span></span> | <span data-ttu-id="d7a9a-368">Disponível se entityType for *Usuário*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="d7a9a-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="d7a9a-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="d7a9a-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-370">userPrincipalName</span></span> | <span data-ttu-id="d7a9a-371">Disponível se entityType for / *MailBox do* / *Usuário MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="d7a9a-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d7a9a-372">testUser2@contoso.com</span></span>
<span data-ttu-id="d7a9a-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-373">mailboxDisplayName</span></span> | <span data-ttu-id="d7a9a-374">Disponível se entityType for *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="d7a9a-375">test User2</span><span class="sxs-lookup"><span data-stu-id="d7a9a-375">test User2</span></span>
<span data-ttu-id="d7a9a-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="d7a9a-376">mailboxAddress</span></span> | <span data-ttu-id="d7a9a-377">Disponível se entityType for / *MailBox do* / *Usuário MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="d7a9a-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d7a9a-378">testUser2@contoso.com</span></span>
<span data-ttu-id="d7a9a-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="d7a9a-379">clusterBy</span></span> | <span data-ttu-id="d7a9a-380">Disponível se entityType for  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="d7a9a-381">Assunto; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="d7a9a-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="d7a9a-382">sender</span><span class="sxs-lookup"><span data-stu-id="d7a9a-382">sender</span></span> | <span data-ttu-id="d7a9a-383">Disponível se entityType for / *MailBox do* / *Usuário MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="d7a9a-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="d7a9a-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="d7a9a-385">destinatário</span><span class="sxs-lookup"><span data-stu-id="d7a9a-385">recipient</span></span> | <span data-ttu-id="d7a9a-386">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="d7a9a-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="d7a9a-387">testUser2@contoso.com</span></span>
<span data-ttu-id="d7a9a-388">assunto</span><span class="sxs-lookup"><span data-stu-id="d7a9a-388">subject</span></span> | <span data-ttu-id="d7a9a-389">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="d7a9a-390">\[Atenção \] EXTERNA</span><span class="sxs-lookup"><span data-stu-id="d7a9a-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="d7a9a-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="d7a9a-391">deliveryAction</span></span> | <span data-ttu-id="d7a9a-392">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="d7a9a-393">Entregue</span><span class="sxs-lookup"><span data-stu-id="d7a9a-393">Delivered</span></span>
<span data-ttu-id="d7a9a-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-394">securityGroupId</span></span> | <span data-ttu-id="d7a9a-395">Disponível se entityType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="d7a9a-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="d7a9a-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="d7a9a-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="d7a9a-397">securityGroupName</span></span> | <span data-ttu-id="d7a9a-398">Disponível se entityType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="d7a9a-399">Operadores de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="d7a9a-399">Network Configuration Operators</span></span>
<span data-ttu-id="d7a9a-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="d7a9a-400">registryHive</span></span> | <span data-ttu-id="d7a9a-401">Disponível se entityType for  *o Registro*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d7a9a-402">COMPUTADOR LOCAL HKEY \_ \_</span><span class="sxs-lookup"><span data-stu-id="d7a9a-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="d7a9a-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="d7a9a-403">registryKey</span></span> | <span data-ttu-id="d7a9a-404">Disponível se entityType for  *o Registro*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d7a9a-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="d7a9a-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="d7a9a-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="d7a9a-406">registryValueType</span></span> | <span data-ttu-id="d7a9a-407">Disponível se entityType for  *o Registro*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d7a9a-408">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="d7a9a-408">String</span></span>
<span data-ttu-id="d7a9a-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="d7a9a-409">registryValue</span></span> | <span data-ttu-id="d7a9a-410">Disponível se entityType for  *o Registro*.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="d7a9a-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="d7a9a-411">31-00-00-00</span></span>
<span data-ttu-id="d7a9a-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="d7a9a-412">deviceId</span></span> | <span data-ttu-id="d7a9a-413">A ID, se for o caso, do dispositivo relacionado à entidade.</span><span class="sxs-lookup"><span data-stu-id="d7a9a-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="d7a9a-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="d7a9a-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="d7a9a-415">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d7a9a-415">Example</span></span>

<span data-ttu-id="d7a9a-416">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="d7a9a-417">**Response**</span><span class="sxs-lookup"><span data-stu-id="d7a9a-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="d7a9a-418">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="d7a9a-418">Related articles</span></span>

- [<span data-ttu-id="d7a9a-419">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d7a9a-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="d7a9a-420">Saiba mais sobre limites e licenciamento da API</span><span class="sxs-lookup"><span data-stu-id="d7a9a-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="d7a9a-421">Noções sobre códigos de erro</span><span class="sxs-lookup"><span data-stu-id="d7a9a-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="d7a9a-422">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="d7a9a-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d7a9a-423">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="d7a9a-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="d7a9a-424">Atualizar API de incidentes</span><span class="sxs-lookup"><span data-stu-id="d7a9a-424">Update incident API</span></span>](api-update-incidents.md)
