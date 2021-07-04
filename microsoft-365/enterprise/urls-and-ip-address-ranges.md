---
title: 'URLs e intervalos de endereço IP do Office 365 '
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/28/2021
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Resumo: o Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem estar acessíveis para os clientes que usam os planos do Office 365, incluindo a Government Community Cloud (GCC).'
hideEdit: true
ms.openlocfilehash: 22294294ba35f00ff33a9b849f320f0e8b42e0ba
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290250"
---
# <a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="0e29e-104">Intervalos de endereços IP e URLs do Office 365</span><span class="sxs-lookup"><span data-stu-id="0e29e-104">Office 365 URLs and IP address ranges</span></span>

<span data-ttu-id="0e29e-p102">O Office 365 requer conectividade com a Internet. Os pontos de extremidade abaixo devem ser acessíveis para os clientes que usam os planos do Office 365, incluindo a nuvem pública da Comunidade (GCC).</span><span class="sxs-lookup"><span data-stu-id="0e29e-p102">Office 365 requires connectivity to the Internet. The endpoints below should be reachable for customers using Office 365 plans, including Government Community Cloud (GCC).</span></span>
  
<span data-ttu-id="0e29e-107">*Office 365 Worldwide (+GCC)* \| [Office 365 operado pela 21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 Alemanha](microsoft-365-germany-endpoints.md) \| [Office 365 Governo dos EUA DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 Governo dos EUA GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|</span><span class="sxs-lookup"><span data-stu-id="0e29e-107">*Office 365 Worldwide (+GCC)* \| [Office 365 operated by 21 Vianet](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 Germany](microsoft-365-germany-endpoints.md) \| [Office 365 U.S. Government DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 U.S. Government GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|</span></span>

|<span data-ttu-id="0e29e-108">Notas</span><span class="sxs-lookup"><span data-stu-id="0e29e-108">Notes</span></span>|<span data-ttu-id="0e29e-109">Baixar</span><span class="sxs-lookup"><span data-stu-id="0e29e-109">Download</span></span>|<span data-ttu-id="0e29e-110">Usar</span><span class="sxs-lookup"><span data-stu-id="0e29e-110">Use</span></span>|
|---|---|---|
|<span data-ttu-id="0e29e-111">**Última atualização:** 28/06/2021 - ![](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png)Alterar registro da assinatura [RSS](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span><span class="sxs-lookup"><span data-stu-id="0e29e-111">**Last updated:** 06/28/2021 - ![RSS](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Change Log subscription](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)</span></span>|<span data-ttu-id="0e29e-112">**Baixar:** todos os destinos obrigatórios e opcionais em uma lista [no formato em JSON](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).</span><span class="sxs-lookup"><span data-stu-id="0e29e-112">**Download:** all required and optional destinations in one [JSON formatted](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) list.</span></span>|<span data-ttu-id="0e29e-113">**Use:** nossos arquivos proxy [PAC](managing-office-365-endpoints.md#pacfiles)</span><span class="sxs-lookup"><span data-stu-id="0e29e-113">**Use:** our proxy [PAC files](managing-office-365-endpoints.md#pacfiles)</span></span>|
|

<span data-ttu-id="0e29e-p103">Comece com [Gerenciar os pontos de extremidade do Office 365](managing-office-365-endpoints.md) para entender nossas recomendações para gerenciar a conectividade de rede usando estes dados. Os dados dos pontos de extremidade são atualizados, conforme necessário, no início de cada mês com novos endereços IP e URLs publicadas 30 dias antes de se tornarem ativas. Isso permite que os clientes que ainda não têm atualizações automáticas completem seus processos antes que uma nova conectividade seja necessária. Os pontos de extremidade também podem ser atualizados durante o mês, se necessário, para tratar de escalações de suporte, incidentes de segurança ou outros requisitos operacionais imediatos. Todos os dados exibidos abaixo nesta página são gerados a partir dos serviços Web baseados em REST. Se estiver usando um script ou dispositivo de rede para acessar esses dados, vá diretamente para o [serviço Web](microsoft-365-ip-web-service.md).</span><span class="sxs-lookup"><span data-stu-id="0e29e-p103">Start with [Managing Office 365 endpoints](managing-office-365-endpoints.md) to understand our recommendations for managing network connectivity using this data. Endpoints data is updated as needed at the beginning of each month with new IP Addresses and URLs published 30 days in advance of being active. This allows for customers who do not yet have automated updates to complete their processes before new connectivity is required. Endpoints may also be updated during the month if needed to address support escalations, security incidents, or other immediate operational requirements. The data shown on this page below is all generated from the REST-based web services. If you are using a script or a network device to access this data, you should go to the [Web service](microsoft-365-ip-web-service.md) directly.</span></span>

<span data-ttu-id="0e29e-p104">Os dados do terminal abaixo listam os requisitos de conectividade da máquina de um usuário ao Office 365. Ele não inclui conexões de rede da Microsoft em uma rede de clientes, às vezes chamadas de conexões de rede híbridas ou de entrada. Consulte [Terminais adicionais](additional-office365-ip-addresses-and-urls.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0e29e-p104">Endpoint data below lists requirements for connectivity from a user's machine to Office 365. It does not include network connections from Microsoft into a customer network, sometimes called hybrid or inbound network connections. See [Additional endpoints](additional-office365-ip-addresses-and-urls.md) for more information.</span></span>

<span data-ttu-id="0e29e-p105">Os pontos de extremidade são agrupados em quatro áreas de serviço. As primeiras três áreas de serviço podem ser selecionadas independentemente de conectividade. A quarta área de serviço é uma dependência comum (chamada de Microsoft 365 Common and Office) e deve ter sempre conectividade de rede.</span><span class="sxs-lookup"><span data-stu-id="0e29e-p105">The endpoints are grouped into four service areas. The first three service areas can be independently selected for connectivity. The fourth service area is a common dependency (called Microsoft 365 Common and Office) and must always have network connectivity.</span></span>

<span data-ttu-id="0e29e-126">As colunas de dados exibidas são:</span><span class="sxs-lookup"><span data-stu-id="0e29e-126">Data columns shown are:</span></span>

- <span data-ttu-id="0e29e-p106">**ID**: O número de ID da linha, também conhecido como um conjunto de pontos de extremidade. Esse ID é o mesmo que é retornado pelo serviço web ao conjunto de pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="0e29e-p106">**ID**: The ID number of the row, also known as an endpoint set. This ID is the same as is returned by the web service for the endpoint set.</span></span>

- <span data-ttu-id="0e29e-p107">**Categoria**: mostra se o conjunto de pontos de extremidade está classificado como “Otimizar”, “Permitir” ou “Padrão”. Você pode ler sobre essas categorias e orientações para o gerenciamento delas em [Novas categorias de pontos de extremidade do Office 365](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). Esta coluna também lista quais conjunto de pontos de extremidade são necessário para se ter conectividade de rede. Quanto aos conjuntos de pontos de extremidade que não precisam ter conectividade de rede, fornecemos notas neste campo para indicar qual funcionalidade faltaria se o conjunto de pontos de extremidade estivesse bloqueado. Se você excluir uma área de serviço inteira, os conjuntos de pontos de extremidade listados conforme necessário não exigirão conectividade.</span><span class="sxs-lookup"><span data-stu-id="0e29e-p107">**Category**: Shows whether the endpoint set is categorized as "Optimize", "Allow", or "Default". You can read about these categories and guidance for management of them at [New Office 365 endpoint categories](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories). This column also lists which endpoint sets are required to have network connectivity. For endpoint sets which are not required to have network connectivity, we provide notes in this field to indicate what functionality would be missing if the endpoint set is blocked. If you are excluding an entire service area, the endpoint sets listed as required do not require connectivity.</span></span>

- <span data-ttu-id="0e29e-p108">**ER**: Aqui, você verá um **Sim** se o conjunto de pontos de extremidade tem suporte no Azure ExpressRoute com prefixos de rota do Office 365. A comunidade do BGP que inclui os prefixos de rota mostrados se alinha com a área do serviço listada. Quando o ER estiver marcado como **Não**, isso significa que o ExpressRoute não é suportado para esse conjunto de pontos de extremidade. No entanto, não devemos presumir que não existem rotas anunciadas para um conjunto de ponto de extremidade onde ER está marcado como **Não**.</span><span class="sxs-lookup"><span data-stu-id="0e29e-p108">**ER**: This is **Yes** if the endpoint set is supported over Azure ExpressRoute with Office 365 route prefixes. The BGP community that includes the route prefixes shown aligns with the service area listed. When ER is **No**, this means that ExpressRoute is not supported for this endpoint set. However, it should not be assumed that no routes are advertised for an endpoint set where ER is **No**.</span></span>

- <span data-ttu-id="0e29e-p109">**Endereços**: lista os FQDNs ou nomes de domínio curinga e intervalos de endereços IP para o conjunto de pontos de extremidade. Observe que o intervalo de endereços IP está no formato CIDR e pode incluir vários endereços IP individuais na rede especificada.</span><span class="sxs-lookup"><span data-stu-id="0e29e-p109">**Addresses**: Lists the FQDNs or wildcard domain names and IP Address ranges for the endpoint set. Note that an IP Address range is in CIDR format and may include many individual IP Addresses in the specified network.</span></span>

- <span data-ttu-id="0e29e-p110">**Portas**: lista as portas TCP ou UDP que são combinadas com os endereços para formar o ponto de extremidade de rede. Você poderá notar algumas duplicações nos intervalos de endereços IP em que há diferentes portas listadas.</span><span class="sxs-lookup"><span data-stu-id="0e29e-p110">**Ports**: Lists the TCP or UDP ports that are combined with the Addresses to form the network endpoint. You may notice some duplication in IP Address ranges where there are different ports listed.</span></span>

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

> [!NOTE]
> <span data-ttu-id="0e29e-142">Para recomendações sobre endereços IP e URLs do Yammer, consulte [Não é recomendável usar endereços IP codificados para o Yammer](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) no blog do Yammer.</span><span class="sxs-lookup"><span data-stu-id="0e29e-142">For recommendations on Yammer IP addresses and URLs, see [Using hard-coded IP addresses for Yammer is not recommended](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) on the Yammer blog.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0e29e-143">Tópicos Relacionados</span><span class="sxs-lookup"><span data-stu-id="0e29e-143">Related Topics</span></span>

[<span data-ttu-id="0e29e-144">Pontos de extremidades adicionais não incluídos no endereço IP do Office 365 e serviço da Web de URL</span><span class="sxs-lookup"><span data-stu-id="0e29e-144">Additional endpoints not included in the Office 365 IP Address and URL Web service</span></span>](additional-office365-ip-addresses-and-urls.md)

[<span data-ttu-id="0e29e-145">Gerenciar pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="0e29e-145">Managing Office 365 endpoints</span></span>](managing-office-365-endpoints.md)

[<span data-ttu-id="0e29e-146">Pontos de extremidade gerais do Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="0e29e-146">General Microsoft Stream endpoints</span></span>](/stream/network-overview#general-microsoft-stream-endpoints)
  
[<span data-ttu-id="0e29e-147">Monitorar a conectividade do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0e29e-147">Monitor Microsoft 365 connectivity</span></span>](./monitor-connectivity.md)

[<span data-ttu-id="0e29e-148">CA raiz e o pacote da autoridade de certificação intermediária no sistema de aplicativos de terceiros</span><span class="sxs-lookup"><span data-stu-id="0e29e-148">Root CA and the Intermediate CA bundle on the third-party application system</span></span>](../compliance/encryption-office-365-certificate-chains.md)
  
[<span data-ttu-id="0e29e-149">Conectividade de cliente</span><span class="sxs-lookup"><span data-stu-id="0e29e-149">Client connectivity</span></span>](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[<span data-ttu-id="0e29e-150">Redes de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="0e29e-150">Content delivery networks</span></span>](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[<span data-ttu-id="0e29e-151">Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem Pública</span><span class="sxs-lookup"><span data-stu-id="0e29e-151">Microsoft Azure IP Ranges and Service Tags – Public Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=56519)

[<span data-ttu-id="0e29e-152">Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem do Governo dos EUA</span><span class="sxs-lookup"><span data-stu-id="0e29e-152">Microsoft Azure IP Ranges and Service Tags – US Government Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57063)

[<span data-ttu-id="0e29e-153">Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem da Alemanha</span><span class="sxs-lookup"><span data-stu-id="0e29e-153">Microsoft Azure IP Ranges and Service Tags – Germany Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57064)

[<span data-ttu-id="0e29e-154">Intervalos IP e Tags de Serviço do Microsoft Azure – Nuvem da China</span><span class="sxs-lookup"><span data-stu-id="0e29e-154">Microsoft Azure IP Ranges and Service Tags – China Cloud</span></span>](https://www.microsoft.com/download/details.aspx?id=57062)
  
[<span data-ttu-id="0e29e-155">Grupos de notícias públicos da Microsoft</span><span class="sxs-lookup"><span data-stu-id="0e29e-155">Microsoft Public IP Space</span></span>](https://www.microsoft.com/download/details.aspx?id=53602)

[<span data-ttu-id="0e29e-156">Nome do Serviço e Registro de Número de Porta de Protocolo de Transporte</span><span class="sxs-lookup"><span data-stu-id="0e29e-156">Service Name and Transport Protocol Port Number Registry</span></span>](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
