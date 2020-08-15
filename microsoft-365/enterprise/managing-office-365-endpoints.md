---
title: Gerenciar pontos de extremidade do Office 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 1/24/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: Saiba como gerenciar os pontos de extremidade do Office 365 para que eles funcionem com a arquitetura de rede da organização de sua empresa.
ms.openlocfilehash: 1c1e76ae6f6ca2c034258c5ba06e3efefd51d04c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687058"
---
# <a name="managing-office-365-endpoints"></a>Gerenciar pontos de extremidade do Office 365

A maioria das organizações corporativas que possuem vários locais de escritório e uma WAN de conexão precisará de configuração para a conectividade de rede do Office 365. Você pode otimizar a rede enviando solicitações de rede confiáveis do Office 365 diretamente por meio do firewall, ignorando toda a inspeção de nível de pacote adicional ou o processamento. Isso reduz a latência e os seus requisitos de capacidade de perímetro. Identificar o tráfego de rede do Office 365 é o primeiro passo para fornecer o desempenho ideal para seus usuários. Para obter mais informações sobre a conectividade de rede do Office 365, confira [Princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md).

A Microsoft recomenda que você acesse os pontos de extremidade de rede do Office 365 e as alterações neles usando a [URL do serviço Web e o endereço IP do Office 365](microsoft-365-ip-web-service.md).

Independentemente de como você gerencia um tráfego de rede vital do Office 365, o Office 365 requer conectividade com a Internet. Outros pontos de extremidade de rede onde a conectividade é necessária são listados em [Pontos de extremidade adicionais não incluídos na URL do serviço Web e o endereço IP do Office 365](additional-office365-ip-addresses-and-urls.md).

A maneira como você usa os pontos de extremidade de rede do Office 365 dependerá da arquitetura de rede de sua empresa. Este artigo descreve várias maneiras pelas quais as arquiteturas de rede corporativas podem se integrar usando os endereços IP e URLs do Office 365. A maneira mais fácil para escolher em quais solicitações de rede confiar é usar dispositivos SDWAN que ofereçam suporte à configuração automatizada do Office 365 em cada um dos seus locais de escritório.

## <a name="sdwan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SDWAN para o acesso à filial local do tráfego de rede vital do Office 365

Em cada filial do escritório, você pode fornecer um dispositivo SDWAN configurado para direcionar o tráfego do Office 365 otimizar a categoria de pontos de extremidade, ou otimizar e permitir categorias diretamente na rede da Microsoft. Outro tráfego de rede, incluindo o tráfego no local do datacenter, o tráfego de sites gerais da Internet e o tráfego para os pontos de extremidade da categoria padrão do Office 365, são enviados para outro local onde você tem um perímetro de rede mais substancial.

A Microsoft está trabalhando com provedores de SDWAN para habilitar a configuração automática. Para saber mais, confira [Programa de Parceiros de Redes do Office 365](microsoft-365-networking-partner-program.md).

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Use um arquivo PAC para o roteamento direto do tráfego vital do Office 365

Use arquivos PAC ou WPAD para gerenciar solicitações de rede associadas ao Office 365 mas que não tenham um endereço IP fornecido. Normalmente, solicitações de rede que são enviadas por meio de um dispositivo de proxy ou perímetro aumentam a latência. Embora a Interrupção e Inspeção de SSL crie a maior latência, outros serviços, como a autenticação de proxy e a pesquisa de reputação, podem causar um desempenho e uma experiência de usuário ruins. Além disso, esses dispositivos de perímetro de rede precisam de capacidade suficiente para processar todas as solicitações de conexão de rede. É recomendável ignorar seus dispositivos de inspeção ou proxy para solicitações de rede diretas do Office 365.
  
[PowerShell Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) é um script do PowerShell que lê os pontos de extremidade de rede mais recentes da URL do serviço Web e o endereço IP do Office 365 e a cria uma amostra de um arquivo PAC. Você pode modificar o script para que ele seja integrado ao gerenciamento de arquivos de PAC existente.

