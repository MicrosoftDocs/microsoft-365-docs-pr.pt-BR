---
title: URL do serviço Web e endereço IP do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Aprenda como usar o endereço IP e o serviço URL da Web do Office 365 para ajudá-lo a identificar e diferenciar melhor o tráfego de rede do Office 365.
ms.openlocfilehash: 03e6eac86e66db6f9e94c3f98e6d7b565ffa0f14
ms.sourcegitcommit: d76a4c07f0be2938372bdfae50e0e4d523bd8e9f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456454"
---
# <a name="office-365-ip-address-and-url-web-service"></a><span data-ttu-id="ffcb5-103">URL do serviço Web e endereço IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-103">Office 365 IP Address and URL web service</span></span>

<span data-ttu-id="ffcb5-104">A URL do serviço Web e endereço IP do Office 365 ajudam a identificar e diferenciar melhor o tráfego de rede do Office 365, tornando mais fácil para você avaliar, configurar e manter-se atualizado com as alterações.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-104">The Office 365 IP Address and URL web service helps you better identify and differentiate Office 365 network traffic, making it easier for you to evaluate, configure, and stay up to date with changes.</span></span> <span data-ttu-id="ffcb5-105">Esse serviço Web baseado em REST substitui os arquivos anteriores do XML para download, que foram desativados em 2 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-105">This REST-based web service replaces the previous XML downloadable files, which were phased out on October 2, 2018.</span></span>

<span data-ttu-id="ffcb5-106">Como um cliente ou um fornecedor de dispositivos de perímetro de rede, você pode criar com o novo serviço Web baseado em REST para as entradas FQDN e os endereços IP do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-106">As a customer or a network perimeter device vendor, you can build against the web service for Office 365 IP address and FQDN entries.</span></span> <span data-ttu-id="ffcb5-107">É possível acessar os dados diretamente de um navegador de Web usando essas URLs:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-107">You can access the data directly in a web browser using these URLs:</span></span>

