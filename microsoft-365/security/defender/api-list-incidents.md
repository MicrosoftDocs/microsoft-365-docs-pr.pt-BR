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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4488a552475121adc4a439106bc0bf0d97cb509a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052844"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="c42b8-104">Listar a API de incidentes no Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c42b8-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c42b8-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="c42b8-105">**Applies to:**</span></span>

- <span data-ttu-id="c42b8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c42b8-106">Microsoft 365 Defender</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c42b8-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="c42b8-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="c42b8-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="c42b8-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="c42b8-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="c42b8-109">API description</span></span>

<span data-ttu-id="c42b8-110">A API de incidentes de lista permite classificar por meio de incidentes para criar uma resposta de segurança cibernética informada.</span><span class="sxs-lookup"><span data-stu-id="c42b8-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="c42b8-111">Ele expõe uma coleção de incidentes que foram sinalizados em sua rede, dentro do intervalo de tempo especificado na política de retenção do ambiente.</span><span class="sxs-lookup"><span data-stu-id="c42b8-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="c42b8-112">Os incidentes mais recentes são exibidos na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="c42b8-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="c42b8-113">Cada incidente contém uma matriz de alertas relacionados e suas entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="c42b8-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="c42b8-114">A API dá suporte aos seguintes **operadores OData:**</span><span class="sxs-lookup"><span data-stu-id="c42b8-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="c42b8-115">`$filter`nas `lastUpdateTime` propriedades , `createdTime` , `status` e `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="c42b8-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="c42b8-116">`$top`, com um valor máximo **de 100**</span><span class="sxs-lookup"><span data-stu-id="c42b8-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="c42b8-117">Limitações</span><span class="sxs-lookup"><span data-stu-id="c42b8-117">Limitations</span></span>

1. <span data-ttu-id="c42b8-118">O tamanho máximo da página **é de 100 incidentes.**</span><span class="sxs-lookup"><span data-stu-id="c42b8-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="c42b8-119">A taxa máxima de solicitações **é de 50 chamadas por minuto** e **1500 chamadas por hora.**</span><span class="sxs-lookup"><span data-stu-id="c42b8-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="c42b8-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="c42b8-120">Permissions</span></span>

