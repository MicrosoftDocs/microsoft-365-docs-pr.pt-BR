---
title: Sistema de rede para a Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda a infraestrutura de rede da Contoso e como a empresa usa sua tecnologia SD-WAN para obter um desempenho de rede ideal para Microsoft 365 para serviços de nuvem empresariais.
ms.openlocfilehash: d5f3581b81d33bdc200321692b82d57a96d09298
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754009"
---
# <a name="networking-for-the-contoso-corporation"></a>Sistema de rede para a Contoso Corporation

Para adotar uma infraestrutura inclusiva na nuvem, a Contoso criou uma mudança fundamental na forma como o tráfego de rede para serviços de nuvem é deslocado. Em vez de um modelo interno de hub e de fala que concentra a conectividade de rede e o tráfego para o próximo nível da hierarquia do office, eles mapearam os locais de usuário para a saída da Internet local e as conexões locais para o local de rede Microsoft 365 mais próximo na Internet.

## <a name="networking-infrastructure"></a>Infraestrutura de rede

Esses são os elementos de rede que vinculam escritórios contoso em todo o mundo:

- Rede WAN de Comutação de Rótulos Multiprotocolo (MPLS)

  Uma rede MPLS WAN conecta a sede de Paris a escritórios regionais e escritórios regionais a escritórios de satélite em uma configuração de hub e de fala. A rede permite que os usuários acessem servidores locais que comem aplicativos de linha de negócios na sede de Paris. Ele também encaminha qualquer tráfego genérico da Internet para o escritório de Paris, onde os dispositivos de segurança de rede assinam as solicitações. Em cada escritório, os roteadores entregam tráfego para hosts com fio ou pontos de acesso sem fio em sub-redes, que usam o espaço de endereço IP privado.

- Acesso direto à Internet local para Microsoft 365 tráfego

  Cada escritório tem um dispositivo WAN (SD-WAN) definido por software que tem um ou mais circuitos de rede ISP da Internet locais com sua própria conectividade com a Internet por meio de um servidor proxy. Normalmente, isso é implementado como um link WAN para um ISP local que também fornece endereços IP públicos e um servidor DNS local.

- Presença na Internet

  A Contoso é proprietária do nome de domínio público contoso \. com. O site público da Contoso para pedidos de produtos é um conjunto de servidores em um datacenter conectado à Internet no campus de Paris. A Contoso usa um intervalo de endereços IP público /24 na Internet.

A Figura 1 mostra a infraestrutura de rede da Contoso e suas conexões com a Internet.

