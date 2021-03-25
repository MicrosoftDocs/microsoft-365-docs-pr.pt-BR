---
title: Criar alerta a partir da API de evento
description: Saiba como usar a API Criar alerta para criar um novo Alerta em cima do Evento no Microsoft Defender para Ponto de Extremidade.
keywords: apis, api gráfica, apis com suporte, obter, alerta, informações, id
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9066bcdae549f7a6b1372714d567674eb03c1e51
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166296"
---
# <a name="create-alert-api"></a><span data-ttu-id="9fb9b-104">Criar API de alerta</span><span class="sxs-lookup"><span data-stu-id="9fb9b-104">Create alert API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9fb9b-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="9fb9b-105">**Applies to:**</span></span>
- [<span data-ttu-id="9fb9b-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="9fb9b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9fb9b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9fb9b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

- <span data-ttu-id="9fb9b-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9fb9b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9fb9b-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a><span data-ttu-id="9fb9b-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="9fb9b-110">API description</span></span>
<span data-ttu-id="9fb9b-111">Cria um [novo Alerta](alerts.md) em cima do **evento**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-111">Creates new [Alert](alerts.md) on top of **Event**.</span></span>
<br><span data-ttu-id="9fb9b-112">**O Evento Do Microsoft Defender para Ponto** de Extremidade é necessário para a criação do alerta.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-112">**Microsoft Defender for Endpoint Event** is required for the alert creation.</span></span>
<br><span data-ttu-id="9fb9b-113">Você precisará fornecer 3 parâmetros do Evento na solicitação: Hora do Evento, **ID do** Computador e **ID do Relatório.**</span><span class="sxs-lookup"><span data-stu-id="9fb9b-113">You will need to supply 3 parameters from the Event in the request: **Event Time**, **Machine ID** and **Report ID**.</span></span> <span data-ttu-id="9fb9b-114">Veja o exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-114">See example below.</span></span>
<br><span data-ttu-id="9fb9b-115">Você pode usar um evento encontrado na API de Busca Avançada ou portal.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-115">You can use an event found in Advanced Hunting API or Portal.</span></span>
<br><span data-ttu-id="9fb9b-116">Se houver um alerta aberto no mesmo Dispositivo com o mesmo Título, o novo alerta criado será mesclado com ele.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-116">If there existing an open alert on the same Device with the same Title, the new created alert will be merged with it.</span></span>
<br><span data-ttu-id="9fb9b-117">Uma investigação automática é iniciada automaticamente em alertas criados por meio da API.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-117">An automatic investigation starts automatically on alerts created via the API.</span></span>


## <a name="limitations"></a><span data-ttu-id="9fb9b-118">Limitações</span><span class="sxs-lookup"><span data-stu-id="9fb9b-118">Limitations</span></span>
1. <span data-ttu-id="9fb9b-119">Limitações de taxa para essa API são 15 chamadas por minuto.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-119">Rate limitations for this API are 15 calls per minute.</span></span>


## <a name="permissions"></a><span data-ttu-id="9fb9b-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="9fb9b-120">Permissions</span></span>

<span data-ttu-id="9fb9b-121">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-121">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9fb9b-122">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9fb9b-122">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9fb9b-123">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="9fb9b-123">Permission type</span></span> |   <span data-ttu-id="9fb9b-124">Permissão</span><span class="sxs-lookup"><span data-stu-id="9fb9b-124">Permission</span></span>  |   <span data-ttu-id="9fb9b-125">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="9fb9b-125">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9fb9b-126">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9fb9b-126">Application</span></span> |   <span data-ttu-id="9fb9b-127">Alerts.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="9fb9b-127">Alerts.ReadWrite.All</span></span> |  <span data-ttu-id="9fb9b-128">'Ler e gravar todos os alertas'</span><span class="sxs-lookup"><span data-stu-id="9fb9b-128">'Read and write all alerts'</span></span>
<span data-ttu-id="9fb9b-129">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="9fb9b-129">Delegated (work or school account)</span></span> | <span data-ttu-id="9fb9b-130">Alert.ReadWrite</span><span class="sxs-lookup"><span data-stu-id="9fb9b-130">Alert.ReadWrite</span></span> | <span data-ttu-id="9fb9b-131">'Alertas de leitura e gravação'</span><span class="sxs-lookup"><span data-stu-id="9fb9b-131">'Read and write alerts'</span></span>

>[!Note]
> <span data-ttu-id="9fb9b-132">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="9fb9b-132">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9fb9b-133">O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9fb9b-133">The user needs to have at least the following role permission: 'Alerts investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9fb9b-134">O usuário precisa ter acesso ao dispositivo associado ao alerta, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos de [dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9fb9b-134">The user needs to have access to the device associated with the alert, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9fb9b-135">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="9fb9b-135">HTTP request</span></span>

```
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a><span data-ttu-id="9fb9b-136">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="9fb9b-136">Request headers</span></span>

<span data-ttu-id="9fb9b-137">Nome</span><span class="sxs-lookup"><span data-stu-id="9fb9b-137">Name</span></span> | <span data-ttu-id="9fb9b-138">Tipo</span><span class="sxs-lookup"><span data-stu-id="9fb9b-138">Type</span></span> | <span data-ttu-id="9fb9b-139">Descrição</span><span class="sxs-lookup"><span data-stu-id="9fb9b-139">Description</span></span>
:---|:---|:---
<span data-ttu-id="9fb9b-140">Autorização</span><span class="sxs-lookup"><span data-stu-id="9fb9b-140">Authorization</span></span> | <span data-ttu-id="9fb9b-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-141">String</span></span> | <span data-ttu-id="9fb9b-142">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-142">Bearer {token}.</span></span> <span data-ttu-id="9fb9b-143">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-143">**Required**.</span></span>
<span data-ttu-id="9fb9b-144">Content-Type</span><span class="sxs-lookup"><span data-stu-id="9fb9b-144">Content-Type</span></span> | <span data-ttu-id="9fb9b-145">Cadeia de Caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-145">String</span></span> | <span data-ttu-id="9fb9b-146">application/json.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-146">application/json.</span></span> <span data-ttu-id="9fb9b-147">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-147">**Required**.</span></span>

## <a name="request-body"></a><span data-ttu-id="9fb9b-148">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="9fb9b-148">Request body</span></span>

<span data-ttu-id="9fb9b-149">No corpo da solicitação, fornece os seguintes valores (todos são necessários):</span><span class="sxs-lookup"><span data-stu-id="9fb9b-149">In the request body, supply the following values (all are required):</span></span>

<span data-ttu-id="9fb9b-150">Propriedade</span><span class="sxs-lookup"><span data-stu-id="9fb9b-150">Property</span></span> | <span data-ttu-id="9fb9b-151">Tipo</span><span class="sxs-lookup"><span data-stu-id="9fb9b-151">Type</span></span> | <span data-ttu-id="9fb9b-152">Descrição</span><span class="sxs-lookup"><span data-stu-id="9fb9b-152">Description</span></span>
:---|:---|:---
<span data-ttu-id="9fb9b-153">eventTime</span><span class="sxs-lookup"><span data-stu-id="9fb9b-153">eventTime</span></span> | <span data-ttu-id="9fb9b-154">DateTime(UTC)</span><span class="sxs-lookup"><span data-stu-id="9fb9b-154">DateTime(UTC)</span></span> | <span data-ttu-id="9fb9b-155">O tempo preciso do evento como cadeia de caracteres, conforme obtido da busca avançada.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-155">The precise time of the event as string, as obtained from advanced hunting.</span></span> <span data-ttu-id="9fb9b-156">por exemplo, ```2018-08-03T16:45:21.7115183Z``` **obrigatório.**</span><span class="sxs-lookup"><span data-stu-id="9fb9b-156">e.g. ```2018-08-03T16:45:21.7115183Z``` **Required**.</span></span>
<span data-ttu-id="9fb9b-157">reportId</span><span class="sxs-lookup"><span data-stu-id="9fb9b-157">reportId</span></span> | <span data-ttu-id="9fb9b-158">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-158">String</span></span> | <span data-ttu-id="9fb9b-159">O reportId do evento, conforme obtido da busca avançada.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-159">The reportId of the event, as obtained from advanced hunting.</span></span> <span data-ttu-id="9fb9b-160">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-160">**Required**.</span></span>
<span data-ttu-id="9fb9b-161">machineId</span><span class="sxs-lookup"><span data-stu-id="9fb9b-161">machineId</span></span> | <span data-ttu-id="9fb9b-162">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-162">String</span></span> | <span data-ttu-id="9fb9b-163">ID do dispositivo no qual o evento foi identificado.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-163">Id of the device on which the event was identified.</span></span> <span data-ttu-id="9fb9b-164">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-164">**Required**.</span></span>
<span data-ttu-id="9fb9b-165">severity</span><span class="sxs-lookup"><span data-stu-id="9fb9b-165">severity</span></span> | <span data-ttu-id="9fb9b-166">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-166">String</span></span> | <span data-ttu-id="9fb9b-167">Gravidade do alerta.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-167">Severity of the alert.</span></span> <span data-ttu-id="9fb9b-168">Os valores da propriedade são: 'Low', 'Medium' e 'High'.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-168">The property values are: 'Low', 'Medium' and 'High'.</span></span> <span data-ttu-id="9fb9b-169">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-169">**Required**.</span></span>
<span data-ttu-id="9fb9b-170">title</span><span class="sxs-lookup"><span data-stu-id="9fb9b-170">title</span></span> | <span data-ttu-id="9fb9b-171">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-171">String</span></span> | <span data-ttu-id="9fb9b-172">Título do alerta.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-172">Title for the alert.</span></span> <span data-ttu-id="9fb9b-173">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-173">**Required**.</span></span>
<span data-ttu-id="9fb9b-174">descrição</span><span class="sxs-lookup"><span data-stu-id="9fb9b-174">description</span></span> | <span data-ttu-id="9fb9b-175">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-175">String</span></span> | <span data-ttu-id="9fb9b-176">Descrição do alerta.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-176">Description of the alert.</span></span> <span data-ttu-id="9fb9b-177">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-177">**Required**.</span></span>
<span data-ttu-id="9fb9b-178">recommendedAction</span><span class="sxs-lookup"><span data-stu-id="9fb9b-178">recommendedAction</span></span>| <span data-ttu-id="9fb9b-179">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-179">String</span></span> | <span data-ttu-id="9fb9b-180">Ação recomendada pelo agente de segurança ao analisar o alerta.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-180">Action that is recommended to be taken by security officer when analyzing the alert.</span></span> <span data-ttu-id="9fb9b-181">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-181">**Required**.</span></span>
<span data-ttu-id="9fb9b-182">category</span><span class="sxs-lookup"><span data-stu-id="9fb9b-182">category</span></span>| <span data-ttu-id="9fb9b-183">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9fb9b-183">String</span></span> | <span data-ttu-id="9fb9b-184">Categoria do alerta.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-184">Category of the alert.</span></span> <span data-ttu-id="9fb9b-185">Os valores da propriedade são: "Geral", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltração", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistência", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-185">The property values are: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltration", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.</span></span>

## <a name="response"></a><span data-ttu-id="9fb9b-186">Resposta</span><span class="sxs-lookup"><span data-stu-id="9fb9b-186">Response</span></span>

<span data-ttu-id="9fb9b-187">Se tiver êxito, este método retornará 200 OK e um novo objeto [de](alerts.md) alerta no corpo da resposta.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-187">If successful, this method returns 200 OK, and a new [alert](alerts.md) object in the response body.</span></span> <span data-ttu-id="9fb9b-188">Se o evento com as propriedades especificadas (_reportId,_ _eventTime_ e _machineId_) não for encontrado - 404 Não Encontrado.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-188">If event with the specified properties (_reportId_, _eventTime_ and _machineId_) was not found - 404 Not Found.</span></span>

## <a name="example"></a><span data-ttu-id="9fb9b-189">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9fb9b-189">Example</span></span>

<span data-ttu-id="9fb9b-190">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9fb9b-190">**Request**</span></span>

<span data-ttu-id="9fb9b-191">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9fb9b-191">Here is an example of the request.</span></span>

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```