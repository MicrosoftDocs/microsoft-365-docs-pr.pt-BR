---
title: Listar a API de incidentes Microsoft 365 Defender
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
ms.openlocfilehash: 038879e77dfa26d82add20d043a32de117f95b19
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287826"
---
# <a name="list-incidents-api-in-microsoft-365-defender"></a><span data-ttu-id="867b4-104">Listar a API de incidentes Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="867b4-104">List incidents API in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="867b4-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="867b4-105">**Applies to:**</span></span>

- [<span data-ttu-id="867b4-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="867b4-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="867b4-107">Algumas informações estão relacionadas a produtos pré-lançados que podem ser substancialmente modificados antes de seu lançamento comercial.</span><span class="sxs-lookup"><span data-stu-id="867b4-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="867b4-108">A Microsoft não faz garantias, expressas ou implícitas, quanto às informações fornecidas aqui.</span><span class="sxs-lookup"><span data-stu-id="867b4-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="api-description"></a><span data-ttu-id="867b4-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="867b4-109">API description</span></span>

<span data-ttu-id="867b4-110">A API de incidentes de lista permite classificar por meio de incidentes para criar uma resposta de segurança cibernética informada.</span><span class="sxs-lookup"><span data-stu-id="867b4-110">The list incidents API allows you to sort through incidents to create an informed cybersecurity response.</span></span> <span data-ttu-id="867b4-111">Ele expõe uma coleção de incidentes que foram sinalizados em sua rede, dentro do intervalo de tempo especificado na política de retenção do ambiente.</span><span class="sxs-lookup"><span data-stu-id="867b4-111">It exposes a collection of incidents that were flagged in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="867b4-112">Os incidentes mais recentes são exibidos na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="867b4-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="867b4-113">Cada incidente contém uma matriz de alertas relacionados e suas entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="867b4-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<span data-ttu-id="867b4-114">A API dá suporte aos seguintes **operadores OData:**</span><span class="sxs-lookup"><span data-stu-id="867b4-114">The API supports the following **OData** operators:</span></span>

- <span data-ttu-id="867b4-115">`$filter`nas `lastUpdateTime` propriedades , `createdTime` , `status` e `assignedTo`</span><span class="sxs-lookup"><span data-stu-id="867b4-115">`$filter` on the `lastUpdateTime`, `createdTime`, `status`, and `assignedTo` properties</span></span>
- <span data-ttu-id="867b4-116">`$top`, com um valor máximo **de 100**</span><span class="sxs-lookup"><span data-stu-id="867b4-116">`$top`, with a maximum value of **100**</span></span>
- `$skip`

## <a name="limitations"></a><span data-ttu-id="867b4-117">Limitações</span><span class="sxs-lookup"><span data-stu-id="867b4-117">Limitations</span></span>

1. <span data-ttu-id="867b4-118">O tamanho máximo da página **é de 100 incidentes.**</span><span class="sxs-lookup"><span data-stu-id="867b4-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="867b4-119">A taxa máxima de solicitações **é de 50 chamadas por minuto** e **1500 chamadas por hora.**</span><span class="sxs-lookup"><span data-stu-id="867b4-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="867b4-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="867b4-120">Permissions</span></span>

<span data-ttu-id="867b4-121">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="867b4-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="867b4-122">Para saber mais, incluindo como escolher permissões, consulte [Access Microsoft 365 Defender APIs](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="867b4-122">To learn more, including how to choose permissions, see [Access Microsoft 365 Defender APIs](api-access.md)</span></span>

<span data-ttu-id="867b4-123">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="867b4-123">Permission type</span></span> | <span data-ttu-id="867b4-124">Permissão</span><span class="sxs-lookup"><span data-stu-id="867b4-124">Permission</span></span> | <span data-ttu-id="867b4-125">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="867b4-125">Permission display name</span></span>
-|-|-
<span data-ttu-id="867b4-126">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="867b4-126">Application</span></span> | <span data-ttu-id="867b4-127">Incident.Read.All</span><span class="sxs-lookup"><span data-stu-id="867b4-127">Incident.Read.All</span></span> | <span data-ttu-id="867b4-128">Ler todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="867b4-128">Read all incidents</span></span>
<span data-ttu-id="867b4-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="867b4-129">Application</span></span> | <span data-ttu-id="867b4-130">Incident.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="867b4-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="867b4-131">Ler e gravar todos os incidentes</span><span class="sxs-lookup"><span data-stu-id="867b4-131">Read and write all incidents</span></span>
<span data-ttu-id="867b4-132">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="867b4-132">Delegated (work or school account)</span></span> | <span data-ttu-id="867b4-133">Incident.Read</span><span class="sxs-lookup"><span data-stu-id="867b4-133">Incident.Read</span></span> | <span data-ttu-id="867b4-134">Ler incidentes</span><span class="sxs-lookup"><span data-stu-id="867b4-134">Read incidents</span></span>
<span data-ttu-id="867b4-135">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="867b4-135">Delegated (work or school account)</span></span> | <span data-ttu-id="867b4-136">Incident.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="867b4-136">Incident.ReadWrite</span></span> | <span data-ttu-id="867b4-137">Incidentes de leitura e gravação</span><span class="sxs-lookup"><span data-stu-id="867b4-137">Read and write incidents</span></span>

> [!Note]
> <span data-ttu-id="867b4-138">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="867b4-138">When obtaining a token using user credentials:</span></span>
>
> - <span data-ttu-id="867b4-139">O usuário precisa ter permissão de exibição para incidentes no portal.</span><span class="sxs-lookup"><span data-stu-id="867b4-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="867b4-140">A resposta incluirá apenas incidentes aos que o usuário está exposto.</span><span class="sxs-lookup"><span data-stu-id="867b4-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="867b4-141">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="867b4-141">HTTP request</span></span>

```HTTP
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="867b4-142">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="867b4-142">Request headers</span></span>

<span data-ttu-id="867b4-143">Nome</span><span class="sxs-lookup"><span data-stu-id="867b4-143">Name</span></span> | <span data-ttu-id="867b4-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="867b4-144">Type</span></span> | <span data-ttu-id="867b4-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="867b4-145">Description</span></span>
-|-|-
<span data-ttu-id="867b4-146">Autorização</span><span class="sxs-lookup"><span data-stu-id="867b4-146">Authorization</span></span> | <span data-ttu-id="867b4-147">String</span><span class="sxs-lookup"><span data-stu-id="867b4-147">String</span></span> | <span data-ttu-id="867b4-148">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="867b4-148">Bearer {token}.</span></span> <span data-ttu-id="867b4-149">**Required**</span><span class="sxs-lookup"><span data-stu-id="867b4-149">**Required**</span></span>


## <a name="request-body"></a><span data-ttu-id="867b4-150">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="867b4-150">Request body</span></span>

<span data-ttu-id="867b4-151">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="867b4-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="867b4-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="867b4-152">Response</span></span>

<span data-ttu-id="867b4-153">Se tiver êxito, este método `200 OK` retornará e uma lista [de incidentes](api-incident.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="867b4-153">If successful, this method returns `200 OK`, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="867b4-154">Mapeamento de esquema</span><span class="sxs-lookup"><span data-stu-id="867b4-154">Schema mapping</span></span>

### <a name="incident-metadata"></a><span data-ttu-id="867b4-155">Metadados de incidente</span><span class="sxs-lookup"><span data-stu-id="867b4-155">Incident metadata</span></span>

<span data-ttu-id="867b4-156">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="867b4-156">Field name</span></span> | <span data-ttu-id="867b4-157">Descrição</span><span class="sxs-lookup"><span data-stu-id="867b4-157">Description</span></span> | <span data-ttu-id="867b4-158">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="867b4-158">Example value</span></span>
-|-|-
<span data-ttu-id="867b4-159">incidentId</span><span class="sxs-lookup"><span data-stu-id="867b4-159">incidentId</span></span> | <span data-ttu-id="867b4-160">Identificador exclusivo para representar o incidente</span><span class="sxs-lookup"><span data-stu-id="867b4-160">Unique identifier to represent the incident</span></span> | <span data-ttu-id="867b4-161">924565</span><span class="sxs-lookup"><span data-stu-id="867b4-161">924565</span></span>
<span data-ttu-id="867b4-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="867b4-162">redirectIncidentId</span></span> | <span data-ttu-id="867b4-163">Somente populado no caso de um incidente estar sendo agrupado com outro incidente, como parte da lógica de processamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="867b4-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span> | <span data-ttu-id="867b4-164">924569</span><span class="sxs-lookup"><span data-stu-id="867b4-164">924569</span></span>
<span data-ttu-id="867b4-165">incidentName</span><span class="sxs-lookup"><span data-stu-id="867b4-165">incidentName</span></span> | <span data-ttu-id="867b4-166">Valor de cadeia de caracteres disponível para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="867b4-166">String value available for every incident.</span></span> | <span data-ttu-id="867b4-167">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="867b4-167">Ransomware activity</span></span>
<span data-ttu-id="867b4-168">createdTime</span><span class="sxs-lookup"><span data-stu-id="867b4-168">createdTime</span></span> | <span data-ttu-id="867b4-169">Hora em que o incidente foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="867b4-169">Time when incident was first created.</span></span> | <span data-ttu-id="867b4-170">2020-09-06T14:46:57.0733333Z</span><span class="sxs-lookup"><span data-stu-id="867b4-170">2020-09-06T14:46:57.0733333Z</span></span>
<span data-ttu-id="867b4-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="867b4-171">lastUpdateTime</span></span> | <span data-ttu-id="867b4-172">Hora em que o incidente foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="867b4-172">Time when the incident was last updated on the backend.</span></span><br /><br /> <span data-ttu-id="867b4-173">Esse campo pode ser usado quando você estiver definindo o parâmetro request para o intervalo de tempo em que os incidentes são recuperados.</span><span class="sxs-lookup"><span data-stu-id="867b4-173">This field can be used when you're setting the request parameter for the range of time that incidents are retrieved.</span></span> | <span data-ttu-id="867b4-174">2020-09-06T14:46:57.29Z</span><span class="sxs-lookup"><span data-stu-id="867b4-174">2020-09-06T14:46:57.29Z</span></span>
<span data-ttu-id="867b4-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="867b4-175">assignedTo</span></span> | <span data-ttu-id="867b4-176">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="867b4-176">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="867b4-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="867b4-177">secop2@contoso.com</span></span>
<span data-ttu-id="867b4-178">classificação</span><span class="sxs-lookup"><span data-stu-id="867b4-178">classification</span></span> | <span data-ttu-id="867b4-179">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="867b4-179">The specification for the incident.</span></span> <span data-ttu-id="867b4-180">Os valores da propriedade são: *Unknown*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="867b4-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span> | <span data-ttu-id="867b4-181">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="867b4-181">Unknown</span></span>
<span data-ttu-id="867b4-182">determinação</span><span class="sxs-lookup"><span data-stu-id="867b4-182">determination</span></span> | <span data-ttu-id="867b4-183">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="867b4-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="867b4-184">Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware*, *Other*</span><span class="sxs-lookup"><span data-stu-id="867b4-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span> | <span data-ttu-id="867b4-185">NotAvailable</span><span class="sxs-lookup"><span data-stu-id="867b4-185">NotAvailable</span></span>
<span data-ttu-id="867b4-186">status</span><span class="sxs-lookup"><span data-stu-id="867b4-186">status</span></span> | <span data-ttu-id="867b4-187">Categorizar incidentes (como *Ativo* ou *Resolvido).*</span><span class="sxs-lookup"><span data-stu-id="867b4-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="867b4-188">Ele pode ajudá-lo a organizar e gerenciar sua resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="867b4-188">It can help you organize and manage your response to incidents.</span></span> | <span data-ttu-id="867b4-189">Ativo</span><span class="sxs-lookup"><span data-stu-id="867b4-189">Active</span></span>
<span data-ttu-id="867b4-190">severity</span><span class="sxs-lookup"><span data-stu-id="867b4-190">severity</span></span> | <span data-ttu-id="867b4-191">Indica o possível impacto nos ativos.</span><span class="sxs-lookup"><span data-stu-id="867b4-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="867b4-192">Quanto maior a gravidade, maior será o impacto.</span><span class="sxs-lookup"><span data-stu-id="867b4-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="867b4-193">Normalmente, itens de severidade mais altos exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="867b4-193">Typically higher severity items require the most immediate attention.</span></span><br /><br /><span data-ttu-id="867b4-194">Um dos seguintes valores: *Informational*, *Low*, \*Medium e *High*.</span><span class="sxs-lookup"><span data-stu-id="867b4-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="867b4-195">Médio</span><span class="sxs-lookup"><span data-stu-id="867b4-195">Medium</span></span>
<span data-ttu-id="867b4-196">tags</span><span class="sxs-lookup"><span data-stu-id="867b4-196">tags</span></span> | <span data-ttu-id="867b4-197">Matriz de marcas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.</span><span class="sxs-lookup"><span data-stu-id="867b4-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span> | \[\]
<span data-ttu-id="867b4-198">comentários</span><span class="sxs-lookup"><span data-stu-id="867b4-198">comments</span></span> | <span data-ttu-id="867b4-199">Matriz de comentários criados por secops ao gerenciar o incidente, por exemplo, informações adicionais sobre a seleção de classificação.</span><span class="sxs-lookup"><span data-stu-id="867b4-199">Array of comments created by secops when managing the incident, for example additional information about the classification selection.</span></span> | \[\]
<span data-ttu-id="867b4-200">alertas</span><span class="sxs-lookup"><span data-stu-id="867b4-200">alerts</span></span> | <span data-ttu-id="867b4-201">Matriz contendo todos os alertas relacionados ao incidente, além de outras informações, como gravidade, entidades envolvidas no alerta e a origem dos alertas.</span><span class="sxs-lookup"><span data-stu-id="867b4-201">Array containing all of the alerts related to the incident, plus other information, such as severity, entities that were involved in the alert, and the source of the alerts.</span></span> | <span data-ttu-id="867b4-202">\[\] (consulte detalhes sobre campos de alerta abaixo)</span><span class="sxs-lookup"><span data-stu-id="867b4-202">\[\] (see details on alert fields below)</span></span>

### <a name="alerts-metadata"></a><span data-ttu-id="867b4-203">Metadados de alertas</span><span class="sxs-lookup"><span data-stu-id="867b4-203">Alerts metadata</span></span>

<span data-ttu-id="867b4-204">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="867b4-204">Field name</span></span> | <span data-ttu-id="867b4-205">Descrição</span><span class="sxs-lookup"><span data-stu-id="867b4-205">Description</span></span> | <span data-ttu-id="867b4-206">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="867b4-206">Example value</span></span>
-|-|-
<span data-ttu-id="867b4-207">alertId</span><span class="sxs-lookup"><span data-stu-id="867b4-207">alertId</span></span> | <span data-ttu-id="867b4-208">Identificador exclusivo para representar o alerta</span><span class="sxs-lookup"><span data-stu-id="867b4-208">Unique identifier to represent the alert</span></span> | <span data-ttu-id="867b4-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="867b4-209">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>
<span data-ttu-id="867b4-210">incidentId</span><span class="sxs-lookup"><span data-stu-id="867b4-210">incidentId</span></span> | <span data-ttu-id="867b4-211">Identificador exclusivo para representar o incidente ao que esse alerta está associado</span><span class="sxs-lookup"><span data-stu-id="867b4-211">Unique identifier to represent the incident this alert is associated with</span></span> | <span data-ttu-id="867b4-212">924565</span><span class="sxs-lookup"><span data-stu-id="867b4-212">924565</span></span>
<span data-ttu-id="867b4-213">serviceSource</span><span class="sxs-lookup"><span data-stu-id="867b4-213">serviceSource</span></span> | <span data-ttu-id="867b4-214">Serviço de origem do alerta, como o Microsoft Defender para Ponto de Extremidade, Microsoft Cloud App Security, Microsoft Defender para Identidade ou Microsoft Defender para Office 365.</span><span class="sxs-lookup"><span data-stu-id="867b4-214">Service that the alert originates from, such as Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, or Microsoft Defender for Office 365.</span></span> | <span data-ttu-id="867b4-215">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="867b4-215">MicrosoftCloudAppSecurity</span></span>
<span data-ttu-id="867b4-216">creationTime</span><span class="sxs-lookup"><span data-stu-id="867b4-216">creationTime</span></span> | <span data-ttu-id="867b4-217">Hora em que o alerta foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="867b4-217">Time when alert was first created.</span></span> | <span data-ttu-id="867b4-218">2020-09-06T14:46:55.7182276Z</span><span class="sxs-lookup"><span data-stu-id="867b4-218">2020-09-06T14:46:55.7182276Z</span></span>
<span data-ttu-id="867b4-219">lastUpdatedTime</span><span class="sxs-lookup"><span data-stu-id="867b4-219">lastUpdatedTime</span></span> | <span data-ttu-id="867b4-220">Hora em que o alerta foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="867b4-220">Time when alert was last updated at the backend.</span></span> | <span data-ttu-id="867b4-221">2020-09-06T14:46:57.2433333Z</span><span class="sxs-lookup"><span data-stu-id="867b4-221">2020-09-06T14:46:57.2433333Z</span></span>
<span data-ttu-id="867b4-222">resolvedTime</span><span class="sxs-lookup"><span data-stu-id="867b4-222">resolvedTime</span></span> | <span data-ttu-id="867b4-223">Hora em que o alerta foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="867b4-223">Time when alert was resolved.</span></span> | <span data-ttu-id="867b4-224">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="867b4-224">2020-09-10T05:22:59Z</span></span>
<span data-ttu-id="867b4-225">firstActivity</span><span class="sxs-lookup"><span data-stu-id="867b4-225">firstActivity</span></span> | <span data-ttu-id="867b4-226">Hora em que o alerta relatou pela primeira vez que a atividade foi atualizada no back-end.</span><span class="sxs-lookup"><span data-stu-id="867b4-226">Time when alert first reported that activity was updated at the backend.</span></span>| <span data-ttu-id="867b4-227">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="867b4-227">2020-09-04T05:22:59Z</span></span>
<span data-ttu-id="867b4-228">title</span><span class="sxs-lookup"><span data-stu-id="867b4-228">title</span></span> | <span data-ttu-id="867b4-229">Breve identificação do valor da cadeia de caracteres disponível para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="867b4-229">Brief identifying string value available for each alert.</span></span> | <span data-ttu-id="867b4-230">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="867b4-230">Ransomware activity</span></span>
<span data-ttu-id="867b4-231">description</span><span class="sxs-lookup"><span data-stu-id="867b4-231">description</span></span> | <span data-ttu-id="867b4-232">Valor de cadeia de caracteres que descreve cada alerta.</span><span class="sxs-lookup"><span data-stu-id="867b4-232">String value describing each alert.</span></span> | <span data-ttu-id="867b4-233">O usuário Test User2 (testUser2@contoso.com) manipulou 99 arquivos com várias extensões terminando com a extensão *incomum herunterladen*.</span><span class="sxs-lookup"><span data-stu-id="867b4-233">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="867b4-234">Esse é um número incomum de manipulações de arquivos e indica um possível ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="867b4-234">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span>
<span data-ttu-id="867b4-235">category</span><span class="sxs-lookup"><span data-stu-id="867b4-235">category</span></span> | <span data-ttu-id="867b4-236">Exibição visual e numérica da distância em que o ataque progrediu ao longo da cadeia de morte.</span><span class="sxs-lookup"><span data-stu-id="867b4-236">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="867b4-237">Alinhado ao [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="867b4-237">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span> | <span data-ttu-id="867b4-238">Impacto</span><span class="sxs-lookup"><span data-stu-id="867b4-238">Impact</span></span>
<span data-ttu-id="867b4-239">status</span><span class="sxs-lookup"><span data-stu-id="867b4-239">status</span></span> | <span data-ttu-id="867b4-240">Categorizar alertas (como *Novo,* *Ativo* ou *Resolvido).*</span><span class="sxs-lookup"><span data-stu-id="867b4-240">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="867b4-241">Ele pode ajudá-lo a organizar e gerenciar sua resposta a alertas.</span><span class="sxs-lookup"><span data-stu-id="867b4-241">It can help you organize and manage your response to alerts.</span></span> | <span data-ttu-id="867b4-242">Novo</span><span class="sxs-lookup"><span data-stu-id="867b4-242">New</span></span>
<span data-ttu-id="867b4-243">severity</span><span class="sxs-lookup"><span data-stu-id="867b4-243">severity</span></span> | <span data-ttu-id="867b4-244">Indica o possível impacto nos ativos.</span><span class="sxs-lookup"><span data-stu-id="867b4-244">Indicates the possible impact on assets.</span></span> <span data-ttu-id="867b4-245">Quanto maior a gravidade, maior será o impacto.</span><span class="sxs-lookup"><span data-stu-id="867b4-245">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="867b4-246">Normalmente, itens de severidade mais altos exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="867b4-246">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="867b4-247">Um dos seguintes valores: *Informational*, *Low*, \*Medium e *High*.</span><span class="sxs-lookup"><span data-stu-id="867b4-247">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span> | <span data-ttu-id="867b4-248">Médio</span><span class="sxs-lookup"><span data-stu-id="867b4-248">Medium</span></span>
<span data-ttu-id="867b4-249">investigationId</span><span class="sxs-lookup"><span data-stu-id="867b4-249">investigationId</span></span> | <span data-ttu-id="867b4-250">A ID de investigação automatizada disparada por esse alerta.</span><span class="sxs-lookup"><span data-stu-id="867b4-250">The automated investigation ID triggered by this alert.</span></span> | <span data-ttu-id="867b4-251">1234</span><span class="sxs-lookup"><span data-stu-id="867b4-251">1234</span></span>
<span data-ttu-id="867b4-252">investigationState</span><span class="sxs-lookup"><span data-stu-id="867b4-252">investigationState</span></span> | <span data-ttu-id="867b4-253">Informações sobre o status atual da investigação.</span><span class="sxs-lookup"><span data-stu-id="867b4-253">Information on the investigation's current status.</span></span> <span data-ttu-id="867b4-254">Um dos seguintes valores: *Unknown* *,* Terminated , *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Enued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span><span class="sxs-lookup"><span data-stu-id="867b4-254">One of the following values: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="867b4-255">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="867b4-255">UnsupportedAlertType</span></span>
<span data-ttu-id="867b4-256">classificação</span><span class="sxs-lookup"><span data-stu-id="867b4-256">classification</span></span> | <span data-ttu-id="867b4-257">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="867b4-257">The specification for the incident.</span></span> <span data-ttu-id="867b4-258">Os valores da propriedade são: *Unknown*, *FalsePositive*, *TruePositive* ou *null*</span><span class="sxs-lookup"><span data-stu-id="867b4-258">The property values are: *Unknown*, *FalsePositive*, *TruePositive*, or *null*</span></span> | <span data-ttu-id="867b4-259">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="867b4-259">Unknown</span></span>
<span data-ttu-id="867b4-260">determinação</span><span class="sxs-lookup"><span data-stu-id="867b4-260">determination</span></span> | <span data-ttu-id="867b4-261">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="867b4-261">Specifies the determination of the incident.</span></span> <span data-ttu-id="867b4-262">Os valores da propriedade são: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel,* *SecurityTesting,* *UnwantedSoftware*, *Other* ou  *null*</span><span class="sxs-lookup"><span data-stu-id="867b4-262">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span> | <span data-ttu-id="867b4-263">Apt</span><span class="sxs-lookup"><span data-stu-id="867b4-263">Apt</span></span>
<span data-ttu-id="867b4-264">assignedTo</span><span class="sxs-lookup"><span data-stu-id="867b4-264">assignedTo</span></span> | <span data-ttu-id="867b4-265">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="867b4-265">Owner of the incident, or *null* if no owner is assigned.</span></span> | <span data-ttu-id="867b4-266">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="867b4-266">secop2@contoso.com</span></span>
<span data-ttu-id="867b4-267">actorName</span><span class="sxs-lookup"><span data-stu-id="867b4-267">actorName</span></span> | <span data-ttu-id="867b4-268">O grupo de atividades, se for o caso, o associado a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="867b4-268">The activity group, if any, the  associated with this alert.</span></span> | <span data-ttu-id="867b4-269">BORON</span><span class="sxs-lookup"><span data-stu-id="867b4-269">BORON</span></span>
<span data-ttu-id="867b4-270">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="867b4-270">threatFamilyName</span></span> | <span data-ttu-id="867b4-271">Família de ameaças associada a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="867b4-271">Threat family associated with this alert.</span></span> | <span data-ttu-id="867b4-272">null</span><span class="sxs-lookup"><span data-stu-id="867b4-272">null</span></span>
<span data-ttu-id="867b4-273">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="867b4-273">mitreTechniques</span></span> | <span data-ttu-id="867b4-274">As técnicas de ataque, conforme alinhadas com o [MITRE ATT](https://attack.mitre.org/)&CK ™ estrutura.</span><span class="sxs-lookup"><span data-stu-id="867b4-274">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span> | \[\]
<span data-ttu-id="867b4-275">devices</span><span class="sxs-lookup"><span data-stu-id="867b4-275">devices</span></span> | <span data-ttu-id="867b4-276">Todos os dispositivos onde os alertas relacionados ao incidente foram enviados.</span><span class="sxs-lookup"><span data-stu-id="867b4-276">All devices where alerts related to the incident were sent.</span></span> | <span data-ttu-id="867b4-277">\[\] (consulte detalhes sobre os campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="867b4-277">\[\] (see details on entity fields below)</span></span>

### <a name="device-format"></a><span data-ttu-id="867b4-278">Formato de dispositivo</span><span class="sxs-lookup"><span data-stu-id="867b4-278">Device format</span></span>

<span data-ttu-id="867b4-279">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="867b4-279">Field name</span></span> | <span data-ttu-id="867b4-280">Descrição</span><span class="sxs-lookup"><span data-stu-id="867b4-280">Description</span></span> | <span data-ttu-id="867b4-281">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="867b4-281">Example value</span></span>
-|-|-
<span data-ttu-id="867b4-282">DeviceId</span><span class="sxs-lookup"><span data-stu-id="867b4-282">DeviceId</span></span> | <span data-ttu-id="867b4-283">A ID do dispositivo conforme designado no Microsoft Defender para Ponto de Extremidade.</span><span class="sxs-lookup"><span data-stu-id="867b4-283">The device ID as designated in Microsoft Defender for Endpoint.</span></span> | <span data-ttu-id="867b4-284">24c222b0b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="867b4-284">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>
<span data-ttu-id="867b4-285">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="867b4-285">aadDeviceId</span></span> |  <span data-ttu-id="867b4-286">A ID do dispositivo conforme designado em [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span><span class="sxs-lookup"><span data-stu-id="867b4-286">The device ID as designated in [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-whatis).</span></span> <span data-ttu-id="867b4-287">Disponível apenas para dispositivos ingressados no domínio.</span><span class="sxs-lookup"><span data-stu-id="867b4-287">Only available for domain-joined devices.</span></span> | <span data-ttu-id="867b4-288">null</span><span class="sxs-lookup"><span data-stu-id="867b4-288">null</span></span>
<span data-ttu-id="867b4-289">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="867b4-289">deviceDnsName</span></span> | <span data-ttu-id="867b4-290">O nome de domínio totalmente qualificado para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="867b4-290">The fully qualified domain name for the device.</span></span> | <span data-ttu-id="867b4-291">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="867b4-291">user5cx.middleeast.corp.contoso.com</span></span>
<span data-ttu-id="867b4-292">osPlatform</span><span class="sxs-lookup"><span data-stu-id="867b4-292">osPlatform</span></span> | <span data-ttu-id="867b4-293">A plataforma do sistema operacional que o dispositivo está executando.</span><span class="sxs-lookup"><span data-stu-id="867b4-293">The OS platform the device is running.</span></span>| <span data-ttu-id="867b4-294">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="867b4-294">WindowsServer2016</span></span>
<span data-ttu-id="867b4-295">osBuild</span><span class="sxs-lookup"><span data-stu-id="867b4-295">osBuild</span></span> | <span data-ttu-id="867b4-296">A versão de com build do sistema operacional em execução do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="867b4-296">The build version for the OS the device is running.</span></span> | <span data-ttu-id="867b4-297">14393</span><span class="sxs-lookup"><span data-stu-id="867b4-297">14393</span></span>
<span data-ttu-id="867b4-298">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="867b4-298">rbacGroupName</span></span> | <span data-ttu-id="867b4-299">O grupo de controle [de acesso](/azure/role-based-access-control/overview) baseado em função (RBAC) associado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="867b4-299">The [role-based access control](/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span> | <span data-ttu-id="867b4-300">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="867b4-300">WDATP-Ring0</span></span>
<span data-ttu-id="867b4-301">firstSeen</span><span class="sxs-lookup"><span data-stu-id="867b4-301">firstSeen</span></span> | <span data-ttu-id="867b4-302">Hora em que o dispositivo foi visto pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="867b4-302">Time when device was first seen.</span></span> | <span data-ttu-id="867b4-303">2020-02-06T14:16:01.9330135Z</span><span class="sxs-lookup"><span data-stu-id="867b4-303">2020-02-06T14:16:01.9330135Z</span></span>
<span data-ttu-id="867b4-304">healthStatus</span><span class="sxs-lookup"><span data-stu-id="867b4-304">healthStatus</span></span> | <span data-ttu-id="867b4-305">O estado de saúde do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="867b4-305">The health state of the device.</span></span> | <span data-ttu-id="867b4-306">Ativo</span><span class="sxs-lookup"><span data-stu-id="867b4-306">Active</span></span>
<span data-ttu-id="867b4-307">riskScore</span><span class="sxs-lookup"><span data-stu-id="867b4-307">riskScore</span></span> | <span data-ttu-id="867b4-308">A pontuação de risco do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="867b4-308">The risk score for the  device.</span></span> | <span data-ttu-id="867b4-309">Alto</span><span class="sxs-lookup"><span data-stu-id="867b4-309">High</span></span>
<span data-ttu-id="867b4-310">entidades</span><span class="sxs-lookup"><span data-stu-id="867b4-310">entities</span></span> | <span data-ttu-id="867b4-311">Todas as entidades identificadas para fazer parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="867b4-311">All entities that have been identified to be part of, or related to, a given alert.</span></span> | <span data-ttu-id="867b4-312">\[\] (consulte detalhes sobre os campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="867b4-312">\[\] (see details on entity fields below)</span></span>

### <a name="entity-format"></a><span data-ttu-id="867b4-313">Formato de entidade</span><span class="sxs-lookup"><span data-stu-id="867b4-313">Entity Format</span></span>

<span data-ttu-id="867b4-314">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="867b4-314">Field name</span></span> | <span data-ttu-id="867b4-315">Descrição</span><span class="sxs-lookup"><span data-stu-id="867b4-315">Description</span></span> | <span data-ttu-id="867b4-316">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="867b4-316">Example value</span></span>
-|-|-
<span data-ttu-id="867b4-317">entityType</span><span class="sxs-lookup"><span data-stu-id="867b4-317">entityType</span></span> | <span data-ttu-id="867b4-318">Entidades identificadas para fazer parte ou relacionadas a um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="867b4-318">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="867b4-319">Os valores das propriedades são: *User*, *Ip*, *Url*, File , *Process*, *MailBox*, *MailMessage,* *MailCluster*, *Registry* </span><span class="sxs-lookup"><span data-stu-id="867b4-319">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span> | <span data-ttu-id="867b4-320">User</span><span class="sxs-lookup"><span data-stu-id="867b4-320">User</span></span>
<span data-ttu-id="867b4-321">sha1</span><span class="sxs-lookup"><span data-stu-id="867b4-321">sha1</span></span> | <span data-ttu-id="867b4-322">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="867b4-322">Available if entityType is *File*.</span></span><br><span data-ttu-id="867b4-323">O hash de arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="867b4-323">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="867b4-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="867b4-324">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>
<span data-ttu-id="867b4-325">sha256</span><span class="sxs-lookup"><span data-stu-id="867b4-325">sha256</span></span> | <span data-ttu-id="867b4-326">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="867b4-326">Available if entityType is *File*.</span></span><br><span data-ttu-id="867b4-327">O hash de arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="867b4-327">The file hash for alerts associated with a file or process.</span></span> | <span data-ttu-id="867b4-328">28cb017dfc99073a1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="867b4-328">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>
<span data-ttu-id="867b4-329">fileName</span><span class="sxs-lookup"><span data-stu-id="867b4-329">fileName</span></span> | <span data-ttu-id="867b4-330">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="867b4-330">Available if entityType is *File*.</span></span><br><span data-ttu-id="867b4-331">O nome do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="867b4-331">The file name for alerts associated with a file or process</span></span> | <span data-ttu-id="867b4-332">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="867b4-332">Detector.UnitTests.dll</span></span>
<span data-ttu-id="867b4-333">filePath</span><span class="sxs-lookup"><span data-stu-id="867b4-333">filePath</span></span> | <span data-ttu-id="867b4-334">Disponível se entityType for *File*.</span><span class="sxs-lookup"><span data-stu-id="867b4-334">Available if entityType is *File*.</span></span><br><span data-ttu-id="867b4-335">O caminho do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="867b4-335">The file path for alerts associated with a file or process</span></span> | <span data-ttu-id="867b4-336">C: \\ \agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span><span class="sxs-lookup"><span data-stu-id="867b4-336">C:\\\agent_work_temp\Deploy\SYSTEM\2020-09-06 12_14_54\Out</span></span>
<span data-ttu-id="867b4-337">processId</span><span class="sxs-lookup"><span data-stu-id="867b4-337">processId</span></span> | <span data-ttu-id="867b4-338">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="867b4-338">Available if entityType is *Process*.</span></span> | <span data-ttu-id="867b4-339">24348</span><span class="sxs-lookup"><span data-stu-id="867b4-339">24348</span></span>
<span data-ttu-id="867b4-340">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="867b4-340">processCommandLine</span></span> | <span data-ttu-id="867b4-341">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="867b4-341">Available if entityType is *Process*.</span></span> | <span data-ttu-id="867b4-342">"Seu arquivo está pronto para baixar \_1911150169.exe"</span><span class="sxs-lookup"><span data-stu-id="867b4-342">"Your File Is Ready To Download\_1911150169.exe"</span></span>
<span data-ttu-id="867b4-343">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="867b4-343">processCreationTime</span></span> | <span data-ttu-id="867b4-344">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="867b4-344">Available if entityType is *Process*.</span></span> | <span data-ttu-id="867b4-345">2020-07-18T03:25:38.5269993Z</span><span class="sxs-lookup"><span data-stu-id="867b4-345">2020-07-18T03:25:38.5269993Z</span></span>
<span data-ttu-id="867b4-346">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="867b4-346">parentProcessId</span></span> | <span data-ttu-id="867b4-347">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="867b4-347">Available if entityType is *Process*.</span></span> | <span data-ttu-id="867b4-348">16840</span><span class="sxs-lookup"><span data-stu-id="867b4-348">16840</span></span>
<span data-ttu-id="867b4-349">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="867b4-349">parentProcessCreationTime</span></span> | <span data-ttu-id="867b4-350">Disponível se entityType for *Process*.</span><span class="sxs-lookup"><span data-stu-id="867b4-350">Available if entityType is *Process*.</span></span> | <span data-ttu-id="867b4-351">2020-07-18T02:12:32.8616797Z</span><span class="sxs-lookup"><span data-stu-id="867b4-351">2020-07-18T02:12:32.8616797Z</span></span>
<span data-ttu-id="867b4-352">ipAddress</span><span class="sxs-lookup"><span data-stu-id="867b4-352">ipAddress</span></span> | <span data-ttu-id="867b4-353">Disponível se entityType for *Ip*.</span><span class="sxs-lookup"><span data-stu-id="867b4-353">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="867b4-354">Endereço IP para alertas associados a eventos de rede, como *Comunicação a um destino de rede mal-intencionado.*</span><span class="sxs-lookup"><span data-stu-id="867b4-354">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="867b4-355">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="867b4-355">62.216.203.204</span></span>
<span data-ttu-id="867b4-356">url</span><span class="sxs-lookup"><span data-stu-id="867b4-356">url</span></span> | <span data-ttu-id="867b4-357">Disponível se entityType for *Url*.</span><span class="sxs-lookup"><span data-stu-id="867b4-357">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="867b4-358">URL para alertas associados a eventos de rede, como Comunicação *a um destino de rede mal-intencionado.*</span><span class="sxs-lookup"><span data-stu-id="867b4-358">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span> | <span data-ttu-id="867b4-359">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="867b4-359">down.esales360.cn</span></span>
<span data-ttu-id="867b4-360">accountName</span><span class="sxs-lookup"><span data-stu-id="867b4-360">accountName</span></span> | <span data-ttu-id="867b4-361">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="867b4-361">Available if entityType is *User*.</span></span> | <span data-ttu-id="867b4-362">testUser2</span><span class="sxs-lookup"><span data-stu-id="867b4-362">testUser2</span></span>
<span data-ttu-id="867b4-363">domainName</span><span class="sxs-lookup"><span data-stu-id="867b4-363">domainName</span></span> | <span data-ttu-id="867b4-364">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="867b4-364">Available if entityType is *User*.</span></span> | <span data-ttu-id="867b4-365">europe.corp.contoso</span><span class="sxs-lookup"><span data-stu-id="867b4-365">europe.corp.contoso</span></span>
<span data-ttu-id="867b4-366">userSid</span><span class="sxs-lookup"><span data-stu-id="867b4-366">userSid</span></span> | <span data-ttu-id="867b4-367">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="867b4-367">Available if entityType is *User*.</span></span> | <span data-ttu-id="867b4-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="867b4-368">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>
<span data-ttu-id="867b4-369">aadUserId</span><span class="sxs-lookup"><span data-stu-id="867b4-369">aadUserId</span></span> | <span data-ttu-id="867b4-370">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="867b4-370">Available if entityType is *User*.</span></span> | <span data-ttu-id="867b4-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="867b4-371">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>
<span data-ttu-id="867b4-372">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="867b4-372">userPrincipalName</span></span> | <span data-ttu-id="867b4-373">Disponível se entityType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="867b4-373">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="867b4-374">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="867b4-374">testUser2@contoso.com</span></span>
<span data-ttu-id="867b4-375">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="867b4-375">mailboxDisplayName</span></span> | <span data-ttu-id="867b4-376">Disponível se entityType for *MailBox*.</span><span class="sxs-lookup"><span data-stu-id="867b4-376">Available if entityType is *MailBox*.</span></span> | <span data-ttu-id="867b4-377">test User2</span><span class="sxs-lookup"><span data-stu-id="867b4-377">test User2</span></span>
<span data-ttu-id="867b4-378">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="867b4-378">mailboxAddress</span></span> | <span data-ttu-id="867b4-379">Disponível se entityType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="867b4-379">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="867b4-380">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="867b4-380">testUser2@contoso.com</span></span>
<span data-ttu-id="867b4-381">clusterBy</span><span class="sxs-lookup"><span data-stu-id="867b4-381">clusterBy</span></span> | <span data-ttu-id="867b4-382">Disponível se entityType for  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="867b4-382">Available if entityType is  *MailCluster*.</span></span> | <span data-ttu-id="867b4-383">Assunto; P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="867b4-383">Subject;P2SenderDomain;ContentType</span></span>
<span data-ttu-id="867b4-384">remetente</span><span class="sxs-lookup"><span data-stu-id="867b4-384">sender</span></span> | <span data-ttu-id="867b4-385">Disponível se entityType for *User* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="867b4-385">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span> | <span data-ttu-id="867b4-386">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="867b4-386">user.abc@mail.contoso.co.in</span></span>
<span data-ttu-id="867b4-387">destinatário</span><span class="sxs-lookup"><span data-stu-id="867b4-387">recipient</span></span> | <span data-ttu-id="867b4-388">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="867b4-388">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="867b4-389">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="867b4-389">testUser2@contoso.com</span></span>
<span data-ttu-id="867b4-390">Assunto</span><span class="sxs-lookup"><span data-stu-id="867b4-390">subject</span></span> | <span data-ttu-id="867b4-391">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="867b4-391">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="867b4-392">\[Atenção \] EXTERNA</span><span class="sxs-lookup"><span data-stu-id="867b4-392">\[EXTERNAL\] Attention</span></span>
<span data-ttu-id="867b4-393">deliveryAction</span><span class="sxs-lookup"><span data-stu-id="867b4-393">deliveryAction</span></span> | <span data-ttu-id="867b4-394">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="867b4-394">Available if entityType is *MailMessage*.</span></span> | <span data-ttu-id="867b4-395">Entregue</span><span class="sxs-lookup"><span data-stu-id="867b4-395">Delivered</span></span>
<span data-ttu-id="867b4-396">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="867b4-396">securityGroupId</span></span> | <span data-ttu-id="867b4-397">Disponível se entityType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="867b4-397">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="867b4-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="867b4-398">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>
<span data-ttu-id="867b4-399">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="867b4-399">securityGroupName</span></span> | <span data-ttu-id="867b4-400">Disponível se entityType for  *SecurityGroup*.</span><span class="sxs-lookup"><span data-stu-id="867b4-400">Available if entityType is  *SecurityGroup*.</span></span> | <span data-ttu-id="867b4-401">Operadores de Configuração de Rede</span><span class="sxs-lookup"><span data-stu-id="867b4-401">Network Configuration Operators</span></span>
<span data-ttu-id="867b4-402">registryHive</span><span class="sxs-lookup"><span data-stu-id="867b4-402">registryHive</span></span> | <span data-ttu-id="867b4-403">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="867b4-403">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="867b4-404">MÁQUINA LOCAL HKEY \_ \_</span><span class="sxs-lookup"><span data-stu-id="867b4-404">HKEY\_LOCAL\_MACHINE</span></span> |
<span data-ttu-id="867b4-405">registryKey</span><span class="sxs-lookup"><span data-stu-id="867b4-405">registryKey</span></span> | <span data-ttu-id="867b4-406">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="867b4-406">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="867b4-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span><span class="sxs-lookup"><span data-stu-id="867b4-407">SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon</span></span>
<span data-ttu-id="867b4-408">registryValueType</span><span class="sxs-lookup"><span data-stu-id="867b4-408">registryValueType</span></span> | <span data-ttu-id="867b4-409">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="867b4-409">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="867b4-410">String</span><span class="sxs-lookup"><span data-stu-id="867b4-410">String</span></span>
<span data-ttu-id="867b4-411">registryValue</span><span class="sxs-lookup"><span data-stu-id="867b4-411">registryValue</span></span> | <span data-ttu-id="867b4-412">Disponível se entityType for  *Registry*.</span><span class="sxs-lookup"><span data-stu-id="867b4-412">Available if entityType is  *Registry*.</span></span> | <span data-ttu-id="867b4-413">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="867b4-413">31-00-00-00</span></span>
<span data-ttu-id="867b4-414">deviceId</span><span class="sxs-lookup"><span data-stu-id="867b4-414">deviceId</span></span> | <span data-ttu-id="867b4-415">A ID, se for o caso, do dispositivo relacionado à entidade.</span><span class="sxs-lookup"><span data-stu-id="867b4-415">The ID, if any, of the device related to the entity.</span></span> | <span data-ttu-id="867b4-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="867b4-416">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>

## <a name="example"></a><span data-ttu-id="867b4-417">Exemplo</span><span class="sxs-lookup"><span data-stu-id="867b4-417">Example</span></span>

### <a name="request"></a><span data-ttu-id="867b4-418">Solicitação</span><span class="sxs-lookup"><span data-stu-id="867b4-418">Request</span></span>

```HTTP
GET https://api.security.microsoft.com/api/incidents
```

### <a name="response"></a><span data-ttu-id="867b4-419">Resposta</span><span class="sxs-lookup"><span data-stu-id="867b4-419">Response</span></span>

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

## <a name="related-articles"></a><span data-ttu-id="867b4-420">Artigos relacionados</span><span class="sxs-lookup"><span data-stu-id="867b4-420">Related articles</span></span>

- [<span data-ttu-id="867b4-421">Acessar as APIs Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="867b4-421">Access the Microsoft 365 Defender APIs</span></span>](api-access.md)
- [<span data-ttu-id="867b4-422">Saiba mais sobre limites de API e licenciamento</span><span class="sxs-lookup"><span data-stu-id="867b4-422">Learn about API limits and licensing</span></span>](api-terms.md)
- [<span data-ttu-id="867b4-423">Compreender códigos de erro</span><span class="sxs-lookup"><span data-stu-id="867b4-423">Understand error codes</span></span>](api-error-codes.md)
- [<span data-ttu-id="867b4-424">Visão geral dos incidentes</span><span class="sxs-lookup"><span data-stu-id="867b4-424">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="867b4-425">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="867b4-425">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="867b4-426">Atualizar API de incidentes</span><span class="sxs-lookup"><span data-stu-id="867b4-426">Update incident API</span></span>](api-update-incidents.md)
