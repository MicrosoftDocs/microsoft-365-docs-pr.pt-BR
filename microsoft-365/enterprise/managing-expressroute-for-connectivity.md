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
# <a name="managing-expressroute-for-office-365-connectivity"></a>Gerenciar o ExpressRoute para conectividade do Office 365

O ExpressRoute para Office 365 oferece um caminho de roteamento alternativo para alcançar muitos serviços do Office 365 sem precisar de todo o tráfego para saída na Internet. Embora a conexão com a Internet com o Office 365 ainda seja necessária, as rotas específicas que a Microsoft anuncia por meio do BGP para a sua rede tornam o circuito direto do ExpressRoute preferencial, a menos que haja outras configurações na sua rede. As três áreas comuns que você pode querer configurar para gerenciar esse roteamento incluem filtragem de prefixo, segurança e conformidade.
  
> [!NOTE]
> A Microsoft alterou o modo como o domínio de roteamento de emparelhamento da Microsoft é revisado para o Azure ExpressRoute. A partir de 31 de julho de 2017, todos os clientes do Azure ExpressRoute podem habilitar o emparelhamento da Microsoft diretamente do console administrativo do Azure ou via PowerShell. Depois de habilitar o emparelhamento da Microsoft, qualquer cliente pode criar filtros de roteamento para receber anúncios de rota de BGP para aplicativos de contrato de cliente do Dynamics 365 (anteriormente conhecido como CRM Online). Os clientes que precisam do Azure ExpressRoute para Office 365 devem obter análise da Microsoft antes de poderem criar filtros de rota para o Office 365. Entre em contato com a equipe de conta da Microsoft para saber mais sobre como solicitar uma revisão para habilitar o Office 365 ExpressRoute. Assinaturas não autorizadas tentando criar filtros de roteamento para o Office 365 receberão uma [mensagem de erro](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Filtragem de prefixo

A Microsoft recomenda que os clientes aceitem todas as rotas de BGP, como anunciados na Microsoft, as rotas fornecidas passam por um processo rigoroso de revisão e validação, removendo qualquer benefício para a análise adicional. O ExpressRoute nativamente oferece os controles recomendados, como propriedade de prefixo IP, integridade e escala, sem filtragem de roteamento de entrada no lado do cliente.
  
Se você precisar de validação adicional de propriedade de rota no emparelhamento público do ExpressRoute, poderá verificar as rotas anunciadas em relação à lista de todos os prefixos IP IPv4 e IPv6 que representam os [intervalos de IP públicos da Microsoft](https://www.microsoft.com/download/details.aspx?id=53602). Esses intervalos abrangem o espaço de endereço da Microsoft completo e mudam com pouca frequência, fornecendo um conjunto confiável de intervalos para filtrar, além de oferecer proteção adicional aos clientes que se preocupam com rotas pertencentes à Microsoft que estão vazando em seu ambiente. No caso de haver uma alteração, ela será feita no primeiro dia do mês e o número da versão na seção **detalhes** da página será alterado sempre que o arquivo for atualizado.
  
Há vários motivos para evitar o uso das [URLs e intervalos de endereços IP do Office 365](https://aka.ms/o365endpoints) para gerar listas de filtros de prefixo. Incluindo o seguinte:
  
- Os prefixos IP do Office 365 passam por muitas alterações com frequência.

- As URLs e os intervalos de endereços IP do Office 365 foram projetados para o gerenciamento de listas de permissões de firewall e infraestrutura de proxy, e não ao roteamento.

- As URLs e os intervalos de endereços IP do Office 365 não abrangem outros serviços da Microsoft que podem estar em escopo para suas conexões do ExpressRoute.

|**Opção**|**Complexidade**|**Controle de alterações**|
|:-----|:-----|:-----|
|Aceitar todas as rotas da Microsoft  <br/> |**Baixo:** O cliente depende dos controles da Microsoft para garantir que todas as rotas estejam devidamente de propriedade.  <br/> |Nenhum  <br/> |
|Filtrar sub-redes de propriedade da Microsoft  <br/> |**Médio:** O cliente implementa listas de filtro de prefixo resumido para permitir somente rotas de propriedade da Microsoft.  <br/> |Os clientes devem garantir que as atualizações não frequentes sejam refletidas nos filtros de rota.  <br/> |
|Filtrar intervalos IP do Office 365  <br/> [!CAUTION] Não recomendado |**Alta:** O cliente filtra rotas com base em prefixos IP do Office 365 definidos.  <br/> |Os clientes devem implementar um processo robusto de gerenciamento de alterações para as atualizações mensais.  <br/> [!CAUTION] Essa solução requer alterações significativas em andamento. As alterações não implementadas no momento provavelmente resultarão em uma interrupção de serviço.   |

Conectar-se ao Office 365 usando o Azure ExpressRoute é baseado em anúncios de BGP de sub-redes IP específicas que representam redes nas quais os pontos de extremidade do Office 365 estão implantados. Devido à natureza global do Office 365 e ao número de serviços que compõem o Office 365, os clientes geralmente precisam gerenciar os anúncios que eles aceitam em sua rede. Se você estiver preocupado com o número de prefixos anunciados no seu ambiente, o recurso [da Comunidade do BGP](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) permite que você filtre os anúncios em um conjunto específico de serviços do Office 365. Este recurso agora está em versão prévia.
  
Independentemente de como você gerencia os anúncios de rota BGP provenientes da Microsoft, você não terá nenhuma exposição especial para os serviços do Office 365 quando comparado à conexão com o Office 365 através de um único circuito da Internet. A Microsoft mantém os mesmos níveis de segurança, conformidade e desempenho, independentemente do tipo de circuito que um cliente usa para se conectar ao Office 365.
  
### <a name="security"></a>Segurança

A Microsoft recomenda que você mantenha seus próprios controles de perímetro de rede e segurança para conexões que vão de e para o emparelhamento público e Microsoft, que inclui conexões de e para os serviços do Office 365. Os controles de segurança devem estar em vigor para solicitações de rede que trafegam de saída da sua rede para a rede da Microsoft, bem como de entrada da rede da Microsoft para sua rede.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Saída de cliente para a Microsoft
  
Quando os computadores se conectam ao Office 365, eles se conectam ao mesmo conjunto de pontos de extremidade, independentemente se a conexão é feita através de um circuito da Internet ou do ExpressRoute. Independentemente do circuito que está sendo usado, a Microsoft recomenda que você trate os serviços do Office 365 como mais confiáveis do que os destinos genéricos da Internet. Os controles de segurança de saída devem se concentrar nas portas e nos protocolos para reduzir a exposição e minimizar a manutenção contínua. As informações de porta necessárias estão disponíveis no artigo de referência de [pontos de extremidade do Office 365](https://aka.ms/o365endpoints) .
  
Para controles adicionados, você pode usar a filtragem de nível de FQDN dentro de sua infraestrutura de proxy para restringir ou inspecionar algumas ou todas as solicitações de rede destinadas à Internet ou ao Office 365. Manter a lista de FQDNs conforme os recursos são lançados e as ofertas do Office 365 evoluem requer o gerenciamento de alterações mais robusto e o controle das alterações nos [pontos de extremidade do Office 365](https://aka.ms/o365endpoints)publicados.
  
> [!CAUTION]
> A Microsoft recomenda que você não confie exclusivamente em prefixos de IP para gerenciar a segurança de saída para o Office 365.

|**Opção**|**Complexidade**|**Controle de alterações**|
|:-----|:-----|:-----|
|Sem restrições  <br/> |**Baixo:** O cliente permite acesso de saída irrestrito à Microsoft.  <br/> |Nenhum  <br/> |
|Restrições de porta  <br/> |**Baixo:** O cliente restringe o acesso de saída para a Microsoft pelas portas esperadas.  <br/> |Não frequentes.  <br/> |
|Restrições de FQDN  <br/> |**Alta:** O cliente restringe o acesso de saída para o Office 365 com base nos FQDNs publicados.  <br/> |Alterações mensais.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Entrada da Microsoft para o cliente
  
Há vários cenários opcionais que exigem que a Microsoft inicie conexões à sua rede.
  
- ADFS durante a validação de senha para entrada.

- [Implantações híbridas do Exchange Server](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- Emails de um locatário do Exchange Online para um host local.

- Envio de email do SharePoint Online do SharePoint Online para um host local.

- [Pesquisa híbrida federada do SharePoint](https://technet.microsoft.com/library/dn197174.aspx).

- [BCS do SharePoint híbrido](https://technet.microsoft.com/library/dn197239.aspx ).

- Federação [híbrida do Skype for Business](https://technet.microsoft.com/library/jj205403.aspx) e/ou [Skype for Business](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

A Microsoft recomenda que você aceite essas conexões através do seu circuito da Internet, em vez do seu circuito ExpressRoute para reduzir a complexidade. Se suas necessidades de conformidade ou desempenho determinam que essas conexões de entrada devem ser aceitas em um circuito ExpressRoute, o uso de um firewall ou de um proxy reverso para fazer o escopo das conexões aceitas é recomendado. Você pode usar os [pontos de extremidade do Office 365](https://aka.ms/o365endpoints) para calcular os FQDNs e prefixos IP corretos.
  
### <a name="compliance"></a>Conformidade

Não confiamos no caminho de roteamento que você usa para qualquer um dos nossos controles de conformidade. Independentemente de você se conectar aos serviços do Office 365 através de um circuito ExpressRoute ou Internet, nossos controles de conformidade não mudarão. Você deve examinar os diferentes níveis de certificação de conformidade e segurança do Office 365 para descobrir a melhor opção para atender às necessidades da sua organização.
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Tópicos relacionados

[Redes de distribuição de conteúdo](content-delivery-networks.md)
  
[URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Treinamento do Azure ExpressRoute para Office 365](https://channel9.msdn.com/series/aer)
