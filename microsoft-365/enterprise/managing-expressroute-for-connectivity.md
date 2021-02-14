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
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687521"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Gerenciar o ExpressRoute para conectividade do Office 365

O ExpressRoute para Office 365 oferece um caminho de roteamento alternativo para alcançar muitos serviços do Office 365 sem precisar de todo o tráfego para sair da Internet. Embora a conexão com a Internet com o Office 365 ainda seja necessária, as rotas específicas que a Microsoft anuncia por meio do BGP para sua rede fazem com que o circuito expressRoute direto seja preferencial, a menos que haja outras configurações em sua rede. As três áreas comuns que você pode configurar para gerenciar esse roteamento incluem filtragem de prefixo, segurança e conformidade.
  
> [!NOTE]
> A Microsoft alterou a forma como o domínio de roteamento do Microsoft Peering é revisado para o Azure ExpressRoute. A partir de 31 de julho de 2017, todos os clientes do Azure ExpressRoute podem habilitar o Microsoft Peering diretamente no console administrativo do Azure ou por meio do PowerShell. Depois de ativar o Microsoft Peering, qualquer cliente pode criar filtros de rota para receber anúncios de rota BGP para aplicativos de Customer Engagement do Dynamics 365 (anteriormente conhecido como CRM Online). Os clientes que precisam do Azure ExpressRoute para o Office 365 devem obter opinião da Microsoft antes de criar filtros de rota para o Office 365. Entre em contato com sua equipe de Conta da Microsoft para saber como solicitar uma revisão para habilitar o Office 365 ExpressRoute. Assinaturas não autorizadas que tentam criar filtros de rota para o Office 365 receberão uma mensagem [de erro](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Filtragem de prefixo

A Microsoft recomenda que os clientes aceitem todas as rotas BGP conforme anunciado pela Microsoft. As rotas fornecidas passam por um processo rigoroso de revisão e validação, removendo todos os benefícios para a apuração adicionada. O ExpressRoute oferece na verdade os controles recomendados, como propriedade, integridade e escala do prefixo IP, sem filtragem de rota de entrada no lado do cliente.
  
Se você precisar de validação adicional da propriedade da rota no paring público do ExpressRoute, poderá verificar as rotas anunciadas em relação à lista de todos os prefixos IP IPv4 e IPv6 que representam os intervalos de IP públicos da [Microsoft.](https://www.microsoft.com/download/details.aspx?id=53602) Esses intervalos abrangem todo o espaço de endereço da Microsoft e mudam com pouca freqüência, fornecendo um conjunto confiável de intervalos para filtrar, o que também oferece proteção adicional aos clientes que estão preocupado com o vazamento de rotas que não pertencem à Microsoft em seu ambiente. Caso haja uma alteração, ela será feita no dia 1º do mês, e o número da versão na seção de detalhes da página mudará toda vez que o arquivo for atualizado. 
  
Há vários motivos para evitar o uso das URLs e intervalos de endereços IP do [Office 365](https://aka.ms/o365endpoints) para gerar listas de filtro de prefixo. Incluindo o seguinte:
  
- Os prefixos de IP do Office 365 passam por muitas alterações com frequência.

- As URLs e intervalos de endereços IP do Office 365 foram projetados para gerenciar listas de firewalls e infraestrutura de proxy, não roteamento.

- As URLs e intervalos de endereços IP do Office 365 não abrangem outros serviços microsoft que podem estar no escopo de suas conexões expressRoute.

|**Opção**|**Complexidade**|**Controle de alteração**|
|:-----|:-----|:-----|
|Aceitar todas as rotas da Microsoft  <br/> |**Baixo:** O cliente depende dos controles da Microsoft para garantir que todas as rotas sejam de propriedade adequada.  <br/> |Nenhum  <br/> |
|Filtrar super-redes de propriedade da Microsoft  <br/> |**Médio:** O cliente implementa listas resumidas de filtro de prefixo para permitir apenas rotas de propriedade da Microsoft.  <br/> |Os clientes devem garantir que as atualizações não frequentes sejam refletidas nos filtros de rota.  <br/> |
|Filtrar intervalos de IP do Office 365  <br/> [!CAUTION] Not-Recommended |**Alta:** Os filtros de clientes filtram rotas com base em prefixos IP definidos do Office 365.  <br/> |Os clientes devem implementar um processo robusto de gerenciamento de alterações para as atualizações mensais.  <br/> [!CAUTION] Essa solução requer alterações significativas em diante. As alterações não implementadas no tempo provavelmente resultarão em uma paralisação de serviço.   |

Conectar-se ao Office 365 usando o Azure ExpressRoute é baseado em anúncios BGP de sub-redes IP específicas que representam redes nas quais os pontos de extremidade do Office 365 são implantados. Devido à natureza global do Office 365 e ao número de serviços que com o Office 365, os clientes geralmente precisam gerenciar os anúncios que aceitam em sua rede. Se você estiver preocupado com o número de prefixos anunciados em seu ambiente, o recurso da comunidade [BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) permite filtrar os anúncios para um conjunto específico de serviços do Office 365. Esse recurso agora está em visualização.
  
Independentemente de como você gerencia os anúncios de rota BGP provenientes da Microsoft, você não obterá nenhuma exposição especial aos serviços do Office 365 em comparação à conexão com o Office 365 por meio de um circuito de Internet sozinho. A Microsoft mantém os mesmos níveis de segurança, conformidade e desempenho, independentemente do tipo de circuito que um cliente usa para se conectar ao Office 365.
  
### <a name="security"></a>Segurança

A Microsoft recomenda que você mantenha seus próprios controles de perímetro de rede e segurança para conexões que vão e são do expressRoute público e do peering da Microsoft, que inclui conexões de e para serviços do Office 365. Os controles de segurança devem estar em lugar de solicitações de rede que viajam de saída da rede para a rede da Microsoft, bem como a entrada da rede da Microsoft para sua rede.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Saída do cliente para a Microsoft
  
Quando os computadores se conectam ao Office 365, eles se conectam ao mesmo conjunto de pontos de extremidade, independentemente de a conexão ser feita por meio de um circuito da Internet ou do ExpressRoute. Independentemente do circuito que está sendo usado, a Microsoft recomenda que você trate os serviços do Office 365 como mais confiáveis do que destinos genéricos da Internet. Seus controles de segurança de saída devem se concentrar nas portas e protocolos para reduzir a exposição e minimizar a manutenção contínua. As informações de porta necessárias estão disponíveis no artigo de referência de pontos de extremidade do [Office 365.](https://aka.ms/o365endpoints)
  
Para controles adicionados, você pode usar a filtragem de nível de FQDN em sua infraestrutura de proxy para restringir ou inspecionar algumas ou todas as solicitações de rede destinadas à Internet ou ao Office 365. Manter a lista de FQDNs à medida que os recursos são lançados e as ofertas do Office 365 evoluem requer um gerenciamento de alterações mais robusto e controle de alterações nos pontos de extremidade publicados do [Office 365.](https://aka.ms/o365endpoints)
  
> [!CAUTION]
> A Microsoft recomenda que você não confie apenas em prefixos IP para gerenciar a segurança de saída para o Office 365.

|**Opção**|**Complexidade**|**Controle de alteração**|
|:-----|:-----|:-----|
|Sem restrições  <br/> |**Baixo:** O cliente permite acesso de saída irrestrito à Microsoft.  <br/> |Nenhum  <br/> |
|Restrições de porta  <br/> |**Baixo:** O cliente restringe o acesso de saída à Microsoft pelas portas esperadas.  <br/> |Não frequente.  <br/> |
|Restrições de FQDN  <br/> |**Alta:** O cliente restringe o acesso de saída ao Office 365 com base nos FQDNs publicados.  <br/> |Alterações mensais.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Entrada da Microsoft para o Cliente
  
Há vários cenários opcionais que exigem que a Microsoft inicie conexões com sua rede.
  
- ADFS durante a validação de senha para entrar.

- [Implantações híbridas do Exchange Server.](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx)

- Email de um locatário do Exchange Online para um host local.

- SharePoint Online Mail send from SharePoint Online to an on-premises host.

- [Pesquisa híbrida federada do SharePoint.](https://technet.microsoft.com/library/dn197174.aspx)

- [BCS híbrido do SharePoint.](https://technet.microsoft.com/library/dn197239.aspx )

- [Federação híbrida](https://technet.microsoft.com/library/jj205403.aspx) do Skype for Business e/ou [Skype for Business.](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx)

- [Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

A Microsoft recomenda que você aceite essas conexões pelo circuito de Internet em vez do circuito expressRoute para reduzir a complexidade. Se suas necessidades de conformidade ou desempenho determinam que essas conexões de entrada devem ser aceitas em um circuito expressRoute, é recomendável usar um firewall ou proxy reverso para escopo das conexões aceitas. Você pode usar os pontos de extremidade do [Office 365](https://aka.ms/o365endpoints) para descobrir os FQDNs e prefixos IP corretos.
  
### <a name="compliance"></a>Conformidade

Não dependemos do caminho de roteamento que você usa para qualquer um de nossos controles de conformidade. Independentemente de você se conectar aos serviços do Office 365 por meio de um circuito do ExpressRoute ou da Internet, nossos controles de conformidade não mudarão. Você deve analisar os diferentes níveis de certificação de conformidade e segurança do Office 365 para descobrir a melhor opção para atender às necessidades da sua organização.
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Tópicos relacionados

[Redes de distribuição de conteúdo](content-delivery-networks.md)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Azure ExpressRoute para Treinamento do Office 365](https://channel9.msdn.com/series/aer)
