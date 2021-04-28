---
title: Listar dispositivos expostos de uma atividade de correção
description: Retorna informações sobre dispositivos expostos para a tarefa de correção especificada.
keywords: apis, correção, api de correção, obter, tarefas de correção,
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
ms.technology: mde
ms.openlocfilehash: 097d8d784ca7c02fce1fc0e9fc51bdc272951f4a
ms.sourcegitcommit: e5b1a900043e2e41650ea1cbf4227043729c6053
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52061103"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="8c3d3-104">Listar dispositivos expostos de uma atividade de correção</span><span class="sxs-lookup"><span data-stu-id="8c3d3-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8c3d3-105">**Aplica-se a:**</span><span class="sxs-lookup"><span data-stu-id="8c3d3-105">**Applies to:**</span></span>

- [<span data-ttu-id="8c3d3-106">Microsoft Defender para Ponto de Extremidade</span><span class="sxs-lookup"><span data-stu-id="8c3d3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8c3d3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8c3d3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8c3d3-108">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="8c3d3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8c3d3-109">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="8c3d3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="8c3d3-110">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="8c3d3-110">API Description</span></span>

<span data-ttu-id="8c3d3-111">Retorna informações sobre dispositivos expostos para a tarefa de correção especificada.</span><span class="sxs-lookup"><span data-stu-id="8c3d3-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="8c3d3-112">[Saiba mais sobre atividades de correção.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="8c3d3-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="8c3d3-113">Listar dispositivos expostos associados a uma tarefa de correção (id)</span><span class="sxs-lookup"><span data-stu-id="8c3d3-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="8c3d3-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="8c3d3-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

<span data-ttu-id="8c3d3-115">**Detalhes das** propriedades</span><span class="sxs-lookup"><span data-stu-id="8c3d3-115">**Properties** details</span></span>

<span data-ttu-id="8c3d3-116">Propriedade (id)</span><span class="sxs-lookup"><span data-stu-id="8c3d3-116">Property (id)</span></span> | <span data-ttu-id="8c3d3-117">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="8c3d3-117">Data type</span></span> | <span data-ttu-id="8c3d3-118">Descrição</span><span class="sxs-lookup"><span data-stu-id="8c3d3-118">Description</span></span> | <span data-ttu-id="8c3d3-119">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8c3d3-119">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="8c3d3-120">id</span><span class="sxs-lookup"><span data-stu-id="8c3d3-120">id</span></span> | <span data-ttu-id="8c3d3-121">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8c3d3-121">String</span></span> | <span data-ttu-id="8c3d3-122">ID do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c3d3-122">Device ID</span></span> | <span data-ttu-id="8c3d3-123">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="8c3d3-123">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="8c3d3-124">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="8c3d3-124">computerDnsName</span></span> | <span data-ttu-id="8c3d3-125">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8c3d3-125">String</span></span> | <span data-ttu-id="8c3d3-126">Nome do dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c3d3-126">Device name</span></span> | <span data-ttu-id="8c3d3-127">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="8c3d3-127">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="8c3d3-128">osPlatform</span><span class="sxs-lookup"><span data-stu-id="8c3d3-128">osPlatform</span></span> | <span data-ttu-id="8c3d3-129">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8c3d3-129">String</span></span> | <span data-ttu-id="8c3d3-130">Sistema operacional de dispositivo</span><span class="sxs-lookup"><span data-stu-id="8c3d3-130">Device operating system</span></span> | <span data-ttu-id="8c3d3-131">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="8c3d3-131">WindowsServer2012R2</span></span>
<span data-ttu-id="8c3d3-132">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="8c3d3-132">rbacGroupName</span></span> | <span data-ttu-id="8c3d3-133">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="8c3d3-133">String</span></span> | <span data-ttu-id="8c3d3-134">Nome do grupo de dispositivos ao que esse dispositivo está associado</span><span class="sxs-lookup"><span data-stu-id="8c3d3-134">Name of the device group this device is associated with</span></span> | <span data-ttu-id="8c3d3-135">Servidores</span><span class="sxs-lookup"><span data-stu-id="8c3d3-135">Servers</span></span>

## <a name="example"></a><span data-ttu-id="8c3d3-136">Exemplo</span><span class="sxs-lookup"><span data-stu-id="8c3d3-136">Example</span></span>

<span data-ttu-id="8c3d3-137">**Exemplo de** solicitação</span><span class="sxs-lookup"><span data-stu-id="8c3d3-137">**Request** example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

<span data-ttu-id="8c3d3-138">**Exemplo de** resposta</span><span class="sxs-lookup"><span data-stu-id="8c3d3-138">**Response** example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8c3d3-139">Confira também</span><span class="sxs-lookup"><span data-stu-id="8c3d3-139">See also</span></span>

- [<span data-ttu-id="8c3d3-140">Métodos e propriedades de correção</span><span class="sxs-lookup"><span data-stu-id="8c3d3-140">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="8c3d3-141">Obter uma atividade de correção por Id</span><span class="sxs-lookup"><span data-stu-id="8c3d3-141">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="8c3d3-142">Listar todas as atividades de correção</span><span class="sxs-lookup"><span data-stu-id="8c3d3-142">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="8c3d3-143">Gerenciamento de vulnerabilidades baseadas em & risco</span><span class="sxs-lookup"><span data-stu-id="8c3d3-143">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="8c3d3-144">Vulnerabilidades em sua organização</span><span class="sxs-lookup"><span data-stu-id="8c3d3-144">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