![A rede Contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: A rede contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso de SD-WAN para conectividade de rede ideal para a Microsoft

A Contoso seguiu os [Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md) para:

- Identificar e diferenciar o tráfego de rede do Microsoft 365
- Enviar conexões de rede de saída localmente
- Evitar hairpins de rede
- Ignorar dispositivos de segurança de rede duplicados

Há três categorias de tráfego de rede para Microsoft 365: *Otimizar,* *Permitir* e *Padrão*. Otimizar e Permitir tráfego é tráfego de rede confiável que é criptografado e protegido nos pontos de extremidade e está destinado à Microsoft 365 rede.

A Contoso decidiu:

- Use a saída direta da Internet para Otimizar e Permitir tráfego de categoria e encaminhar todo o tráfego de categoria padrão para a conexão de internet central baseada em Paris.

- Implante dispositivos SD-WAN em cada escritório como uma maneira simples de seguir esses princípios e obter o desempenho de rede ideal para Microsoft 365 serviços baseados em nuvem.

  Os dispositivos SD-WAN possuem uma porta LAN para a rede do escritório local e várias portas WAN. Uma porta WAN se conecta à rede MPLS. Outro se conecta a um circuito ISP local. O dispositivo SD-WAN roteia o tráfego de rede da categoria Otimizar e Permitir através do link ISP.



## <a name="the-contoso-line-of-business-app-infrastructure"></a>A infraestrutura de aplicativo de linha de negócios da Contoso

A Contoso arquitetou sua infraestrutura de intranet de aplicativo de linha de negócios e servidor para o seguinte:

- As filiais usam servidores de cache locais para armazenar documentos acessados com frequência e sites internos.
- Os hubs regionais usam servidores de aplicativo regionais para os escritórios regionais e as filiais. Esses servidores sincronizam-se com os servidores da matriz de Paris.
- Os datacenters do campus de Paris contêm servidores de aplicativos centralizados que atendem a toda a organização.

A Figura 2 mostra a porcentagem de capacidade de tráfego de rede usada ao acessar servidores na intranet da Contoso.

![A infraestrutura contoso para aplicativos internos](../media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: A infraestrutura contoso para aplicativos internos**

Para os escritórios de hub de satélite ou regionais, 60% dos recursos necessários pelos funcionários podem ser atendidos por servidores de escritórios de hub regionais e satélite. Os 40% adicionais de solicitações de recursos devem passar pelo link WAN para o campus de Paris.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Análise de rede e preparação para Microsoft 365 para empresas

A adoção bem-sucedida de Microsoft 365 para serviços corporativos pelos usuários da Contoso depende da conectividade altamente disponível e performante com a Internet ou diretamente aos serviços de nuvem da Microsoft. A Contoso tomou estas etapas para planejar e implementar conectividade otimizada para Microsoft 365 para serviços de nuvem empresariais:

1. Criar um diagrama de rede WAN da empresa para ajudar no planejamento

   Para iniciar o planejamento de rede, a Contoso criou um diagrama mostrando seus locais de escritório, conectividade de rede existente, dispositivos de perímetro de rede existentes e classes de serviço gerenciadas na rede. Ela usou este diagrama para cada etapa subsequente no planejamento e na implementação da conectividade de rede.

2. Criar um plano para Microsoft 365 conectividade de rede corporativa

   A Contoso usou os [Microsoft 365](microsoft-365-network-connectivity-principles.md) de conectividade de rede e arquiteturas de rede de referência de exemplo para identificar o SD-WAN como sua topologia preferencial para Microsoft 365 conectividade.

3. Analisar a utilização de conexão com a Internet e a largura de banda MPLS-WAN em cada escritório e aumentar a largura de banda conforme necessário

   O uso atual de cada escritório foi analisado e os circuitos foram aumentados, de modo que o tráfego baseado na nuvem previsto Microsoft 365 operaria com uma capacidade média de 20% não utilizado.

4. Otimizar o desempenho dos serviços de rede da Microsoft

   A Contoso determinou o conjunto de pontos de extremidade Office 365, Intune e Azure e firewalls configurados, dispositivos de segurança e outros sistemas no caminho da Internet para obter o desempenho ideal. Os pontos de extremidade para Office 365 tráfego de categoria Otimizar e Permitir foram configurados nos dispositivos SD-WAN para roteamento pelo circuito ISP.

5. Configurar DNS interno

   O DNS precisa ser funcional e ser pesquisado localmente para o tráfego do Microsoft 365.

6. Validar o ponto de extremidade de rede e a conectividade de porta

   A Contoso correu as ferramentas de teste de conectividade de rede da Microsoft para validar a conectividade para Microsoft 365 para serviços de nuvem empresariais.

7. Otimizar computadores de funcionários para conectividade de rede

   Computadores individuais foram verificados para garantir que as atualizações mais recentes do sistema operacional foram instaladas e que o monitoramento de segurança do ponto de extremidade estava ativo em todos os clientes.

## <a name="next-step"></a>Próxima etapa

Saiba como a Contoso está aproveitando seus Serviços de Domínio do Active Directory local na nuvem para [funcionários](contoso-identity.md) e federando autenticação para clientes e parceiros comerciais.

## <a name="see-also"></a>Confira também

[Roteiro de rede para Microsoft 365](networking-roadmap-microsoft-365.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
