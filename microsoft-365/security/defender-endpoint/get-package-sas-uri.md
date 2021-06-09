---
title: Obter a API de URI do SAS do pacote
description: Use essa API para obter um URI que permite baixar um pacote de investigação.
keywords: apis, api gráfica, apis com suporte, obter pacote, sas, uri
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 054db1766cdab3aa5b49da4940dcdddfe6086434
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52770680"
---
# <a name="get-package-sas-uri-api"></a><span data-ttu-id="9128b-104">Obter a API de URI do SAS do pacote</span><span class="sxs-lookup"><span data-stu-id="9128b-104">Get package SAS URI API</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9128b-105">**Aplica-se a:** [Microsoft Defender para Ponto de Extremidade](https://go.microsoft.com/fwlink/?linkid=2154037)</span><span class="sxs-lookup"><span data-stu-id="9128b-105">**Applies to:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)</span></span>

- <span data-ttu-id="9128b-106">Deseja experimentar o Microsoft Defender para Ponto de Extremidade?</span><span class="sxs-lookup"><span data-stu-id="9128b-106">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9128b-107">Inscreva-se para uma avaliação gratuita.</span><span class="sxs-lookup"><span data-stu-id="9128b-107">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="9128b-108">Descrição da API</span><span class="sxs-lookup"><span data-stu-id="9128b-108">API description</span></span>
<span data-ttu-id="9128b-109">Obter um URI que permita o download de um pacote [de Investigação.](collect-investigation-package.md)</span><span class="sxs-lookup"><span data-stu-id="9128b-109">Get a URI that allows downloading of an [Investigation package](collect-investigation-package.md).</span></span>


