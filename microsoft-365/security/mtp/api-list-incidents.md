---
title: Listar a API de incidentes no Microsoft Threat Protection
description: Saiba como listar a API de incidentes no Microsoft Threat Protection
keywords: lista, incidente, incidentes, API
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 9defc9c0f8fa04e019c0108ca0f4111de54edb5f
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195371"
---
# <a name="list-incidents-api-in-microsoft-threat-protection"></a><span data-ttu-id="92dbd-104">Listar a API de incidentes no Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="92dbd-104">List incidents API in Microsoft Threat Protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="92dbd-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="92dbd-105">**Applies to:**</span></span>

- <span data-ttu-id="92dbd-106">Proteção contra Ameaças da Microsoft</span><span class="sxs-lookup"><span data-stu-id="92dbd-106">Microsoft Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="92dbd-107">Algumas informações estão relacionadas ao produto já publicado que pode ser modificado substancialmente antes de ser lançado comercialmente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-107">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="92dbd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span><span class="sxs-lookup"><span data-stu-id="92dbd-108">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>


## <a name="api-description"></a><span data-ttu-id="92dbd-109">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="92dbd-109">API description</span></span>

<span data-ttu-id="92dbd-110">A API de incidentes permite que você classifique por meio de incidentes para priorizar e criar uma resposta cybersecurity informada.</span><span class="sxs-lookup"><span data-stu-id="92dbd-110">The Incident API allows you to sort through incidents to prioritize and create an informed cybersecurity response.</span></span> <span data-ttu-id="92dbd-111">Ele expõe uma coleção de incidentes que foram sinalizados de dispositivos, contas de email e usuários em sua rede, dentro do intervalo de tempo especificado em sua política de retenção de ambiente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-111">It exposes a collection of incidents that were flagged from devices, email accounts, and users in your network, within the time range you specified in your environment retention policy.</span></span> <span data-ttu-id="92dbd-112">Os incidentes mais recentes são exibidos na parte superior da lista.</span><span class="sxs-lookup"><span data-stu-id="92dbd-112">The most recent incidents are displayed at the top of the list.</span></span> <span data-ttu-id="92dbd-113">Cada incidente contém uma matriz de alertas relacionados e suas entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="92dbd-113">Each incident contains an array of related alerts, and their related entities.</span></span>

<br><span data-ttu-id="92dbd-114">A API oferece suporte aos seguintes operadores **OData** :</span><span class="sxs-lookup"><span data-stu-id="92dbd-114">The API supports the following **OData** operators:</span></span>
<br><span data-ttu-id="92dbd-115">```$filter``` nas ```lastUpdateTime``` Propriedades: ```createdTime``` , ```status``` e ```assignedTo``` .</span><span class="sxs-lookup"><span data-stu-id="92dbd-115">```$filter``` on: ```lastUpdateTime```, ```createdTime```, ```status``` and ```assignedTo``` properties.</span></span>
<br><span data-ttu-id="92dbd-116">```$top``` com o valor máximo de **100**</span><span class="sxs-lookup"><span data-stu-id="92dbd-116">```$top``` with max value of **100**</span></span>
<br>```$skip```

## <a name="limitations"></a><span data-ttu-id="92dbd-117">Limitações</span><span class="sxs-lookup"><span data-stu-id="92dbd-117">Limitations</span></span>

1. <span data-ttu-id="92dbd-118">O tamanho máximo da página é de **100 incidentes**.</span><span class="sxs-lookup"><span data-stu-id="92dbd-118">Maximum page size is **100 incidents**.</span></span>
2. <span data-ttu-id="92dbd-119">A taxa máxima de solicitações é de **50 chamadas por minuto** e **1500 de chamadas por hora**.</span><span class="sxs-lookup"><span data-stu-id="92dbd-119">Maximum rate of requests is **50 calls per minute** and **1500 calls per hour**.</span></span>

## <a name="permissions"></a><span data-ttu-id="92dbd-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="92dbd-120">Permissions</span></span>

<span data-ttu-id="92dbd-121">Uma das seguintes permissões é necessária para chamar esta API.</span><span class="sxs-lookup"><span data-stu-id="92dbd-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="92dbd-122">Para saber mais, incluindo como escolher permissões, confira [acessar APIs de proteção contra ameaças da Microsoft](api-access.md)</span><span class="sxs-lookup"><span data-stu-id="92dbd-122">To learn more, including how to choose permissions, see [Access Microsoft Threat Protection APIs](api-access.md)</span></span>

<span data-ttu-id="92dbd-123">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="92dbd-123">Permission type</span></span> |   <span data-ttu-id="92dbd-124">Permissão</span><span class="sxs-lookup"><span data-stu-id="92dbd-124">Permission</span></span>  |   <span data-ttu-id="92dbd-125">Nome para exibição da permissão</span><span class="sxs-lookup"><span data-stu-id="92dbd-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="92dbd-126">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="92dbd-126">Application</span></span> |   <span data-ttu-id="92dbd-127">Incident. Read. All</span><span class="sxs-lookup"><span data-stu-id="92dbd-127">Incident.Read.All</span></span> | <span data-ttu-id="92dbd-128">' Ler todos os incidentes '</span><span class="sxs-lookup"><span data-stu-id="92dbd-128">'Read all incidents'</span></span>
<span data-ttu-id="92dbd-129">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="92dbd-129">Application</span></span> |   <span data-ttu-id="92dbd-130">Incident. ReadWrite. All</span><span class="sxs-lookup"><span data-stu-id="92dbd-130">Incident.ReadWrite.All</span></span> | <span data-ttu-id="92dbd-131">' Ler e gravar todos os incidentes '</span><span class="sxs-lookup"><span data-stu-id="92dbd-131">'Read and write all incidents'</span></span>
<span data-ttu-id="92dbd-132">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="92dbd-132">Delegated (work or school account)</span></span> | <span data-ttu-id="92dbd-133">Incidente. Read</span><span class="sxs-lookup"><span data-stu-id="92dbd-133">Incident.Read</span></span> | <span data-ttu-id="92dbd-134">"Ler incidentes"</span><span class="sxs-lookup"><span data-stu-id="92dbd-134">'Read incidents'</span></span>
<span data-ttu-id="92dbd-135">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="92dbd-135">Delegated (work or school account)</span></span> | <span data-ttu-id="92dbd-136">Incident. ReadWrite</span><span class="sxs-lookup"><span data-stu-id="92dbd-136">Incident.ReadWrite</span></span> | <span data-ttu-id="92dbd-137">' Ler e gravar incidentes '</span><span class="sxs-lookup"><span data-stu-id="92dbd-137">'Read and write incidents'</span></span>

