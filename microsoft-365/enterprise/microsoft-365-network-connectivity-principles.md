---
title: Princípios de conectividade de rede do Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/23/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
search.appverid: MET150
ms.assetid: 76e7f232-917a-4b13-8fe2-4f8dbccfe041
f1.keywords:
- NOCSH
description: Este artigo fornece as diretrizes mais recentes para otimizar a conectividade de rede do Microsoft 365 com segurança.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e0391133721270c0fdfb288b5d26ab23f301a844
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923285"
---
# <a name="microsoft-365-network-connectivity-principles"></a>Princípios de conectividade de rede do Microsoft 365

*Este artigo se aplica tanto ao Microsoft 365 Enterprise quanto ao Office 365 Enterprise.*

Antes de começar a planejar sua rede para a conectividade de rede do Microsoft 365, é importante compreender os princípios de conectividade para gerenciar o tráfego do Microsoft 365 com segurança e obter o melhor desempenho possível. Este artigo vai ajudá-lo a entender as diretrizes mais recentes para otimizar a conectividade de rede do Microsoft 365 com segurança.
  
As redes corporativas tradicionais são projetadas principalmente para fornecer aos usuários acesso a aplicativos e dados hospedados em datacenters operados pela empresa com forte segurança de perímetro. O modelo tradicional presume que os usuários acessem aplicativos e dados de dentro do perímetro de rede corporativa, em links WAN de filiais ou remotamente por conexões VPN.
  
A adoção de aplicativos SaaS como o Microsoft 365 move algumas combinações de serviços e dados de fora do perímetro de rede. Sem otimização, o tráfego entre usuários e aplicativos SaaS fica sujeito à latência introduzida pela inspeção de pacotes, hairpins de rede, conexões inadvertidas para pontos de extremidade geograficamente distantes e outros fatores. Você pode garantir o melhor desempenho e a confiabilidade da Microsoft 365 compreendendo e implementando as principais diretrizes de otimização.
  
Neste artigo, você aprenderá sobre:
  