![Conectando-se ao Office 365 por meio de proxies e firewalls.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Figura 1: perímetro de rede corporativa simples**

O arquivo PAC é implantado em navegadores da Web, no ponto 1, na Figura 1. Ao usar um arquivo PAC para o acesso direto ao tráfego de rede vital do Office 365, você também precisa permitir a conectividade para os endereços IP por trás dessas URLs no firewall de perímetro de rede. Isso é feito buscando os endereços IP das mesmas categorias de ponto de extremidade do Office 365 conforme especificado no arquivo PAC e criando ACLs de firewall baseadas nesses endereços. O firewall é o ponto 3 na Figura 1.

Se você optar por apenas direcionar o roteamento direto para os pontos de extremidade da categoria Otimizar, qualquer ponto de extremidade da categoria Permitir que for enviado para o servidor proxy deverão estar listados no servidor proxy para ignorar um processamento mais profundo. Por exemplo, Interrupção e Inspeção de SSL e autenticação de proxy são incompatíveis com os pontos de extremidade da categoria Otimizar e Permitir. O servidor proxy é o ponto 2 na Figura 1.

A configuração comum é permitir sem processar todo o tráfego de saída do servidor proxy para os endereços IP de destino do tráfego de rede do Office 365 que atinge o servidor proxy. Para saber mais sobre problemas com a Interrupção e Inspeção de SSL, confira [usando dispositivos de rede de terceiros ou soluções no tráfego do Office 365](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

Há dois tipos de arquivos PAC que o script Get-PacFile vai gerar.

| Tipo | Descrição |
|:-----|:-----|
|**1** <br/> |Enviar Otimizar o tráfego de ponto de extremidade direto e todo o conteúdo restante para o servidor proxy. <br/> |
|**2** <br/> |Enviar Otimizar e Permitir o tráfego de ponto de extremidade direto e todo o conteúdo restante para o servidor proxy. Esse tipo também pode ser usado para enviar todo o ExpressRoute com suporte para o tráfego do Office 365 a segmentos de rede do ExpressRoute e todo o conteúdo restante para o servidor proxy. <br/> |

Veja um exemplo simples de como chamar o script do PowerShell:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

Há vários parâmetros que você pode passar para o script:

| Parâmetro | Descrição |
|:-----|:-----|
|**ClientRequestId** <br/> |Isso é obrigatório e é uma GUID passada para o serviço Web que representa o computador cliente que faz a chamada. <br/> |
|**Instance** <br/> |A instância de serviço do Office 365 que usa o padrão mundial. Também passada para o serviço Web. <br/> |
|**TenantName** <br/> |Seu nome de locatário do Office 365. Transmitido para o serviço Web e usado como um parâmetro substituível em algumas URLs do Office 365. <br/> |
|**Type** <br/> |O tipo de Arquivo PAC de proxy que você deseja gerar. <br/> |

Veja outro exemplo de como chamar o script do PowerShell com parâmetros adicionais:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>O servidor proxy ignora o processamento do tráfego de rede do Office 365

Quando os arquivos PAC não são usados para tráfego de saída direto, você ainda deve ignorar o processamento no perímetro de rede configurando o servidor proxy. Alguns fornecedores de servidor proxy habilitaram a configuração automática deste, conforme descrito no [Programa de Parceiros de Redes do Office 365](microsoft-365-networking-partner-program.md).

Se você estiver fazendo isso manualmente, será necessário obter os dados do ponto de extremidade Otimizar e Permitir da URL do serviço Web e o endereço IP do Office 365 e configurar o servidor proxy para ignorar o processamento. É importante evitar a Interrupção e Inspeção de SSL e autenticação de proxy para os pontos de extremidade da categoria Otimizar e Permitir.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Alterar o gerenciamento de endereços IP e URLs do Office 365

Além de selecionar uma configuração adequada para seu perímetro de rede, é fundamental que você adote um processo de gerenciamento de alterações para os pontos de extremidade do Office 365. Esses pontos de extremidade mudam regularmente, e, caso não gerencie as alterações, você pode acabar com usuários bloqueados ou com baixo desempenho após um novo endereço IP ou URL ser adicionado.

As alterações nos endereços IP e URLs do Office 365 geralmente são publicadas no último dia de cada mês. Às vezes, uma mudança será publicada fora desse cronograma devido a requisitos operacionais, de suporte, ou de segurança.

Quando uma alteração é publicada e exige que você aja devido a um endereço IP ou URL ter sido adicionado, você deve esperar receber um aviso de 30 dias desde a hora em que publicamos a alteração até que haja um serviço do Office 365 no ponto de extremidade. Embora visamos esse período de notificação, nem sempre é possível devido aos requisitos operacionais, de suporte, ou de segurança. As alterações que não exigem ações imediatas para manter a conectividade, como endereços IP removidos, URLs ou alterações menos significativas, não incluem notificações prévias. Independentemente da notificação que é fornecida, listamos a data de ativação do serviço esperada para cada alteração.

### <a name="change-notification-using-the-web-service"></a>Alterar notificação usando o serviço Web

Você pode usar a URL do serviço Web e endereço IP do Office 365 para obter uma notificação de alteração. Recomendamos que você chame o método web **/version** uma vez por hora para verificar a versão dos pontos de extremidade que você está usando para conectar-se ao Office 365. Se essa versão mudar quando comparada à versão que você está usando, você deverá obter os dados mais recentes do ponto de extremidade do método web **/endpoints** e, opcionalmente, obter as diferenças entre o método web **/changes**. Não é necessário chamar os métodos web **/endpoints** ou **/changes** caso ainda não tenha feito nenhuma alteração na versão encontrada.

Para obter mais informações, confira [URL do serviço Web e o Endereço IP do Office 365](microsoft-365-ip-web-service.md).

### <a name="change-notification-using-rss-feeds"></a>Alterar notificação usando o serviço Web

O endereço IP e a URL do serviço Web do Office 365 fornecem um RSS feed no qual você pode se inscrever no Outlook. Há links para as URLs RSS em cada uma das páginas específicas da instância do serviço do Office 365 para os endereços IP e URLs. Para obter mais informações, confira [URL do serviço Web e o Endereço IP do Office 365](microsoft-365-ip-web-service.md).

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Alterar notificação e revisão de aprovação usando o Microsoft Flow

Entendemos que você ainda pode exigir o processamento manual de alterações dos ponto de extremidade de rede que acontecem todo mês. Você pode usar o Microsoft Flow para criar um fluxo que o notifique por email e opcionalmente execute um processo de aprovação para alterações quando os pontos de extremidade de rede do Office 365 sofram alterações. Depois de concluir a revisão, você pode fazer com que o fluxo envie automaticamente por email as alterações para o seu firewall e sua equipe de gerenciamento do servidor proxy.

Para mais informações sobre a amostra e modelo do Microsoft Flow, consulte [Usar o Microsoft Flow para receber um email de alterações de endereços IP e URLs do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651).
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Perguntas frequentes sobre pontos de extremidade de rede do Office 365

Perguntas frequentes de administradores sobre a conectividade do Office 365:
  
### <a name="how-do-i-submit-a-question"></a>Como enviar uma pergunta?

Clique no link que está no final da tela para indicar se este artigo foi útil ou não e envie mais perguntas. Monitoramos os comentários e atualizamos as perguntas com os questionamentos mais frequentes.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>Como determinar o local do meu locatário?

 O **local do locatário** é determinado da melhor forma usando nosso [mapa de datacenters](https://aka.ms/datamaps).
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>Estou me emparelhando adequadamente com a Microsoft?

 **Locais de emparelhamento** são descritos em mais detalhes em [emparelhamento com a Microsoft](https://www.microsoft.com/peering).
  
Com mais de 2.500 relações de emparelhamento de ISP globalmente e 70 pontos de presença, a passagem de sua rede para a nossa deve ser perfeita. Não custa nada gastar alguns minutos garantindo que a relação de emparelhamento de seu ISP seja ideal. [Veja alguns exemplos](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__guidance/) de entregas de emparelhamento boas e não tão boas para nossa rede.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Não vejo as solicitações de rede para os endereços IP na lista publicada, eu preciso fornecer acesso a eles?

Só fornecemos endereços IP para os servidores do Office 365 para os quais você deve fazer o encaminhamento diretamente. Essa não é uma lista abrangente de todos os endereços IP para os quais você verá solicitações de rede. Você verá solicitações de rede para endereços IP exclusivos não publicados da Microsoft e de terceiros. Esses endereços IP são gerados dinamicamente ou gerenciados de maneira a impedir o aviso em tempo hábil quando eles mudam. Se o firewall não permitir o acesso com base em FQDNs para essas solicitações de rede, use um arquivo PAC ou WPAD para gerenciar as solicitações.
  
Há um IP associado ao Office 365 sobre o qual você deseja obter mais informações?
  
1. Verifique se o endereço IP está incluído em um intervalo publicado maior usando uma calculadora CIDR como essas para o [IPv4](https://www.ipaddressguide.com/cidr)ou[IPv6](https://www.ipaddressguide.com/ipv6-cidr). Por exemplo, 40.96.0.0/13 inclui o endereço IP 40.103.0.1 apesar de 40.96 não corresponder a 40.103.
2. Ver se um parceiro é responsável pelo IP com uma [consulta whois](https://dnsquery.org/). Se for de propriedade da Microsoft, pode ser um parceiro interno. Muitos pontos de extremidade de rede de parceiro são listados como pertencentes à categoria _Padrão_, para a qual os endereços IP não são publicados.
3. O endereço IP pode não fazer parte do Office 365 ou uma dependência. A publicação do ponto de extremidade de rede do Office 365 não inclui todos os pontos de extremidade de rede da Microsoft.
4. Verifique o certificado. Em um navegador, conecte-se ao endereço IP utilizando *HTTPS://\<IP_ADDRESS\>*  , verifique os domínios listados no certificado para entender quais domínios estão associados com o endereço IP. Se é um endereço IP de propriedade da Microsoft e não está na lista de endereços IP do Office 365, é provável que o endereço IP esteja associado ao CDN da Microsoft como *MSOCDN.NET*  ou outro domínio da Microsoft sem informações de IP publicadas. Se você descobrir que o domínio do certificado é um domínio onde podemos solicitar que seja listado o endereço IP, informe-nos.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Algumas URLs do Office 365 apontam para registros CNAME em vez de registros A no DNS. O que preciso fazer com os registros CNAME?

Os computadores clientes precisam de um registro DNS A ou AAAA que inclua um ou mais endereços IP para se conectar a um serviço na nuvem. Algumas URLs incluídas no Office 365 mostram registros CNAME em vez de registros A ou AAAA. Esses registros CNAME são intermediários e pode haver vários em uma cadeia. Eles sempre serão eventualmente resolvidos para um registro A ou AAAA de um endereço IP. Por exemplo, considere a seguinte série de registros DNS, o que, por fim, é resolvido para o endereço IP _IP_1_:

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Esses redirecionamentos CNAME são uma parte normal do DNS e são transparentes para o computador cliente e transparentes para os servidores proxy. Eles são usados para balancear a carga, redes de distribuição de conteúdo, alta disponibilidade e mitigação de incidentes de serviço. A Microsoft não publica os registros CNAME intermediários, pois eles estão sujeitos a alterações a qualquer momento, e você não deve configurá-los como permitido no servidor proxy.

Um servidor proxy valida a URL inicial que, no exemplo acima, é serviceA.office.com e essa URL seria incluída na publicação do Office 365. O servidor proxy solicita a resolução de DNS dessa URL para um endereço IP e receberá IP_1 novamente. Ela não valida os registros de redirecionamento de CNAME intermediário.

As configurações de código fixo ou a lista de permissões baseada em FQDNs indiretos do Office 365 não são recomendadas, não têm suporte da Microsoft e são conhecidas por causar problemas de conectividade do cliente. As soluções DNS que bloqueiam o redirecionamento de CNAME ou que resolvem incorretamente entradas DNS do Office 365, podem ser resolvidas por meio do encaminhamento DNS condicional (com escopo para os FQDNs do Office 365) com a recursão de DNS habilitado. Muitos produtos de perímetro de rede de terceiros integram nativamente a lista de pontos de extremidade do Office 365 à sua configuração usando a [URL do serviço web e do endereço IP do Office 365](microsoft-365-ip-web-service.md).

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>Por que vejo nomes como nsatc.net ou akadns.net em nomes de domínio da Microsoft?

O Office 365 e outros serviços da Microsoft usam vários serviços de terceiros como Akamai e MarkMonitor para melhorar a experiência do Office 365. Para continuar a oferecer a melhor experiência possível, podemos alterar esses serviços no futuro. Domínios de terceiros podem hospedar conteúdo, como uma CDN, ou podem hospedar um serviço, como um serviço de gerenciamento de tráfego geográfico. Alguns dos serviços em uso no momento incluem:
  
[MarkMonitor](https://www.markmonitor.com/) é em uso quando você vê as solicitações que incluem *\*.nsatc.net*. Esse serviço fornece proteção de nome de domínio e monitoramento para proteção contra comportamentos mal intencionados.
  
[ExactTarget](https://www.marketingcloud.com/) é em uso quando você vê as solicitações para *\*.exacttarget.com*. Esse serviço fornece gerenciamento de link de email e monitoramento contra comportamentos mal-intencionados.
  
[Akamai](https://www.akamai.com/) é em uso quando você vê as solicitações que incluem um dos seguintes FQDNs. Esse serviço oferece DNS geográfica e serviços de rede de distribuição de conteúdo.
  
```console
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net
```

<a name="bkmk_thirdparty"> </a>
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>Preciso ter a conectividade mínima possível para o Office 365

Como o Office 365 é um conjunto de serviços criado para funcionar pela internet, as promessas confiabilidade e disponibilidade se baseiam em muitos serviços de internet padrão que estão disponíveis. Por exemplo, serviços de internet padrão como DNS, CRL e CDNs devem estar acessíveis para usar o Office 365 exatamente como eles devem estar acessíveis para usar os serviços de internet mais modernos.

O pacote do Office 365 é dividido nas áreas principais de serviço. Elas podem ser habilitados seletivamente para conectividade, e há uma área comum que é uma dependência para todas e sempre é necessária.

| Área de Serviço | Descrição |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online e Proteção do Exchange Online <br/> |
|**SharePoint** <br/> |SharePoint Online e OneDrive for Business <br/> |
|**Skype for Business Online e Microsoft Teams** <br/> |Skype for Business Online e Microsoft Teams <br/> |
|**Comum** <br/> |Office 365 Pro Plus, Office em um navegador, Azure AD e outros pontos de extremidade de rede comuns <br/> |

Além dos serviços básicos de internet, há serviços de terceiros que são usados somente para integrar funcionalidade. Enquanto eles são necessários para integração, estão marcados como opcionais no artigo de pontos de extremidade do Office 365, o que significa que a funcionalidade principal do serviço continuará funcionando se o ponto de extremidade não for acessível. Todos os pontos de extremidade de rede que são necessários terão os atributos necessários definidos como verdadeiro. Todos os pontos de extremidade de rede que são opcionais terão o atributo necessário definido como falso, e o atributo de observações detalhará a funcionalidade ausente que você deve esperar se a conectividade for bloqueada.
  
Se você está tentando usar o Office 365 e está encontrando serviços de terceiros não acessíveis, convém [garantir que todos os FQDNs marcados como obrigatórios ou opcionais neste artigo sejam permitidos por meio de proxy e firewall](urls-and-ip-address-ranges.md).
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>Como bloqueio o acesso aos serviços do consumidor da Microsoft?

Restringir o acesso aos nossos serviços do consumidor deve ser feito por sua conta e risco. A única maneira confiável de bloquear os serviços do consumidor é restringir o acesso aos *login.live.com* FQDN. Esse FQDN é usado por um amplo conjunto de serviços, incluindo serviços de não consumidor, como MSDN, TechNet, entre outros. Esse FQDN também é usado pelo Programa de Troca Segura de Arquivos do Suporte da Microsoft e é necessário para transferir arquivos, facilitando a solução de problemas para produtos da Microsoft.  A restrição de acesso a esse FQDN pode resultar também na necessidade de incluir exceções à regra para solicitações de rede associadas a esses serviços.
  
Tenha em mente que apenas bloquear o acesso aos serviços do consumidor da Microsoft não impede a capacidade de alguém na sua rede filtrar informações usando um locatário do Office 365 ou outro serviço.

<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>O firewall exige endereços IP e não processa URLs. Como configurar o para o Office 365?

O Office 365 não fornece endereços IP de todos os pontos de extremidade de rede necessários. Alguns são fornecidos somente como URLs e são categorizados como padrão. As URLs na categoria padrão que são necessárias devem ser permitidas por meio de um servidor proxy. Se você não tiver um servidor proxy, examine as solicitações da Web para URLs que os usuários digitam na barra de endereços de um navegador da Web. O usuário não pode fornecer um endereço IP. As URLs das categorias padrão do Office 365 que não fornecem endereços IP devem ser configuradas da mesma maneira.

## <a name="related-topics"></a>Tópicos Relacionados

[URL do serviço Web e endereço IP do Office 365](microsoft-365-ip-web-service.md)

[Intervalos de IP do Datacenter do Microsoft Azure](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Grupos de notícias públicos da Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Requisitos de infraestrutura de rede para o Microsoft Intune](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute e Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[Intervalos de URLs e de endereços IP do Office 365](urls-and-ip-address-ranges.md)
  
[Como gerenciar o ExpressRoute para a conectividade do Office 365](managing-expressroute-for-connectivity.md)
  
[Princípios de conectividade de rede do Office 365](microsoft-365-network-connectivity-principles.md)