> [!Note]
> <span data-ttu-id="92dbd-138">Ao obter um token usando as credenciais do usuário:</span><span class="sxs-lookup"><span data-stu-id="92dbd-138">When obtaining a token using user credentials:</span></span>
> - <span data-ttu-id="92dbd-139">O usuário precisa ter permissão de exibição para incidentes no Portal.</span><span class="sxs-lookup"><span data-stu-id="92dbd-139">The user needs to have view permission for incidents in the portal.</span></span>
> - <span data-ttu-id="92dbd-140">A resposta só incluirá incidentes aos quais o usuário está exposto.</span><span class="sxs-lookup"><span data-stu-id="92dbd-140">The response will only include incidents that the user is exposed to.</span></span>

## <a name="http-request"></a><span data-ttu-id="92dbd-141">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="92dbd-141">HTTP request</span></span>

```
GET /api/incidents
```

## <a name="request-headers"></a><span data-ttu-id="92dbd-142">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="92dbd-142">Request headers</span></span>

<span data-ttu-id="92dbd-143">Nome</span><span class="sxs-lookup"><span data-stu-id="92dbd-143">Name</span></span> | <span data-ttu-id="92dbd-144">Tipo</span><span class="sxs-lookup"><span data-stu-id="92dbd-144">Type</span></span> | <span data-ttu-id="92dbd-145">Descrição</span><span class="sxs-lookup"><span data-stu-id="92dbd-145">Description</span></span>
:---|:---|:---
<span data-ttu-id="92dbd-146">Autorização</span><span class="sxs-lookup"><span data-stu-id="92dbd-146">Authorization</span></span> | <span data-ttu-id="92dbd-147">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92dbd-147">String</span></span> | <span data-ttu-id="92dbd-148">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="92dbd-148">Bearer {token}.</span></span> <span data-ttu-id="92dbd-149">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="92dbd-149">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="92dbd-150">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="92dbd-150">Request body</span></span>
<span data-ttu-id="92dbd-151">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="92dbd-151">None.</span></span>

## <a name="response"></a><span data-ttu-id="92dbd-152">Resposta</span><span class="sxs-lookup"><span data-stu-id="92dbd-152">Response</span></span>
<span data-ttu-id="92dbd-153">Se tiver êxito, este método retornará 200 OK e uma lista de [incidentes](api-incident.md) no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="92dbd-153">If successful, this method returns 200 OK, and a list of [incidents](api-incident.md) in the response body.</span></span>

## <a name="schema-mapping"></a><span data-ttu-id="92dbd-154">Mapeamento de esquema</span><span class="sxs-lookup"><span data-stu-id="92dbd-154">Schema mapping</span></span>