- [A arquitetura Microsoft 365](microsoft-365-network-connectivity-principles.md#BKMK_Architecture)que se aplica à conectividade do cliente à nuvem
- [Princípios de conectividade do Microsoft 365](microsoft-365-network-connectivity-principles.md#BKMK_Principles) atualizados e estratégias para otimizar o tráfego de rede e a experiência do usuário final
- O [serviço web dos pontos de extremidade do Office 365](microsoft-365-network-connectivity-principles.md#BKMK_WebSvc), que permite que os administradores de rede usem uma lista estruturada de pontos de extremidade para usar em otimização de rede
- [Novas categorias de pontos de extremidade do Office 365](microsoft-365-network-connectivity-principles.md#BKMK_Categories) e diretrizes de otimização
- [Comparação de segurança de perímetro de rede com a segurança do ponto de extremidade](microsoft-365-network-connectivity-principles.md#BKMK_SecurityComparison)
- Opções de[otimização incremental](microsoft-365-network-connectivity-principles.md#BKMK_IncOpt) para o tráfego do Microsoft 365
- [Teste de conectividade do Microsoft 365](https://aka.ms/netonboard), uma nova ferramenta para testar a conectividade básica com o Microsoft 365

## <a name="microsoft-365-architecture"></a>Arquitetura do Microsoft 365
<a name="BKMK_Architecture"> </a>

O Microsoft 365 é uma nuvem distribuída de Software como Serviço (SaaS), que oferece cenários de produtividade e colaboração por meio de um conjunto diversificado de serviços e aplicativos, como o Exchange Online, o SharePoint Online, o Skype for Business Online, o Microsoft Teams, a Proteção do Exchange Online, o Office em um navegador e muitos outros. Embora aplicativos específicos do Microsoft 365 possam ter seus recursos exclusivos, à medida que se aplicam à rede do cliente e conectividade com a nuvem, todos compartilham alguns princípios, metas e padrões de arquitetura. Esses princípios e padrões de arquitetura para a conectividade são comuns em várias outras nuvens SaaS e, ao mesmo tempo, são diferentes dos modelos de implantação típicos das nuvens Plataforma como serviço e Infraestrutura como serviço, como o Microsoft Azure.
  
Um dos recursos mais significativos da arquitetura Microsoft 365 (que geralmente é esquecido ou mal interpretado pelos arquitetos de rede) é um serviço distribuído verdadeiramente global, no contexto de como os usuários se conectam a ele. O local do locatário de destino do Microsoft 365 é importante para compreender a localidade de onde os dados do cliente estão armazenados na nuvem, mas a experiência do usuário com o Microsoft 365 não envolve a conexão direta a discos que contêm os dados. A experiência do usuário com o Microsoft 365 (incluindo desempenho, confiabilidade e outras características de qualidade importantes) envolve a conectividade por meio de uma porta frontal de serviço altamente distribuída que é ampliada entre centenas de locais da Microsoft em todo o mundo. Na maioria dos casos, é possível ter a melhor experiência de usuário permitindo que a rede do cliente encaminhe as solicitações de usuário para o ponto de entrada de serviço mais próximo do Microsoft 365, em vez de se conectar ao Microsoft 365 por meio de um ponto de saída em um local ou região central.
  
Para a maioria dos clientes, os usuários do Microsoft 365 são distribuídos em vários locais. Para obter os melhores resultados, os princípios descritos neste documento devem ser examinados a partir do ponto de vista de expansão (não ampliação), concentrando-se em otimizar a conectividade para o ponto de presença mais próximo na rede global da Microsoft, não para a localização geográfica do locatário do Microsoft 365. Em essência, isso significa que, embora os dados do locatário do Microsoft 365 possam estar armazenados em um local geográfico específico, a experiência do Microsoft 365 para esse locatário continua a ser distribuída e pode estar presente em uma localidade muito próxima (rede) de cada local do usuário final que o locatário possui.
  
## <a name="microsoft-365-connectivity-principles"></a>Princípios de conectividade do Microsoft 365
<a name="BKMK_Principles"> </a>

A Microsoft recomenda os seguintes princípios para alcançar uma melhor conectividade e desempenho do Microsoft 365. Use estes princípios de conectividade do Microsoft 365 para gerenciar seu tráfego e obter o melhor desempenho ao se conectar ao Microsoft 365.
  
O objetivo principal no design de rede deve ser minimizar a latência, reduzindo o tempo de resposta (RTT) da sua rede para a Rede Global da Microsoft, o backbone de rede pública da Microsoft que se conecta a todos os datacenters da Microsoft com baixa latência e pontos de entrada de aplicativo em nuvem espalhados ao redor do mundo. Você pode saber mais sobre a Rede Global da Microsoft no [Como a Microsoft cria uma rede global rápida e confiável](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/).
  
<a name="BKMK_P1"> </a>
### <a name="identify-and-differentiate-microsoft-365-traffic"></a>Identificar e diferenciar o tráfego do Microsoft 365

![Identificar o tráfego do Microsoft 365](../media/621aaec9-971d-4f19-907a-1ae2ef6d72fc.png)
  
Identificar o tráfego de rede do Microsoft 365 é o primeiro passo para diferenciar esse tráfego do tráfego de rede genérico vinculado à Internet. A conectividade do Microsoft 365 pode ser otimizada implementando uma combinação de abordagens, como otimização de rota de rede, regras de firewall, configurações de proxy do navegador e bypass de dispositivos de inspeção de rede para certos pontos de extremidade.
  
Diretrizes de otimização anterior do Microsoft 365 divididos em pontos de extremidade do Microsoft 365 em duas categorias, **Necessário** e **Opcional**. Como os pontos de extremidade foram adicionados para dar suporte a novos recursos e serviços do Microsoft 365, reorganizamos os pontos de extremidade do Microsoft 365 em três categorias: **Otimizar**, **Permitir** e **Padrão**. As diretrizes de cada categoria se aplicam a todos os pontos de extremidade da categoria, facilitando a compreensão e a implementação de otimizações.
  
Para obter mais informações sobre as categorias e os métodos de otimização do ponto de extremidade do Microsoft 365, confira a seção [Novas categorias de ponto de extremidade do Office 365](microsoft-365-network-connectivity-principles.md#BKMK_Categories).
  
Agora a Microsoft publica todos os pontos de extremidade do Microsoft 365 como um serviço Web e fornece orientação sobre como usar esses dados. Para obter mais informações sobre como buscar e trabalhar com pontos de extremidade do Microsoft 365, confira o artigo [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
<a name="BKMK_P2"> </a>
### <a name="egress-network-connections-locally"></a>Enviar conexões de rede de saída localmente

![Enviar conexões de rede de saída localmente](../media/b42a45be-1ab4-4073-a7dc-fbdfb4aedd24.png)
  
O DNS local e a saída para a Internet são muito importantes para reduzir a latência da conexão e garantir que as conexões de usuários sejam feitas do ponto de entrada mais próximo para os serviços do Microsoft 365. Em uma topologia de rede complexa, é importante implementar o DNS local e a saída para a internet local juntos. Para obter mais informações sobre como o Microsoft 365 roteia as conexões do cliente para o ponto de entrada mais próximo, confira o artigo [Conectividade do Cliente](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b).
  
Antes do surgimento dos serviços de nuvem, como o Microsoft 365, a conectividade da Internet para usuários finais como fator de design na arquitetura de rede era relativamente simples. Quando os serviços de Internet e os sites são distribuídos em todo o mundo, a latência entre os pontos de saída corporativos e qualquer ponto de extremidade de destino é basicamente uma função de distância geográfica.
  
Em uma arquitetura de rede tradicional, todas as conexões de saída de Internet atravessam a rede corporativa e saem de um local central. À medida que as ofertas de nuvem da Microsoft amadureceram, uma arquitetura de rede distribuída voltada para a Internet se tornou fundamental para o suporte a serviços de nuvem sensível à latência. A Rede Global da Microsoft foi projetada para atender aos requisitos de latência com a infraestrutura de Porta Frontal do Serviço Distribuído, uma malha dinâmica de pontos de entrada globais que roteia as conexões do serviço de nuvem de entrada para o ponto de entrada mais próximo. Isso se destina a reduzir o comprimento da "última quilometragem" para os clientes da nuvem da Microsoft, reduzindo a rota entre o cliente e a nuvem com eficácia.
  
As WANs corporativas geralmente são projetadas para transportar o tráfego de rede para o escritório central da empresa para inspeção antes da saída para a Internet, geralmente por um ou mais servidores proxy. O diagrama a seguir ilustra essa topologia de rede.
  
![Modelo tradicional de rede corporativa](../media/fc87b8fd-a191-47a7-9704-1e445599813a.png)
  
Como o Microsoft 365 é executado na Rede Global da Microsoft, que inclui servidores front-end em todo o mundo,geralmente haverá um servidor front-end próximo ao local do usuário. Fornecendo acesso à Internet local e configurando servidores DNS internos para fornecer a resolução de nomes locais para pontos de extremidade do Microsoft 365, o tráfego de rede destinado ao Microsoft 365 pode se conectar aos servidores front-end do Microsoft 365 o mais próximo possível do usuário. O diagrama a seguir mostra um exemplo de uma topologia de rede que permite que os usuários se conectem a partir do escritório central, de uma filial e de locais remotos para seguir a rota mais curta até o ponto de entrada mais próximo do Microsoft 365.
  
![Modelo de rede WAN com pontos de egresso regionais](../media/4d4c07cc-a928-42b8-9a54-6c3741380a33.png)
  
Encurtar o caminho de rede para os pontos de entrada do Microsoft 365 dessa maneira pode melhorar o desempenho da conectividade e a experiência do usuário final no Microsoft 365, além de ajudar a reduzir o impacto de alterações futuras na arquitetura de rede no desempenho e na confiabilidade do Microsoft 365.
  
Além disso, as solicitações DNS poderão apresentar a latência se o servidor DNS de resposta estiver distante ou ocupado. Você pode minimizar a latência de resolução de nomes ao provisionar os servidores DNS locais em filiais e verificar se eles estão configurados para armazenar em cache os registros DNS de forma adequada.
  
Embora a saída regional possa funcionar bem para o Microsoft 365, o modelo de conectividade ideal seria sempre fornecer a saída de rede no local do usuário, independentemente de você estar na rede corporativa ou em locais remotos, como casas, hotéis, cafeterias e aeroportos. Esse modelo de saída direta local é representado no diagrama a seguir.
  
![Arquitetura de rede de saída local](../media/6bc636b0-1234-4ceb-a45a-aadd1044b39c.png)
  
As empresas que adotaram o Microsoft 365 podem tirar proveito da arquitetura de Porta Frontal do Serviço Distribuído da Rede Global da Microsoft, garantindo que as conexões com o usuário da Microsoft 365 adotem a rota mais curta possível para o ponto de entrada mais próximo da Rede Global da Microsoft. A arquitetura de rede de saída local faz isso, permitindo que o tráfego do Microsoft 365 seja roteado pela saída mais próxima, independentemente do local do usuário.
  
A arquitetura de saída local tem os seguintes benefícios em relação ao modelo tradicional:
  
- Oferece o melhor desempenho do Microsoft 365, melhorando o comprimento da rota. as conexões de usuários finais são roteadas dinamicamente para o ponto de entrada mais próximo do Microsoft 365 pela infraestrutura de Porta Frontal do Serviço Distribuído.
- Reduz a carga da infraestrutura de rede corporativa, permitindo a saída local.
- Protege as conexões em ambas as extremidades, aproveitando a segurança do ponto de extremidades e os recursos de segurança da nuvem.

<a name="BKMK_P3"> </a>
### <a name="avoid-network-hairpins"></a>Evitar hairpins de rede

![Evitar hairpins](../media/ee53e8af-f57b-4292-a256-4f36733b263a.png)
  
Como regra geral, a rota mais curta e direta entre o usuário e o ponto de extremidade do Microsoft 365 oferecerão o melhor desempenho. Um hairpin de rede acontece quando o tráfego WAN ou VPN vinculado a um destino específico primeiro é direcionado primeiro para outro local intermediário (como a pilha de segurança, o broker de acesso à nuvem, ou gateway da Web baseado na nuvem), introduzindo latência e redirecionamento potencial para um ponto de extremidade distante geograficamente. Os hairpins de rede também podem ser causados por ineficiências de roteamento/emparelhamento ou de DNS (remoto).
  
Para garantir que a conectividade do Microsoft 365 não esteja sujeita à hairpins de rede mesmo no caso de saída local, verifique se o ISP que é usado para fornecer o acesso à Internet para o local do usuário tem uma relação de emparelhamento direto com a Rede Global da Microsoft próxima desse local. Você também pode configurar o roteamento de saída para enviar tráfego confiável do Microsoft 365 diretamente, em vez de fazer proxy ou encapsulamento por meio de um fornecedor terceirizado de segurança de rede baseado em nuvem ou na nuvem que processa o tráfego ligado à Internet. A resolução de nomes DNS local de pontos de extremidade do Microsoft 365 ajuda a garantir que, além do roteamento direto, os pontos de entrada mais próximos do Microsoft 365 estejam sendo usados para as conexões de usuário.
  
Se você usa serviços de rede ou segurança baseados em nuvem para o tráfego do Microsoft 365, certifique-se de que o resultado do hairpin seja avaliado e seu impacto no desempenho do Microsoft 365 seja compreendido. É possível fazer isso examinando o número e as localizações de locais de provedores de serviços por meio dos quais o tráfego é encaminhado em relação ao número de suas filiais e pontos de emparelhamento da Rede Global da Microsoft, qualidade da relação de emparelhamento de rede do provedor de serviços com seu ISP e com a Microsoft, e o impacto no desempenho de backhaul na infraestrutura do provedor de serviços.
  
Devido a um grande número de locais distribuídos com os pontos de entrada do Microsoft 365 e sua proximidade com os usuários finais, o roteamento de tráfego do Microsoft 365 para qualquer provedor de segurança ou rede de terceiros pode ter um impacto adverso nas conexões do Microsoft 365, caso a rede do provedor não esteja configurada para o emparelhamento ideal do Microsoft 365.
  
<a name="BKMK_P4"> </a>
### <a name="assess-bypassing-proxies-traffic-inspection-devices-and-duplicate-security-technologies"></a>Avaliar ignorar proxies, dispositivos de inspeção de tráfego e tecnologias de segurança duplicadas

![Ignorar proxies, dispositivos de inspeção de tráfego e tecnologias de segurança duplicadas](../media/0131930d-c6cb-4ae1-bbff-fe4cf6939a23.png)
  
Os clientes empresariais devem revisar seus métodos de redução de risco e de segurança de rede especificamente para o tráfego vinculado ao Microsoft 365 e usar os recursos de segurança do Microsoft 365 para reduzir sua dependência de tecnologias de segurança de rede intrusivas, caras e com impacto no desempenho para o tráfego de rede do Microsoft 365.
  
A maioria das redes corporativas impõe a segurança de rede para o tráfego de Internet usando tecnologias como proxies, inspeção SSL, inspeção de pacotes e sistemas de prevenção contra perda de dados. Essas tecnologias oferecem redução de risco importantes para solicitações de Internet genéricas, mas podem reduzir significativamente o desempenho, a capacidade de expansão e a qualidade da experiência do usuário final quando aplicada aos pontos de extremidade do Microsoft 365.
  
<a name="BKMK_WebSvc"> </a>
#### <a name="office-365-endpoints-web-service"></a>Serviços Web dos Pontos de extremidade do Office 365

Os administradores do Microsoft 365 podem usar um script ou uma chamada REST para consumir uma lista estruturada de pontos de extremidade do serviço Web de pontos de extremidade do Office 365 e atualizar as configurações de firewalls de perímetro e outros dispositivos de rede. Isso garantirá que o tráfego vinculado ao Microsoft 365 seja identificado, tratado adequadamente e gerenciado de forma diferente do tráfego de rede associado a sites genéricos e geralmente desconhecidos da Internet. Para saber mais sobre como usar o serviço Web de pontos de extremidade do Office 365, confira o artigo [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US).
  
#### <a name="pac-proxy-automatic-configuration-scripts"></a>Scripts de PAC (Configuração Automática de Proxy)
<a name="BKMK_WebSvc"> </a>

Os administradores do Microsoft 365 podem criar scripts PAC (Configuração Automática de Proxy) que podem ser entregues aos computadores dos usuários por meio de WPAD ou de GPO. Os scripts PAC podem ser usados para ignorar os proxies de solicitações do Microsoft 365 de usuários de WAN ou VPN, permitindo que o tráfego do Microsoft 365 use conexões diretas com a Internet em vez de atravessar a rede corporativa.
  
#### <a name="microsoft-365-security-features"></a>Recursos de segurança do Microsoft 365
<a name="BKMK_WebSvc"> </a>

A Microsoft é transparente sobre a segurança do datacenter, a segurança operacional e a redução de riscos em relação aos servidores da Microsoft 365 e aos pontos de extremidade de rede que eles representam. Os recursos de segurança integrados do Microsoft 365 estão disponíveis para reduzir o risco de segurança da rede, como Prevenção Contra Perda de Dados, Antivírus, Autenticação Multifator, Caixa de Bloqueio do Cliente, Defender para Office 365, Inteligência Contra Ameaças do Microsoft 365, Pontuação Segura do Microsoft 365, Proteção do Exchange Online e Segurança DDOS de Rede.
  
Para obter mais informações sobre o datacenter da Microsoft e a segurança da Rede Global, confira [Central de Confiabilidade da Microsoft](https://www.microsoft.com/trustcenter/security).
  
## <a name="new-office-365-endpoint-categories"></a>Novas categorias de pontos de extremidade do Office 365
<a name="BKMK_Categories"> </a>

Os pontos de extremidade do Office 365 representam um conjunto variado de endereços de rede e sub-redes. Os pontos de extremidade podem ser URLs, endereços IP ou intervalos de IP, e alguns pontos de extremidade são listados com portas TCP/UDP específicas. As URLs podem ser FQDN, como *account.office.net* ou uma URL curinga como *\*.office365.com*.
  
> [!NOTE]
> Os locais dos pontos de extremidade do Office 365 dentro da rede não estão diretamente relacionados à localização dos dados do locatário do Microsoft 365. Por esse motivo, os clientes devem examinar o Microsoft 365 como um serviço distribuído e global e não devem tentar bloquear as conexões de rede para os pontos de extremidade do Office 365 com base nos critérios geográficos.
  
Nas diretrizes anteriores para o gerenciamento de tráfego do Microsoft 365, os pontos de extremidade eram organizados em duas categorias, **Necessário** e **Opcional**. Os pontos de extremidade de cada categoria exigiam otimizações diferentes dependendo da criticalidade do serviço e muitos clientes enfrentaram desafios ao justificar a aplicação das mesmas otimizações de rede à lista completa de URLs e endereços IP do Office 365.
  
No novo modelo, os pontos de extremidade são separados em três categorias, **Otimizar**, **Permitir** e **Padrão**, fornecendo uma tabela dinâmica baseada em prioridade sobre onde você deve focar os esforços de otimização de rede para obter os melhores aperfeiçoamentos de desempenho e retorno sobre o investimento. Os pontos de extremidade são consolidados nas categorias acima, com base na sensibilidade da experiência efetiva do usuário à qualidade da rede, volume e envelope de desempenho dos cenários e facilidade de implementação. As otimizações recomendadas podem ser aplicadas da mesma forma em todos os pontos de extremidade de uma determinada categoria.
  
- **Otimizar** os pontos de extremidades é necessário para a conectividade com todos os serviços do Microsoft 365 e representa mais de 75% da largura de banda, conexões e volume de dados do Office 365. Esses pontos de extremidade representam os cenários do Office 365 mais confidenciais para o desempenho, latência e disponibilidade da rede. Todos os pontos de extremidade estão hospedados em datacenters da Microsoft. A taxa de alteração para os pontos de extremidade nesta categoria deve ser muito menor do que para os pontos de extremidade nas outras duas categorias. Essa categoria inclui um pequeno conjunto (na ordem de aproximadamente 10) de URLs principais e um conjunto de sub-redes IP dedicadas às cargas de trabalho principais do Office 365, como o Exchange Online, o SharePoint Online, o Skype for Business Online e o Microsoft Teams.

    Uma lista condensada de pontos de extremidade críticos muito definidos deve ajudar você a planejar e implementar otimizações de rede de alto valor para esses destinos de maneira mais rápida e fácil.

    Exemplos de *Otimizar*  pontos de extremidade incluem *https://outlook.office365.com*, *https://\<tenant\>.sharepoint.com* e *https://\<tenant\>-my.sharepoint.com*.

    Os métodos de otimização incluem:

  - Ignorar *a otimização* pontos de extremidades nos serviços e dispositivos de rede que executam a interceptação de tráfego, a descriptografia SSL, a inspeção profunda de pacotes e a filtragem de conteúdo.
  - Ignorar os dispositivos de proxy local e os serviços de proxy baseados na nuvem geralmente usados para navegação na Internet genérica.
  - Priorizar a avaliação desses pontos de extremidade como totalmente confiável por sua infraestrutura de rede e pelos sistemas de perímetro.
  - Priorizar a redução ou a eliminação de backhaul da WAN e facilite o envio direto da saída baseada na Internet para esses pontos de extremidade, o mais próximo possível do que os usuários/filiais.
  - Facilitar a conectividade direta a esses pontos de extremidade de nuvem para usuários VPN, implementando o tunelamento dividido.
  - Certificar-se de que os endereços IP retornados pela resolução de nome DNS correspondam à trajetória de saída de roteamento para esses pontos de extremidade.
  - Priorize esses pontos de extremidade para a integração do SD-WAN para roteamento direto de latência mínima para o ponto de acesso à Internet mais próximo da rede global da Microsoft.

- **Permitir** os pontos de extremidade é necessário para a conectividade com os recursos e serviços específicos do Office 365, mas não são tão sensíveis ao desempenho e à latência da rede quanto os da categoria *Otimizar*. O espaço total de rede desses pontos de extremidade, desde o ponto de vista da largura de banda e a contagem de conexão também é menor. Esses pontos de extremidade são dedicados ao Office 365 e estão hospedados em datacenters da Microsoft. Elas representam um amplo conjunto de microserviços do Office 365 e suas dependências (na ordem de aproximadamente 100 URLs) e devem mudar a uma taxa mais alta do que a da categoria *Otimizar*. Nem todos os pontos de extremidade nesta categoria estão associados a sub-redes IP dedicadas definidas.

    Otimizações de rede para  *Permitir*  que os pontos de extremidade possam melhorar a experiência do usuário do Office 365, mas alguns clientes podem optar por escolhê-los de forma mais restrita para minimizar as alterações na rede.

    Exemplos de pontos de extremidade *Permitir* incluem *https://\*. protection.outlook.com* e *https://accounts.accesscontrol.windows.net*.

    Os métodos de otimização incluem:

  - Ignorar *a permissão* de pontos de extremidades nos serviços e dispositivos de rede que executam a interceptação de tráfego, a descriptografia SSL, a inspeção profunda de pacotes e a filtragem de conteúdo.
  - Priorizar a avaliação desses pontos de extremidade como totalmente confiável por sua infraestrutura de rede e pelos sistemas de perímetro.
  - Priorizar a redução ou a eliminação de backhaul da WAN e facilite o envio direto da saída baseada na Internet para esses pontos de extremidade, o mais próximo possível do que os usuários/filiais.
  - Certificar-se de que os endereços IP retornados pela resolução de nome DNS correspondam à trajetória de saída de roteamento para esses pontos de extremidade.
  - Priorize esses pontos de extremidade para a integração do SD-WAN para roteamento direto de latência mínima para o ponto de acesso à Internet mais próximo da rede global da Microsoft.

- **Os pontos de extremidade de** padrão representam as dependências e os serviços do Office 365 que não exigem otimização e podem ser tratados por redes de clientes como tráfego de Internet padrão. Alguns pontos de extremidade nesta categoria podem não estar hospedados em datacenters da Microsoft. Os exemplos incluem *https://odc.officeapps.live.com* e *https://appexsin.stb.s-msn.com*.

Para obter mais informações sobre as técnicas de otimização de rede do Office 365, confira o artigo [Gerenciando pontos de extremidade do Office 365](managing-office-365-endpoints.md).
  
## <a name="comparing-network-perimeter-security-with-endpoint-security"></a>Comparando a segurança de perímetro de rede com a segurança do ponto de extremidade
<a name="BKMK_SecurityComparison"> </a>

O objetivo da segurança de rede tradicional é otimizar o perímetro da rede corporativa contra invasões e explorações maliciosas. À medida que as organizações adotam o Microsoft 365, alguns serviços de rede e dados são parcialmente ou totalmente migrados para a nuvem. Quanto à mudança fundamental da arquitetura de rede, esse processo exige uma reavaliação da segurança da rede que leva em consideração os fatores emergentes:
  
- À medida que os serviços de nuvem são adotados, os serviços de rede e os dados são distribuídos entre os datacenters locais e a nuvem, e a segurança de perímetro não é mais adequada por si só.
- Os usuários remotos se conectam aos recursos corporativos em datacenters locais e na nuvem contra locais não controlados, como casas, hotéis e cafeterias.
- Os recursos de segurança criados para fins específicos estão cada vez mais incorporados ao serviços de nuvem e podem potencialmente complementar ou substituir os sistemas de segurança existentes.

A Microsoft oferece uma ampla variedade de recursos de segurança do Microsoft 365, além de uma orientação prescritiva para a aplicação de práticas recomendadas de segurança, que podem ajudar a garantir a segurança de dados e de rede da Microsoft 365. As práticas recomendadas são as seguintes:
  
- **Usar a MFA (autenticação multifator)** A MFA adiciona uma outra camada de proteção a uma estratégia de senha forte exigindo que os usuários confirmem uma chamada, mensagem de texto ou uma notificação de aplicativo no smartphone após inserir a senha corretamente.

- **Usar o Microsoft Cloud App Security** Configurar políticas para controlar atividades anômalas e agir sobre ela. Configurar alertas com o Microsoft Cloud App Security, para que os administradores possam examinar atividades de usuário incomuns ou arriscadas, como o download de grandes quantidades de dados, várias tentativas de entrada com falha ou conexões de um endereço IP desconhecido ou perigoso.

- **Configurar a Prevenção contra Perda de Dados (DLP)** A DLP permite que você identifique dados confidenciais e crie políticas que ajudam a impedir que os usuários compartilhem os dados acidentalmente ou intencionalmente. A DLP funciona em todo o Microsoft 365, incluindo o Exchange Online, o SharePoint Online e o OneDrive, para que os usuários possam se manter em conformidade sem interromper o fluxo de trabalho.

- **Usar o Sistema de Proteção de Dados do Cliente** Como administrador do Microsoft 365, você pode usar o Sistema de Proteção de Dados do Cliente para controlar a forma como o engenheiro de suporte da Microsoft acessa seus dados durante uma sessão de ajuda. Em casos em que o engenheiro requer acesso aos dados para solucionar e corrigir um problema, o Sistema de Proteção de Dados do Cliente permite que você aprove ou rejeite a solicitação de acesso.

- **Usar a Classificação de Segurança do Office 365** Uma ferramenta de análise de segurança que recomenda o que você pode fazer para reduzir ainda mais o risco. As pontuações de pontos de segurança analisa as suas configurações e atividades do Microsoft 365 e as compara a uma linha de base estabelecida pela Microsoft. Você receberá uma pontuação baseada em quão alinhado você está com as práticas recomendadas de segurança.

Uma abordagem holística para a segurança aprimorada deve incluir o seguinte:
  
- Mudar a ênfase do perímetro de segurança em relação à segurança do ponto de extremidade, aplicando recursos de segurança de cliente do Office e baseado na nuvem.
  - Reduzir o perímetro de segurança para o datacenter
  - Habilitação de confiança equivalente para dispositivos do usuário dentro do escritório ou em locais remotos
  - Foco na proteção do local de dados e do local do usuário
  - As máquinas de usuário gerenciado têm confiança maior com a segurança do ponto de extremidade
- Gerenciar toda a segurança de informações de forma global, sem se concentrar exclusivamente no perímetro
  - Redefinir a segurança da rede WAN e a criação da segurança de rede de perímetro, permitindo que o tráfego confiável ignore dispositivos de segurança e separe dispositivos não gerenciados para redes Wi-Fi convidadas.
  - Reduzir os requisitos de segurança de rede da borda da WAN corporativa
  - Alguns dispositivos de segurança de perímetro de rede, como firewalls, ainda são necessários, mas o carregamento é reduzido
  - Garante a saída local do tráfego do Microsoft 365
- Os aperfeiçoamentos podem ser abordados incrementalmente conforme descrito na seção de [Otimização incremental](microsoft-365-network-connectivity-principles.md#BKMK_IncOpt). Algumas técnicas de otimização podem oferecer melhores taxas de custo/benefício, dependendo de sua arquitetura de rede, e você deve escolher otimizações que fazem mais sentido para sua organização.

Para obter mais informações sobre o Centro de segurança do Microsoft 365, confira o artigo [Centro de segurança do Microsoft 365](../security/index.yml) e [Centro de conformidade do Microsoft 365](../compliance/index.yml).
  
## <a name="incremental-optimization"></a>Otimização incremental
<a name="BKMK_IncOpt"> </a>

Representamos o modelo ideal de conectividade de rede para SaaS no início desse artigo, mas para muitas organizações de grande porte com arquiteturas de rede complexas, não será prático fazer todas essas alterações. Nessa seção, discutimos várias alterações incrementais que podem ajudar a melhorar o desempenho e a confiabilidade do Microsoft 365.
  
Os métodos que você usará para otimizar o tráfego do Microsoft 365 variam de acordo com a topologia de rede e os dispositivos de rede que você implementou. Grandes empresas com vários locais e práticas de segurança de rede complexas precisarão desenvolver uma estratégia que inclui a maioria dos princípios listados na seção [princípios de conectividade do Microsoft 365](microsoft-365-network-connectivity-principles.md#BKMK_Principles), enquanto organizações menores talvez precisem apenas considerar um ou dois.
  
Você pode abordar a otimização como um processo incremental, aplicando cada método sucessivamente. A tabela a seguir lista os principais métodos de otimização na ordem de seu impacto sobre a latência e a confiabilidade para o maior número de usuários.
  
|**Método de otimização**|**Descrição**|**Impacto**|
|:-----|:-----|:-----|
|Resolução DNS local e saída da Internet  <br/> |Provisionar servidores DNS locais em cada local e garantir a que as conexões do Microsoft 365 saiam para a Internet o mais próximo possível da localização do usuário.  <br/> | Minimizar latência  <br/>  Melhorar a conectividade confiável com o ponto de entrada mais próximo do Microsoft 365  <br/> |
|Adicionar pontos de saída regionais  <br/> |Se sua rede corporativa tiver vários locais, mas apenas um ponto de saída, adicione pontos de saída regionais para permitir que os usuários se conectem ao ponto de entrada mais próximo do Microsoft 365.  <br/> | Minimizar latência  <br/>  Melhorar a conectividade confiável com o ponto de entrada mais próximo do Microsoft 365  <br/> |
|Ignorar proxies e dispositivos de inspeção  <br/> |Configurar os navegadores com arquivos PAC que enviam solicitações do Microsoft 365 diretamente para pontos de saída.  <br/> Configurar roteadores de borda e firewalls para permitir o tráfego do Microsoft 365 sem inspeção.  <br/> | Minimizar latência  <br/>  Reduzir a carga em dispositivos de rede  <br/> |
|Habilitar a conexão direta para usuários VPN  <br/> |Para usuários VPN, habilite as conexões do Microsoft 365 para se conectar diretamente da rede do usuário, em vez de pelo túnel VPN, implementando o tunelamento dividido.  <br/> | Minimizar latência  <br/>  Melhorar a conectividade confiável com o ponto de entrada mais próximo do Microsoft 365  <br/> |
|Migrar da WAN tradicional para a SD-WAN  <br/> |SD-WANs (Redes de Longa Distância Definidas por Software) simplificam o gerenciamento da WAN e melhoram o desempenho substituindo os roteadores WAN tradicionais por dispositivos virtuais, semelhante à virtualização de recursos de computação usando VMs (máquinas virtuais).  <br/> | Melhorar o desempenho e a capacidade de gerenciamento do tráfego de WAN  <br/>  Reduzir a carga em dispositivos de rede  <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Visão Geral da Conectividade de Rede do Microsoft 365](microsoft-365-networking-overview.md)

[Gerenciar pontos de extremidade do Office 365](managing-office-365-endpoints.md)

[URLs e intervalos de endereços IP do Office 365](urls-and-ip-address-ranges.md)

[URL do serviço Web e endereço IP do Office 365](microsoft-365-ip-web-service.md)

[Avaliando a conectividade de rede do Microsoft 365](assessing-network-connectivity.md)

[Planejamento de rede e ajuste de desempenho para o Microsoft 365](network-planning-and-performance.md)

[Ajuste de desempenho do Office 365 usando linhas de base e histórico de desempenho](performance-tuning-using-baselines-and-history.md)

[Plano de solução de problemas de desempenho do Office 365](performance-troubleshooting-plan.md)

[Redes de Distribuição de Conteúdo](content-delivery-networks.md)

[Teste de conectividade do Microsoft 365](https://aka.ms/netonboard)

[Como a Microsoft cria sua rede global confiável e rápida](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Blog de rede do Office 365](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)