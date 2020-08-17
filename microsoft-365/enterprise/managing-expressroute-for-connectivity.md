---
title: Gerenciar o ExpressRoute para conectividade do Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: Saiba como gerenciar o ExpressRoute para o Office 365, incluindo áreas comuns para configurar a filtragem de prefixo, segurança e conformidade.
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687521"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a><span data-ttu-id="150c4-103">Gerenciar o ExpressRoute para conectividade do Office 365</span><span class="sxs-lookup"><span data-stu-id="150c4-103">Managing ExpressRoute for Office 365 connectivity</span></span>

<span data-ttu-id="150c4-104">O ExpressRoute para Office 365 oferece um caminho de roteamento alternativo para alcançar muitos serviços do Office 365 sem precisar de todo o tráfego para saída na Internet.</span><span class="sxs-lookup"><span data-stu-id="150c4-104">ExpressRoute for Office 365 offers an alternative routing path to reach many Office 365 services without needing all traffic to egress to the internet.</span></span> <span data-ttu-id="150c4-105">Embora a conexão com a Internet com o Office 365 ainda seja necessária, as rotas específicas que a Microsoft anuncia por meio do BGP para a sua rede tornam o circuito direto do ExpressRoute preferencial, a menos que haja outras configurações na sua rede.</span><span class="sxs-lookup"><span data-stu-id="150c4-105">Although the internet connection to Office 365 is still needed, the specific routes that Microsoft advertises through BGP to your network make the direct ExpressRoute circuit preferred unless there are other configurations in your network.</span></span> <span data-ttu-id="150c4-106">As três áreas comuns que você pode querer configurar para gerenciar esse roteamento incluem filtragem de prefixo, segurança e conformidade.</span><span class="sxs-lookup"><span data-stu-id="150c4-106">The three common areas you may want to configure to manage this routing include prefix filtering, security, and compliance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="150c4-107">A Microsoft alterou o modo como o domínio de roteamento de emparelhamento da Microsoft é revisado para o Azure ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="150c4-107">Microsoft changed how the Microsoft Peering routing domain is reviewed for Azure ExpressRoute.</span></span> <span data-ttu-id="150c4-108">A partir de 31 de julho de 2017, todos os clientes do Azure ExpressRoute podem habilitar o emparelhamento da Microsoft diretamente do console administrativo do Azure ou via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="150c4-108">Starting July 31st, 2017, all Azure ExpressRoute customers can enable Microsoft Peering directly from the Azure Administrative console or via PowerShell.</span></span> <span data-ttu-id="150c4-109">Depois de habilitar o emparelhamento da Microsoft, qualquer cliente pode criar filtros de roteamento para receber anúncios de rota de BGP para aplicativos de contrato de cliente do Dynamics 365 (anteriormente conhecido como CRM Online).</span><span class="sxs-lookup"><span data-stu-id="150c4-109">After enabling Microsoft Peering, any customer can create route filters to receive BGP route advertisements for Dynamics 365 Customer Engagement applications (Formerly known as CRM Online).</span></span> <span data-ttu-id="150c4-110">Os clientes que precisam do Azure ExpressRoute para Office 365 devem obter análise da Microsoft antes de poderem criar filtros de rota para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="150c4-110">Customers needing Azure ExpressRoute for Office 365 must obtain review from Microsoft before they can create route filters for Office 365.</span></span> <span data-ttu-id="150c4-111">Entre em contato com a equipe de conta da Microsoft para saber mais sobre como solicitar uma revisão para habilitar o Office 365 ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="150c4-111">Please contact your Microsoft Account team to learn about how to request a review for enabling Office 365 ExpressRoute.</span></span> <span data-ttu-id="150c4-112">Assinaturas não autorizadas tentando criar filtros de roteamento para o Office 365 receberão uma [mensagem de erro](https://support.microsoft.com/kb/3181709)</span><span class="sxs-lookup"><span data-stu-id="150c4-112">Unauthorized subscriptions trying to create route filters for Office 365 will receive an [error message](https://support.microsoft.com/kb/3181709)</span></span>
  
## <a name="prefix-filtering"></a><span data-ttu-id="150c4-113">Filtragem de prefixo</span><span class="sxs-lookup"><span data-stu-id="150c4-113">Prefix filtering</span></span>

<span data-ttu-id="150c4-114">A Microsoft recomenda que os clientes aceitem todas as rotas de BGP, como anunciados na Microsoft, as rotas fornecidas passam por um processo rigoroso de revisão e validação, removendo qualquer benefício para a análise adicional.</span><span class="sxs-lookup"><span data-stu-id="150c4-114">Microsoft recommends that customers accept all BGP routes as advertised from Microsoft, the routes provided undergo a rigorous review and validation process removing any benefits to added scrutiny.</span></span> <span data-ttu-id="150c4-115">O ExpressRoute nativamente oferece os controles recomendados, como propriedade de prefixo IP, integridade e escala, sem filtragem de roteamento de entrada no lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="150c4-115">ExpressRoute natively offers the recommended controls such as IP prefix ownership, integrity, and scale - with no inbound route filtering on the customer side.</span></span>
  
<span data-ttu-id="150c4-116">Se você precisar de validação adicional de propriedade de rota no emparelhamento público do ExpressRoute, poderá verificar as rotas anunciadas em relação à lista de todos os prefixos IP IPv4 e IPv6 que representam os [intervalos de IP públicos da Microsoft](https://www.microsoft.com/download/details.aspx?id=53602).</span><span class="sxs-lookup"><span data-stu-id="150c4-116">If you require additional validation of route ownership across ExpressRoute public peering, you can check the advertised routes against the list of all IPv4 and IPv6 IP prefixes that represent [Microsoft's public IP ranges](https://www.microsoft.com/download/details.aspx?id=53602).</span></span> <span data-ttu-id="150c4-117">Esses intervalos abrangem o espaço de endereço da Microsoft completo e mudam com pouca frequência, fornecendo um conjunto confiável de intervalos para filtrar, além de oferecer proteção adicional aos clientes que se preocupam com rotas pertencentes à Microsoft que estão vazando em seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="150c4-117">These ranges cover the full Microsoft address space and change infrequently, providing a reliable set of ranges to filter against that also provides additional protection to customers who are concerned about non-Microsoft owned routes leaking into their environment.</span></span> <span data-ttu-id="150c4-118">No caso de haver uma alteração, ela será feita no primeiro dia do mês e o número da versão na seção **detalhes** da página será alterado sempre que o arquivo for atualizado.</span><span class="sxs-lookup"><span data-stu-id="150c4-118">In the event there is a change, it will be made on the 1st of the month and the version number in the **details** section of the page will change every time the file is updated.</span></span>
  
<span data-ttu-id="150c4-119">Há vários motivos para evitar o uso das [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365endpoints) para gerar listas de filtros de prefixo.</span><span class="sxs-lookup"><span data-stu-id="150c4-119">There are a number of reasons to avoid the use of the [Office 365 URLs and IP address ranges](https://aka.ms/o365endpoints) for generating prefix filter lists.</span></span> <span data-ttu-id="150c4-120">Incluindo o seguinte:</span><span class="sxs-lookup"><span data-stu-id="150c4-120">Including the following:</span></span>
  
- <span data-ttu-id="150c4-121">Os prefixos IP do Office 365 passam por muitas alterações com frequência.</span><span class="sxs-lookup"><span data-stu-id="150c4-121">The Office 365 IP prefixes undergo lots of changes on a frequent basis.</span></span>

- <span data-ttu-id="150c4-122">As URLs e os intervalos de endereços IP do Office 365 foram projetados para o gerenciamento de listas de permissões de firewall e infraestrutura de proxy, e não ao roteamento.</span><span class="sxs-lookup"><span data-stu-id="150c4-122">The Office 365 URLs and IP address ranges are designed for managing firewall allow lists and Proxy infrastructure, not routing.</span></span>

- <span data-ttu-id="150c4-123">As URLs e os intervalos de endereços IP do Office 365 não abrangem outros serviços da Microsoft que podem estar em escopo para suas conexões do ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="150c4-123">The Office 365 URLs and IP address ranges do not cover other Microsoft services that may be in scope for your ExpressRoute connections.</span></span>

|<span data-ttu-id="150c4-124">**Opção**</span><span class="sxs-lookup"><span data-stu-id="150c4-124">**Option**</span></span>|<span data-ttu-id="150c4-125">**Complexidade**</span><span class="sxs-lookup"><span data-stu-id="150c4-125">**Complexity**</span></span>|<span data-ttu-id="150c4-126">**Controle de alterações**</span><span class="sxs-lookup"><span data-stu-id="150c4-126">**Change Control**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="150c4-127">Aceitar todas as rotas da Microsoft</span><span class="sxs-lookup"><span data-stu-id="150c4-127">Accept all Microsoft routes</span></span>  <br/> |<span data-ttu-id="150c4-128">**Baixo:** O cliente depende dos controles da Microsoft para garantir que todas as rotas estejam devidamente de propriedade.</span><span class="sxs-lookup"><span data-stu-id="150c4-128">**Low:** Customer relies upon Microsoft controls to ensure all routes are properly owned.</span></span>  <br/> |<span data-ttu-id="150c4-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="150c4-129">None</span></span>  <br/> |
|<span data-ttu-id="150c4-130">Filtrar sub-redes de propriedade da Microsoft</span><span class="sxs-lookup"><span data-stu-id="150c4-130">Filter Microsoft owned supernets</span></span>  <br/> |<span data-ttu-id="150c4-131">**Médio:** O cliente implementa listas de filtro de prefixo resumido para permitir somente rotas de propriedade da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="150c4-131">**Medium:** Customer implements summarized prefix filter lists to allow only Microsoft owned routes.</span></span>  <br/> |<span data-ttu-id="150c4-132">Os clientes devem garantir que as atualizações não frequentes sejam refletidas nos filtros de rota.</span><span class="sxs-lookup"><span data-stu-id="150c4-132">Customers must ensure the infrequent updates are reflected in route filters.</span></span>  <br/> |
|<span data-ttu-id="150c4-133">Filtrar intervalos IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="150c4-133">Filter Office 365 IP ranges</span></span>  <br/> [!CAUTION] <span data-ttu-id="150c4-134">Não recomendado</span><span class="sxs-lookup"><span data-stu-id="150c4-134">Not-Recommended</span></span> |<span data-ttu-id="150c4-135">**Alta:** O cliente filtra rotas com base em prefixos IP do Office 365 definidos.</span><span class="sxs-lookup"><span data-stu-id="150c4-135">**High:** Customer filters routes based on defined Office 365 IP prefixes.</span></span>  <br/> |<span data-ttu-id="150c4-136">Os clientes devem implementar um processo robusto de gerenciamento de alterações para as atualizações mensais.</span><span class="sxs-lookup"><span data-stu-id="150c4-136">Customers must implement a robust change management process for the monthly updates.</span></span>  <br/> [!CAUTION] <span data-ttu-id="150c4-137">Essa solução requer alterações significativas em andamento.</span><span class="sxs-lookup"><span data-stu-id="150c4-137">This solution requires significant on-going changes.</span></span> <span data-ttu-id="150c4-138">As alterações não implementadas no momento provavelmente resultarão em uma interrupção de serviço.</span><span class="sxs-lookup"><span data-stu-id="150c4-138">Changes not implemented in time will likely result in a service outage.</span></span>   |

<span data-ttu-id="150c4-139">Conectar-se ao Office 365 usando o Azure ExpressRoute é baseado em anúncios de BGP de sub-redes IP específicas que representam redes nas quais os pontos de extremidade do Office 365 estão implantados.</span><span class="sxs-lookup"><span data-stu-id="150c4-139">Connecting to Office 365 using Azure ExpressRoute is based on BGP advertisements of specific IP subnets that represent networks where Office 365 endpoints are deployed.</span></span> <span data-ttu-id="150c4-140">Devido à natureza global do Office 365 e ao número de serviços que compõem o Office 365, os clientes geralmente precisam gerenciar os anúncios que eles aceitam em sua rede.</span><span class="sxs-lookup"><span data-stu-id="150c4-140">Due to the global nature of Office 365 and the number of services that make up Office 365, customers often have a need to manage the advertisements they accept on their network.</span></span> <span data-ttu-id="150c4-141">Se você estiver preocupado com o número de prefixos anunciados no seu ambiente, o recurso [da Comunidade do BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) permite que você filtre os anúncios em um conjunto específico de serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="150c4-141">If you're concerned with number of prefixes advertised into your environment, the [BGP community](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) feature allows you to filter the advertisements to a specific set of Office 365 services.</span></span> <span data-ttu-id="150c4-142">Este recurso agora está em versão prévia.</span><span class="sxs-lookup"><span data-stu-id="150c4-142">This feature is now in preview.</span></span>
  
<span data-ttu-id="150c4-143">Independentemente de como você gerencia os anúncios de rota BGP provenientes da Microsoft, você não terá nenhuma exposição especial para os serviços do Office 365 quando comparado à conexão com o Office 365 através de um único circuito da Internet.</span><span class="sxs-lookup"><span data-stu-id="150c4-143">Regardless of how you manage the BGP route advertisements coming from Microsoft, you won't gain any special exposure to Office 365 services when compared to connecting to Office 365 over an internet circuit alone.</span></span> <span data-ttu-id="150c4-144">A Microsoft mantém os mesmos níveis de segurança, conformidade e desempenho, independentemente do tipo de circuito que um cliente usa para se conectar ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="150c4-144">Microsoft maintains the same security, compliance, and performance levels regardless of the type of circuit a customer uses to connect to Office 365.</span></span>
  
### <a name="security"></a><span data-ttu-id="150c4-145">Segurança</span><span class="sxs-lookup"><span data-stu-id="150c4-145">Security</span></span>

<span data-ttu-id="150c4-146">A Microsoft recomenda que você mantenha seus próprios controles de perímetro de rede e segurança para conexões que vão de e para o emparelhamento público e Microsoft, que inclui conexões de e para os serviços do Office 365.</span><span class="sxs-lookup"><span data-stu-id="150c4-146">Microsoft recommends that you maintain your own network and security perimeter controls for connections going to and from ExpressRoute public and Microsoft peering, which includes connections to and from Office 365 services.</span></span> <span data-ttu-id="150c4-147">Os controles de segurança devem estar em vigor para solicitações de rede que trafegam de saída da sua rede para a rede da Microsoft, bem como de entrada da rede da Microsoft para sua rede.</span><span class="sxs-lookup"><span data-stu-id="150c4-147">Security controls should be in place for network requests that travel outbound from your network to Microsoft's network as well as inbound from Microsoft's network to your network.</span></span>
  
#### <a name="outbound-from-customer-to-microsoft"></a><span data-ttu-id="150c4-148">Saída de cliente para a Microsoft</span><span class="sxs-lookup"><span data-stu-id="150c4-148">Outbound from Customer to Microsoft</span></span>
  
<span data-ttu-id="150c4-149">Quando os computadores se conectam ao Office 365, eles se conectam ao mesmo conjunto de pontos de extremidade, independentemente se a conexão é feita através de um circuito da Internet ou do ExpressRoute.</span><span class="sxs-lookup"><span data-stu-id="150c4-149">When computers connect to Office 365, they connect to the same set of endpoints regardless of whether the connection is made over an internet or ExpressRoute circuit.</span></span> <span data-ttu-id="150c4-150">Independentemente do circuito que está sendo usado, a Microsoft recomenda que você trate os serviços do Office 365 como mais confiáveis do que os destinos genéricos da Internet.</span><span class="sxs-lookup"><span data-stu-id="150c4-150">Regardless of the circuit being used, Microsoft recommends that you treat Office 365 services as more trusted than generic internet destinations.</span></span> <span data-ttu-id="150c4-151">Os controles de segurança de saída devem se concentrar nas portas e nos protocolos para reduzir a exposição e minimizar a manutenção contínua.</span><span class="sxs-lookup"><span data-stu-id="150c4-151">Your outbound security controls should focus on the ports and protocols to reduce exposure and minimize ongoing maintenance.</span></span> <span data-ttu-id="150c4-152">As informações de porta necessárias estão disponíveis no artigo de referência de [pontos de extremidade do Office 365](https://aka.ms/o365endpoints) .</span><span class="sxs-lookup"><span data-stu-id="150c4-152">The required port information is available in the [Office 365 endpoints](https://aka.ms/o365endpoints) reference article.</span></span>
  
<span data-ttu-id="150c4-153">Para controles adicionados, você pode usar a filtragem de nível de FQDN dentro de sua infraestrutura de proxy para restringir ou inspecionar algumas ou todas as solicitações de rede destinadas à Internet ou ao Office 365.</span><span class="sxs-lookup"><span data-stu-id="150c4-153">For added controls, you can use FQDN level filtering within your proxy infrastructure to restrict or inspect some or all network requests destined for the internet or Office 365.</span></span> <span data-ttu-id="150c4-154">Manter a lista de FQDNs conforme os recursos são lançados e as ofertas do Office 365 evoluem requer o gerenciamento de alterações mais robusto e o controle das alterações nos [pontos de extremidade do Office 365](https://aka.ms/o365endpoints)publicados.</span><span class="sxs-lookup"><span data-stu-id="150c4-154">Maintaining the list of FQDNs as features are released and the Office 365 offerings evolve requires more robust change management and tracking of changes to the published [Office 365 endpoints](https://aka.ms/o365endpoints).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="150c4-155">A Microsoft recomenda que você não confie exclusivamente em prefixos de IP para gerenciar a segurança de saída para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="150c4-155">Microsoft recommends you don't rely solely on IP prefixes to manage outbound security to Office 365.</span></span>

|<span data-ttu-id="150c4-156">**Opção**</span><span class="sxs-lookup"><span data-stu-id="150c4-156">**Option**</span></span>|<span data-ttu-id="150c4-157">**Complexidade**</span><span class="sxs-lookup"><span data-stu-id="150c4-157">**Complexity**</span></span>|<span data-ttu-id="150c4-158">**Controle de alterações**</span><span class="sxs-lookup"><span data-stu-id="150c4-158">**Change Control**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="150c4-159">Sem restrições</span><span class="sxs-lookup"><span data-stu-id="150c4-159">No restrictions</span></span>  <br/> |<span data-ttu-id="150c4-160">**Baixo:** O cliente permite acesso de saída irrestrito à Microsoft.</span><span class="sxs-lookup"><span data-stu-id="150c4-160">**Low:** Customer allows unrestricted outbound access to Microsoft.</span></span>  <br/> |<span data-ttu-id="150c4-161">Nenhum</span><span class="sxs-lookup"><span data-stu-id="150c4-161">None</span></span>  <br/> |
|<span data-ttu-id="150c4-162">Restrições de porta</span><span class="sxs-lookup"><span data-stu-id="150c4-162">Port restrictions</span></span>  <br/> |<span data-ttu-id="150c4-163">**Baixo:** O cliente restringe o acesso de saída para a Microsoft pelas portas esperadas.</span><span class="sxs-lookup"><span data-stu-id="150c4-163">**Low:** Customer restricts outbound access to Microsoft by the expected ports.</span></span>  <br/> |<span data-ttu-id="150c4-164">Não frequentes.</span><span class="sxs-lookup"><span data-stu-id="150c4-164">Infrequent.</span></span>  <br/> |
|<span data-ttu-id="150c4-165">Restrições de FQDN</span><span class="sxs-lookup"><span data-stu-id="150c4-165">FQDN restrictions</span></span>  <br/> |<span data-ttu-id="150c4-166">**Alta:** O cliente restringe o acesso de saída para o Office 365 com base nos FQDNs publicados.</span><span class="sxs-lookup"><span data-stu-id="150c4-166">**High:** Customer restricts outbound access to Office 365 based on the published FQDNs.</span></span>  <br/> |<span data-ttu-id="150c4-167">Alterações mensais.</span><span class="sxs-lookup"><span data-stu-id="150c4-167">Monthly changes.</span></span>  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a><span data-ttu-id="150c4-168">Entrada da Microsoft para o cliente</span><span class="sxs-lookup"><span data-stu-id="150c4-168">Inbound from Microsoft to Customer</span></span>
  
<span data-ttu-id="150c4-169">Há vários cenários opcionais que exigem que a Microsoft inicie conexões à sua rede.</span><span class="sxs-lookup"><span data-stu-id="150c4-169">There are several optional scenarios that require Microsoft to initiate connections to your network.</span></span>
  
- <span data-ttu-id="150c4-170">ADFS durante a validação de senha para entrada.</span><span class="sxs-lookup"><span data-stu-id="150c4-170">ADFS during password validation for sign-in.</span></span>

- <span data-ttu-id="150c4-171">[Implantações híbridas do Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="150c4-171">[Exchange Server Hybrid deployments](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).</span></span>

- <span data-ttu-id="150c4-172">Emails de um locatário do Exchange Online para um host local.</span><span class="sxs-lookup"><span data-stu-id="150c4-172">Mail from an Exchange Online tenant to an on-premises host.</span></span>

- <span data-ttu-id="150c4-173">Envio de email do SharePoint Online do SharePoint Online para um host local.</span><span class="sxs-lookup"><span data-stu-id="150c4-173">SharePoint Online Mail send from SharePoint Online to an on-premises host.</span></span>

- <span data-ttu-id="150c4-174">[Pesquisa híbrida federada do SharePoint](https://technet.microsoft.com/library/dn197174.aspx).</span><span class="sxs-lookup"><span data-stu-id="150c4-174">[SharePoint federated hybrid search](https://technet.microsoft.com/library/dn197174.aspx).</span></span>

- <span data-ttu-id="150c4-175">[BCS do SharePoint híbrido](https://technet.microsoft.com/library/dn197239.aspx ).</span><span class="sxs-lookup"><span data-stu-id="150c4-175">[SharePoint hybrid BCS](https://technet.microsoft.com/library/dn197239.aspx ).</span></span>

- <span data-ttu-id="150c4-176">Federação [híbrida do Skype for Business](https://technet.microsoft.com/library/jj205403.aspx) e/ou [Skype for Business](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).</span><span class="sxs-lookup"><span data-stu-id="150c4-176">[Skype for Business hybrid](https://technet.microsoft.com/library/jj205403.aspx) and/or [Skype for Business federation](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).</span></span>

- <span data-ttu-id="150c4-177">[Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).</span><span class="sxs-lookup"><span data-stu-id="150c4-177">[Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).</span></span>

<span data-ttu-id="150c4-178">A Microsoft recomenda que você aceite essas conexões através do seu circuito da Internet, em vez do seu circuito ExpressRoute para reduzir a complexidade.</span><span class="sxs-lookup"><span data-stu-id="150c4-178">Microsoft recommends that you accept these connections over your internet circuit instead of your ExpressRoute circuit to reduce complexity.</span></span> <span data-ttu-id="150c4-179">Se suas necessidades de conformidade ou desempenho determinam que essas conexões de entrada devem ser aceitas em um circuito ExpressRoute, o uso de um firewall ou de um proxy reverso para fazer o escopo das conexões aceitas é recomendado.</span><span class="sxs-lookup"><span data-stu-id="150c4-179">If your compliance or performance needs dictate these inbound connections must be accepted over an ExpressRoute circuit, using a firewall or reverse proxy to scope the accepted connections is recommended.</span></span> <span data-ttu-id="150c4-180">Você pode usar os [pontos de extremidade do Office 365](https://aka.ms/o365endpoints) para calcular os FQDNs e prefixos IP corretos.</span><span class="sxs-lookup"><span data-stu-id="150c4-180">You can use the [Office 365 endpoints](https://aka.ms/o365endpoints) to figure out the right FQDNs and IP prefixes.</span></span>
  
### <a name="compliance"></a><span data-ttu-id="150c4-181">Conformidade</span><span class="sxs-lookup"><span data-stu-id="150c4-181">Compliance</span></span>

<span data-ttu-id="150c4-182">Não confiamos no caminho de roteamento que você usa para qualquer um dos nossos controles de conformidade.</span><span class="sxs-lookup"><span data-stu-id="150c4-182">We don't rely on the routing path you use for any of our compliance controls.</span></span> <span data-ttu-id="150c4-183">Independentemente de você se conectar aos serviços do Office 365 através de um circuito ExpressRoute ou Internet, nossos controles de conformidade não mudarão.</span><span class="sxs-lookup"><span data-stu-id="150c4-183">Regardless of whether you connect to Office 365 services over an ExpressRoute or internet circuit, our compliance controls won't change.</span></span> <span data-ttu-id="150c4-184">Você deve examinar os diferentes níveis de certificação de conformidade e segurança do Office 365 para descobrir a melhor opção para atender às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="150c4-184">You should review the different compliance and security certification levels for Office 365 to figure out the best choice for meeting your organization's needs.</span></span>
  
<span data-ttu-id="150c4-185">Aqui está um link curto que você pode usar para voltar: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)</span><span class="sxs-lookup"><span data-stu-id="150c4-185">Here's a short link you can use to come back: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="150c4-186">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="150c4-186">Related topics</span></span>

[<span data-ttu-id="150c4-187">Redes de distribuição de conteúdo</span><span class="sxs-lookup"><span data-stu-id="150c4-187">Content delivery networks</span></span>](content-delivery-networks.md)
  
[<span data-ttu-id="150c4-188">URLs e intervalos de endereços IP do Office 365</span><span class="sxs-lookup"><span data-stu-id="150c4-188">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="150c4-189">Gerenciar pontos de extremidade do Office 365</span><span class="sxs-lookup"><span data-stu-id="150c4-189">Managing Office 365 endpoints</span></span>](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[<span data-ttu-id="150c4-190">Treinamento do Azure ExpressRoute para Office 365</span><span class="sxs-lookup"><span data-stu-id="150c4-190">Azure ExpressRoute for Office 365 Training</span></span>](https://channel9.msdn.com/series/aer)