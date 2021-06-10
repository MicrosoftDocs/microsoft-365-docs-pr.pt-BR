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
description: Use essas informações para saber como o Office 365 usa CDNs (Redes de Entrega de Conteúdo) para melhorar o desempenho.
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911091"
---
# <a name="content-delivery-networks-cdns"></a>Redes de distribuição de conteúdo

*Esse artigo se aplica ao Microsoft 365 Enterprise e ao Office 365 Enterprise.*

As CDNs ajudam a manter Office 365 rápidas e confiáveis para usuários finais. Serviços de nuvem como Office 365 usam CDNs para armazenar em cache ativos estáticos mais próximos dos navegadores que os solicitam para acelerar os downloads e reduzir a latência do usuário final percebido. As informações neste tópico ajudarão você a aprender sobre CDNs (Redes de Entrega de Conteúdo) e como elas são usadas por Office 365.

## <a name="what-exactly-is-a-cdn"></a>O que é exatamente um CDN?

Um CDN é uma rede geograficamente distribuída que consiste em servidores de proxy e arquivos em datacenters conectados por redes de backbone de alta velocidade. As CDNs são usadas para reduzir o tempo de latência e de carga para um conjunto especificado de arquivos e objetos em um site ou serviço. Um CDN pode ter muitos milhares de pontos de extremidade para a manutenção ideal de solicitações de entrada de qualquer local.

As CDNs são comumente usadas para fornecer downloads mais rápidos de conteúdo genérico para um site ou serviço, como arquivos javascript, ícones e imagens, e também podem fornecer acesso privado ao conteúdo do usuário, como arquivos em bibliotecas de documentos do SharePoint Online, arquivos de mídia de streaming e código personalizado.

As CDNs são usadas pela maioria dos serviços de nuvem empresariais. Serviços de nuvem, como Office 365, têm milhões de clientes baixando uma mistura de conteúdo proprietário (como emails) e conteúdo genérico (como ícones) ao mesmo tempo. É mais eficiente colocar imagens que todos usam, como ícones, o mais próximo possível do computador do usuário. Não é prático para cada serviço de nuvem criar CDN datacenters que armazenam esse conteúdo genérico em todas as áreas metropolitanas ou mesmo em todos os principais hubs de Internet em todo o mundo, portanto, algumas dessas CDNs são compartilhadas.

## <a name="how-do-cdns-make-services-work-faster"></a>Como as CDNs fazem com que os serviços funcionem mais rapidamente?

Baixar objetos comuns, como imagens de site e ícones, uma e outra vez pode assumir a largura de banda da rede que pode ser melhor usada para baixar conteúdo pessoal importante, como emails ou documentos. Como Office 365 usa uma arquitetura que inclui CDNs, os ícones, scripts e outros conteúdos genéricos podem ser baixados de servidores mais próximos de computadores cliente, tornando os downloads mais rápidos. Isso significa acesso mais rápido ao seu conteúdo pessoal, que é armazenado com segurança Office 365 datacenters.

As CDNs ajudam a melhorar o desempenho do serviço na nuvem de várias maneiras:

- As CDNs deslocam parte da carga de download de rede e arquivo do serviço de nuvem, liberando recursos de serviço de nuvem para atender ao conteúdo do usuário e outros serviços, reduzindo a necessidade de atender solicitações de ativos estáticos.
- As CDNs são criadas para fornecer acesso a arquivos de baixa latência implementando redes de alto desempenho e servidores de arquivos e aproveitando protocolos de rede atualizados, como [HTTP/2,](https://en.wikipedia.org/wiki/HTTP/2) com compactação altamente eficiente e solicitação de multiplexação.
- CDN redes usam muitos pontos de extremidade distribuídos globalmente para disponibilizar o conteúdo o mais próximo possível dos usuários.

## <a name="the-office-365-cdn"></a>O Office 365 CDN

O Office 365 Rede de Distribuição de Conteúdo (CDN) integrado permite que os administradores Office 365 forneçam melhor desempenho para as páginas do SharePoint Online da organização, armazenando em cache ativos estáticos mais próximos dos navegadores que os solicitam, o que ajuda a acelerar os downloads e reduzir a latência. O Office 365 CDN usa o [protocolo HTTP/2 para](https://en.wikipedia.org/wiki/HTTP/2) velocidades de compactação e download aprimoradas.

> [!NOTE]
> O Office 365 CDN está disponível apenas para locatários na nuvem **produção** (em todo o mundo). Os locatários nas nuvens do Governo dos EUA, China e Alemanha atualmente não suportam o Office 365 CDN.

A CDN do Office 365 é composta por várias CDNs que permitem que você hospede ativos estáticos em vários locais ou _origens_ e sirva-os de redes globais de alta velocidade. Dependendo do tipo de conteúdo você quiser hospedar na CDN do Office 365, você pode adicionar origens **públicas**, origens **privadas** ou ambas.

![Office 365 CDN diagrama conceitual](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN diagrama conceitual")

O conteúdo de origens **públicas** dentro da CDN do Office 365 é anonimamente acessível e pode ser acessado por qualquer um que tenha as URLs dos ativos hospedados. Como o acesso ao conteúdo de origens públicas é anônimo, você só deve usá-lo para o armazenamento em cache de conteúdo genérico e não sensível como arquivos javascript, scripts, ícones e imagens. A CDN do Office 365 é usada por padrão para baixar os ativos de recurso genérico, como aplicativos de cliente do Office 365 de uma origem pública.

**As** origens privadas no Office 365 CDN fornecem acesso privado ao conteúdo do usuário, SharePoint como bibliotecas de documentos online, sites e imagens proprietárias. O acesso ao conteúdo com origens privadas é protegido com tokens gerados dinamicamente, portanto só podem ser acessados por usuários com permissões para a biblioteca ou local armazenamento do documento original. Origens privadas na CDN do Office 365 só podem ser usadas para o conteúdo do SharePoint Online e você só poderá acessar ativos por meio do redirecionamento do seu locatário do SharePoint Online.

O serviço de CDN do Office 365 faz parte da assinatura do SharePoint Online.

Para obter mais informações sobre como usar o Office 365 CDN, consulte [Use the Office 365 content delivery network with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Para assistir a uma série de vídeos curtos que fornecem informações conceituais e HOWTO sobre como usar o Office 365 CDN, visite o canal SharePoint Padrões e Práticas de [Desenvolvedores do YouTube](https://aka.ms/sppnp-videos).

## <a name="other-microsoft-cdns"></a>Outras CDNs da Microsoft

Embora não seja parte do Office 365 CDN, você pode usar essas CDNs em seu locatário Office 365 para acessar bibliotecas de desenvolvimento do SharePoint, código personalizado e outras finalidades que se enquadram fora do escopo do Office 365 CDN.

### <a name="azure-cdn"></a>CDN do Azure

>[!NOTE]
>A partir do 3º trimestre de 2020, o SharePoint Online começará a gravar vídeos em cache no CDN do Azure para dar suporte à reprodução de vídeo e confiabilidade aprimoradas. Os vídeos populares serão transmitidos do ponto CDN ponto de extremidade mais próximo do usuário. Esses dados permanecerão dentro do limite Microsoft 365 conformidade. Esse é um serviço gratuito para todos os locatários e não exige que qualquer ação do cliente seja configurada.

Você pode usar o **CDN do Azure** para implantar sua própria instância de CDN para hospedar web parts, bibliotecas e outros ativos de recursos personalizados, o que permite aplicar chaves de acesso ao armazenamento CDN e exercer maior controle sobre sua configuração CDN. O uso da CDN do Azure não é gratuito e requer uma assinatura do Azure.

Para obter mais informações sobre como configurar uma instância CDN do Azure, consulte Início rápido: Integrar uma conta de armazenamento do [Azure](/azure/cdn/cdn-create-a-storage-account-with-cdn)com CDN do Azure .

Para um exemplo de como o CDN do Azure pode ser usado para hospedar web parts SharePoint, consulte [Deploy your SharePoint client-side web part to CDN do Azure](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Para obter informações sobre o CDN do Azure do PowerShell, consulte [Manage CDN do Azure with PowerShell](/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

O **Ajax CDN** da Microsoft é um CDN somente leitura que oferece muitas bibliotecas de desenvolvimento populares, incluindo jQuery (e todas as outras bibliotecas), ASP.NET Ajax, Bootstrap, Knockout.js e outras.
  
Para incluir esses scripts em seu projeto, basta substituir quaisquer referências a essas bibliotecas disponíveis publicamente por referências ao endereço CDN em vez de incluí-los no próprio projeto. Por exemplo, use o seguinte código para vincular ao jQuery:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Para obter mais informações sobre como usar o microsoft ajax CDN, consulte [Microsoft Ajax CDN](/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Como Office 365 o conteúdo de um CDN?

Independentemente do CDN você configurar para seu locatário Office 365, o processo básico de recuperação de dados é o mesmo.

1. Seu cliente (um navegador ou um aplicativo cliente Office) solicita dados de Office 365.

2. Office 365 retorna os dados diretamente para seu cliente ou, se os dados fazem parte de um conjunto de conteúdo hospedado pelo CDN, redireciona seu cliente para a URL CDN.

    a. Se os dados já estão  armazenados em cache em uma origem pública, seu cliente baixa os dados diretamente do local CDN local mais próximo para seu cliente.

    b. Se os dados já estão  armazenados em cache em uma origem privada, o serviço CDN verifica as permissões da sua conta de usuário Office 365 na origem. Se você tiver permissões, o SharePoint Online gerará dinamicamente uma URL personalizada composta do caminho para o ativo no CDN e dois tokens de acesso e retornará a URL personalizada para seu cliente. Em seguida, seu cliente baixa os dados diretamente do local de CDN mais próximo para seu cliente usando a URL personalizada.

3. Se os dados não são armazenados em cache no CDN, o nó CDN solicita os dados do Office 365 e, em seguida, armazena em cache os dados por um período de tempo após o cliente baixar os dados.

O CDN descobre o datacenter mais próximo do navegador do usuário e, usando o redirecionamento, baixa os dados solicitados de lá. CDN redirecionamento é rápido e pode economizar muito tempo de download para os usuários.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Como configurar minha rede para que as CDNs funcionem melhor com Office 365?

Minimizar a latência entre clientes em sua rede e CDN pontos de extremidade é a principal consideração para garantir o desempenho ideal. Você pode usar as práticas recomendadas descritas em Managing [Office 365 endpoints](managing-office-365-endpoints.md) para garantir que sua configuração de rede permita que os navegadores clientes acessem o CDN diretamente em vez de rotear o tráfego CDN por meio de proxies centrais para evitar a introdução de latência desnecessária.

Você também pode ler [Office 365 Princípios](./microsoft-365-network-connectivity-principles.md) de Conectividade de Rede para entender os conceitos por trás da otimização Office 365 de rede.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Há uma lista de todas as CDNs que Office 365 usa?

As CDNs em uso por Office 365 estão sempre sujeitas a alterações e, em muitos casos, há vários parceiros CDN configurados no caso de um não estar disponível. As CDNs principais usadas por Office 365 são:

|CDN  |Empresa  |Uso  |Link  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Ativos genéricos em origens públicas, SharePoint conteúdo do usuário em origens privadas         |[Usar a rede de distribuição de conteúdo do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|CDN do Azure     |Microsoft         |Código personalizado, Estrutura do SharePoint soluções         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (somente leitura)     |Microsoft         |Bibliotecas comuns para Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js etc.         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Quais ganhos de desempenho um CDN fornece?

Há muitos fatores envolvidos na medição de diferenças específicas no desempenho entre os dados baixados diretamente do Office 365 e os dados baixados de um CDN específico, como sua localização em relação ao locatário e ao ponto de extremidade mais próximo do CDN, o número de ativos em uma página que são atendidos pelo CDN e alterações transitórias na latência e largura de banda da rede. No entanto, um teste A/B simples pode ajudar a mostrar a diferença no tempo de download de um arquivo específico.

As capturas de tela a seguir ilustram a diferença na velocidade de download entre o local do arquivo nativo no Office 365 e o mesmo arquivo hospedado no [Microsoft Ajax Rede de Distribuição de Conteúdo](/aspnet/ajax/cdn/overview). Essas capturas de tela são da guia **Rede** nas ferramentas de desenvolvedor do Internet Explorer 11. Essas capturas de tela mostram a latência no jQuery da biblioteca popular. Para abrir essa tela, no Internet Explorer, pressione  **F12** e selecione a guia Rede que é símbolo com um ícone Wi-Fi.
  
![Captura de tela da Rede F12](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Esta captura de tela mostra a biblioteca carregada na galeria de páginas mestras no próprio site SharePoint Online. O tempo necessário para carregar a biblioteca é de 1,51 segundos.
  
![Captura de tela do tempo de carregamento 1,51 s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
A segunda captura de tela mostra o mesmo arquivo entregue pelo CDN da Microsoft. Desta vez, a latência é de cerca de 496 milissegundos. Isso é uma grande melhoria e mostra que um segundo inteiro é cortado do tempo total para baixar o objeto.
  
![Captura de tela dos tempos de carregamento em 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Meus dados são seguros?

Cuidamos muito para proteger os dados que executam sua empresa. Os dados armazenados no Office 365 CDN são criptografados em trânsito e em repouso, e o acesso aos dados no Office 365 SharePoint CDN é protegido por permissões de usuário Office 365 e autorização de token. Solicitações de dados no Office 365 SharePoint CDN devem ser referenciadas (redirecionadas) do locatário Office 365 ou um token de autorização não será gerado.

Para garantir que seus dados permaneçam seguros, recomendamos que você nunca armazene conteúdo do usuário ou outros dados confidenciais em uma CDN. Como o acesso aos dados em um site público CDN anônimo, as CDNs públicas só devem ser usadas para hospedar conteúdo genérico, como arquivos de script da Web, ícones, imagens e outros ativos não confidenciais.

> [!NOTE]
> Os provedores de CDN de terceiros podem ter padrões de privacidade e conformidade diferentes dos compromissos descritos pela Central de Confiação Office 365. Os dados armazenados em cache por meio do serviço CDN podem não estar em conformidade com os Termos de Processamento de Dados da Microsoft (DPT) e podem estar fora dos limites de conformidade Office 365 Central de Confiações.

Para obter informações detalhadas sobre privacidade e proteção de dados para Office 365 CDN provedores, visite o seguinte:  

- Saiba mais sobre Office 365 privacidade e proteção de dados no [Centro de Confiança da Microsoft](https://www.microsoft.com/trustcenter)
- Saiba mais sobre a privacidade e a proteção de dados de Akamai no Centro de Confiança de [Privacidade Akamai](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Saiba mais sobre a privacidade e a proteção de dados do Azure no [Centro de Confiança do Azure](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Como posso proteger minha rede com todos esses serviços de terceiros?

Aproveitar um amplo conjunto de serviços de parceiros permite Office 365 dimensionar e atender aos requisitos de disponibilidade, bem como aprimorar a experiência do usuário ao usar Office 365. Os serviços de terceiros Office 365 de uso incluem ambas as listas de revogação de certificados; como crl.microsoft.com ou sa.symcb.com e CDNs; como r3.res.outlook.com. Cada CDN FQDN gerado pelo Office 365 é um FQDN personalizado para Office 365. Se você for enviado a um FQDN a pedido do Office 365, poderá ter certeza de que o provedor CDN controla o FQDN e o conteúdo subjacente nesse local.
  
Para clientes que querem segregar solicitações destinadas a um datacenter microsoft ou Office 365 de solicitações [destinadas a](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)terceiros, escrevemos orientações sobre Como gerenciar pontos de extremidade Office 365 .

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Há uma lista de todos os FQDNs que aproveitam CDNs?

A lista de FQDNs e como eles aproveitam as CDNs mudam ao longo do tempo. Consulte nossa página de Office 365 URLs e intervalos de [endereços IP publicados](./urls-and-ip-address-ranges.md) para obter atualizados os FQDNs mais recentes que aproveitam CDNs.

Você também pode usar o Office 365 ip e o serviço [Web de URL](microsoft-365-ip-web-service.md) para solicitar as URLs de Office 365 atuais e intervalos de endereços IP formatados como CSV ou JSON.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Posso usar meu próprio conteúdo de CDN cache na minha rede local?

Estamos continuamente procurando novas maneiras de dar suporte às necessidades de nossos clientes e, no momento, estamos explorando o uso de soluções de proxy de cache e outras soluções de CDN locais.

Embora não faça parte do Office 365 CDN, você também pode usar o **CDN do Azure** para hospedar web parts, bibliotecas e outros ativos de recursos personalizados, o que permite aplicar chaves de acesso ao armazenamento CDN e exercer maior controle sobre sua configuração do CDN. O uso da CDN do Azure não é gratuito e requer uma assinatura do Azure. Para obter mais informações sobre como configurar uma instância CDN do Azure, consulte Início rápido: Integrar uma conta de armazenamento do [Azure](/azure/cdn/cdn-create-a-storage-account-with-cdn)com CDN do Azure .

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Estou usando o Azure ExpressRoute para Office 365, isso altera as coisas?

[O Azure ExpressRoute para Office 365](azure-expressroute.md) fornece uma conexão dedicada Office 365 infraestrutura segregada da internet pública. Isso significa que os clientes ainda precisarão se conectar em conexões não ExpressaRoute para se conectar a CDNs e outras infraestruturas da Microsoft que não estão explicitamente incluídas na lista de serviços suportados pelo ExpressRoute. Para obter mais informações sobre como rotear tráfego específico, como solicitações destinadas a CDNs, consulte Office 365 [gerenciamento de tráfego de rede.](routing-with-expressroute.md)

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>Posso usar CDNs com SharePoint Servidor local?

Usar CDNs só faz sentido em um contexto SharePoint Online e deve ser evitado com SharePoint Server. Isso acontece porque todas as vantagens em relação à localização geográfica não são verdadeiras se o servidor estiver localizado no local ou geograficamente próximo de qualquer maneira. Além disso, se houver uma conexão de rede com os servidores onde ele está hospedado, o site poderá ser usado sem uma conexão com a Internet e, portanto, não poderá recuperar os arquivos CDN. Caso contrário, você deve usar uma CDN se houver uma disponível e estável para a biblioteca e os arquivos necessários para seu site.
  
Aqui está um link curto que você pode usar para voltar: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Confira também

[Princípios de conectividade de rede do Office 365](./microsoft-365-network-connectivity-principles.md)

[Avaliando a conectividade de rede do Office 365](assessing-network-connectivity.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](./urls-and-ip-address-ranges.md)

[Usar a rede de distribuição de conteúdo do Office 365 com o SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Central de Confiabilidade da Microsoft](https://www.microsoft.com/trustcenter)

[Ajustar o desempenho do Office 365](tune-microsoft-365-performance.md)