<span data-ttu-id="c42b8-121">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="c42b8-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c42b8-122">Para saber mais, incluindo como escolher permissões, consulte [Access Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="c42b8-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="c42b8-123">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="c42b8-123">Permission type</span></span> | <span data-ttu-id="c42b8-124">Permissão</span><span class="sxs-lookup"><span data-stu-id="c42b8-124">Permission</span></span> | <span data-ttu-id="c42b8-125">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="c42b8-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="c42b8-126">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="c42b8-126">Application</span></span> | <span data-ttu-id="c42b8-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="c42b8-127">Incident.Read.All</span></span> | <span data-ttu-id="c42b8-128">Ler todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="c42b8-128">Read all incidents</span></span>
<span data-ttu-id="c42b8-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="c42b8-129">Application</span></span> | <span data-ttu-id="c42b8-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="c42b8-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="c42b8-131">Ler e gravar todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="c42b8-131">Read and write all incidents</span></span>
<span data-ttu-id="c42b8-132">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="c42b8-132">Delegated (work or school account)</span></span> | <span data-ttu-id="c42b8-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="c42b8-133">Incident.Read</span></span> | <span data-ttu-id="c42b8-134">Ler incidentes</span><span class="sxs-lookup"><span data-stu-id="c42b8-134">Read incidents</span></span>
<span data-ttu-id="c42b8-135">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="c42b8-135">Delegated (work or school account)</span></span> | <span data-ttu-id="c42b8-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="c42b8-136">Incident.ReadWrite</span></span> | <span data-ttu-id="c42b8-137">Incidentes de leitura e gravação</span><span class="sxs-lookup"><span data-stu-id="c42b8-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="c42b8-138">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="c42b8-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="c42b8-139">O usuário precisa ter permissão de exibição para incidentes no portal.</span><span class="sxs-lookup"><span data-stu-id="c42b8-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="c42b8-140">A resposta incluirá apenas incidentes aos que o usuário está exposto.</span><span class="sxs-lookup"><span data-stu-id="c42b8-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="c42b8-141">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="c42b8-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="c42b8-142">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="c42b8-142">Request headers</span></span>

<span data-ttu-id="c42b8-143">Nome</span><span class="sxs-lookup"><span data-stu-id="c42b8-143">Name</span></span> | <span data-ttu-id="c42b8-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="c42b8-144">Type</span></span> | <span data-ttu-id="c42b8-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="c42b8-145">Description</span></span>
-|-|-
<span data-ttu-id="c42b8-146">Autorização</span><span class="sxs-lookup"><span data-stu-id="c42b8-146">Authorization</span></span> | <span data-ttu-id="c42b8-147">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c42b8-147">String</span></span> | <span data-ttu-id="c42b8-148">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="c42b8-148">Bearer {token}.</span></span> <span data-ttu-id="c42b8-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="c42b8-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="c42b8-150">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="c42b8-150">Request body</span></span>

<span data-ttu-id="c42b8-151">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="c42b8-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="c42b8-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="c42b8-152">Response</span></span>

<span data-ttu-id="c42b8-153">Se tiver êxito, este método `200 OK` retornará e uma lista [de incidentes](api-incident.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="c42b8-154">Mapeamento de esquema</span><span class="sxs-lookup"><span data-stu-id="c42b8-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="c42b8-155">Metadados de incidente</span><span class="sxs-lookup"><span data-stu-id="c42b8-155">Incident metadata</span></span>

<span data-ttu-id="c42b8-156">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="c42b8-156">Field name</span></span> | <span data-ttu-id="c42b8-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="c42b8-157">Description</span></span> | <span data-ttu-id="c42b8-158">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="c42b8-158">Example value</span></span>
-|-|-
<span data-ttu-id="c42b8-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="c42b8-159">incidentId</span></span> | <span data-ttu-id="c42b8-160">Identificador exclusivo para representar o incidente</span><span class="sxs-lookup"><span data-stu-id="c42b8-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="c42b8-161">924565</span><span class="sxs-lookup"><span data-stu-id="c42b8-161">924565</span></span>
<span data-ttu-id="c42b8-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="c42b8-162">redirectIncidentId</span></span> | <span data-ttu-id="c42b8-163">Somente populado no caso de um incidente estar sendo agrupado com outro incidente, como parte da lógica de processamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="c42b8-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="c42b8-164">924569</span><span class="sxs-lookup"><span data-stu-id="c42b8-164">924569</span></span>
<span data-ttu-id="c42b8-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="c42b8-165">incidentName</span></span> | <span data-ttu-id="c42b8-166">Valor de cadeia de caracteres disponível para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="c42b8-166">String value available for every incident.</span></span> | <span data-ttu-id="c42b8-167">Atividade ransomware</span><span class="sxs-lookup"><span data-stu-id="c42b8-167">Ransomware activity</span></span>
<span data-ttu-id="c42b8-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="c42b8-168">createdTime</span></span> | <span data-ttu-id="c42b8-169">Hora em que o incidente foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="c42b8-169">Time when incident was first created.</span></span> | <span data-ttu-id="c42b8-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="c42b8-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="c42b8-171">lastUpdateTime</span></span> | <span data-ttu-id="c42b8-172">Hora em que o incidente foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="c42b8-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="c42b8-173">Esse campo pode ser usado quando você estiver definindo o parâmetro request para o intervalo de tempo em que os incidentes são recuperados.</span><span class="sxs-lookup"><span data-stu-id="c42b8-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="c42b8-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="c42b8-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="c42b8-175">assignedTo</span></span> | <span data-ttu-id="c42b8-176">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="c42b8-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="c42b8-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c42b8-177">secop2@contoso.com</span></span>
<span data-ttu-id="c42b8-178">classificação</span><span class="sxs-lookup"><span data-stu-id="c42b8-178">classification</span></span> | <span data-ttu-id="c42b8-179">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="c42b8-179">The specification for the incident.</span></span> <span data-ttu-id="c42b8-180">Os valores da propriedade são: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="c42b8-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="c42b8-181">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="c42b8-181">Unknown</span></span>
<span data-ttu-id="c42b8-182">determinação</span><span class="sxs-lookup"><span data-stu-id="c42b8-182">determination</span></span> | <span data-ttu-id="c42b8-183">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="c42b8-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="c42b8-184">Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="c42b8-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="c42b8-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="c42b8-185">NotAvailable</span></span>
<span data-ttu-id="c42b8-186">status</span><span class="sxs-lookup"><span data-stu-id="c42b8-186">status</span></span> | <span data-ttu-id="c42b8-187">Categorizar incidentes (como *Ativo* ou *Resolvido).*</span><span class="sxs-lookup"><span data-stu-id="c42b8-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="c42b8-188">Ele pode ajudá-lo a organizar e gerenciar sua resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="c42b8-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="c42b8-189">Ativo</span><span class="sxs-lookup"><span data-stu-id="c42b8-189">Active</span></span>
<span data-ttu-id="c42b8-190">severity</span><span class="sxs-lookup"><span data-stu-id="c42b8-190">severity</span></span> | <span data-ttu-id="c42b8-191">Indica o possível impacto nos ativos.</span><span class="sxs-lookup"><span data-stu-id="c42b8-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="c42b8-192">Quanto maior a gravidade, maior será o impacto.</span><span class="sxs-lookup"><span data-stu-id="c42b8-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="c42b8-193">Normalmente, itens de severidade mais altos exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="c42b8-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="c42b8-194">Um dos seguintes valores: *Informational*, *Low*, \*Medium e *High*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="c42b8-195">Médio</span><span class="sxs-lookup"><span data-stu-id="c42b8-195">Medium</span></span>
<span data-ttu-id="c42b8-196">tags</span><span class="sxs-lookup"><span data-stu-id="c42b8-196">tags</span></span> | <span data-ttu-id="c42b8-197">Matriz de marcas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.</span><span class="sxs-lookup"><span data-stu-id="c42b8-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="c42b8-198">alerts</span><span class="sxs-lookup"><span data-stu-id="c42b8-198">alerts</span></span> | <span data-ttu-id="c42b8-199">Matriz contendo todos os alertas relacionados ao incidente, além de outras informações, como gravidade, entidades envolvidas no alerta e a origem dos alertas.</span><span class="sxs-lookup"><span data-stu-id="c42b8-199">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="c42b8-200">\[\] (consulte detalhes sobre campos de alerta abaixo)</span><span class="sxs-lookup"><span data-stu-id="c42b8-200">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="c42b8-201">Metadados de alertas</span><span class="sxs-lookup"><span data-stu-id="c42b8-201">Alerts metadata</span></span>

<span data-ttu-id="c42b8-202">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="c42b8-202">Field name</span></span> | <span data-ttu-id="c42b8-203">Descrição</span><span class="sxs-lookup"><span data-stu-id="c42b8-203">Description</span></span> | <span data-ttu-id="c42b8-204">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="c42b8-204">Example value</span></span>
-|-|-
<span data-ttu-id="c42b8-205">alertId</span><span class="sxs-lookup"><span data-stu-id="c42b8-205">alertId</span></span> | <span data-ttu-id="c42b8-206">Identificador exclusivo para representar o alerta</span><span class="sxs-lookup"><span data-stu-id="c42b8-206">Unique identifier to represent the alert</span></span> | <span data-ttu-id="c42b8-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="c42b8-207">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="c42b8-208">incidentId</span><span class="sxs-lookup"><span data-stu-id="c42b8-208">incidentId</span></span> | <span data-ttu-id="c42b8-209">Identificador exclusivo para representar o incidente ao que esse alerta está associado</span><span class="sxs-lookup"><span data-stu-id="c42b8-209">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="c42b8-210">924565</span><span class="sxs-lookup"><span data-stu-id="c42b8-210">924565</span></span>
<span data-ttu-id="c42b8-211">serviceSource</span><span class="sxs-lookup"><span data-stu-id="c42b8-211">serviceSource</span></span> | <span data-ttu-id="c42b8-212">Serviço de origem do alerta, como o Microsoft Defender para Ponto de Extremidade, o Microsoft Cloud App Security, o Microsoft Defender para Identidade ou o Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="c42b8-212">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="c42b8-213">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="c42b8-213">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="c42b8-214">creationTime</span><span class="sxs-lookup"><span data-stu-id="c42b8-214">creationTime</span></span> | <span data-ttu-id="c42b8-215">Hora em que o alerta foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="c42b8-215">Time when alert was first created.</span></span> | <span data-ttu-id="c42b8-216">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-216">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="c42b8-217">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="c42b8-217">lastUpdatedTime</span></span> | <span data-ttu-id="c42b8-218">Hora em que o alerta foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="c42b8-218">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="c42b8-219">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-219">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="c42b8-220">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="c42b8-220">resolvedTime</span></span> | <span data-ttu-id="c42b8-221">Hora em que o alerta foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="c42b8-221">Time when alert was resolved.</span></span> | <span data-ttu-id="c42b8-222">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-222">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="c42b8-223">firstActivity</span><span class="sxs-lookup"><span data-stu-id="c42b8-223">firstActivity</span></span> | <span data-ttu-id="c42b8-224">Hora em que o alerta relatou pela primeira vez que a atividade foi atualizada no back-end.</span><span class="sxs-lookup"><span data-stu-id="c42b8-224">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="c42b8-225">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-225">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="c42b8-226">title</span><span class="sxs-lookup"><span data-stu-id="c42b8-226">title</span></span> | <span data-ttu-id="c42b8-227">Breve identificação do valor da cadeia de caracteres disponível para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-227">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="c42b8-228">Atividade ransomware</span><span class="sxs-lookup"><span data-stu-id="c42b8-228">Ransomware activity</span></span>
<span data-ttu-id="c42b8-229">descrição</span><span class="sxs-lookup"><span data-stu-id="c42b8-229">description</span></span> | <span data-ttu-id="c42b8-230">Valor de cadeia de caracteres que descreve cada alerta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-230">String value describing each alert.</span></span> | <span data-ttu-id="c42b8-231">O usuário Test User2 (testUser2@contoso.com) manipulou 99 arquivos com várias extensões terminando com a extensão *incomum herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-231">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="c42b8-232">Esse é um número incomum de manipulações de arquivos e indica um possível ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="c42b8-232">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="c42b8-233">category</span><span class="sxs-lookup"><span data-stu-id="c42b8-233">category</span></span> | <span data-ttu-id="c42b8-234">Exibição visual e numérica da distância em que o ataque progrediu ao longo da cadeia de morte.</span><span class="sxs-lookup"><span data-stu-id="c42b8-234">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="c42b8-235">Alinhado ao [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="c42b8-235">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="c42b8-236">Impacto</span><span class="sxs-lookup"><span data-stu-id="c42b8-236">Impact</span></span>
<span data-ttu-id="c42b8-237">status</span><span class="sxs-lookup"><span data-stu-id="c42b8-237">status</span></span> | <span data-ttu-id="c42b8-238">Categorizar alertas (como *Novo,* *Ativo* ou *Resolvido).*</span><span class="sxs-lookup"><span data-stu-id="c42b8-238">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="c42b8-239">Ele pode ajudá-lo a organizar e gerenciar sua resposta a alertas.</span><span class="sxs-lookup"><span data-stu-id="c42b8-239">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="c42b8-240">Novo</span><span class="sxs-lookup"><span data-stu-id="c42b8-240">New</span></span>
<span data-ttu-id="c42b8-241">severity</span><span class="sxs-lookup"><span data-stu-id="c42b8-241">severity</span></span> | <span data-ttu-id="c42b8-242">Indica o possível impacto nos ativos.</span><span class="sxs-lookup"><span data-stu-id="c42b8-242">Indicates the possible impact on assets.</span></span> <span data-ttu-id="c42b8-243">Quanto maior a gravidade, maior será o impacto.</span><span class="sxs-lookup"><span data-stu-id="c42b8-243">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="c42b8-244">Normalmente, itens de severidade mais altos exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="c42b8-244">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="c42b8-245">Um dos seguintes valores: *Informational*, *Low*, \*Medium e *High*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-245">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="c42b8-246">Médio</span><span class="sxs-lookup"><span data-stu-id="c42b8-246">Medium</span></span>
<span data-ttu-id="c42b8-247">investigationId</span><span class="sxs-lookup"><span data-stu-id="c42b8-247">investigationId</span></span> | <span data-ttu-id="c42b8-248">A ID de investigação automatizada disparada por esse alerta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-248">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="c42b8-249">1234</span><span class="sxs-lookup"><span data-stu-id="c42b8-249">1234</span></span>
<span data-ttu-id="c42b8-250">investigationState</span><span class="sxs-lookup"><span data-stu-id="c42b8-250">investigationState</span></span> | <span data-ttu-id="c42b8-251">Informações sobre o status atual da investigação.</span><span class="sxs-lookup"><span data-stu-id="c42b8-251">Information on the investigation's current status.</span></span> <span data-ttu-id="c42b8-252">Um dos seguintes valores: *Unknown* *,* Terminated , *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Enued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-252">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="c42b8-253">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="c42b8-253">UnsupportedAlertType</span></span>
<span data-ttu-id="c42b8-254">classificação</span><span class="sxs-lookup"><span data-stu-id="c42b8-254">classification</span></span> | <span data-ttu-id="c42b8-255">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="c42b8-255">The specification for the incident.</span></span> <span data-ttu-id="c42b8-256">Os valores da propriedade são: *Unknown*, *FalsePositive*, *TruePositive* ou *null*</span><span class="sxs-lookup"><span data-stu-id="c42b8-256">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="c42b8-257">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="c42b8-257">Unknown</span></span>
<span data-ttu-id="c42b8-258">determinação</span><span class="sxs-lookup"><span data-stu-id="c42b8-258">determination</span></span> | <span data-ttu-id="c42b8-259">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="c42b8-259">Specifies the determination of the incident.</span></span> <span data-ttu-id="c42b8-260">Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware*, *Other* ou  *null*</span><span class="sxs-lookup"><span data-stu-id="c42b8-260">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="c42b8-261">Apt</span><span class="sxs-lookup"><span data-stu-id="c42b8-261">Apt</span></span>
<span data-ttu-id="c42b8-262">assignedTo</span><span class="sxs-lookup"><span data-stu-id="c42b8-262">assignedTo</span></span> | <span data-ttu-id="c42b8-263">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="c42b8-263">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="c42b8-264">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c42b8-264">secop2@contoso.com</span></span>
<span data-ttu-id="c42b8-265">actorName</span><span class="sxs-lookup"><span data-stu-id="c42b8-265">actorName</span></span> | <span data-ttu-id="c42b8-266">O grupo de atividades, se for o caso, o associado a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-266">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="c42b8-267">BORON</span><span class="sxs-lookup"><span data-stu-id="c42b8-267">BORON</span></span>
<span data-ttu-id="c42b8-268">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="c42b8-268">threatFamilyName</span></span> | <span data-ttu-id="c42b8-269">Família de ameaças associada a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-269">Threat family associated with this alert.</span></span> | <span data-ttu-id="c42b8-270">null</span><span class="sxs-lookup"><span data-stu-id="c42b8-270">null</span></span>
<span data-ttu-id="c42b8-271">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="c42b8-271">mitreTechniques</span></span> | <span data-ttu-id="c42b8-272">As técnicas de ataque, conforme alinhadas com o [MITRE ATT](https://attack.mitre.org/)&CK ™ estrutura.</span><span class="sxs-lookup"><span data-stu-id="c42b8-272">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="c42b8-273">devices</span><span class="sxs-lookup"><span data-stu-id="c42b8-273">devices</span></span> | <span data-ttu-id="c42b8-274">Todos os dispositivos onde os alertas relacionados ao incidente foram enviados.</span><span class="sxs-lookup"><span data-stu-id="c42b8-274">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="c42b8-275">\[\] (consulte detalhes sobre os campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="c42b8-275">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="c42b8-276">Formato de dispositivo</span><span class="sxs-lookup"><span data-stu-id="c42b8-276">Device format</span></span>

<span data-ttu-id="c42b8-277">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="c42b8-277">Field name</span></span> | <span data-ttu-id="c42b8-278">Descrição</span><span class="sxs-lookup"><span data-stu-id="c42b8-278">Description</span></span> | <span data-ttu-id="c42b8-279">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="c42b8-279">Example value</span></span>
-|-|-
<span data-ttu-id="c42b8-280">DeviceId</span><span class="sxs-lookup"><span data-stu-id="c42b8-280">DeviceId</span></span> | <span data-ttu-id="c42b8-281">A ID do dispositivo conforme designado no Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c42b8-281">The device ID as designated in Microsoft Defender ATP.</span></span> | <span data-ttu-id="c42b8-282">24c222b0b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="c42b8-282">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="c42b8-283">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="c42b8-283">aadDeviceId</span></span> |  <span data-ttu-id="c42b8-284">A ID do dispositivo conforme designado no [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="c42b8-284">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="c42b8-285">Disponível apenas para dispositivos ingressados no domínio.</span><span class="sxs-lookup"><span data-stu-id="c42b8-285">Only available for domain-joined devices.</span></span> | <span data-ttu-id="c42b8-286">null</span><span class="sxs-lookup"><span data-stu-id="c42b8-286">null</span></span>
<span data-ttu-id="c42b8-287">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="c42b8-287">deviceDnsName</span></span> | <span data-ttu-id="c42b8-288">O nome de domínio totalmente qualificado para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c42b8-288">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="c42b8-289">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c42b8-289">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="c42b8-290">osPlatform</span><span class="sxs-lookup"><span data-stu-id="c42b8-290">osPlatform</span></span> | <span data-ttu-id="c42b8-291">A plataforma do sistema operacional que o dispositivo está executando.</span><span class="sxs-lookup"><span data-stu-id="c42b8-291">The OS platform the device is running.</span></span>| <span data-ttu-id="c42b8-292">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="c42b8-292">WindowsServer2016</span></span>
<span data-ttu-id="c42b8-293">osBuild</span><span class="sxs-lookup"><span data-stu-id="c42b8-293">osBuild</span></span> | <span data-ttu-id="c42b8-294">A versão de com build do sistema operacional em execução do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c42b8-294">The build version for the OS the device is running.</span></span> | <span data-ttu-id="c42b8-295">14393</span><span class="sxs-lookup"><span data-stu-id="c42b8-295">14393</span></span>
<span data-ttu-id="c42b8-296">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c42b8-296">rbacGroupName</span></span> | <span data-ttu-id="c42b8-297">O grupo de controle [de acesso](/azure/role-based-access-control/overview) baseado em função (RBAC) associado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c42b8-297">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="c42b8-298">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="c42b8-298">WDATP-Ring0</span></span>
<span data-ttu-id="c42b8-299">firstSeen</span><span class="sxs-lookup"><span data-stu-id="c42b8-299">firstSeen</span></span> | <span data-ttu-id="c42b8-300">Hora em que o dispositivo foi visto pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="c42b8-300">Time when device was first seen.</span></span> | <span data-ttu-id="c42b8-301">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-301">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="c42b8-302">healthStatus</span><span class="sxs-lookup"><span data-stu-id="c42b8-302">healthStatus</span></span> | <span data-ttu-id="c42b8-303">O estado de saúde do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c42b8-303">The health state of the device.</span></span> | <span data-ttu-id="c42b8-304">Ativo</span><span class="sxs-lookup"><span data-stu-id="c42b8-304">Active</span></span>
<span data-ttu-id="c42b8-305">riskScore</span><span class="sxs-lookup"><span data-stu-id="c42b8-305">riskScore</span></span> | <span data-ttu-id="c42b8-306">A pontuação de risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c42b8-306">The risk score for the  device.</span></span> | <span data-ttu-id="c42b8-307">Alto</span><span class="sxs-lookup"><span data-stu-id="c42b8-307">High</span></span>
<span data-ttu-id="c42b8-308">entidades</span><span class="sxs-lookup"><span data-stu-id="c42b8-308">entities</span></span> | <span data-ttu-id="c42b8-309">Todas as entidades identificadas para fazer parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-309">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="c42b8-310">\[\] (consulte detalhes sobre os campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="c42b8-310">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="c42b8-311">Formato de entidade</span><span class="sxs-lookup"><span data-stu-id="c42b8-311">Entity Format</span></span>

<span data-ttu-id="c42b8-312">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="c42b8-312">Field name</span></span> | <span data-ttu-id="c42b8-313">Descrição</span><span class="sxs-lookup"><span data-stu-id="c42b8-313">Description</span></span> | <span data-ttu-id="c42b8-314">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="c42b8-314">Example value</span></span>
-|-|-
<span data-ttu-id="c42b8-315">entityType</span><span class="sxs-lookup"><span data-stu-id="c42b8-315">entityType</span></span> | <span data-ttu-id="c42b8-316">Entidades identificadas para fazer parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="c42b8-316">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="c42b8-317">Os valores das propriedades são: *User*, *Ip*, *Url*, File , *Process*, *MailBox*, *MailMessage,* *MailCluster*, *Registry* </span><span class="sxs-lookup"><span data-stu-id="c42b8-317">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="c42b8-318">User</span><span class="sxs-lookup"><span data-stu-id="c42b8-318">User</span></span>
<span data-ttu-id="c42b8-319">sha1</span><span class="sxs-lookup"><span data-stu-id="c42b8-319">sha1</span></span> | <span data-ttu-id="c42b8-320">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-320">Available if entityType is *File*.</span></span><br><span data-ttu-id="c42b8-321">O hash de arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="c42b8-321">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="c42b8-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="c42b8-322">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="c42b8-323">sha256</span><span class="sxs-lookup"><span data-stu-id="c42b8-323">sha256</span></span> | <span data-ttu-id="c42b8-324">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-324">Available if entityType is *File*.</span></span><br><span data-ttu-id="c42b8-325">O hash de arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="c42b8-325">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="c42b8-326">28cb017dfc99073a1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="c42b8-326">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="c42b8-327">fileName</span><span class="sxs-lookup"><span data-stu-id="c42b8-327">fileName</span></span> | <span data-ttu-id="c42b8-328">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-328">Available if entityType is *File*.</span></span><br><span data-ttu-id="c42b8-329">O nome do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="c42b8-329">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="c42b8-330">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="c42b8-330">Detector.UnitTests.dll</span></span>
<span data-ttu-id="c42b8-331">filePath</span><span class="sxs-lookup"><span data-stu-id="c42b8-331">filePath</span></span> | <span data-ttu-id="c42b8-332">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-332">Available if entityType is *File*.</span></span><br><span data-ttu-id="c42b8-333">O caminho do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="c42b8-333">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="c42b8-334">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="c42b8-334">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="c42b8-335">processId</span><span class="sxs-lookup"><span data-stu-id="c42b8-335">processId</span></span> | <span data-ttu-id="c42b8-336">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-336">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c42b8-337">24348</span><span class="sxs-lookup"><span data-stu-id="c42b8-337">24348</span></span>
<span data-ttu-id="c42b8-338">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="c42b8-338">processCommandLine</span></span> | <span data-ttu-id="c42b8-339">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-339">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c42b8-340">"Seu arquivo está pronto para baixar \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="c42b8-340">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="c42b8-341">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="c42b8-341">processCreationTime</span></span> | <span data-ttu-id="c42b8-342">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-342">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c42b8-343">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-343">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="c42b8-344">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="c42b8-344">parentProcessId</span></span> | <span data-ttu-id="c42b8-345">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-345">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c42b8-346">16840</span><span class="sxs-lookup"><span data-stu-id="c42b8-346">16840</span></span>
<span data-ttu-id="c42b8-347">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="c42b8-347">parentProcessCreationTime</span></span> | <span data-ttu-id="c42b8-348">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-348">Available if entityType is *Process*.</span></span> | <span data-ttu-id="c42b8-349">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="c42b8-349">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="c42b8-350">ipAddress</span><span class="sxs-lookup"><span data-stu-id="c42b8-350">ipAddress</span></span> | <span data-ttu-id="c42b8-351">Disponível se entityType for *Ip*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-351">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="c42b8-352">Endereço IP para alertas associados a eventos de rede, como *Comunicação a um destino de rede mal-intencionado.*</span><span class="sxs-lookup"><span data-stu-id="c42b8-352">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="c42b8-353">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="c42b8-353">62.216.203.204</span></span>
<span data-ttu-id="c42b8-354">url</span><span class="sxs-lookup"><span data-stu-id="c42b8-354">url</span></span> | <span data-ttu-id="c42b8-355">Disponível se entityType for *Url*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-355">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="c42b8-356">URL para alertas associados a eventos de rede, como Comunicação *a um destino de rede mal-intencionado.*</span><span class="sxs-lookup"><span data-stu-id="c42b8-356">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="c42b8-357">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="c42b8-357">down.esales360.cn</span></span>
<span data-ttu-id="c42b8-358">accountName</span><span class="sxs-lookup"><span data-stu-id="c42b8-358">accountName</span></span> | <span data-ttu-id="c42b8-359">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-359">Available if entityType is *User*.</span></span> | <span data-ttu-id="c42b8-360">testUser2</span><span class="sxs-lookup"><span data-stu-id="c42b8-360">testUser2</span></span>
<span data-ttu-id="c42b8-361">domainName</span><span class="sxs-lookup"><span data-stu-id="c42b8-361">domainName</span></span> | <span data-ttu-id="c42b8-362">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-362">Available if entityType is *User*.</span></span> | <span data-ttu-id="c42b8-363">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="c42b8-363">europe.corp.contoso</span></span>
<span data-ttu-id="c42b8-364">userSid</span><span class="sxs-lookup"><span data-stu-id="c42b8-364">userSid</span></span> | <span data-ttu-id="c42b8-365">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-365">Available if entityType is *User*.</span></span> | <span data-ttu-id="c42b8-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="c42b8-366">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="c42b8-367">aadUserId</span><span class="sxs-lookup"><span data-stu-id="c42b8-367">aadUserId</span></span> | <span data-ttu-id="c42b8-368">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-368">Available if entityType is *User*.</span></span> | <span data-ttu-id="c42b8-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="c42b8-369">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="c42b8-370">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="c42b8-370">userPrincipalName</span></span> | <span data-ttu-id="c42b8-371">Disponível se entityType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-371">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="c42b8-372">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c42b8-372">testUser2@contoso.com</span></span>
<span data-ttu-id="c42b8-373">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="c42b8-373">mailboxDisplayName</span></span> | <span data-ttu-id="c42b8-374">Disponível se entityType for *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-374">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="c42b8-375">test User2</span><span class="sxs-lookup"><span data-stu-id="c42b8-375">test User2</span></span>
<span data-ttu-id="c42b8-376">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="c42b8-376">mailboxAddress</span></span> | <span data-ttu-id="c42b8-377">Disponível se entityType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-377">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="c42b8-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c42b8-378">testUser2@contoso.com</span></span>
<span data-ttu-id="c42b8-379">clusterBy</span><span class="sxs-lookup"><span data-stu-id="c42b8-379">clusterBy</span></span> | <span data-ttu-id="c42b8-380">Disponível se entityType for  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-380">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="c42b8-381">Assunto; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="c42b8-381">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="c42b8-382">sender</span><span class="sxs-lookup"><span data-stu-id="c42b8-382">sender</span></span> | <span data-ttu-id="c42b8-383">Disponível se entityType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-383">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="c42b8-384">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="c42b8-384">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="c42b8-385">destinatário</span><span class="sxs-lookup"><span data-stu-id="c42b8-385">recipient</span></span> | <span data-ttu-id="c42b8-386">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-386">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="c42b8-387">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="c42b8-387">testUser2@contoso.com</span></span>
<span data-ttu-id="c42b8-388">assunto</span><span class="sxs-lookup"><span data-stu-id="c42b8-388">subject</span></span> | <span data-ttu-id="c42b8-389">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-389">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="c42b8-390">\[Atenção \] EXTERNA</span><span class="sxs-lookup"><span data-stu-id="c42b8-390">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="c42b8-391">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="c42b8-391">deliveryAction</span></span> | <span data-ttu-id="c42b8-392">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-392">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="c42b8-393">Entregue</span><span class="sxs-lookup"><span data-stu-id="c42b8-393">Delivered</span></span>
<span data-ttu-id="c42b8-394">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="c42b8-394">securityGroupId</span></span> | <span data-ttu-id="c42b8-395">Disponível se entityType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-395">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="c42b8-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="c42b8-396">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="c42b8-397">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="c42b8-397">securityGroupName</span></span> | <span data-ttu-id="c42b8-398">Disponível se entityType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-398">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="c42b8-399">Operadores de Configuração de Rede</span><span class="sxs-lookup"><span data-stu-id="c42b8-399">Network Configuration Operators</span></span>
<span data-ttu-id="c42b8-400">registryHive</span><span class="sxs-lookup"><span data-stu-id="c42b8-400">registryHive</span></span> | <span data-ttu-id="c42b8-401">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-401">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c42b8-402">MÁQUINA LOCAL HKEY \_ \_</span><span class="sxs-lookup"><span data-stu-id="c42b8-402">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="c42b8-403">registryKey</span><span class="sxs-lookup"><span data-stu-id="c42b8-403">registryKey</span></span> | <span data-ttu-id="c42b8-404">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-404">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c42b8-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="c42b8-405">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="c42b8-406">registryValueType</span><span class="sxs-lookup"><span data-stu-id="c42b8-406">registryValueType</span></span> | <span data-ttu-id="c42b8-407">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-407">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c42b8-408">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="c42b8-408">String</span></span>
<span data-ttu-id="c42b8-409">registryValue</span><span class="sxs-lookup"><span data-stu-id="c42b8-409">registryValue</span></span> | <span data-ttu-id="c42b8-410">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="c42b8-410">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="c42b8-411">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="c42b8-411">31-00-00-00</span></span>
<span data-ttu-id="c42b8-412">deviceId</span><span class="sxs-lookup"><span data-stu-id="c42b8-412">deviceId</span></span> | <span data-ttu-id="c42b8-413">A ID, se for o caso, do dispositivo relacionado à entidade.</span><span class="sxs-lookup"><span data-stu-id="c42b8-413">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="c42b8-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="c42b8-414">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="c42b8-415">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c42b8-415">Example</span></span>

<span data-ttu-id="c42b8-416">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="c42b8-416">**Request**</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="c42b8-417">**Response**</span><span class="sxs-lookup"><span data-stu-id="c42b8-417">**Response**</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="c42b8-418">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="c42b8-418">Related articles</span></span>

- [<span data-ttu-id="c42b8-419">Acessar as APIs do Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c42b8-419">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="c42b8-420">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="c42b8-420">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="c42b8-421">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="c42b8-421">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="c42b8-422">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="c42b8-422">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="c42b8-423">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="c42b8-423">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="c42b8-424">Atualizar API de incidentes</span><span class="sxs-lookup"><span data-stu-id="c42b8-424">Update incident API</span></span>](api-update-incidents.md)