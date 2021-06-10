---
title: Listar dispositivos expostos de uma atividade de correção
description: Retorna informações sobre dispositivos expostos para a tarefa de correção especificada.
keywords: apis, correção, api de correção, tarefas de correção, dispositivos expostos de correção
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9b10659f76e5b05bea11f5c6c55ca7c2a34a2db5
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772156"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="04665-104">Listar dispositivos expostos de uma atividade de correção</span><span class="sxs-lookup"><span data-stu-id="04665-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="04665-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="04665-105">**Applies to:**</span></span>

- [<span data-ttu-id="04665-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="04665-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="04665-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="04665-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="04665-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="04665-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="04665-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="04665-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="04665-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="04665-110">API Description</span></span>

<span data-ttu-id="04665-111">Retorna informações sobre dispositivos expostos para a tarefa de correção especificada.</span><span class="sxs-lookup"><span data-stu-id="04665-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="04665-112">[Saiba mais sobre atividades de correção.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="04665-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="04665-113">Listar dispositivos expostos associados a uma tarefa de correção (id)</span><span class="sxs-lookup"><span data-stu-id="04665-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="04665-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="04665-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="04665-115">Permissões</span><span class="sxs-lookup"><span data-stu-id="04665-115">Permissions</span></span>

<span data-ttu-id="04665-116">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="04665-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="04665-117">Para saber mais, incluindo como escolher permissões, consulte [Use Microsoft Defender for Endpoint APIs para obter detalhes.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="04665-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="04665-118">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="04665-118">Permission type</span></span> | <span data-ttu-id="04665-119">Permissão</span><span class="sxs-lookup"><span data-stu-id="04665-119">Permission</span></span> | <span data-ttu-id="04665-120">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="04665-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="04665-121">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="04665-121">Application</span></span> | <span data-ttu-id="04665-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="04665-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="04665-123">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="04665-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="04665-124">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="04665-124">Delegated (work or school account)</span></span> | <span data-ttu-id="04665-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="04665-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="04665-126">\'Ler informações de vulnerabilidade de Gerenciamento de Ameaças e Vulnerabilidades\'</span><span class="sxs-lookup"><span data-stu-id="04665-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="04665-127">Detalhes das propriedades</span><span class="sxs-lookup"><span data-stu-id="04665-127">Properties details</span></span>

<span data-ttu-id="04665-128">Propriedade (id)</span><span class="sxs-lookup"><span data-stu-id="04665-128">Property (id)</span></span> | <span data-ttu-id="04665-129">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="04665-129">Data type</span></span> | <span data-ttu-id="04665-130">Descrição</span><span class="sxs-lookup"><span data-stu-id="04665-130">Description</span></span> | <span data-ttu-id="04665-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="04665-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="04665-132">id</span><span class="sxs-lookup"><span data-stu-id="04665-132">id</span></span> | <span data-ttu-id="04665-133">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="04665-133">String</span></span> | <span data-ttu-id="04665-134">ID do dispositivo</span><span class="sxs-lookup"><span data-stu-id="04665-134">Device ID</span></span> | <span data-ttu-id="04665-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="04665-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="04665-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="04665-136">computerDnsName</span></span> | <span data-ttu-id="04665-137">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="04665-137">String</span></span> | <span data-ttu-id="04665-138">Nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="04665-138">Device name</span></span> | <span data-ttu-id="04665-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="04665-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="04665-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="04665-140">osPlatform</span></span> | <span data-ttu-id="04665-141">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="04665-141">String</span></span> | <span data-ttu-id="04665-142">Sistema operacional de dispositivo</span><span class="sxs-lookup"><span data-stu-id="04665-142">Device operating system</span></span> | <span data-ttu-id="04665-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="04665-143">WindowsServer2012R2</span></span>
<span data-ttu-id="04665-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="04665-144">rbacGroupName</span></span> | <span data-ttu-id="04665-145">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="04665-145">String</span></span> | <span data-ttu-id="04665-146">Nome do grupo de dispositivos ao que esse dispositivo está associado</span><span class="sxs-lookup"><span data-stu-id="04665-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="04665-147">Servidores</span><span class="sxs-lookup"><span data-stu-id="04665-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="04665-148">Exemplo</span><span class="sxs-lookup"><span data-stu-id="04665-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="04665-149">Exemplo de solicitação</span><span class="sxs-lookup"><span data-stu-id="04665-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="04665-150">Exemplo de resposta</span><span class="sxs-lookup"><span data-stu-id="04665-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="04665-151">Confira também</span><span class="sxs-lookup"><span data-stu-id="04665-151">See also</span></span>

- [<span data-ttu-id="04665-152">Métodos e propriedades de correção</span><span class="sxs-lookup"><span data-stu-id="04665-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="04665-153">Obter uma atividade de correção por ID</span><span class="sxs-lookup"><span data-stu-id="04665-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="04665-154">Listar todas as atividades de correção</span><span class="sxs-lookup"><span data-stu-id="04665-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="04665-155">Ameaças baseadas em risco & Gerenciamento de Vulnerabilidades</span><span class="sxs-lookup"><span data-stu-id="04665-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="04665-156">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="04665-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
