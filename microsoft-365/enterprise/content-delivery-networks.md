---
title: Redes de fornecimento de conteúdo
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: Use essas informações para saber como o Office 365 usa redes de distribuição de conteúdo (CDNs) para melhorar o desempenho.
ms.openlocfilehash: 1c2230b76f354bf6f3de524b2b8c75b7d8c380e7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46687102"
---
# <a name="content-delivery-networks-cdns"></a>Redes de distribuição de conteúdo

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

CDNs ajudar a manter o Office 365 rápido e confiável para usuários finais. Os serviços de nuvem, como o Office 365, usam CDNs para armazenar em cache ativos estáticos mais próximos dos navegadores que os solicitam para acelerar os downloads e reduzir a latência de usuário final percebida. As informações neste tópico vão ajudá-lo a aprender sobre redes de distribuição de conteúdo (CDNs) e como elas são usadas pelo Office 365.

## <a name="what-exactly-is-a-cdn"></a>O que é exatamente uma CDN?

Uma CDN é uma rede geograficamente distribuída que consiste em servidores de arquivos e proxy em datacenters conectados por redes de backbone de alta velocidade. CDNs são usados para reduzir a latência e tempos de carregamento para um conjunto especificado de arquivos e objetos em um site ou serviço. Uma CDN pode ter milhares de pontos de extremidade para manutenção ideal de solicitações de entrada de qualquer local.

CDNs são comumente usados para fornecer downloads mais rápidos de conteúdo genérico para um site ou serviço, como arquivos JavaScript, ícones e imagens, e também pode fornecer acesso privado a conteúdo do usuário, como arquivos em bibliotecas de documentos do SharePoint Online, arquivos de mídia de fluxo e código personalizado.

CDNs são usados pela maioria dos serviços de nuvem corporativos. Os serviços de nuvem, como o Office 365, têm milhões de clientes baixando uma mistura de conteúdo proprietário (como emails) e conteúdo genérico (como ícones) ao mesmo tempo. É mais eficiente colocar as imagens que todos usam, como ícones, o mais próximo possível do computador do usuário. Não é prático que todos os serviços de nuvem criem datacenters CDN que armazenem esse conteúdo genérico em todas as áreas metropolitanas ou até mesmo em cada Hub de Internet principal em todo o mundo, de forma que alguns desses CDNs sejam compartilhados.

## <a name="how-do-cdns-make-services-work-faster"></a>Como o CDNs faz os serviços funcionarem mais rapidamente?

Baixar objetos comuns, como imagens e ícones de site repetidamente, pode ocupar a largura de banda da rede que pode ser usada melhor para baixar conteúdo pessoal importante, como emails ou documentos. Como o Office 365 usa uma arquitetura que inclui o CDNs, os ícones, scripts e outros conteúdos genéricos podem ser baixados de servidores mais próximos dos computadores cliente, tornando os downloads mais rápidos. Isso significa acesso mais rápido ao conteúdo pessoal, que é armazenado com segurança nos datacenters do Office 365.

CDNs ajuda a melhorar o desempenho do serviço de nuvem de várias maneiras:

