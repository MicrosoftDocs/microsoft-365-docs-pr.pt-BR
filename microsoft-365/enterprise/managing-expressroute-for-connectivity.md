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
description: Saiba como gerenciar o ExpressRoute para Office 365, incluindo áreas comuns para configurar como filtragem de prefixo, segurança e conformidade.
ms.openlocfilehash: e8de0763df7d592bc41802b1ead48df06891e6dc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916663"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Gerenciar o ExpressRoute para conectividade do Office 365

O ExpressRoute para Office 365 oferece um caminho de roteamento alternativo para alcançar muitos serviços Office 365 sem precisar de todo o tráfego para sair da Internet. Embora a conexão com a Internet Office 365 ainda seja necessária, as rotas específicas que a Microsoft anuncia por meio do BGP para sua rede fazem o circuito ExpressRoute direto preferir, a menos que haja outras configurações em sua rede. As três áreas comuns que você pode configurar para gerenciar esse roteamento incluem filtragem de prefixo, segurança e conformidade.
  
> [!NOTE]
> A Microsoft alterou como o domínio de roteamento do Microsoft Peering é revisado para o Azure ExpressRoute. A partir de 31 de julho de 2017, todos os clientes do Azure ExpressRoute podem habilitar o Microsoft Peering diretamente do console administrativo do Azure ou por meio do PowerShell. Depois de habilitar o Microsoft Peering, qualquer cliente pode criar filtros de rota para receber anúncios de rota BGP para aplicativos de Envolvimento do Cliente do Dynamics 365 (anteriormente conhecido como CRM Online). Os clientes que precisam do Azure ExpressRoute para Office 365 devem obter revisão da Microsoft antes de criar filtros de rota para Office 365. Entre em contato com sua equipe de Conta da Microsoft para saber como solicitar uma revisão para habilitar Office 365 ExpressRoute. Assinaturas não autorizadas que tentam criar filtros de rota para Office 365 receberão uma [mensagem de erro](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Filtragem de prefixo

A Microsoft recomenda que os clientes aceitem todas as rotas BGP conforme anunciado pela Microsoft, as rotas fornecidas passam por um rigoroso processo de revisão e validação removendo quaisquer benefícios para um exame de análise adicionado. O ExpressRoute oferece de forma nativa os controles recomendados, como propriedade, integridade e escala de prefixo IP , sem filtragem de rota de entrada no lado do cliente.
  
Se você exigir validação adicional da propriedade de rota no paramento público ExpressRoute, poderá verificar as rotas anunciadas na lista de todos os prefixos IP IPv4 e IPv6 que representam os intervalos ip públicos da [Microsoft.](https://www.microsoft.com/download/details.aspx?id=53602) Esses intervalos abrangem o espaço de endereço completo da Microsoft e mudam com pouca freqüência, fornecendo um conjunto confiável de intervalos para filtrar que também fornece proteção adicional aos clientes que estão preocupados com o vazamento de rotas não pertencentes à Microsoft para seu ambiente. Caso haja uma alteração, ela será feita no dia 1º do mês  e o número da versão na seção de detalhes da página será alterado sempre que o arquivo for atualizado.
  
Há vários motivos para evitar o uso das [URLs](./urls-and-ip-address-ranges.md) de Office 365 e intervalos de endereços IP para gerar listas de filtros de prefixo. Incluindo o seguinte:
  
- Os Office 365 IP passam por muitas alterações com frequência.

- As Office 365 URLs e intervalos de endereços IP foram projetados para gerenciar listas de firewall e infraestrutura de Proxy, não para roteamento.

- As Office 365 URLs e intervalos de endereços IP não abrangem outras serviços Microsoft que podem estar no escopo de suas conexões ExpressRoute.

|**Opção**|**Complexidade**|**Alterar Controle**|
|:-----|:-----|:-----|
|Aceitar todas as rotas da Microsoft  <br/> |**Baixo:** O cliente depende dos controles da Microsoft para garantir que todas as rotas sejam de propriedade adequada.  <br/> |Nenhum  <br/> |
|Filtrar super-redes de propriedade da Microsoft  <br/> |**Médio:** O cliente implementa listas de filtros de prefixo resumidos para permitir apenas rotas de propriedade da Microsoft.  <br/> |Os clientes devem garantir que as atualizações pouco frequentes sejam refletidas em filtros de rota.  <br/> |
|Filtrar Office 365 intervalos IP  <br/> [!CAUTION] Not-Recommended |**Alto:** O cliente filtra rotas com base em prefixos IP Office 365 definidos.  <br/> |Os clientes devem implementar um processo robusto de gerenciamento de alterações para as atualizações mensais.  <br/> [!CAUTION] Essa solução requer alterações significativas em uso. As alterações não implementadas no tempo provavelmente resultarão em uma paralisação de serviço.   |

Conectar-se ao Office 365 usando o Azure ExpressRoute baseia-se em anúncios BGP de sub-redes IP específicas que representam redes nas quais Office 365 pontos de extremidade são implantados. Devido à natureza global da Office 365 e ao número de serviços que com eles Office 365, os clientes geralmente precisam gerenciar os anúncios aceitos em sua rede. Se você estiver preocupado com o número de prefixos anunciados em seu ambiente, o recurso da comunidade [BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) permite filtrar os anúncios para um conjunto específico de serviços Office 365. Esse recurso agora está em visualização.
  
Independentemente de como você gerencia os anúncios de rota BGP provenientes da Microsoft, você não obterá nenhuma exposição especial aos serviços Office 365 quando comparado à conexão com o Office 365 em um circuito da Internet sozinho. A Microsoft mantém os mesmos níveis de segurança, conformidade e desempenho, independentemente do tipo de circuito que um cliente usa para se conectar ao Office 365.
  
### <a name="security"></a>Segurança

A Microsoft recomenda que você mantenha seus próprios controles de perímetro de rede e segurança para conexões que vão e para o público expressRoute e o peering da Microsoft, que inclui conexões de e para Office 365 serviços. Os controles de segurança devem estar no local para solicitações de rede que viajam de saída de sua rede para a rede da Microsoft, bem como a entrada da rede da Microsoft para sua rede.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Saída do Cliente para a Microsoft
  
Quando os computadores se conectam Office 365, eles se conectam ao mesmo conjunto de pontos de extremidade, independentemente de a conexão ser feita por meio de um circuito de Internet ou ExpressRoute. Independentemente do circuito que está sendo usado, a Microsoft recomenda que você trate os serviços Office 365 como mais confiáveis do que destinos genéricos da Internet. Seus controles de segurança de saída devem se concentrar nas portas e protocolos para reduzir a exposição e minimizar a manutenção contínua. As informações de porta necessárias estão disponíveis no artigo de referência [Office 365 pontos](./urls-and-ip-address-ranges.md) de extremidade.
  
Para controles adicionados, você pode usar a filtragem de nível FQDN em sua infraestrutura proxy para restringir ou inspecionar algumas ou todas as solicitações de rede destinadas à Internet ou Office 365. A manutenção da lista de FQDNs à medida que os recursos são lançados e as ofertas Office 365 evoluem exigem um gerenciamento de alterações mais robusto e o controle de alterações nos pontos de extremidade Office 365 [publicados.](./urls-and-ip-address-ranges.md)
  
> [!CAUTION]
> A Microsoft recomenda que você não confie apenas em prefixos IP para gerenciar a segurança de saída para Office 365.

|**Opção**|**Complexidade**|**Alterar Controle**|
|:-----|:-----|:-----|
|Sem restrições  <br/> |**Baixo:** O cliente permite acesso de saída irrestrito à Microsoft.  <br/> |Nenhum  <br/> |
|Restrições de porta  <br/> |**Baixo:** O cliente restringe o acesso de saída à Microsoft pelas portas esperadas.  <br/> |Pouco frequente.  <br/> |
|Restrições de FQDN  <br/> |**Alto:** O cliente restringe o acesso de saída Office 365 com base nos FQDNs publicados.  <br/> |Alterações mensais.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Entrada da Microsoft para o Cliente
  
Há vários cenários opcionais que exigem que a Microsoft inicie conexões com sua rede.
  
- ADFS durante a validação de senha para entrar.

- [Exchange Server implantações híbridas.](/exchange/exchange-hybrid)

- Email de um Exchange Online locatário para um host local.

- SharePoint Envio de email online do SharePoint Online para um host local.

- [SharePoint pesquisa híbrida federada.](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)

- [SharePoint BCS híbrido.](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)

- [Skype for Business federação](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) híbrida [e/ou Skype for Business.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

- [Skype for Business Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

A Microsoft recomenda que você aceite essas conexões em seu circuito da Internet em vez de seu circuito ExpressRoute para reduzir a complexidade. Se suas necessidades de conformidade ou desempenho ditar essas conexões de entrada devem ser aceitas em um circuito ExpressRoute, é recomendável usar um firewall ou proxy reverso para escopo das conexões aceitas. Você pode usar os [Office 365 de](./urls-and-ip-address-ranges.md) extremidade para descobrir os FQDNs e prefixos IP corretos.
  
### <a name="compliance"></a>Conformidade

Não dependemos do caminho de roteamento que você usa para qualquer um de nossos controles de conformidade. Independentemente de você se conectar Office 365 serviços por meio de um expressRoute ou um circuito da Internet, nossos controles de conformidade não mudarão. Você deve analisar os diferentes níveis de certificação de conformidade e segurança Office 365 para descobrir a melhor opção para atender às necessidades da sua organização.
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>Tópicos relacionados

[Redes de distribuição de conteúdo](content-delivery-networks.md)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute para treinamento Office 365 treinamento](https://channel9.msdn.com/series/aer)