- <span data-ttu-id="ffcb5-108">Para ter a última versão dos intervalos de endereços IP e URLs do Office 365, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-108">For the latest version of the Office 365 URLs and IP address ranges, use [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="ffcb5-109">Para os dados na página de intervalos de endereços IP e URLs do Office 365 para firewalls e servidores proxy, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-109">For the data on the Office 365 URLs and IP address ranges page for firewalls and proxy servers, use [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>
- <span data-ttu-id="ffcb5-110">Para obter as últimas alterações desde julho de 2018, quando o serviço Web foi disponibilizado, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-110">To get all the latest changes since July 2018 when the web service was first available, use [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span></span>

<span data-ttu-id="ffcb5-111">Como cliente, você pode usar esse serviço Web para:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-111">As a customer, you can use this web service to:</span></span>

- <span data-ttu-id="ffcb5-112">Atualize os seus scripts do Windows PowerShell para obter dados de ponto de extremidade do Office 365 e modificar qualquer formatação dos dispositivos de rede.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-112">Update your PowerShell scripts to obtain Office 365 endpoint data and modify any formatting for your networking devices.</span></span>
- <span data-ttu-id="ffcb5-113">Use essas informações para atualizar os arquivos PAC implantados nos computadores clientes.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-113">Use this information to update PAC files deployed to client computers.</span></span>

<span data-ttu-id="ffcb5-114">Como fornecedor de dispositivos de perímetro de rede, é possível usar esse serviço Web para:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-114">As a network perimeter device vendor, you can use this web service to:</span></span>

- <span data-ttu-id="ffcb5-115">Criar e testar o software do dispositivo para baixar a lista de configuração automatizada.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-115">Create and test device software to download the list for automated configuration.</span></span>
- <span data-ttu-id="ffcb5-116">Verificar a versão atual.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-116">Check for the current version.</span></span>
- <span data-ttu-id="ffcb5-117">Obter as alterações atuais.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-117">Get the current changes.</span></span>

> [!NOTE]
> <span data-ttu-id="ffcb5-118">Se você estiver usando o Azure ExpressRoute para se conectar ao Office 365, confira [Azure ExpressRoute para Office 365](azure-expressroute.md) para se familiarizar com os serviços do Office 365 com suporte no Azure ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-118">If you are using Azure ExpressRoute to connect to Office 365, please review [Azure ExpressRoute for Office 365](azure-expressroute.md) to familiarize yourself with the Office 365 services supported over Azure ExpressRoute.</span></span> <span data-ttu-id="ffcb5-119">Além disso, veja o artigo [URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md) para entender quais solicitações de rede para aplicativos do Office 365 exigem conectividade com a Internet.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-119">Also review the article [Office 365 URLs and IP address ranges](urls-and-ip-address-ranges.md) to understand which network requests for Office 365 applications require Internet connectivity.</span></span> <span data-ttu-id="ffcb5-120">Isso ajudará a configurar melhor seus dispositivos de segurança de perímetro.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-120">This will help to better configure your perimeter security devices.</span></span>

<span data-ttu-id="ffcb5-121">Para saber mais, veja:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-121">For more information, see:</span></span>

- [<span data-ttu-id="ffcb5-122">Comunicado de postagem no blog do Fórum da Comunidade de Tecnologia do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-122">Announcement blog post in the Office 365 Tech Community Forum</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [<span data-ttu-id="ffcb5-123">Fórum da Comunidade de Tecnologia do Office 365 para perguntas sobre o uso dos serviços Web</span><span class="sxs-lookup"><span data-stu-id="ffcb5-123">Office 365 Tech Community Forum for questions about use of the web services</span></span>](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a><span data-ttu-id="ffcb5-124">Parâmetros comuns</span><span class="sxs-lookup"><span data-stu-id="ffcb5-124">Common parameters</span></span>

<span data-ttu-id="ffcb5-125">Estes parâmetros são comuns a todos os métodos de serviço Web:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-125">These parameters are common across all the web service methods:</span></span>

- <span data-ttu-id="ffcb5-126">**format=<JSON | CSV>** — Por padrão, o formato de dados retornado é JSON.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-126">**format=<JSON | CSV>** — By default, the returned data format is JSON.</span></span> <span data-ttu-id="ffcb5-127">Use este parâmetro opcional para retornar os dados no formato de valores separados por vírgula (CSV).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-127">Use this optional parameter to return the data in comma-separated values (CSV) format.</span></span>
- <span data-ttu-id="ffcb5-128">**ClientRequestId=\<guid>** — Um GUID necessário que você gera para associação de clientes.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-128">**ClientRequestId=\<guid>** — A required GUID that you generate for client association.</span></span> <span data-ttu-id="ffcb5-129">Gerar um GUID exclusivo para cada computador que chama um serviço Web (os scripts incluídos na página geram um GUID para você).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-129">Generate a unique GUID for each machine that calls the web service (the scripts included on this page generate a GUID for you).</span></span> <span data-ttu-id="ffcb5-130">Não use os GUIDs mostrados nos exemplos a seguir porque eles podem ser bloqueados pelo serviço da Web no futuro.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-130">Do not use the GUIDs shown in the following examples because they might be blocked by the web service in the future.</span></span> <span data-ttu-id="ffcb5-131">O formato GUID é_ xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, em que x representa um número hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-131">GUID format is _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, where x represents a hexadecimal number.</span></span>

  <span data-ttu-id="ffcb5-132">Para gerar um GUID, você pode usar o comando [New-Guid](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) do PowerShell ou usar um serviço online como [Gerador de GUIDs Online](https://www.guidgenerator.com/).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-132">To generate a GUID, you can use the [New-Guid](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/new-guid?view=powershell-6) PowerShell command, or use an online service such as [Online GUID Generator](https://www.guidgenerator.com/).</span></span>

## <a name="version-web-method"></a><span data-ttu-id="ffcb5-133">Método da web de versão</span><span class="sxs-lookup"><span data-stu-id="ffcb5-133">Version web method</span></span>

<span data-ttu-id="ffcb5-134">A Microsoft atualiza as entradas de FQDN e o endereço IP do Office 365 ao final de cada mês.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-134">Microsoft updates the Office 365 IP address and FQDN entries at the end of each month.</span></span> <span data-ttu-id="ffcb5-135">Atualizações fora de banda às vezes são publicadas por causa de incidentes de suporte, atualizações de segurança ou outros requisitos operacionais.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-135">Out-of-band updates are sometimes published due to support incidents, security updates or other operational requirements.</span></span>

<span data-ttu-id="ffcb5-136">Os dados de cada instância publicada recebem um número de versão e o método Web de versão permite que você verifique a última versão de cada instância de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-136">The data for each published instance is assigned a version number, and the version web method enables you to check for the latest version of each Office 365 service instance.</span></span> <span data-ttu-id="ffcb5-137">Recomendamos verificar a versão não mais que uma vez.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-137">We recommend that you check the version not more than once an hour.</span></span>

<span data-ttu-id="ffcb5-138">Os parâmetros para o método da web de versão são:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-138">Parameters for the version web method are:</span></span>

- <span data-ttu-id="ffcb5-139">**AllVersions=<true | false>** — Por padrão, a versão retornada é a mais recente.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-139">**AllVersions=<true | false>** — By default, the version returned is the latest.</span></span> <span data-ttu-id="ffcb5-140">Inclua este parâmetro opcional para solicitar todas as versões publicadas desde que o serviço da Web foi lançado pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-140">Include this optional parameter to request all published versions since the web service was first released.</span></span>
- <span data-ttu-id="ffcb5-141">**Format=<JSON | CSV | RSS>** — Além dos formatos JSON e CSV, o método Web de versão também é compatível com RSS.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-141">**Format=<JSON | CSV | RSS>** — In addition to the JSON and CSV formats, the version web method also supports RSS.</span></span> <span data-ttu-id="ffcb5-142">Você pode usar esse parâmetro opcional junto com o parâmetro _AllVersions=true_ para solicitar um feed RSS que possa ser usado com o Outlook ou outros leitores de RSS.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-142">You can use this optional parameter along with the _AllVersions=true_ parameter to request an RSS feed that can be used with Outlook or other RSS readers.</span></span>
- <span data-ttu-id="ffcb5-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Este parâmetro opcional especifica a instância para o retorno da versão.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-143">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This optional parameter specifies the instance to return the version for.</span></span> <span data-ttu-id="ffcb5-144">Se omitido, todas as instâncias serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-144">If omitted, all instances are returned.</span></span> <span data-ttu-id="ffcb5-145">As instâncias válidas são: em todo o mundo, China, Alemanha, USGovDoD, USGovGCCHigh.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-145">Valid instances are: Worldwide, China, Germany, USGovDoD, USGovGCCHigh.</span></span>

<span data-ttu-id="ffcb5-146">O método Web de versão não é limitado por taxa e nunca retornará o código de resposta HTTP 429.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-146">The version web method is not rate limited and does not ever return 429 HTTP Response Codes.</span></span> <span data-ttu-id="ffcb5-147">A resposta ao método Web de versão inclui um cabeçalho de controle de cache que recomenda o armazenamento em cache dos dados por 1 hora.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-147">The response to the version web method does include a cache-control header recommending caching of the data for 1 hour.</span></span> <span data-ttu-id="ffcb5-148">O resultado do método Web de versão pode ser um único registro ou uma matriz de registros.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-148">The result from the version web method can be a single record or an array of records.</span></span> <span data-ttu-id="ffcb5-149">Os elementos de cada registro são:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-149">The elements of each record are:</span></span>

- <span data-ttu-id="ffcb5-150">instance — Um nome curto da instância de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-150">instance — The short name of the Office 365 service instance.</span></span>
- <span data-ttu-id="ffcb5-151">latest — A versão mais recente dos pontos de extremidade da instância especificada.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-151">latest — The latest version for endpoints of the specified instance.</span></span>
- <span data-ttu-id="ffcb5-152">versions — Uma lista com todas as versões anteriores da instância especificada.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-152">versions — A list of all previous versions for the specified instance.</span></span> <span data-ttu-id="ffcb5-153">Este elemento só será incluído se o parâmetro _AllVersions_ for verdadeiro.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-153">This element is only included if the _AllVersions_ parameter is true.</span></span>

### <a name="examples"></a><span data-ttu-id="ffcb5-154">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-154">Examples:</span></span>

<span data-ttu-id="ffcb5-155">Exemplo 1 de URI de solicitação: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-155">Example 1 request URI: [https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-p113">Esse URI retorna a última versão de cada instância de serviço do Office 365. Exemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p113">This URI returns the latest version of each Office 365 service instance. Example result:</span></span>

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> <span data-ttu-id="ffcb5-p114">O GUID para o parâmetro ClientRequestID nesses URIs são apenas um exemplo. Para experimentar os URIs do serviço Web, gere o seu próprio GUID. O GUIDs exibido nesses exemplos pode ser bloqueado pelo serviço Web no futuro.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p114">The GUID for the ClientRequestID parameter in these URIs are only an example. To try the web service URIs out, generate your own GUID. The GUIDs shown in these examples may be blocked by the web service in the future.</span></span>

<span data-ttu-id="ffcb5-161">Exemplo 2 de URI de solicitação: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-161">Example 2 request URI: [https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-p115">Esse URI retorna a última versão da instância de serviço especificada do Office 365. Exemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p115">This URI returns the latest version of the specified Office 365 service instance. Example result:</span></span>

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

<span data-ttu-id="ffcb5-164">Exemplo 3 de URI de solicitação: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-164">Example 3 request URI: [https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?Format=CSV&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-p116">Este URI mostra os resultados no formato CSV. Exemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p116">This URI shows output in CSV format. Example result:</span></span>

```csv
instance,latest
Worldwide,2018063000
```

<span data-ttu-id="ffcb5-167">Exemplo 4 de URI de solicitação: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-167">Example 4 request URI: [https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/version/Worldwide?AllVersions=true&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-p117">Este URI mostra todas as versões anteriores que foram publicadas para a instância de serviço do Office 365 em todo o mundo. Exemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p117">This URI shows all prior versions that have been published for the Office 365 worldwide service instance. Example result:</span></span>

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

<span data-ttu-id="ffcb5-170">Exemplo 5 de URI de RSS feed: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-170">Example 5 RSS Feed URI: [https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS](https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS)</span></span>

<span data-ttu-id="ffcb5-p118">Este URI mostra um RSS feed das versões publicadas que contêm links para a lista de alterações de cada versão. Exemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p118">This URI shows an RSS feed of the published versions that include links to the list of changes for each version. Example result:</span></span>

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a><span data-ttu-id="ffcb5-173">Método da Web de pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="ffcb5-173">Endpoints web method</span></span>

<span data-ttu-id="ffcb5-174">O método da Web de pontos de extremidade retorna todos os registros para intervalos de endereços IP e URLs que compõem o serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-174">The endpoints web method returns all records for IP address ranges and URLs that make up the Office 365 service.</span></span> <span data-ttu-id="ffcb5-175">Os dados mais recentes do método da Web de pontos de extremidade devem ser usados para a configuração de dispositivos de rede.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-175">The latest data from the endpoints web method should always be used for network device configuration.</span></span> <span data-ttu-id="ffcb5-176">A Microsoft fornece notificações antecipadas 30 dias antes de publicar novas incursões para dar tempo para atualizar listas de controle de acesso e listas de bypass de servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-176">Microsoft provides advance notice 30 days prior to publishing new additions to give you time to update access control lists and proxy server bypass lists.</span></span> <span data-ttu-id="ffcb5-177">Recomendamos que você chame o método da Web de pontos de extremidade o método Web da versão indicar que uma nova versão dos dados que está disponível.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-177">We recommend that you only call the endpoints web method again when the version web method indicates that a new version of the data is available.</span></span>

<span data-ttu-id="ffcb5-178">Os parâmetros para o método da Web de pontos de extremidade são:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-178">Parameters for the endpoints web method are:</span></span>

- <span data-ttu-id="ffcb5-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — Uma lista de áreas de serviço separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-179">**ServiceAreas=<Common | Exchange | SharePoint | Skype>** — A comma-separated list of service areas.</span></span> <span data-ttu-id="ffcb5-180">Os itens válidos são _Common_, _Exchange_, _SharePoint_ e _Skype_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-180">Valid items are _Common_, _Exchange_, _SharePoint_, and _Skype_.</span></span> <span data-ttu-id="ffcb5-181">Como os itens da área de serviço _Common_ são um pré-requisito para todas as outras áreas de serviço, o serviço da Web sempre os incluirá.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-181">Because _Common_ service area items are a prerequisite for all other service areas, the web service always includes them.</span></span> <span data-ttu-id="ffcb5-182">Se você não incluir esse parâmetro, todas as áreas de serviço serão retornadas.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-182">If you do not include this parameter, all service areas are returned.</span></span>
- <span data-ttu-id="ffcb5-183">**TenantName=<tenant_name>** — Seu nome de locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-183">**TenantName=<tenant_name>** — Your Office 365 tenant name.</span></span> <span data-ttu-id="ffcb5-184">O serviço da web insere o seu nome fornecido em partes de URLs que incluem o nome do locatário.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-184">The web service takes your provided name and inserts it in parts of URLs that include the tenant name.</span></span> <span data-ttu-id="ffcb5-185">Se você não fornecer um nome de locatário, essas partes das URLs terão o caractere curinga (\*).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-185">If you don't provide a tenant name, those parts of URLs have the wildcard character (\*).</span></span>
- <span data-ttu-id="ffcb5-186">**NoIPv6=<true | false>** — Defina o valor como _verdadeiro_ para excluir endereços IPv6 dos resultados se você não usar o IPv6 em sua rede.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-186">**NoIPv6=<true | false>** — Set the value to _true_ to exclude IPv6 addresses from the output if you don't use IPv6 in your network.</span></span>
- <span data-ttu-id="ffcb5-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — Este parâmetro obrigatório especifica a instância para a qual retornar os terminais.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-187">**Instance=<Worldwide | China | Germany | USGovDoD | USGovGCCHigh>** — This required parameter specifies the instance from which to return the endpoints.</span></span> <span data-ttu-id="ffcb5-188">As instâncias válidas são: _Mundialmente_, _China_, _Alemanha_, _USGovDoD_ e _USGovGCCHigh_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-188">Valid instances are: _Worldwide_, _China_, _Germany_, _USGovDoD_, and _USGovGCCHigh_.</span></span>

<span data-ttu-id="ffcb5-189">Se você chamar o método Web de pontos de extremidade um grande número de vezes a partir do mesmo endereço IP do cliente, poderá receber o código de resposta HTTP _429 (Excesso de solicitações)_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-189">If you call the endpoints web method too many times from the same client IP address, you might receive HTTP response code _429 (Too Many Requests)_.</span></span> <span data-ttu-id="ffcb5-190">Se você receber o código de resposta, você deve esperar 1 hora antes de repetir sua solicitação ou gerar um GUID para a solicitação.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-190">If you get this response code, wait 1 hour before repeating your request, or generate a new GUID for the request.</span></span> <span data-ttu-id="ffcb5-191">Como prática recomendada geral, apenas chame o método Web de pontos de extremidade quando o método Web de versão indicar que há uma nova versão disponível.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-191">As a general best practice, only call the endpoints web method when the version web method indicates that a new version is available.</span></span>

<span data-ttu-id="ffcb5-192">O resultado do método Web de pontos de extremidade é uma matriz de registros com cada registro representado um conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-192">The result from the endpoints web method is an array of records in which each record represents a specific endpoint set.</span></span> <span data-ttu-id="ffcb5-193">Os elementos de cada registro são:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-193">The elements for each record are:</span></span>

- <span data-ttu-id="ffcb5-194">id — O número de ID imutável do conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-194">id — The immutable id number of the endpoint set.</span></span>
- <span data-ttu-id="ffcb5-195">serviceArea — A área de serviço que faz parte do: _Common_, _Exchange_, _SharePoint_ ou _Skype_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-195">serviceArea — The service area that this is part of: _Common_, _Exchange_, _SharePoint_, or _Skype_.</span></span>
- <span data-ttu-id="ffcb5-196">urls — As URLs do conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-196">urls — URLs for the endpoint set.</span></span> <span data-ttu-id="ffcb5-197">Uma matriz JSON de registros DNS.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-197">A JSON array of DNS records.</span></span> <span data-ttu-id="ffcb5-198">Omitidas caso estejam em branco.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-198">Omitted if blank.</span></span>
- <span data-ttu-id="ffcb5-199">tcpPorts — As portas TCP para o conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-199">tcpPorts — TCP ports for the endpoint set.</span></span> <span data-ttu-id="ffcb5-200">Os elementos de todas as portas são formatados como uma lista separada por vírgulas ou intervalos de portas separados por um hífen (-).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-200">All ports elements are formatted as a comma-separated list of ports or port ranges separated by a dash character (-).</span></span> <span data-ttu-id="ffcb5-201">As portas se aplicam a todos os endereços IP e todas as URLs do conjunto de pontos de extremidade para essa categoria.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-201">Ports apply to all IP addresses and all URLs in the endpoint set for a given category.</span></span> <span data-ttu-id="ffcb5-202">Omitidas caso estejam em branco.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-202">Omitted if blank.</span></span>
- <span data-ttu-id="ffcb5-203">udpPorts — As portas UDP para os intervalos de endereço IP deste conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-203">udpPorts — UDP ports for the IP address ranges in this endpoint set.</span></span> <span data-ttu-id="ffcb5-204">Omitidas caso estejam em branco.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-204">Omitted if blank.</span></span>
- <span data-ttu-id="ffcb5-205">ips — Os intervalos de endereço IP associados a esse conjunto de pontos de extremidade conforme associação com as portas TCP ou UDP listadas.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-205">ips — The IP address ranges associated with this endpoint set as associated with the listed TCP or UDP ports.</span></span> <span data-ttu-id="ffcb5-206">Uma matriz JSON de intervalos de endereço IP.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-206">A JSON array of IP address ranges.</span></span> <span data-ttu-id="ffcb5-207">Omitidas caso estejam em branco.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-207">Omitted if blank.</span></span>
- <span data-ttu-id="ffcb5-208">category — A categoria do conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-208">category — The connectivity category for the endpoint set.</span></span> <span data-ttu-id="ffcb5-209">Os valores válidos são _Otimizar_, _Permitir_ e _Padrão_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-209">Valid values are _Optimize_, _Allow_, and _Default_.</span></span> <span data-ttu-id="ffcb5-210">Se você pesquisar a saída do método Web de pontos de extremidade de um endereço IP ou URL específicos, é possível que sua consulta retornará várias categorias.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-210">If you search the endpoints web method output for the category of a specific IP address or URL, it is possible that your query will return multiple categories.</span></span> <span data-ttu-id="ffcb5-211">Nesse caso, siga a recomendação para a categoria de maior prioridade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-211">In such a case, follow the recommendation for the highest priority category.</span></span> <span data-ttu-id="ffcb5-212">Por exemplo, se o ponto de extremidade aparecer tanto em _Otimizar_ quanto em _Permitir_, você deve seguir os requisitos de _Otimizar_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-212">For example, if the endpoint appears in both _Optimize_ and _Allow_, you should follow the requirements for _Optimize_.</span></span> <span data-ttu-id="ffcb5-213">Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-213">Required.</span></span>
- <span data-ttu-id="ffcb5-214">expressRoute — _Verdadeiro_ se esse conjunto de pontos de extremidade é roteado sobre ExpressRoute, caso contrário, _falso_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-214">expressRoute — _True_ if this endpoint set is routed over ExpressRoute, _False_ if not.</span></span>
- <span data-ttu-id="ffcb5-215">required — _Verdadeiro_ se esse conjunto de pontos de extremidade precisar de conectividade com o Office 365 para ter suporte.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-215">required — _True_ if this endpoint set is required to have connectivity for Office 365 to be supported.</span></span> <span data-ttu-id="ffcb5-216">_Falso_ se o conjunto de pontos de extremidade for opcional.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-216">_False_ if this endpoint set is optional.</span></span>
- <span data-ttu-id="ffcb5-217">notes — Para pontos de extremidade opcionais, este texto descreve a funcionalidade do Office 365 que não estará disponível se os endereços IP ou URLs deste conjunto de pontos de extremidade não puderem ser acessados na camada de rede.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-217">notes — For optional endpoints, this text describes Office 365 functionality that would be unavailable if IP addresses or URLs in this endpoint set cannot be accessed at the network layer.</span></span> <span data-ttu-id="ffcb5-218">Omitidas caso estejam em branco.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-218">Omitted if blank.</span></span>

### <a name="examples"></a><span data-ttu-id="ffcb5-219">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-219">Examples:</span></span>

<span data-ttu-id="ffcb5-220">Exemplo 1 de URI de solicitação: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-220">Example 1 request URI: [https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-221">Esse URI obtém todos os pontos de extremidade da instância do Office 365 em todo o mundo para todas as cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-221">This URI obtains all endpoints for the Office 365 worldwide instance for all workloads.</span></span> <span data-ttu-id="ffcb5-222">Exemplo de resultado mostrando um trecho da saída:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-222">Example result that shows an excerpt of the output:</span></span>

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

<span data-ttu-id="ffcb5-223">Note que a saída completa da solicitação neste exemplo conteria outros conjuntos de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-223">Note that the full output of the request in this example would contain other endpoint sets.</span></span>

<span data-ttu-id="ffcb5-224">Exemplo 2 de URI de solicitação: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-224">Example 2 request URI: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-225">Esse exemplo obtém pontos de extremidade da instância do Office 365 em todo o mundo apenas para o Exchange Online e dependências.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-225">This example obtains endpoints for the Office 365 Worldwide instance for Exchange Online and dependencies only.</span></span>

<span data-ttu-id="ffcb5-226">A saída para o exemplo 2 é semelhante ao do exemplo 1, exceto que os resultados não incluirão pontos de extremidade do SharePoint Online ou do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-226">The output for example 2 is similar to example 1 except that the results would not include endpoints for SharePoint Online or Skype for Business Online.</span></span>

## <a name="changes-web-method"></a><span data-ttu-id="ffcb5-227">Método Web de alterações</span><span class="sxs-lookup"><span data-stu-id="ffcb5-227">Changes web method</span></span>

<span data-ttu-id="ffcb5-228">O método Web de alterações retorna as atualizações mais recentes publicadas, normalmente as alterações do mês anterior de URLs e dos intervalos de endereços IP.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-228">The changes web method returns the most recent updates that have been published, typically the previous month's changes to IP address ranges and URLs.</span></span>

<span data-ttu-id="ffcb5-229">As alterações mais importantes em dados de pontos de extremidade são novos endereços de URL e de IP.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-229">The most critical changes to endpoints data are new URLs and IP addresses.</span></span> <span data-ttu-id="ffcb5-230">Falha ao adicionar um endereço de IP a uma lista de controle de acesso do firewall a um lista de bypass de servidores proxy pode causar uma interrupção para usuários do Office 365 por trás desse dispositivo de rede.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-230">Failure to add an IP address to a firewall access control list or a URL to a proxy server bypass list can cause an outage for Office 365 users behind that network device.</span></span> <span data-ttu-id="ffcb5-231">Apesar dos requisitos operacionais, novos pontos de extremidade são publicados no serviço Web 30 dias antes da data que os pontos de extremidades são provisionados para uso para lhe dar tempo de atualizar listas de controle de acesso e listas de bypass de servidores proxy.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-231">Notwithstanding operational requirements, new endpoints are published to the web service 30 days in advance of the date the endpoints are provisioned for use to give you time to update access control lists and proxy server bypass lists.</span></span>

<span data-ttu-id="ffcb5-232">O parâmetro necessário para o método da web de alterações é:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-232">The required parameter for the changes web method is:</span></span>

- <span data-ttu-id="ffcb5-233">**Version=\<YYYYMMDDNN>** — Parâmetro de rota URL obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-233">**Version=\<YYYYMMDDNN>** — Required URL route parameter.</span></span> <span data-ttu-id="ffcb5-234">Este valor é a versão que você tem implementada atualmente.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-234">This value is the version that you have currently implemented.</span></span> <span data-ttu-id="ffcb5-235">O serviço da Web retornará as alterações desde essa versão.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-235">The web service will return the changes since that version.</span></span> <span data-ttu-id="ffcb5-236">O formato é _YYYYMMDDNN_, em que _NN_ é um número natural incrementado, se houver várias versões que precisem ser publicadas em um único dia, com _00_ representando a primeira atualização de um determinado dia.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-236">The format is _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day, with _00_ representing the first update for a given day.</span></span> <span data-ttu-id="ffcb5-237">O serviço da web requer que o parâmetro de _versão_ contenha exatamente 10 dígitos.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-237">The web service requires the _version_ parameter to contain exactly 10 digits.</span></span>

<span data-ttu-id="ffcb5-238">O método da Web de alterações é limitado por taxa da mesma forma que o método da web de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-238">The changes web method is rate limited in the same way as the endpoints web method.</span></span> <span data-ttu-id="ffcb5-239">Se você receber um código de resposta HTTP 429, espere 1 hora antes de repetir sua solicitação ou para gerar um novo GUID para a solicitação.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-239">If you receive a 429 HTTP response code, wait 1 hour before repeating your request or generate a new GUID for the request.</span></span>

<span data-ttu-id="ffcb5-240">O resultado do método Web de alterações é uma matriz de registros em que cada registro representa uma alteração em uma versão específica dos pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-240">The result from the changes web method is an array of records in which each record represents a change in a specific version of the endpoints.</span></span> <span data-ttu-id="ffcb5-241">Os elementos de cada registro são:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-241">The elements for each record are:</span></span>

- <span data-ttu-id="ffcb5-242">id — A ID imutável do registro de alterações.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-242">id — The immutable id of the change record.</span></span>
- <span data-ttu-id="ffcb5-243">endpointSetId — O ID do registro do conjunto de pontos de extremidade que é alterado.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-243">endpointSetId — The ID of the endpoint set record that is changed.</span></span>
- <span data-ttu-id="ffcb5-244">disposition — Descreve o que a alteração fez com o registro do conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-244">disposition — Describes what the change did to the endpoint set record.</span></span> <span data-ttu-id="ffcb5-245">Os valores são _alterar_, _adicionar_ ou _remover_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-245">Values are _change_, _add_, or _remove_.</span></span>
- <span data-ttu-id="ffcb5-246">impact — Nem todas as alterações serão igualmente importantes para todos os ambientes.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-246">impact — Not all changes will be equally important to every environment.</span></span> <span data-ttu-id="ffcb5-247">Isso descreve o impacto esperado para um ambiente de perímetro de rede corporativa como resultado dessa alteração.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-247">This element describes the expected impact to an enterprise network perimeter environment as a result of this change.</span></span> <span data-ttu-id="ffcb5-248">Este elemento está incluído apenas nos registros de alterações da versão **2018112800** e posterior.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-248">This element is included only in change records of version **2018112800** and later.</span></span> <span data-ttu-id="ffcb5-249">As opções para o impacto são: — AddedIp – Um endereço de IP foi adicionado ao Office 365 e estará ativo no serviço em breve.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-249">Options for the impact are: — AddedIp – An IP address was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="ffcb5-250">Isso representa uma alteração que você precisa realizar em um firewall ou em outro dispositivo de perímetro de rede de camada 3.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-250">This represents a change you need to take on a firewall or other layer 3 network perimeter device.</span></span> <span data-ttu-id="ffcb5-251">Se você não adicionar isso antes de começar a usá-lo, talvez haja uma interrupção.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-251">If you don’t add this before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="ffcb5-252">— AddedUrl – Uma URL foi adicionada ao Office 365 e estará ativa no serviço em breve.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-252">— AddedUrl – A URL was added to Office 365 and will be live on the service soon.</span></span> <span data-ttu-id="ffcb5-253">Isso representa uma mudança que você precisa fazer em um servidor de proxy ou dispositivo de perímetro de rede de análise de URL.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-253">This represents a change you need to take on a proxy server or URL parsing network perimeter device.</span></span> <span data-ttu-id="ffcb5-254">Se você não adicionar esta URL antes de usá-la, talvez haja uma interrupção.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-254">If you don’t add this URL before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="ffcb5-255">— AddedIpAndUrl — Um endereço de IP e URL foram adicionados.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-255">— AddedIpAndUrl — Both an IP address and a URL were added.</span></span> <span data-ttu-id="ffcb5-256">Isso representa uma alteração que você precisa realizar em um dispositivo de camada 3 de firewall ou em um servidor proxy ou dispositivo de análise da URL.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-256">This represents a change you need to take on either a firewall layer 3 device or a proxy server or URL parsing device.</span></span> <span data-ttu-id="ffcb5-257">Se você não adicionar esse par IP/URL antes de começar a usá-lo, você pode observar uma interrupção.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-257">If you don’t add this IP/URL pair before we start using it, you may experience an outage.</span></span>
  <span data-ttu-id="ffcb5-258">— RemovedIpOrUrl – Pelo menos um endereço IP ou URL foi removido do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-258">— RemovedIpOrUrl – At least one IP address or URL was removed from Office 365.</span></span> <span data-ttu-id="ffcb5-259">Remover os pontos de extremidade de rede nos seus dispositivos de perímetro, mas não há nenhuma data limite para você fazer isso.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-259">Remove the network endpoints from your perimeter devices, but there’s no deadline for you to do this.</span></span>
  <span data-ttu-id="ffcb5-260">— ChangedIsExpressRoute – O atributo de suporte do ExpressRoute foi modificado.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-260">— ChangedIsExpressRoute – The ExpressRoute support attribute was changed.</span></span> <span data-ttu-id="ffcb5-261">Se você usar o ExpressRoute será necessário tomar medidas dependendo da configuração.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-261">If you use ExpressRoute, you might need to take action depending on your configuration.</span></span>
  <span data-ttu-id="ffcb5-262">— MovedIpOrUrl – Movemos um endereço IP ou uma Url entre esse conjunto de ponto de extremidade e outro.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-262">— MovedIpOrUrl – We moved an IP address or Url between this endpoint set and another one.</span></span> <span data-ttu-id="ffcb5-263">Geralmente, nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-263">Generally no action is required.</span></span>
  <span data-ttu-id="ffcb5-264">— RemovedDuplicateIpOrUrl – Removemos um endereço IP ou uma URL duplicados, mas ele ainda é publicado para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-264">— RemovedDuplicateIpOrUrl – We removed a duplicate IP address or Url but it’s still published for Office 365.</span></span> <span data-ttu-id="ffcb5-265">Geralmente, nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-265">Generally no action is required.</span></span>
  <span data-ttu-id="ffcb5-266">— OtherNonPriorityChanges – Alteramos algo menos crítico que todas as opções como um campo de anotações.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-266">— OtherNonPriorityChanges – We changed something less critical than all of the other options, such as the contents of a note field.</span></span>
- <span data-ttu-id="ffcb5-267">version — A versão do conjunto de pontos de extremidade em que a alteração foi introduzida.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-267">version — The version of the published endpoint set in which the change was introduced.</span></span> <span data-ttu-id="ffcb5-268">Os números de versões estão no formato _YYYYMMDDNN_, em que _NN_ é um número natural incrementado caso existam várias versões a serem publicadas em um único dia.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-268">Version numbers are of the format _YYYYMMDDNN_, where _NN_ is a natural number incremented if there are multiple versions required to be published on a single day.</span></span>
- <span data-ttu-id="ffcb5-269">previous — Uma subestrutura detalhando os valores anteriores de elementos alterados no conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-269">previous — A substructure detailing previous values of changed elements on the endpoint set.</span></span> <span data-ttu-id="ffcb5-270">Isso não será incluído para conjuntos de pontos de extremidade recém-adicionados.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-270">This will not be included for newly added endpoint sets.</span></span> <span data-ttu-id="ffcb5-271">Inclui _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-271">Includes  _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="ffcb5-272">current — Uma subestrutura detalhando valores atualizados de elementos de alterações no conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-272">current — A substructure detailing updated values of changes elements on the endpoint set.</span></span> <span data-ttu-id="ffcb5-273">Inclui _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ e _notes_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-273">Includes _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_, and _notes_.</span></span>
- <span data-ttu-id="ffcb5-274">add — Uma subestrutura que detalha os itens a serem adicionados às coleções do conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-274">add — A substructure detailing items to be added to endpoint set collections.</span></span> <span data-ttu-id="ffcb5-275">Omitida caso não haja nenhuma adição.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-275">Omitted if there are no additions.</span></span>
  <span data-ttu-id="ffcb5-276">— effectiveDate — Define os dados de quando as adições estarão disponíveis no serviço.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-276">— effectiveDate — Defines the data when the additions will be live in the service.</span></span>
  <span data-ttu-id="ffcb5-277">— ips — Itens a serem adicionados à matriz _ips_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-277">— ips — Items to be added to the _ips_ array.</span></span>
  <span data-ttu-id="ffcb5-278">— urls- Itens a serem adicionados à matriz _urls_. </span><span class="sxs-lookup"><span data-stu-id="ffcb5-278">— urls- Items to be added to the _urls_ array.</span></span>
- <span data-ttu-id="ffcb5-279">remove — Uma subestrutura detalhando itens a serem removidos do conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-279">remove — A substructure detailing items to be removed from the endpoint set.</span></span> <span data-ttu-id="ffcb5-280">Omitido se não houver remoções.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-280">Omitted if there are no removals.</span></span>
  <span data-ttu-id="ffcb5-281">— ips — Itens a serem removidos da matriz _ips_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-281">— ips — Items to be removed from the _ips_ array.</span></span>
  <span data-ttu-id="ffcb5-282">— urls- Itens a serem removidos da matriz _urls_. </span><span class="sxs-lookup"><span data-stu-id="ffcb5-282">— urls- Items to be removed from the _urls_ array.</span></span>

### <a name="examples"></a><span data-ttu-id="ffcb5-283">Exemplos:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-283">Examples:</span></span>

<span data-ttu-id="ffcb5-284">Exemplo 1 de URI de solicitação: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-284">Example 1 request URI: [https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-p144">Solicita todas as alterações anteriores da instância do serviço do Office 365 em todo o mundo. Exemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p144">This requests all previous changes to the Office 365 worldwide service instance. Example result:</span></span>

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

<span data-ttu-id="ffcb5-287">Exemplo 2 de URI de solicitação: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="ffcb5-287">Example 2 request URI: [https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>

<span data-ttu-id="ffcb5-p145">Solicita as alterações desde a versão especificada da instância do Office 365 em todo o mundo. Nesse caso, a versão especificada é a mais recente. Exemplo de resultado:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p145">This requests changes since the specified version to the Office 365 Worldwide instance. In this case, the version specified is the latest. Example result:</span></span>

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a><span data-ttu-id="ffcb5-291">Exemplo de script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffcb5-291">Example PowerShell Script</span></span>

<span data-ttu-id="ffcb5-292">Você pode executar esse script do PowerShell para ver se há ações que você precisa tomar para os dados atualizados.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-292">You can run this PowerShell script to see if there are actions you need to take for updated data.</span></span> <span data-ttu-id="ffcb5-293">Você pode executar esse script como uma tarefa agendada para verificar se há uma atualização da versão.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-293">You can run this script as a scheduled task to check for a version update.</span></span> <span data-ttu-id="ffcb5-294">Para evitar a carga excessiva no serviço Web, tente não executar o script mais do que uma vez por hora.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-294">To avoid excessive load on the web service, try not to run the script more than once an hour.</span></span>

<span data-ttu-id="ffcb5-295">O script faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-295">The script does the following:</span></span>

- <span data-ttu-id="ffcb5-296">Verifica o número da versão dos pontos de extremidade da instância do Office 365 Worldwide, chamando a API REST do serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-296">Checks the version number of the current Office 365 Worldwide instance endpoints by calling the web service REST API.</span></span>
- <span data-ttu-id="ffcb5-297">Verifica uma versão do arquivo atual em _$Env:TEMP\O365_endpoints_latestversion.txt_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-297">Checks for a current version file at _$Env:TEMP\O365_endpoints_latestversion.txt_.</span></span> <span data-ttu-id="ffcb5-298">O caminho da variável global **$Env:TEMP** normalmente é _C:\Users\\<username\>\AppData\Local\Temp_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-298">The path of the global variable **$Env:TEMP** is usually _C:\Users\\<username\>\AppData\Local\Temp_.</span></span>
- <span data-ttu-id="ffcb5-299">Se esta é a primeira vez que o script é executado, o script retorna a versão atual e todos os endereços IP e URLs atuais, grava a versão de pontos de extremidade no arquivo _$Env:TEMP\O365_endpoints_latestversion.txt_ e a saída de dados dos pontos de extremidade para o arquivo _$Env:TEMP\O365_endpoints_data.txt_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-299">If this is the first time the script has been run, the script returns the current version and all current IP addresses and URLs, writes the endpoints version to the file _$Env:TEMP\O365_endpoints_latestversion.txt_ and the endpoints data output to the file _$Env:TEMP\O365_endpoints_data.txt_.</span></span> <span data-ttu-id="ffcb5-300">Você pode modificar o caminho e/ou o nome do arquivo de saída editando estas linhas:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-300">You can modify the path and/or name of the output file by editing these lines:</span></span>

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- <span data-ttu-id="ffcb5-301">Em cada execução subsequente do script, se a versão mais recente do serviço Web for idêntica à versão do arquivo _O365_endpoints_latestversion.txt_, o script sairá sem fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-301">On each subsequent execution of the script, if the latest web service version is identical to the version in the _O365_endpoints_latestversion.txt_ file, the script exits without making any changes.</span></span>
- <span data-ttu-id="ffcb5-302">Quando a versão mais recente do serviço Web é mais recente do que a versão do arquivo _O365_endpoints_latestversion.txt_, o script retorna os pontos de extremidade e os filtros para a categoria de pontos de extremidade **Permitir** e **Otimizar**, atualiza a versão no arquivo _O365_endpoints_latestversion.txt_ e grava os dados atualizados no arquivo _O365_endpoints_data.txt_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-302">When the latest web service version is newer than the version in the _O365_endpoints_latestversion.txt_ file, the script returns the endpoints and filters for the **Allow** and **Optimize** category endpoints, updates the version in the _O365_endpoints_latestversion.txt_ file, and writes the updated data to the _O365_endpoints_data.txt_ file.</span></span>

<span data-ttu-id="ffcb5-303">O script gera um _ClientRequestId_ exclusivo para o computador em que ele é executado e reutiliza essa ID em várias chamadas.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-303">The script generates a unique _ClientRequestId_ for the computer it is executed on, and reuses this ID across multiple calls.</span></span> <span data-ttu-id="ffcb5-304">Essa ID é armazenada no arquivo _O365_endpoints_latestversion.txt_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-304">This ID is stored in the _O365_endpoints_latestversion.txt_ file.</span></span>

### <a name="to-run-the-powershell-script"></a><span data-ttu-id="ffcb5-305">Para executar o script do PowerShell</span><span class="sxs-lookup"><span data-stu-id="ffcb5-305">To run the PowerShell script</span></span>

1. <span data-ttu-id="ffcb5-306">Copie o script e salve-o no seu disco rígido local ou no local do script como _Get-O365WebServiceUpdates.ps1_.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-306">Copy the script and save it to your local hard drive or script location as _Get-O365WebServiceUpdates.ps1_.</span></span>
1. <span data-ttu-id="ffcb5-307">Execute o script em seu editor de script preferido, como o ISE do PowerShell ou o VS Code, ou de um consolo do PowerShell usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-307">Execute the script in your preferred script editor such as the PowerShell ISE or VS Code, or from a PowerShell console using the following command:</span></span>

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    <span data-ttu-id="ffcb5-308">Não há parâmetros para passar para o script.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-308">There are no parameters to pass to the script.</span></span>

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a><span data-ttu-id="ffcb5-309">Exemplo de script do Python</span><span class="sxs-lookup"><span data-stu-id="ffcb5-309">Example Python Script</span></span>

<span data-ttu-id="ffcb5-p150">Esse é um script do Python, testado com o Python 3.6.3 no Windows 10, que você pode executar para ver se há ações que você precisa realizar em relação aos dados atualizados. Esse script verifica o número da versão dos pontos de extremidade de instâncias do Office 365 em todo o mundo. Quando houver uma alteração, ele baixará os pontos de extremidade e os filtros dos pontos de extremidade das categorias _Permitir_ e _Otimizar_. Ele também usa um ClientRequestId exclusivo em várias chamadas e salva a última versão encontrada em um arquivo temporário. Você deve chamar esse script uma vez por hora para verificar se há alguma atualização da versão.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-p150">Here is a Python script, tested with Python 3.6.3 on Windows 10, that you can run to see if there are actions you need to take for updated data. This script checks the version number for the Office 365 Worldwide instance endpoints. When there is a change, it downloads the endpoints and filters for the _Allow_ and _Optimize_ category endpoints. It also uses a unique ClientRequestId across multiple calls and saves the latest version found in a temporary file. You should call this script once an hour to check for a version update.</span></span>

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a><span data-ttu-id="ffcb5-315">Controle de versão de interface do serviço da Web</span><span class="sxs-lookup"><span data-stu-id="ffcb5-315">Web Service interface versioning</span></span>

<span data-ttu-id="ffcb5-316">As atualizações dos parâmetros ou resultados para esses métodos de serviço Web podem ser necessárias no futuro.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-316">Updates to the parameters or results for these web service methods may be required in the future.</span></span> <span data-ttu-id="ffcb5-317">Após a publicação da disponibilidade geral desses serviços Web, a Microsoft tomará medidas razoáveis para oferecer um aviso prévio de atualizações de material para o serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-317">After the general availability version of these web services is published, Microsoft will make reasonable efforts to provide advance notice of material updates to the web service.</span></span> <span data-ttu-id="ffcb5-318">Quando a Microsoft acredita que uma atualização exigirá mudanças aos clientes usando o serviço Web, a Microsoft manterá a versão anterior (uma versão mais antiga) do serviço Web disponível por pelo menos 12 meses após o lançamento da nova versão.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-318">When Microsoft believes that an update will require changes to clients using the web service, Microsoft will keep the previous version (one version back) of the web service available for at least 12 months after the release of the new version.</span></span> <span data-ttu-id="ffcb5-319">Os clientes que não atualizarem durante esse período poderão não acessar o serviço Web e seus métodos.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-319">Customers who do not upgrade during that time may be unable to access the web service and its methods.</span></span> <span data-ttu-id="ffcb5-320">Os clientes devem garantir que os clientes do serviço Web continuem funcionando sem erro se as seguintes alterações forem feitas na assinatura da interface do serviço Web:</span><span class="sxs-lookup"><span data-stu-id="ffcb5-320">Customers must ensure that clients of the web service continue working without error if the following changes are made to the web service interface signature:</span></span>

- <span data-ttu-id="ffcb5-321">Adição de um novo parâmetro opcional a um método Web existente que não precise ser fornecido por clientes mais antigos e que não afete os resultados recebidos por um cliente mais antigo.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-321">Adding a new optional parameter to an existing web method that doesn't have to be provided by older clients and doesn't impact the result an older client receives.</span></span>
- <span data-ttu-id="ffcb5-322">Adição de um novo atributo nomeado em um dos itens do REST de resposta ou em colunas adicionais para o CSV de resposta.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-322">Adding a new named attribute in one of the response REST items or additional columns to the response CSV.</span></span>
- <span data-ttu-id="ffcb5-323">Adição de um novo método Web com um novo nome que não é chamado pelos clientes mais antigos.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-323">Adding a new web method with a new name that is not called by the older clients.</span></span>

## <a name="update-notifications"></a><span data-ttu-id="ffcb5-324">Notificações de atualização</span><span class="sxs-lookup"><span data-stu-id="ffcb5-324">Update notifications</span></span>

<span data-ttu-id="ffcb5-325">Você pode usar alguns métodos diferentes para obter notificações por email quando as alterações nos endereços IP e URLs forem publicadas no serviço Web.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-325">You can use a few different methods to get email notifications when changes to the IP addresses and URLs are published to the web service.</span></span>

- <span data-ttu-id="ffcb5-326">Para usar uma solução Microsoft Flow, consulte [Usar o Microsoft Flow para receber um email de alterações com em endereços IP e URLs do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-326">To use a Microsoft Flow solution, see [Use Microsoft Flow to receive an email for changes to Office 365 IP Addresses and URLs](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).</span></span>
- <span data-ttu-id="ffcb5-327">Para implantar um Aplicativo Lógico do Azure usando um modelo ARM, confira [Notificação de atualização do Office 365 (v1.1)](https://aka.ms/ipurlws-updates-template).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-327">To deploy an Azure Logic App using an ARM template, see [Office 365 Update Notification (v1.1)](https://aka.ms/ipurlws-updates-template).</span></span>
- <span data-ttu-id="ffcb5-328">Para escrever um script usando o PowerShell, confira [Send-MailMessage](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-328">To write your own notification script using PowerShell, see [Send-MailMessage](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/send-mailmessage).</span></span>

## <a name="exporting-a-proxy-pac-file"></a><span data-ttu-id="ffcb5-329">Exportando um arquivo Proxy PAC</span><span class="sxs-lookup"><span data-stu-id="ffcb5-329">Exporting a Proxy PAC file</span></span>

<span data-ttu-id="ffcb5-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) é um script do PowerShell que lê os pontos de extremidade de rede mais recentes da URL do serviço Web e endereço IP do Office 365 e a criação de uma amostra de um arquivo PAC.</span><span class="sxs-lookup"><span data-stu-id="ffcb5-330">[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) is a PowerShell script that reads the latest network endpoints from the Office 365 IP Address and URL web service and creates a sample PAC file.</span></span> <span data-ttu-id="ffcb5-331">Para saber mais sobre como usar Get-PacFile, confira [Usar um arquivo PAC para o roteamento direto do tráfego vital o Office 365](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span><span class="sxs-lookup"><span data-stu-id="ffcb5-331">For information on using Get-PacFile, see [Use a PAC file for direct routing of vital Office 365 traffic](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ffcb5-332">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="ffcb5-332">Related Topics</span></span>
  
[<span data-ttu-id="ffcb5-333">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-333">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="ffcb5-334">Gerenciar pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-334">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)
  
[<span data-ttu-id="ffcb5-335">Perguntas frequentes sobre pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-335">Office 365 endpoints FAQ</span></span>](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[<span data-ttu-id="ffcb5-336">Princípios de conectividade de rede do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-336">Office 365 Network Connectivity Principles</span></span>](microsoft-365-network-connectivity-principles.md)

[<span data-ttu-id="ffcb5-337">Rede do Office 365 e ajuste de desempenho</span><span class="sxs-lookup"><span data-stu-id="ffcb5-337">Office 365 network and performance tuning</span></span>](network-planning-and-performance.md)

[<span data-ttu-id="ffcb5-338">Avaliando a conectividade de rede do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-338">Assessing Office 365 network connectivity</span></span>](assessing-network-connectivity.md)
  
[<span data-ttu-id="ffcb5-339">Qualidade da mídia e desempenho de conectividade de rede no Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ffcb5-339">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[<span data-ttu-id="ffcb5-340">Como otimizar a sua rede para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ffcb5-340">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[<span data-ttu-id="ffcb5-341">Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho</span><span class="sxs-lookup"><span data-stu-id="ffcb5-341">Office 365 performance tuning using baselines and performance history</span></span>](performance-tuning-using-baselines-and-history.md)
  
[<span data-ttu-id="ffcb5-342">Plano de solução de problemas de desempenho do Office 365</span><span class="sxs-lookup"><span data-stu-id="ffcb5-342">Performance troubleshooting plan for Office 365</span></span>](performance-troubleshooting-plan.md)