- CDNs a parte do turno da rede e do arquivo descarregá-lo do serviço de nuvem, liberando recursos do serviço de nuvem para servir conteúdo de usuário e outros serviços reduzindo a necessidade de atender às solicitações de ativos estáticos.
- O CDNs é projetado para fornecer acesso a arquivos de baixa latência implementando redes de alto desempenho e servidores de arquivos, e aproveitando os protocolos de rede atualizados, como [http/2](https://en.wikipedia.org/wiki/HTTP/2) , com compactação altamente eficiente e multiplexação de solicitação.
- As redes CDN usam vários pontos de extremidade distribuídos globalmente para tornar o conteúdo disponível o mais próximo possível dos usuários.

## <a name="the-office-365-cdn"></a>A CDN do Office 365

A rede interna de distribuição de conteúdo (CDN) do Office 365 permite que os administradores do Office 365 ofereçam melhor desempenho para as páginas do SharePoint Online da sua organização, armazenando ativos estáticos mais próximos dos navegadores que os solicitam, o que ajuda a acelerar os downloads e a reduzir a latência. A CDN do Office 365 usa o [protocolo http/2](https://en.wikipedia.org/wiki/HTTP/2) para melhorar a compactação e a velocidade de download.

> [!NOTE]
> A CDN do Office 365 só está disponível para locatários na nuvem de **produção** (internacional). Os locatários nas nuvens do governo dos EUA, da China e da Alemanha não suportam atualmente a CDN do Office 365.

A CDN do Office 365 é composta por várias CDNs que permitem que você hospede ativos estáticos em vários locais ou _origens_e sirva-os de redes globais de alta velocidade. Dependendo do tipo de conteúdo você quiser hospedar na CDN do Office 365, você pode adicionar origens **públicas**, origens **privadas** ou ambas.

![Diagrama conceitual da CDN do Office 365](../media/O365-CDN/o365-cdn-flow-transparent.svg "Diagrama conceitual da CDN do Office 365")

O conteúdo de origens **públicas** dentro da CDN do Office 365 é anonimamente acessível e pode ser acessado por qualquer um que tenha as URLs dos ativos hospedados. Como o acesso ao conteúdo de origens públicas é anônimo, você só deve usá-lo para o armazenamento em cache de conteúdo genérico e não sensível como arquivos javascript, scripts, ícones e imagens. A CDN do Office 365 é usada por padrão para baixar os ativos de recurso genérico, como aplicativos de cliente do Office 365 de uma origem pública.

Origens **privadas** dentro da CDN do Office 365 oferecem acesso privado a conteúdo do usuário, como bibliotecas de documentos do SharePoint Online, sites e imagens proprietárias. O acesso ao conteúdo com origens privadas é protegido com tokens gerados dinamicamente, portanto só podem ser acessados por usuários com permissões para a biblioteca ou local armazenamento do documento original. Origens privadas na CDN do Office 365 só podem ser usadas para o conteúdo do SharePoint Online e você só poderá acessar ativos por meio do redirecionamento do seu locatário do SharePoint Online.

O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.

Para obter mais informações sobre como usar a CDN do Office 365, consulte [usar a rede de distribuição de conteúdo do office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Para assistir a uma série de vídeos curtos que oferecem informações conceituais e HOWTOs sobre como usar a CDN do Office 365, visite o [canal do YouTube de padrões e práticas do desenvolvedor do SharePoint](https://aka.ms/sppnp-videos).

## <a name="other-microsoft-cdns"></a>Outros Microsoft CDNs

Embora não seja uma parte da CDN do Office 365, você pode usar essas CDNs em seu locatário do Office 365 para acessar bibliotecas de desenvolvimento do SharePoint, código personalizado e outros propósitos que estão fora do escopo da CDN do Office 365.

### <a name="azure-cdn"></a>CDN do Azure

>[!NOTE]
>A partir do terceiro trimestre de 2020, o SharePoint Online começará a armazenar em cache os vídeos na CDN do Azure para suportar a reprodução e a confiabilidade de vídeo aprimoradas Vídeos populares serão transmitidos do ponto de extremidade da CDN mais próximo ao usuário. Esses dados permanecerão no limite de conformidade da Microsoft 365. Este é um serviço gratuito para todos os locatários e não requer nenhuma ação de cliente para configurar.

Você pode usar a **CDN do Azure** para implantar sua própria instância de CDN para hospedar Web Parts, bibliotecas e outros ativos de recursos personalizados, o que permite aplicar chaves de acesso ao seu armazenamento CDN e exercer maior controle sobre a configuração da CDN. O uso da CDN do Azure não é gratuito e exige uma assinatura do Azure.

Para obter mais informações sobre como configurar uma instância de CDN do Azure, consulte [QuickStart: integrar uma conta de armazenamento do Azure com a CDN do Azure](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

Para obter um exemplo de como a CDN do Azure pode ser usada para hospedar Web Parts do SharePoint, consulte [implantar a Web Part do lado do cliente do SharePoint na CDN do Azure](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Para obter informações sobre o módulo PowerShell CDN do Azure, consulte [Manage Azure CDN with PowerShell](https://docs.microsoft.com/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>CDN do Microsoft Ajax

A **CDN do AJAX** da Microsoft é uma CDN somente leitura que oferece várias bibliotecas de desenvolvimento populares, incluindo jQuery (e todas as outras bibliotecas), ASP.NET AJAX, Bootstrap, Knockout.js e outras.
  
Para incluir esses scripts em seu projeto, basta substituir qualquer referência a essas bibliotecas disponíveis publicamente com referências ao endereço da CDN, em vez de incluí-lo em seu próprio projeto. Por exemplo, use o seguinte código para vincular ao jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Para obter mais informações sobre como usar a CDN do Microsoft Ajax, consulte [CDN do Microsoft Ajax](https://docs.microsoft.com/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Como o Office 365 usa o conteúdo de uma CDN?

Independentemente da CDN que você configurou para o seu locatário do Office 365, o processo de recuperação de dados básico é o mesmo.

1. Seu cliente (um aplicativo de navegador ou de cliente do Office) solicita dados do Office 365.

2. O Office 365 retorna os dados diretamente para o cliente ou, se os dados fizerem parte de um conjunto de conteúdo hospedado pela CDN, redireciona seu cliente para a URL da CDN.

    a. Se os dados já estiverem armazenados em cache em uma origem _pública_ , o cliente baixará os dados diretamente do local da CDN mais próximo para o cliente.

    b. Se os dados já estiverem armazenados em cache em uma origem _privada_ , o serviço de CDN verificará as permissões da conta de usuário do Office 365 na origem. Se você tiver permissões, o SharePoint Online gerará dinamicamente uma URL personalizada composta do caminho para o ativo na CDN e dois tokens de acesso e retornará a URL personalizada ao cliente. Em seguida, o cliente baixa os dados diretamente do local da CDN mais próxima para o cliente usando a URL personalizada.

3. Se os dados não estiverem armazenados em cache na CDN, o nó CDN solicitará os dados do Office 365 e, em seguida, armazenará em cache os dados por um período de tempo após o cliente baixar os dados.

A CDN calcula o datacenter mais próximo ao navegador do usuário e, usando o redirecionamento, baixa os dados solicitados. O redirecionamento da CDN é rápido e pode economizar muito tempo de download dos usuários.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Como configurar minha rede para que o CDNs funcione melhor com o Office 365?

Minimizar a latência entre os clientes na rede e os pontos de extremidade da CDN é a consideração principal para garantir o desempenho ideal. Você pode usar as práticas recomendadas descritas no [Gerenciamento de pontos de extremidade do Office 365](managing-office-365-endpoints.md) para garantir que sua configuração de rede permita que navegadores de clientes acessem a CDN diretamente, em vez de rotear o tráfego de CDN por meio de proxies centrais para evitar a introdução à latência desnecessária.

Você também pode ler os [princípios de conectividade de rede do office 365](https://aka.ms/o365networkingprinciples) para entender os conceitos por trás da otimização do desempenho da rede do Office 365.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Há uma lista de todos os CDNs que o Office 365 usa?

O CDNs em uso pelo Office 365 está sempre sujeito a alterações e, em muitos casos, há vários parceiros CDN configurados no evento um não está disponível. O CDNs principal usado pelo Office 365 são:

|CDN  |Empresa  |Uso  |Link  |
|---------|---------|---------|---------|
|CDN do Office 365     |Akamai         |Ativos genéricos em origens públicas, conteúdo de usuário do SharePoint em origens privadas         |[Usar a rede de distribuição de conteúdo do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|CDN do Azure     |Microsoft         |Código personalizado, soluções da estrutura do SharePoint         |[CDN do Microsoft Azure](https://azure.microsoft.com/documentation/services/cdn/)         |
|CDN do Microsoft AJAX (somente leitura)     |Microsoft         |Bibliotecas comuns para AJAX, jQuery, ASP.NET, Bootstrap, Knockout.js, etc.         |[CDN do Microsoft Ajax](https://docs.microsoft.com/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Quais ganhos de desempenho uma CDN oferece?

Há muitos fatores envolvidos na medição de diferenças específicas de desempenho entre os dados baixados diretamente do Office 365 e os dados baixados de uma CDN específica, como seu local em relação ao seu locatário e ao ponto de extremidade da CDN mais próximo, o número de ativos em uma página que são atendidos pela CDN e alterações transitórias na latência e largura de banda da rede. No entanto, um teste A/B simples pode ajudar a mostrar a diferença no tempo de download para um arquivo específico.

As capturas de tela a seguir ilustram a diferença na velocidade de download entre o local do arquivo nativo no Office 365 e o mesmo arquivo hospedado na [rede de distribuição de conteúdo do Microsoft Ajax](https://docs.microsoft.com/aspnet/ajax/cdn/overview). Essas capturas de tela são da guia **rede** nas ferramentas de desenvolvedor do Internet Explorer 11. Essas capturas de tela mostram a latência na biblioteca popular jQuery. Para exibir essa tela, no Internet Explorer, pressione **F12** e selecione a guia **rede** que é simbolizada com um ícone de Wi-Fi.
  
![Captura de tela da Rede F12](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Esta captura de tela mostra a biblioteca carregada para a Galeria de páginas mestras no próprio site do SharePoint Online. O tempo necessário para carregar a biblioteca é de 1,51 segundos.
  
![Captura de tela do tempo de carregamento 1,51 s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
A segunda captura de tela mostra o mesmo arquivo entregue pela CDN da Microsoft. Desta vez, a latência é de cerca de 496 milissegundos. Este é um grande aperfeiçoamento e mostra que todo um segundo é Shaved do tempo total para baixar o objeto.
  
![Captura de tela dos tempos de carregamento em 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Meus dados estão seguros?

É preciso ter muito cuidado para proteger os dados que executam sua empresa. Os dados armazenados na CDN do Office 365 são criptografados em trânsito e em repouso, e o acesso aos dados na CDN do Office 365 SharePoint é protegido por permissões de usuário e autorização de token do Office 365. As solicitações de dados na CDN do Office 365 SharePoint devem ser referenciadas (redirecionadas) do seu locatário do Office 365 ou um token de autorização não será gerado.

Para garantir que seus dados permaneçam seguros, recomendamos que você nunca armazene o conteúdo do usuário ou outros dados confidenciais em uma CDN pública. Como o acesso aos dados em uma CDN pública é anônimo, os CDNs públicos só devem ser usados para hospedar conteúdo genérico, como arquivos de script da Web, ícones, imagens e outros ativos não sensíveis.

> [!NOTE]
> provedores de CDN de terceiros podem ter padrões de privacidade e conformidade que diferem dos compromissos indicados pela central de confiabilidade do Office 365. Os dados armazenados em cache através do serviço de CDN podem não estar em conformidade com os termos de processamento de dados da Microsoft (DPT) e podem estar fora dos limites de conformidade da central de confiabilidade do Office 365.

Para obter informações detalhadas sobre privacidade e proteção de dados para provedores de CDN do Office 365, visite o seguinte:  

- Saiba mais sobre a proteção de dados e privacidade do Office 365 na [central de confiabilidade da Microsoft](https://www.microsoft.com/trustcenter)
- Saiba mais sobre a privacidade e a proteção de dados da Akamai no [Akamai Privacy Trust Center](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Saiba mais sobre privacidade e proteção de dados do Azure na [central de confiabilidade do Azure](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Como posso proteger minha rede com todos esses serviços de terceiros?

O uso de um conjunto abrangente de serviços parceiros permite que o Office 365 dimensione e atenda aos requisitos de disponibilidade, bem como aprimore a experiência do usuário ao usar o Office 365. Os serviços de terceiros do Office 365 aproveitam as listas de certificados revogados; como crl.microsoft.com ou sa.symcb.com, e CDNs; como r3.res.outlook.com. Todos os FQDNS CDN gerados pelo Office 365 são um FQDN personalizado para o Office 365. Se você for enviado para um FQDN na solicitação do Office 365, poderá ter certeza de que o provedor de CDN controla o FQDN e o conteúdo subjacente nesse local.
  
Para clientes que desejam segregar solicitações destinadas a um datacenter da Microsoft ou do Office 365 de solicitações destinadas a um terceiro, criamos orientações sobre como [gerenciar pontos de extremidade do Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Há uma lista de todos os FQDNs que utilizam o CDNs?

A lista de FQDNs e como eles aproveitam o CDNs mudam com o tempo. Consulte nossa página de [URLs e intervalos de endereços IP do Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744) publicados para se manter atualizado sobre os FQDNs mais recentes que aproveitam o CDNs.

Você também pode usar o [endereço IP do office 365 e o serviço Web de URL](microsoft-365-ip-web-service.md) para solicitar as URLs atuais do Office 365 e os intervalos de endereços IP formatados como CSV ou JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Posso usar minha própria CDN e o conteúdo de cache na minha rede local?

Estamos continuamente procurando novas maneiras de dar suporte às necessidades dos clientes e estamos explorando atualmente o uso de soluções de proxy de cache e outras soluções de CDN no local.

Embora não faça parte da CDN do Office 365, você também pode usar a CDN do **Azure** para hospedar Web Parts, bibliotecas e outros ativos de recursos personalizados, o que permite aplicar chaves de acesso ao seu armazenamento CDN e exercer maior controle sobre a configuração da CDN. O uso da CDN do Azure não é gratuito e exige uma assinatura do Azure. Para obter mais informações sobre como configurar uma instância de CDN do Azure, consulte [QuickStart: integrar uma conta de armazenamento do Azure com a CDN do Azure](https://docs.microsoft.com/azure/cdn/cdn-create-a-storage-account-with-cdn).

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Estou usando o Azure ExpressRoute para Office 365, isso muda de coisa?

O [Azure ExpressRoute para Office 365](azure-expressroute.md) fornece uma conexão dedicada à infraestrutura 365 do Office que é segregada da Internet pública. Isso significa que os clientes ainda precisarão se conectar por conexões não-ExpressRoute para se conectarem ao CDNs e a outra infraestrutura da Microsoft que não esteja explicitamente incluída na lista de serviços com suporte do ExpressRoute. Para obter mais informações sobre como rotear tráfego específico, como solicitações destinadas a CDNs, consulte o [Gerenciamento de tráfego de rede do Office 365](routing-with-expressroute.md).

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>Posso usar o CDNs com o SharePoint Server no local?

O uso do CDNs faz sentido em um contexto do SharePoint Online e deve ser evitado com o SharePoint Server. Isso ocorre porque todas as vantagens em torno do local geográfico não são verdadeiras se o servidor está localizado no local ou geographicly Close, mesmo assim. Além disso, se houver uma conexão de rede com os servidores em que ele está hospedado, o site poderá ser usado sem uma conexão com a Internet e, portanto, não poderá recuperar os arquivos CDN. Caso contrário, você deverá usar uma CDN se houver uma disponível e estável para a biblioteca e os arquivos necessários para o site.
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/o365cdns](https://aka.ms/o365cdns)
  
## <a name="see-also"></a>Confira também

[Princípios de conectividade de rede do Office 365](https://aka.ms/o365networkingprinciples)

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](https://go.microsoft.com/fwlink/p/?LinkID=293744)

[Usar a rede de distribuição de conteúdo do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Central de Confiabilidade da Microsoft](https://www.microsoft.com/trustcenter)

[Ajustar o desempenho do Office 365](tune-microsoft-365-performance.md)