## <a name="permissions"></a><span data-ttu-id="9128b-110">Permissões</span><span class="sxs-lookup"><span data-stu-id="9128b-110">Permissions</span></span>
<span data-ttu-id="9128b-111">Uma das seguintes permissões é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="9128b-111">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="9128b-112">Para saber mais, incluindo como escolher permissões, consulte [Access the Microsoft Defender for Endpoint APIs](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="9128b-112">To learn more, including how to choose permissions, see [Access the Microsoft Defender for Endpoint APIs](apis-intro.md)</span></span>

<span data-ttu-id="9128b-113">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="9128b-113">Permission type</span></span> |   <span data-ttu-id="9128b-114">Permissão</span><span class="sxs-lookup"><span data-stu-id="9128b-114">Permission</span></span>  |   <span data-ttu-id="9128b-115">Nome de exibição de permissão</span><span class="sxs-lookup"><span data-stu-id="9128b-115">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="9128b-116">Aplicativo</span><span class="sxs-lookup"><span data-stu-id="9128b-116">Application</span></span> |   <span data-ttu-id="9128b-117">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="9128b-117">Machine.CollectForensics</span></span> |  <span data-ttu-id="9128b-118">'Coletar evidências forenses'</span><span class="sxs-lookup"><span data-stu-id="9128b-118">'Collect forensics'</span></span>
<span data-ttu-id="9128b-119">Delegado (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="9128b-119">Delegated (work or school account)</span></span> | <span data-ttu-id="9128b-120">Machine.CollectForensics</span><span class="sxs-lookup"><span data-stu-id="9128b-120">Machine.CollectForensics</span></span> | <span data-ttu-id="9128b-121">'Coletar evidências forenses'</span><span class="sxs-lookup"><span data-stu-id="9128b-121">'Collect forensics'</span></span>

>[!Note]
> <span data-ttu-id="9128b-122">Ao obter um token usando credenciais de usuário:</span><span class="sxs-lookup"><span data-stu-id="9128b-122">When obtaining a token using user credentials:</span></span>
>- <span data-ttu-id="9128b-123">O usuário precisa ter pelo menos a seguinte permissão de função: 'Investigação de alertas' (Consulte Criar e [gerenciar funções](user-roles.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9128b-123">The user needs to have at least the following role permission: 'Alerts Investigation' (See [Create and manage roles](user-roles.md) for more information)</span></span>
>- <span data-ttu-id="9128b-124">O usuário precisa ter acesso ao dispositivo, com base nas configurações do grupo de dispositivos (Consulte Criar e gerenciar grupos [de dispositivos](machine-groups.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="9128b-124">The user needs to have access to the device, based on device group settings (See [Create and manage device groups](machine-groups.md) for more information)</span></span>

## <a name="http-request"></a><span data-ttu-id="9128b-125">Solicitação HTTP</span><span class="sxs-lookup"><span data-stu-id="9128b-125">HTTP request</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/{machine action id}/getPackageUri
```

## <a name="request-headers"></a><span data-ttu-id="9128b-126">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="9128b-126">Request headers</span></span>

<span data-ttu-id="9128b-127">Nome</span><span class="sxs-lookup"><span data-stu-id="9128b-127">Name</span></span> | <span data-ttu-id="9128b-128">Tipo</span><span class="sxs-lookup"><span data-stu-id="9128b-128">Type</span></span> | <span data-ttu-id="9128b-129">Descrição</span><span class="sxs-lookup"><span data-stu-id="9128b-129">Description</span></span>
:---|:---|:---
<span data-ttu-id="9128b-130">Autorização</span><span class="sxs-lookup"><span data-stu-id="9128b-130">Authorization</span></span> | <span data-ttu-id="9128b-131">Cadeia de caracteres</span><span class="sxs-lookup"><span data-stu-id="9128b-131">String</span></span> | <span data-ttu-id="9128b-132">Portador {token}.</span><span class="sxs-lookup"><span data-stu-id="9128b-132">Bearer {token}.</span></span> <span data-ttu-id="9128b-133">**Obrigatório**.</span><span class="sxs-lookup"><span data-stu-id="9128b-133">**Required**.</span></span>


## <a name="request-body"></a><span data-ttu-id="9128b-134">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="9128b-134">Request body</span></span>

<span data-ttu-id="9128b-135">Vazio</span><span class="sxs-lookup"><span data-stu-id="9128b-135">Empty</span></span>

## <a name="response"></a><span data-ttu-id="9128b-136">Resposta</span><span class="sxs-lookup"><span data-stu-id="9128b-136">Response</span></span>

<span data-ttu-id="9128b-137">Se tiver êxito, este método retornará 200, código de resposta Ok com o objeto que contém o link para o pacote no parâmetro "value".</span><span class="sxs-lookup"><span data-stu-id="9128b-137">If successful, this method returns 200, Ok response code with object that holds the link to the package in the “value” parameter.</span></span> <span data-ttu-id="9128b-138">Esse link é válido por um período muito curto e deve ser usado imediatamente para baixar o pacote para um armazenamento local.</span><span class="sxs-lookup"><span data-stu-id="9128b-138">This link is valid for a very short time and should be used immediately for downloading the package to a local storage.</span></span>


## <a name="example"></a><span data-ttu-id="9128b-139">Exemplo</span><span class="sxs-lookup"><span data-stu-id="9128b-139">Example</span></span>

<span data-ttu-id="9128b-140">**Solicitação**</span><span class="sxs-lookup"><span data-stu-id="9128b-140">**Request**</span></span>

<span data-ttu-id="9128b-141">Este é um exemplo da solicitação.</span><span class="sxs-lookup"><span data-stu-id="9128b-141">Here is an example of the request.</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machineactions/7327b54fd718525cbca07dacde913b5ac3c85673/GetPackageUri

```

<span data-ttu-id="9128b-142">**Response**</span><span class="sxs-lookup"><span data-stu-id="9128b-142">**Response**</span></span>

<span data-ttu-id="9128b-143">Veja a seguir um exemplo da resposta.</span><span class="sxs-lookup"><span data-stu-id="9128b-143">Here is an example of the response.</span></span>

```http
HTTP/1.1 200 Ok
Content-type: application/json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Edm.String",
    "value": "\"https://userrequests-us.securitycenter.windows.com:443/safedownload/WDATP_Investigation_Package.zip?token=gbDyj7y%2fbWGAZjn2sFiZXlliBTXOCVG7yiJ6mXNaQ9pLByC2Wxeno9mENsPFP3xMk5l%2bZiJXjLvqAyNEzUNROxoM2I1er9dxzfVeBsxSmclJjPsAx%2btiNyxSz1Ax%2b5jaT5cL5bZg%2b8wgbwY9urXbTpGjAKh6FB1e%2b0ypcWkPm8UkfOwsmtC%2biZJ2%2bPqnkkeQk7SKMNoAvmh9%2fcqDIPKXGIBjMa0D9auzypOqd8bQXp7p2BnLSH136BxST8n9IHR4PILvRjAYW9kvtHkBpBitfydAsUW4g2oDZSPN3kCLBOoo1C4w4Lkc9Bc3GNU2IW6dfB7SHcp7G9p4BDkeJl3VuDs6esCaeBorpn9FKJ%2fXo7o9pdcI0hUPZ6Ds9hiPpwPUtz5J29CBE3QAopCK%2fsWlf6OW2WyXsrNRSnF1tVE5H3wXpREzuhD7S4AIA3OIEZKzC4jIPLeMu%2bazZU9xGwuc3gICOaokbwMJiZTqcUuK%2fV9YdBdjdg8wJ16NDU96Pl6%2fgew2KYuk6Wo7ZuHotgHI1abcsvdlpe4AvixDbqcRJthsg2PpLRaFLm5av44UGkeK6TJpFvxUn%2f9fg6Zk5yM1KUTHb8XGmutoCM8U9er6AzXZlY0gGc3D3bQOg41EJZkEZLyUEbk1hXJB36ku2%2bW01cG71t7MxMBYz7%2bdXobxpdo%3d%3bRWS%2bCeoDfTyDcfH5pkCg6hYDmCOPr%2fHYQuaUWUBNVnXURYkdyOzVHqp%2fe%2f1BNyPdVoVkpQHpz1pPS3b5g9h7IMmNKCk5gFq5m2nPx6kk9EYtzx8Ndoa2m9Yj%2bSaf8zIFke86YnfQL4AYewsnQNJJh4wc%2bXxGlBq7axDcoiOdX91rKzVicH3GSBkFoLFAKoegWWsF%2fEDZcVpF%2fXUA1K8HvB6dwyfy4y0sAqnNPxYTQ97mG7yHhxPt4Pe9YF2UPPAJVuEf8LNlQ%2bWHC9%2f7msF6UUI4%2fca%2ftpjFs%2fSNeRE8%2fyQj21TI8YTF1SowvaJuDc1ivEoeopNNGG%2bGI%2fX0SckaVxU9Hdkh0zbydSlT5SZwbSwescs0IpzECitBbaLUz4aT8KTs8T0lvx8D7Te3wVsKAJ1r3iFMQZrlk%2bS1WW8rvac7oHRx2HKURn1v7fDIQWgJr9aNsNlFz4fLJ50T2qSHuuepkLVbe93Va072aMGhvr09WVKoTpAf1j2bcFZZU6Za5PxI32mr0k90FgiYFJ1F%2f1vRDrGwvWVWUkR3Z33m4g0gHa52W1FMxQY0TJIwbovD6FaSNDx7xhKZSd5IJ7r6P91Gez49PaZRcAZPjd%2bfbul3JNm1VqQPTLohT7wa0ymRiXpSST74xtFzuEBzNSNATdbngj3%2fwV4JesTjZjIj5Dc%3d%3blumqauVlFuuO8MQffZgs0tLJ4Fq6fpeozPTdDf8Ll6XLegi079%2b4mSPFjTK0y6eohstxdoOdom2wAHiZwk0u4KLKmRkfYOdT1wHY79qKoBQ3ZDHFTys9V%2fcwKGl%2bl8IenWDutHygn5IcA1y7GTZj4g%3d%3d\""
}
```