| <span data-ttu-id="92dbd-155">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="92dbd-155">Field name</span></span>                                | <span data-ttu-id="92dbd-156">Descrição</span><span class="sxs-lookup"><span data-stu-id="92dbd-156">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-157">Valor de exemplo</span><span class="sxs-lookup"><span data-stu-id="92dbd-157">Example value</span></span>                                                                                                                                                                                                                                     |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="92dbd-158">**Metadados de incidentes**</span><span class="sxs-lookup"><span data-stu-id="92dbd-158">**Incident metadata**</span></span>                         |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="92dbd-159">incidentalid</span><span class="sxs-lookup"><span data-stu-id="92dbd-159">incidentId</span></span>                                | <span data-ttu-id="92dbd-160">Identificador exclusivo para representar o incidente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-160">Unique identifier to represent the incident.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-161">924565</span><span class="sxs-lookup"><span data-stu-id="92dbd-161">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-162">redirectIncidentId</span><span class="sxs-lookup"><span data-stu-id="92dbd-162">redirectIncidentId</span></span>                        | <span data-ttu-id="92dbd-163">Apenas preenchido no caso de um incidente ser agrupado com outro incidente, como parte da lógica de processamento de incidentes.</span><span class="sxs-lookup"><span data-stu-id="92dbd-163">Only populated in case an incident is being grouped together with another incident, as part of the incident processing logic.</span></span>                                                                                                                                                                                                                                                           | <span data-ttu-id="92dbd-164">924569</span><span class="sxs-lookup"><span data-stu-id="92dbd-164">924569</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-165">incidentalname</span><span class="sxs-lookup"><span data-stu-id="92dbd-165">incidentName</span></span>                              | <span data-ttu-id="92dbd-166">Valor de cadeia de caracteres disponível para cada incidente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-166">String value available for every incident.</span></span>                                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="92dbd-167">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="92dbd-167">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="92dbd-168">createdtime</span><span class="sxs-lookup"><span data-stu-id="92dbd-168">createdTime</span></span>                               | <span data-ttu-id="92dbd-169">Hora em que o incidente foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="92dbd-169">Time when incident was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                      | <span data-ttu-id="92dbd-170">2020-09-06T14:46:57.0733333 Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-170">2020-09-06T14:46:57.0733333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-171">lastUpdateTime</span><span class="sxs-lookup"><span data-stu-id="92dbd-171">lastUpdateTime</span></span>                            | <span data-ttu-id="92dbd-172">Hora em que o incidente foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="92dbd-172">Time when incident was last updated at the backend.</span></span><br> <span data-ttu-id="92dbd-173">Este campo pode ser usado ao definir o parâmetro de solicitação para o intervalo de tempo em que os incidentes são recuperados.</span><span class="sxs-lookup"><span data-stu-id="92dbd-173">This field can be used when setting the request parameter for the range of time that incidents are retrieved.</span></span>                                                                                                                                                                                                                      | <span data-ttu-id="92dbd-174">2020-09-06T14:46:57.29 Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-174">2020-09-06T14:46:57.29Z</span></span>                                                                                                                                                                                                                           |
| <span data-ttu-id="92dbd-175">assignedTo</span><span class="sxs-lookup"><span data-stu-id="92dbd-175">assignedTo</span></span>                                | <span data-ttu-id="92dbd-176">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="92dbd-176">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="92dbd-177">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92dbd-177">secop2@contoso.com</span></span>                                                                                                                                                                                                |
| <span data-ttu-id="92dbd-178">classificação</span><span class="sxs-lookup"><span data-stu-id="92dbd-178">classification</span></span>                            | <span data-ttu-id="92dbd-179">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-179">The specification for the incident.</span></span> <span data-ttu-id="92dbd-180">Os valores da propriedade são: *desconhecido*, *FalsePositive*, *TruePositive*</span><span class="sxs-lookup"><span data-stu-id="92dbd-180">The property values are: *Unknown*, *FalsePositive*, *TruePositive*</span></span>                                                                                                                                                                                                                                                                           | <span data-ttu-id="92dbd-181">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="92dbd-181">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="92dbd-182">determinação</span><span class="sxs-lookup"><span data-stu-id="92dbd-182">determination</span></span>                             | <span data-ttu-id="92dbd-183">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-183">Specifies the determination of the incident.</span></span> <span data-ttu-id="92dbd-184">Os valores de propriedade são: *não disponível*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *outros*</span><span class="sxs-lookup"><span data-stu-id="92dbd-184">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other*</span></span>                                                                                                                                                                                                                | <span data-ttu-id="92dbd-185">Não disponível</span><span class="sxs-lookup"><span data-stu-id="92dbd-185">NotAvailable</span></span>                                                                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-186">status</span><span class="sxs-lookup"><span data-stu-id="92dbd-186">status</span></span>                                    | <span data-ttu-id="92dbd-187">Categorizar incidentes (como *ativos*ou *resolvidos*).</span><span class="sxs-lookup"><span data-stu-id="92dbd-187">Categorize incidents (as *Active*, or *Resolved*).</span></span> <span data-ttu-id="92dbd-188">Isso ajuda a organizar e gerenciar sua resposta a incidentes.</span><span class="sxs-lookup"><span data-stu-id="92dbd-188">This helps you organize and manage your response to incidents.</span></span>                                                                                                                                                                                                                                                                  | <span data-ttu-id="92dbd-189">Ativo</span><span class="sxs-lookup"><span data-stu-id="92dbd-189">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-190">severity</span><span class="sxs-lookup"><span data-stu-id="92dbd-190">severity</span></span>                                  | <span data-ttu-id="92dbd-191">Indica o possível impacto nos ativos.</span><span class="sxs-lookup"><span data-stu-id="92dbd-191">Indicates the possible impact on assets.</span></span> <span data-ttu-id="92dbd-192">Quanto maior a gravidade, maior o impacto.</span><span class="sxs-lookup"><span data-stu-id="92dbd-192">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="92dbd-193">Normalmente, os itens de maior severidade exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="92dbd-193">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="92dbd-194">Um dos seguintes valores: *informativo*, *baixo*, \* médio e *alto*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-194">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                | <span data-ttu-id="92dbd-195">Médio</span><span class="sxs-lookup"><span data-stu-id="92dbd-195">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-196">categorias</span><span class="sxs-lookup"><span data-stu-id="92dbd-196">tags</span></span>                                      | <span data-ttu-id="92dbd-197">Matriz de marcas personalizadas associadas a um incidente, por exemplo, para sinalizar um grupo de incidentes com uma característica comum.</span><span class="sxs-lookup"><span data-stu-id="92dbd-197">Array of custom tags associated with an incident, for example to flag a group of incidents with a common characteristic.</span></span>                                                                                                                                                                                                                                                                  | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-198">alerts</span><span class="sxs-lookup"><span data-stu-id="92dbd-198">alerts</span></span>                                    | <span data-ttu-id="92dbd-199">Matriz de todos os alertas relacionados ao incidente e outras informações, como gravidade, entidades que estavam envolvidas no alerta, a fonte dos alertas.</span><span class="sxs-lookup"><span data-stu-id="92dbd-199">Array of all the alerts related to the incident and other information, such as severity, entities that were involved in the alert, the source of the alerts.</span></span>                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-200">\[\] (veja detalhes nos campos de alerta abaixo)</span><span class="sxs-lookup"><span data-stu-id="92dbd-200">\[\] (see details on alert fields below)</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="92dbd-201">**Metadados de alertas**</span><span class="sxs-lookup"><span data-stu-id="92dbd-201">**Alerts metadata**</span></span>                           |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="92dbd-202">Alertid</span><span class="sxs-lookup"><span data-stu-id="92dbd-202">alertId</span></span>                                   | <span data-ttu-id="92dbd-203">Identificador exclusivo para representar o alerta</span><span class="sxs-lookup"><span data-stu-id="92dbd-203">Unique identifier to represent the alert</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="92dbd-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span><span class="sxs-lookup"><span data-stu-id="92dbd-204">caD70CFEE2-1F54-32DB-9988-3A868A1EBFAC</span></span>                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-205">incidentalid</span><span class="sxs-lookup"><span data-stu-id="92dbd-205">incidentId</span></span>                                | <span data-ttu-id="92dbd-206">Identificador exclusivo para representar o incidente ao qual este alerta está associado</span><span class="sxs-lookup"><span data-stu-id="92dbd-206">Unique identifier to represent the incident this alert is associated with</span></span>                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="92dbd-207">924565</span><span class="sxs-lookup"><span data-stu-id="92dbd-207">924565</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-208">Unificação de serviço</span><span class="sxs-lookup"><span data-stu-id="92dbd-208">serviceSource</span></span>                             | <span data-ttu-id="92dbd-209">Serviço do qual o alerta se origina, como o Microsoft defender ATP, o Microsoft Cloud app Security, o Azure ATP ou o Office 365 ATP.</span><span class="sxs-lookup"><span data-stu-id="92dbd-209">Service that the alert originates from, such as Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, or Office 365 ATP.</span></span>                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-210">MicrosoftCloudAppSecurity</span><span class="sxs-lookup"><span data-stu-id="92dbd-210">MicrosoftCloudAppSecurity</span></span>                                                                                                                                                                                                                         |
| <span data-ttu-id="92dbd-211">creationTime</span><span class="sxs-lookup"><span data-stu-id="92dbd-211">creationTime</span></span>                              | <span data-ttu-id="92dbd-212">Hora em que o alerta foi criado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="92dbd-212">Time when alert was first created.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="92dbd-213">2020-09-06T14:46:55.7182276 Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-213">2020-09-06T14:46:55.7182276Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-214">lastUpdatedtime</span><span class="sxs-lookup"><span data-stu-id="92dbd-214">lastUpdatedTime</span></span>                           | <span data-ttu-id="92dbd-215">Hora em que o alerta foi atualizado pela última vez no back-end.</span><span class="sxs-lookup"><span data-stu-id="92dbd-215">Time when alert was last updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="92dbd-216">2020-09-06T14:46:57.2433333 Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-216">2020-09-06T14:46:57.2433333Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-217">reresolvitime</span><span class="sxs-lookup"><span data-stu-id="92dbd-217">resolvedTime</span></span>                              | <span data-ttu-id="92dbd-218">Hora em que o alerta foi resolvido.</span><span class="sxs-lookup"><span data-stu-id="92dbd-218">Time when alert was resolved.</span></span>                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="92dbd-219">2020-09-10T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-219">2020-09-10T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-220">firstActivity</span><span class="sxs-lookup"><span data-stu-id="92dbd-220">firstActivity</span></span>                             | <span data-ttu-id="92dbd-221">Hora em que o alerta primeiro informou que a atividade foi atualizada no back-end.</span><span class="sxs-lookup"><span data-stu-id="92dbd-221">Time when alert first reported that activity was updated at the backend.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="92dbd-222">2020-09-04T05:22:59Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-222">2020-09-04T05:22:59Z</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-223">Título</span><span class="sxs-lookup"><span data-stu-id="92dbd-223">title</span></span>                                     | <span data-ttu-id="92dbd-224">Valor de cadeia de caracteres de identificação rápida disponível para cada alerta.</span><span class="sxs-lookup"><span data-stu-id="92dbd-224">Brief identifying string value available for each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-225">Atividade de ransomware</span><span class="sxs-lookup"><span data-stu-id="92dbd-225">Ransomware activity</span></span>                                                                                                                                                                                                                               |
| <span data-ttu-id="92dbd-226">description</span><span class="sxs-lookup"><span data-stu-id="92dbd-226">description</span></span>                               | <span data-ttu-id="92dbd-227">Valor da cadeia de caracteres descrevendo cada alerta.</span><span class="sxs-lookup"><span data-stu-id="92dbd-227">String value describing each alert.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="92dbd-228">O testUser2@contoso.com de teste de usuário (Usuário2) manipulou 99 arquivos com várias extensões terminando com a extensão *Herunterladen*incomuns.</span><span class="sxs-lookup"><span data-stu-id="92dbd-228">The user Test User2 (testUser2@contoso.com) manipulated 99 files with multiple extensions ending with the uncommon extension *herunterladen*.</span></span> <span data-ttu-id="92dbd-229">Esse é um número incomum de manipulação de arquivos e indica um possível ataque de ransomware.</span><span class="sxs-lookup"><span data-stu-id="92dbd-229">This is an unusual number of file manipulations and is indicative of a potential ransomware attack.</span></span> |
| <span data-ttu-id="92dbd-230">category</span><span class="sxs-lookup"><span data-stu-id="92dbd-230">category</span></span>                                  | <span data-ttu-id="92dbd-231">Visual e o modo de exibição numérico de quanto o ataque evoluiu ao longo da cadeia de Kill.</span><span class="sxs-lookup"><span data-stu-id="92dbd-231">Visual and numeric view of how far the attack has progressed along the kill chain.</span></span> <span data-ttu-id="92dbd-232">Alinhado com o [Mitre ATT&CK™ Framework](https://attack.mitre.org/).</span><span class="sxs-lookup"><span data-stu-id="92dbd-232">Aligned to the [MITRE ATT&CK™ framework](https://attack.mitre.org/).</span></span>                                                                                                                                                                                                                           | <span data-ttu-id="92dbd-233">Impacto</span><span class="sxs-lookup"><span data-stu-id="92dbd-233">Impact</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-234">status</span><span class="sxs-lookup"><span data-stu-id="92dbd-234">status</span></span>                                    | <span data-ttu-id="92dbd-235">Categorizar alertas (como *novos*, *ativos*ou *resolvidos*).</span><span class="sxs-lookup"><span data-stu-id="92dbd-235">Categorize alerts (as *New*, *Active*, or *Resolved*).</span></span> <span data-ttu-id="92dbd-236">Isso ajuda a organizar e gerenciar sua resposta a alertas.</span><span class="sxs-lookup"><span data-stu-id="92dbd-236">This helps you organize and manage your response to alerts.</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="92dbd-237">Novo</span><span class="sxs-lookup"><span data-stu-id="92dbd-237">New</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="92dbd-238">severity</span><span class="sxs-lookup"><span data-stu-id="92dbd-238">severity</span></span>                                  | <span data-ttu-id="92dbd-239">Indica o possível impacto nos ativos.</span><span class="sxs-lookup"><span data-stu-id="92dbd-239">Indicates the possible impact on assets.</span></span> <span data-ttu-id="92dbd-240">Quanto maior a gravidade, maior o impacto.</span><span class="sxs-lookup"><span data-stu-id="92dbd-240">The higher the severity the bigger the impact.</span></span> <span data-ttu-id="92dbd-241">Normalmente, os itens de maior severidade exigem a atenção mais imediata.</span><span class="sxs-lookup"><span data-stu-id="92dbd-241">Typically higher severity items require the most immediate attention.</span></span><br><span data-ttu-id="92dbd-242">Um dos seguintes valores: *informativo*, *baixo*, \* médio e *alto*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-242">One of the following values: *Informational*, *Low*, \*Medium, and *High*.</span></span>                                                                                                                                   | <span data-ttu-id="92dbd-243">Médio</span><span class="sxs-lookup"><span data-stu-id="92dbd-243">Medium</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-244">investigaid</span><span class="sxs-lookup"><span data-stu-id="92dbd-244">investigationId</span></span>                           | <span data-ttu-id="92dbd-245">A ID de investigação automatizada disparada por esse alerta.</span><span class="sxs-lookup"><span data-stu-id="92dbd-245">The automated investigation id triggered by this alert.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-246">1234</span><span class="sxs-lookup"><span data-stu-id="92dbd-246">1234</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-247">investigable</span><span class="sxs-lookup"><span data-stu-id="92dbd-247">investigationState</span></span>                        | <span data-ttu-id="92dbd-248">Informações sobre o status atual da investigação.</span><span class="sxs-lookup"><span data-stu-id="92dbd-248">Information on the investigation's current status.</span></span> <span data-ttu-id="92dbd-249">Uma das seguintes opções: *desconhecido*, *terminado*, *SuccessfullyRemediated*, *benigno*, *Failed*, *PartiallyRemediated*, *running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs, UnsupportedAlertType*, *SuppressedAlert*. *UnsupportedAlertType*</span><span class="sxs-lookup"><span data-stu-id="92dbd-249">One of the following: *Unknown*, *Terminated*, *SuccessfullyRemediated*, *Benign*, *Failed*, *PartiallyRemediated*, *Running*, *PendingApproval*, *PendingResource*, *PartiallyInvestigated*, *TerminatedByUser*, *TerminatedBySystem*, *Queued*, *InnerFailure*, *PreexistingAlert*, *UnsupportedOs*, *UnsupportedAlertType*, *SuppressedAlert*.</span></span> | <span data-ttu-id="92dbd-250">UnsupportedAlertType</span><span class="sxs-lookup"><span data-stu-id="92dbd-250">UnsupportedAlertType</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-251">classificação</span><span class="sxs-lookup"><span data-stu-id="92dbd-251">classification</span></span>                            | <span data-ttu-id="92dbd-252">A especificação do incidente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-252">The specification for the incident.</span></span> <span data-ttu-id="92dbd-253">Os valores da propriedade são: *desconhecido*, *FalsePositive*, *TruePositive* ou *nulo*</span><span class="sxs-lookup"><span data-stu-id="92dbd-253">The property values are: *Unknown*, *FalsePositive*, *TruePositive* or *null*</span></span>                                                                                                                                                                                                                                                                   | <span data-ttu-id="92dbd-254">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="92dbd-254">Unknown</span></span>                                                                                                                                                                                                                                           |
| <span data-ttu-id="92dbd-255">determinação</span><span class="sxs-lookup"><span data-stu-id="92dbd-255">determination</span></span>                             | <span data-ttu-id="92dbd-256">Especifica a determinação do incidente.</span><span class="sxs-lookup"><span data-stu-id="92dbd-256">Specifies the determination of the incident.</span></span> <span data-ttu-id="92dbd-257">Os valores de propriedade são: *não disponível*, *apt*, *malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *outros* ou  *nulos*</span><span class="sxs-lookup"><span data-stu-id="92dbd-257">The property values are: *NotAvailable*, *Apt*, *Malware*, *SecurityPersonnel*, *SecurityTesting*, *UnwantedSoftware*, *Other* or  *null*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="92dbd-258">Chance</span><span class="sxs-lookup"><span data-stu-id="92dbd-258">Apt</span></span>                                                                                                                                                                                                                                               |
| <span data-ttu-id="92dbd-259">assignedTo</span><span class="sxs-lookup"><span data-stu-id="92dbd-259">assignedTo</span></span>                                | <span data-ttu-id="92dbd-260">Proprietário do incidente ou *nulo* se nenhum proprietário for atribuído.</span><span class="sxs-lookup"><span data-stu-id="92dbd-260">Owner of the incident, or *null* if no owner is assigned.</span></span>                                                                                                                                                                                                                                                                                                                            | <span data-ttu-id="92dbd-261">secop2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92dbd-261">secop2@contoso.com</span></span>                                                                                                                                                                                                 |
| <span data-ttu-id="92dbd-262">actorname</span><span class="sxs-lookup"><span data-stu-id="92dbd-262">actorName</span></span>                                 | <span data-ttu-id="92dbd-263">O grupo de atividades, se houver, associado a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="92dbd-263">The activity group, if any, the  associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="92dbd-264">BORON</span><span class="sxs-lookup"><span data-stu-id="92dbd-264">BORON</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="92dbd-265">threatFamilyName</span><span class="sxs-lookup"><span data-stu-id="92dbd-265">threatFamilyName</span></span>                          | <span data-ttu-id="92dbd-266">Família de ameaças associada a esse alerta.</span><span class="sxs-lookup"><span data-stu-id="92dbd-266">Threat family associated with this alert.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="92dbd-267">null</span><span class="sxs-lookup"><span data-stu-id="92dbd-267">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-268">mitreTechniques</span><span class="sxs-lookup"><span data-stu-id="92dbd-268">mitreTechniques</span></span>                           | <span data-ttu-id="92dbd-269">As técnicas de ataque, conforme alinhado com o [Mitre ATT&CK](https://attack.mitre.org/)™ Framework.</span><span class="sxs-lookup"><span data-stu-id="92dbd-269">The attack techniques, as aligned with the [MITRE ATT&CK](https://attack.mitre.org/)™ framework.</span></span>                                                                                                                                                                                                                                                                                                                              | \[\]                                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-270">dispositivos</span><span class="sxs-lookup"><span data-stu-id="92dbd-270">devices</span></span>                                   | <span data-ttu-id="92dbd-271">Todos os dispositivos em que os alertas relacionados ao incidente foram enviados.</span><span class="sxs-lookup"><span data-stu-id="92dbd-271">All devices where alerts related to the incident were sent.</span></span>                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-272">\[\] (veja detalhes nos campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="92dbd-272">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="92dbd-273">**Formato do dispositivo**</span><span class="sxs-lookup"><span data-stu-id="92dbd-273">**Device format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="92dbd-274">DeviceId</span><span class="sxs-lookup"><span data-stu-id="92dbd-274">DeviceId</span></span>                                  | <span data-ttu-id="92dbd-275">A ID do dispositivo, conforme designado no Microsoft defender ATP.</span><span class="sxs-lookup"><span data-stu-id="92dbd-275">The device ID as designated in Microsoft Defender ATP.</span></span>                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="92dbd-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span><span class="sxs-lookup"><span data-stu-id="92dbd-276">24c222b0b60fe148eeece49ac83910cc6a7ef491</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="92dbd-277">aadDeviceId</span><span class="sxs-lookup"><span data-stu-id="92dbd-277">aadDeviceId</span></span>                               |  <span data-ttu-id="92dbd-278">A ID do dispositivo, conforme designado no [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span><span class="sxs-lookup"><span data-stu-id="92dbd-278">The device Id as designated in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) (AAD).</span></span> <span data-ttu-id="92dbd-279">Disponível apenas para dispositivos que ingressaram no domínio.</span><span class="sxs-lookup"><span data-stu-id="92dbd-279">Only available for domain-joined devices.</span></span>                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="92dbd-280">null</span><span class="sxs-lookup"><span data-stu-id="92dbd-280">null</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-281">deviceDnsName</span><span class="sxs-lookup"><span data-stu-id="92dbd-281">deviceDnsName</span></span>                             | <span data-ttu-id="92dbd-282">O nome de domínio totalmente qualificado para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92dbd-282">The fully qualified domain name for the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="92dbd-283">user5cx.middleeast.corp.contoso.com</span><span class="sxs-lookup"><span data-stu-id="92dbd-283">user5cx.middleeast.corp.contoso.com</span></span>                                                                                                                                                                                                    |
| <span data-ttu-id="92dbd-284">osPlatform</span><span class="sxs-lookup"><span data-stu-id="92dbd-284">osPlatform</span></span>                                | <span data-ttu-id="92dbd-285">A plataforma do sistema operacional que o dispositivo está executando.</span><span class="sxs-lookup"><span data-stu-id="92dbd-285">The OS platform the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-286">WindowsServer2016</span><span class="sxs-lookup"><span data-stu-id="92dbd-286">WindowsServer2016</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="92dbd-287">osBuild</span><span class="sxs-lookup"><span data-stu-id="92dbd-287">osBuild</span></span>                                   | <span data-ttu-id="92dbd-288">A versão de compilação do sistema operacional que o dispositivo está executando.</span><span class="sxs-lookup"><span data-stu-id="92dbd-288">The build version for the OS the device is running.</span></span>                                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-289">14393</span><span class="sxs-lookup"><span data-stu-id="92dbd-289">14393</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="92dbd-290">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="92dbd-290">rbacGroupName</span></span>                             | <span data-ttu-id="92dbd-291">O grupo RBAC ( [controle de acesso baseado em função](https://docs.microsoft.com/azure/role-based-access-control/overview) ) associado ao dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92dbd-291">The [role-based access control](https://docs.microsoft.com/azure/role-based-access-control/overview) (RBAC) group associated with the device.</span></span>                                                                                                                                                                                                                                                                                                                             | <span data-ttu-id="92dbd-292">WDATP-Ring0</span><span class="sxs-lookup"><span data-stu-id="92dbd-292">WDATP-Ring0</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="92dbd-293">firstSeen</span><span class="sxs-lookup"><span data-stu-id="92dbd-293">firstSeen</span></span>                                 | <span data-ttu-id="92dbd-294">Hora em que o dispositivo foi visto pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="92dbd-294">Time when device was first seen.</span></span>                                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="92dbd-295">2020-02-06T14:16:01.9330135 Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-295">2020-02-06T14:16:01.9330135Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-296">healthStatus</span><span class="sxs-lookup"><span data-stu-id="92dbd-296">healthStatus</span></span>                              | <span data-ttu-id="92dbd-297">O estado de integridade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92dbd-297">The health state of the device.</span></span>                                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="92dbd-298">Ativo</span><span class="sxs-lookup"><span data-stu-id="92dbd-298">Active</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-299">riskScore</span><span class="sxs-lookup"><span data-stu-id="92dbd-299">riskScore</span></span>                                 | <span data-ttu-id="92dbd-300">A pontuação de risco para o dispositivo.</span><span class="sxs-lookup"><span data-stu-id="92dbd-300">The risk score for the  device.</span></span>                                                                                                                                                                                                                                                                                                                                                                       | <span data-ttu-id="92dbd-301">Alto</span><span class="sxs-lookup"><span data-stu-id="92dbd-301">High</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-302">contabilidade</span><span class="sxs-lookup"><span data-stu-id="92dbd-302">entities</span></span>                                  | <span data-ttu-id="92dbd-303">Todas as entidades que foram identificadas como parte de, ou relacionadas a, um determinado alerta.</span><span class="sxs-lookup"><span data-stu-id="92dbd-303">All entities that have been identified to be part of, or related to, a given alert.</span></span>                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-304">\[\] (veja detalhes nos campos de entidade abaixo)</span><span class="sxs-lookup"><span data-stu-id="92dbd-304">\[\] (see details on entity fields below)</span></span>                                                                                                                                                                                                         |
| <span data-ttu-id="92dbd-305">**Formato de entidade**</span><span class="sxs-lookup"><span data-stu-id="92dbd-305">**Entity Format**</span></span>                             |                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                   |
| <span data-ttu-id="92dbd-306">entityType</span><span class="sxs-lookup"><span data-stu-id="92dbd-306">entityType</span></span>                                | <span data-ttu-id="92dbd-307">Entidades que foram identificadas como parte de um determinado alerta ou relacionadas a ela.</span><span class="sxs-lookup"><span data-stu-id="92dbd-307">Entities that have been identified to be part of, or related to, a given alert.</span></span><br><span data-ttu-id="92dbd-308">Os valores de propriedades são: *usuário*, *IP*, *URL*, *arquivo*, *processo*, *caixa de correio*, *MailMessage*, *MailCluster*, *registro*</span><span class="sxs-lookup"><span data-stu-id="92dbd-308">The properties values are: *User*, *Ip*, *Url*, *File*, *Process*, *MailBox*, *MailMessage*, *MailCluster*, *Registry*</span></span>                                                                                                                                                                                                     | <span data-ttu-id="92dbd-309">Usuário</span><span class="sxs-lookup"><span data-stu-id="92dbd-309">User</span></span>                                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-310">SHA1</span><span class="sxs-lookup"><span data-stu-id="92dbd-310">sha1</span></span>                                      | <span data-ttu-id="92dbd-311">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-311">Available if entityType is *File*.</span></span><br><span data-ttu-id="92dbd-312">O hash do arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="92dbd-312">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="92dbd-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span><span class="sxs-lookup"><span data-stu-id="92dbd-313">5de839186691aa96ee2ca6d74f0a38fb8d1bd6dd</span></span>                                                                                                                                                                                                          |
| <span data-ttu-id="92dbd-314">SHA256</span><span class="sxs-lookup"><span data-stu-id="92dbd-314">sha256</span></span>                                    | <span data-ttu-id="92dbd-315">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-315">Available if entityType is *File*.</span></span><br><span data-ttu-id="92dbd-316">O hash do arquivo para alertas associados a um arquivo ou processo.</span><span class="sxs-lookup"><span data-stu-id="92dbd-316">The file hash for alerts associated with a file or process.</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="92dbd-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span><span class="sxs-lookup"><span data-stu-id="92dbd-317">28cb017dfc99073aa1b47c1b30f413e3ce774c4991eb4158de50f9dbb36d8043</span></span>                                                                                                                                                                                  |
| <span data-ttu-id="92dbd-318">fileName</span><span class="sxs-lookup"><span data-stu-id="92dbd-318">fileName</span></span>                                  | <span data-ttu-id="92dbd-319">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-319">Available if entityType is *File*.</span></span><br><span data-ttu-id="92dbd-320">O nome de arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="92dbd-320">The file name for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="92dbd-321">Detector.UnitTests.dll</span><span class="sxs-lookup"><span data-stu-id="92dbd-321">Detector.UnitTests.dll</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-322">filePath</span><span class="sxs-lookup"><span data-stu-id="92dbd-322">filePath</span></span>                                  | <span data-ttu-id="92dbd-323">Disponível se entityType for *arquivo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-323">Available if entityType is *File*.</span></span><br><span data-ttu-id="92dbd-324">O caminho do arquivo para alertas associados a um arquivo ou processo</span><span class="sxs-lookup"><span data-stu-id="92dbd-324">The file path for alerts associated with a file or process</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="92dbd-325">C: \\ \\ \\ \\ \_ serviço de implantação temporária de trabalho do agente \\ \\ \_ \\ \\ \_ 2020-09-06 12 \_ 14 \_ 54 \\ \\</span><span class="sxs-lookup"><span data-stu-id="92dbd-325">C:\\\\Agent\\\\\_work\\\\\_temp\\\\Deploy\_SYSTEM 2020-09-06 12\_14\_54\\\\Out</span></span>                                                                                                                                                                    |
| <span data-ttu-id="92dbd-326">Identificação</span><span class="sxs-lookup"><span data-stu-id="92dbd-326">processId</span></span>                                 | <span data-ttu-id="92dbd-327">Disponível se entityType for *processo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-327">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-328">24348</span><span class="sxs-lookup"><span data-stu-id="92dbd-328">24348</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="92dbd-329">processCommandLine</span><span class="sxs-lookup"><span data-stu-id="92dbd-329">processCommandLine</span></span>                        | <span data-ttu-id="92dbd-330">Disponível se entityType for *processo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-330">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-331">" \\ " Seu arquivo está pronto para baixar \_1911150169.exe\\ ""</span><span class="sxs-lookup"><span data-stu-id="92dbd-331">"\\"Your File Is Ready To Download\_1911150169.exe\\" "</span></span>                                                                                                                                                                                           |
| <span data-ttu-id="92dbd-332">processCreationTime</span><span class="sxs-lookup"><span data-stu-id="92dbd-332">processCreationTime</span></span>                       | <span data-ttu-id="92dbd-333">Disponível se entityType for *processo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-333">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-334">2020-07-18T03:25:38.5269993 Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-334">2020-07-18T03:25:38.5269993Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-335">parentProcessId</span><span class="sxs-lookup"><span data-stu-id="92dbd-335">parentProcessId</span></span>                           | <span data-ttu-id="92dbd-336">Disponível se entityType for *processo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-336">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                   | <span data-ttu-id="92dbd-337">16840</span><span class="sxs-lookup"><span data-stu-id="92dbd-337">16840</span></span>                                                                                                                                                                                                                                             |
| <span data-ttu-id="92dbd-338">parentProcessCreationTime</span><span class="sxs-lookup"><span data-stu-id="92dbd-338">parentProcessCreationTime</span></span>                 | <span data-ttu-id="92dbd-339">Disponível se entityType for *processo*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-339">Available if entityType is *Process*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-340">2020-07-18T02:12:32.8616797 Z</span><span class="sxs-lookup"><span data-stu-id="92dbd-340">2020-07-18T02:12:32.8616797Z</span></span>                                                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-341">ipAddress</span><span class="sxs-lookup"><span data-stu-id="92dbd-341">ipAddress</span></span>                                 | <span data-ttu-id="92dbd-342">Disponível se entityType for *IP*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-342">Available if entityType is *Ip*.</span></span> <br><span data-ttu-id="92dbd-343">Endereço IP para alertas associados a eventos de rede, como *comunicação com um destino de rede mal-intencionado*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-343">IP address for alerts associated with network events, such as *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                   | <span data-ttu-id="92dbd-344">62.216.203.204</span><span class="sxs-lookup"><span data-stu-id="92dbd-344">62.216.203.204</span></span>                                                                                                                                                                                                                                    |
| <span data-ttu-id="92dbd-345">url</span><span class="sxs-lookup"><span data-stu-id="92dbd-345">url</span></span>                                       | <span data-ttu-id="92dbd-346">Disponível se entityType for *URL*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-346">Available if entityType is *Url*.</span></span> <br><span data-ttu-id="92dbd-347">URL para alertas associados a eventos de rede, como *comunicação com um destino de rede mal-intencionado*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-347">Url for alerts associated to network events, such as, *Communication to a malicious network destination*.</span></span>                                                                                                                                                                                                                                  | <span data-ttu-id="92dbd-348">down.esales360.cn</span><span class="sxs-lookup"><span data-stu-id="92dbd-348">down.esales360.cn</span></span>                                                                                                                                                                                                                                 |
| <span data-ttu-id="92dbd-349">accountName</span><span class="sxs-lookup"><span data-stu-id="92dbd-349">accountName</span></span>                               | <span data-ttu-id="92dbd-350">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-350">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                         | <span data-ttu-id="92dbd-351">testUser2</span><span class="sxs-lookup"><span data-stu-id="92dbd-351">testUser2</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="92dbd-352">domainName</span><span class="sxs-lookup"><span data-stu-id="92dbd-352">domainName</span></span>                                | <span data-ttu-id="92dbd-353">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-353">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="92dbd-354">Europa. Corp. contoso</span><span class="sxs-lookup"><span data-stu-id="92dbd-354">europe.corp.contoso</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-355">Userid</span><span class="sxs-lookup"><span data-stu-id="92dbd-355">userSid</span></span>                                   | <span data-ttu-id="92dbd-356">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-356">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="92dbd-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span><span class="sxs-lookup"><span data-stu-id="92dbd-357">S-1-5-21-1721254763-462695806-1538882281-4156657</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="92dbd-358">aadUserId</span><span class="sxs-lookup"><span data-stu-id="92dbd-358">aadUserId</span></span>                                 | <span data-ttu-id="92dbd-359">Disponível se entityType for *User*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-359">Available if entityType is *User*.</span></span>                                                                                                                                                                                                                                                                                                                                                        | <span data-ttu-id="92dbd-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span><span class="sxs-lookup"><span data-stu-id="92dbd-360">fc8f7484-f813-4db2-afab-bc1507913fb6</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-361">userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="92dbd-361">userPrincipalName</span></span>                         | <span data-ttu-id="92dbd-362">Disponível se EntityType é o MailMessage da caixa de correio do *usuário* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-362">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-363">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92dbd-363">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-364">mailboxDisplayName</span><span class="sxs-lookup"><span data-stu-id="92dbd-364">mailboxDisplayName</span></span>                        | <span data-ttu-id="92dbd-365">Disponível se entityType for *Mailbox*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-365">Available if entityType is *MailBox*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-366">testar Usuário2</span><span class="sxs-lookup"><span data-stu-id="92dbd-366">test User2</span></span>                                                                                                                                                                                                                                        |
| <span data-ttu-id="92dbd-367">mailboxAddress</span><span class="sxs-lookup"><span data-stu-id="92dbd-367">mailboxAddress</span></span>                            | <span data-ttu-id="92dbd-368">Disponível se EntityType é o MailMessage da caixa de correio do *usuário* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-368">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-369">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92dbd-369">testUser2@contoso.com</span></span>                                                                                                                                                                                      |
| <span data-ttu-id="92dbd-370">clusterBy</span><span class="sxs-lookup"><span data-stu-id="92dbd-370">clusterBy</span></span>                                 | <span data-ttu-id="92dbd-371">Disponível se entityType for  *MailCluster*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-371">Available if entityType is  *MailCluster*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="92dbd-372">Sob P2SenderDomain; ContentType</span><span class="sxs-lookup"><span data-stu-id="92dbd-372">Subject;P2SenderDomain;ContentType</span></span>                                                                                                                                                                                                                |
| <span data-ttu-id="92dbd-373">sender</span><span class="sxs-lookup"><span data-stu-id="92dbd-373">sender</span></span>                                    | <span data-ttu-id="92dbd-374">Disponível se EntityType é o MailMessage da caixa de correio do *usuário* / *MailBox* / *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-374">Available if entityType is *User*/*MailBox*/*MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                  | <span data-ttu-id="92dbd-375">user.abc@mail.contoso.co.in</span><span class="sxs-lookup"><span data-stu-id="92dbd-375">user.abc@mail.contoso.co.in</span></span>                                                                                                                                                                 |
| <span data-ttu-id="92dbd-376">destinatário</span><span class="sxs-lookup"><span data-stu-id="92dbd-376">recipient</span></span>                                 | <span data-ttu-id="92dbd-377">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-377">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                | <span data-ttu-id="92dbd-378">testUser2@contoso.com</span><span class="sxs-lookup"><span data-stu-id="92dbd-378">testUser2@contoso.com</span></span>                                                                                                                                                                                       |
| <span data-ttu-id="92dbd-379">assunto</span><span class="sxs-lookup"><span data-stu-id="92dbd-379">subject</span></span>                                   | <span data-ttu-id="92dbd-380">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-380">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="92dbd-381">\[\]Atenção externa</span><span class="sxs-lookup"><span data-stu-id="92dbd-381">\[EXTERNAL\] Attention</span></span>                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-382">deliveryaction</span><span class="sxs-lookup"><span data-stu-id="92dbd-382">deliveryAction</span></span>                            | <span data-ttu-id="92dbd-383">Disponível se entityType for *MailMessage*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-383">Available if entityType is *MailMessage*.</span></span>                                                                                                                                                                                                                                                                                                                                                 | <span data-ttu-id="92dbd-384">Gerados</span><span class="sxs-lookup"><span data-stu-id="92dbd-384">Delivered</span></span>                                                                                                                                                                                                                                         |
| <span data-ttu-id="92dbd-385">securityGroupId</span><span class="sxs-lookup"><span data-stu-id="92dbd-385">securityGroupId</span></span>                           | <span data-ttu-id="92dbd-386">Disponível se entityType for  *segurança*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-386">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="92dbd-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span><span class="sxs-lookup"><span data-stu-id="92dbd-387">301c47c8-e15f-4059-ab09-e2ba9ffd372b</span></span>                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-388">securityGroupName</span><span class="sxs-lookup"><span data-stu-id="92dbd-388">securityGroupName</span></span>                         | <span data-ttu-id="92dbd-389">Disponível se entityType for  *segurança*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-389">Available if entityType is  *SecurityGroup*.</span></span>                                                                                                                                                                                                                                                                                                                                               | <span data-ttu-id="92dbd-390">Operadores de configuração de rede</span><span class="sxs-lookup"><span data-stu-id="92dbd-390">Network Configuration Operators</span></span>                                                                                                                                                                                                                   |
| <span data-ttu-id="92dbd-391">registryHive</span><span class="sxs-lookup"><span data-stu-id="92dbd-391">registryHive</span></span>                              | <span data-ttu-id="92dbd-392">Disponível se entityType for  *registro*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-392">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="92dbd-393">\_máquina local \_ HKEY</span><span class="sxs-lookup"><span data-stu-id="92dbd-393">HKEY\_LOCAL\_MACHINE</span></span>                                                                                                                                                                                                                              |
| <span data-ttu-id="92dbd-394">Chaves</span><span class="sxs-lookup"><span data-stu-id="92dbd-394">registryKey</span></span>                               | <span data-ttu-id="92dbd-395">Disponível se entityType for  *registro*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-395">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                     | <span data-ttu-id="92dbd-396">SOFTWARE \\ \\ Microsoft \\ \\ Windows NT \\ \\ CurrentVersion \\ \\ Winlogon</span><span class="sxs-lookup"><span data-stu-id="92dbd-396">SOFTWARE\\\\Microsoft\\\\Windows NT\\\\CurrentVersion\\\\Winlogon</span></span>                                                                                                                                                                                 |
| <span data-ttu-id="92dbd-397">registryValueType</span><span class="sxs-lookup"><span data-stu-id="92dbd-397">registryValueType</span></span>                         | <span data-ttu-id="92dbd-398">Disponível se entityType for  *registro*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-398">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="92dbd-399">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="92dbd-399">String</span></span>                                                                                                                                                                                                                                            |
| <span data-ttu-id="92dbd-400">REGISTRYVALUE</span><span class="sxs-lookup"><span data-stu-id="92dbd-400">registryValue</span></span>                             | <span data-ttu-id="92dbd-401">Disponível se entityType for  *registro*.</span><span class="sxs-lookup"><span data-stu-id="92dbd-401">Available if entityType is  *Registry*.</span></span>                                                                                                                                                                                                                                                                                                                                                    | <span data-ttu-id="92dbd-402">31-00-00-00</span><span class="sxs-lookup"><span data-stu-id="92dbd-402">31-00-00-00</span></span>                                                                                                                                                                                                                                       |
| <span data-ttu-id="92dbd-403">deviceId</span><span class="sxs-lookup"><span data-stu-id="92dbd-403">deviceId</span></span>                                  | <span data-ttu-id="92dbd-404">A ID, se houver, do dispositivo relacionado à entidade.</span><span class="sxs-lookup"><span data-stu-id="92dbd-404">The ID, if any, of the device related to the entity.</span></span>                                                                                                                                                                                                                                                                                                                                           | <span data-ttu-id="92dbd-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span><span class="sxs-lookup"><span data-stu-id="92dbd-405">986e5df8b73dacd43c8917d17e523e76b13c75cd</span></span>                                                                                                                                                                                                          |



## <a name="example"></a><span data-ttu-id="92dbd-406">Exemplo</span><span class="sxs-lookup"><span data-stu-id="92dbd-406">Example</span></span>

<span data-ttu-id="92dbd-407">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="92dbd-407">**Request**</span></span>

```
GET https://api.security.microsoft.com/api/incidents
```

<span data-ttu-id="92dbd-408">**Resposta**</span><span class="sxs-lookup"><span data-stu-id="92dbd-408">**Response**</span></span>
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

## <a name="related-topic"></a><span data-ttu-id="92dbd-409">Tópico relacionado</span><span class="sxs-lookup"><span data-stu-id="92dbd-409">Related topic</span></span>
- [<span data-ttu-id="92dbd-410">APIs de Incidente</span><span class="sxs-lookup"><span data-stu-id="92dbd-410">Incident APIs</span></span>](api-incident.md)
- [<span data-ttu-id="92dbd-411">Atualizar incidente</span><span class="sxs-lookup"><span data-stu-id="92dbd-411">Update incident</span></span>](api-update-incidents.md)
