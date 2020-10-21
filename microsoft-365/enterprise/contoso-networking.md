---
title: Sistema de rede para a Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Compreenda a infraestrutura de rede da Contoso e como ela usa a tecnologia SD-WAN para o desempenho ideal de rede para o Microsoft 365 para serviços em nuvem corporativos.
ms.openlocfilehash: ca673e6dcbf0f3db4bde33d388598e5f4ffac914
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48637182"
---
# <a name="networking-for-the-contoso-corporation"></a>Sistema de rede para a Contoso Corporation

Para adotar uma infraestrutura incluindo a nuvem, a contoso criou uma mudança fundamental na forma como o tráfego de rede para os serviços em nuvem viaja. Em vez de um modelo de Hub e spoke interno que focaliza a conectividade de rede e o tráfego para o próximo nível da hierarquia do Office, eles mapearam os locais de usuário para conexões locais e de saída da Internet para o local de rede do Microsoft 365 mais próximo na Internet.

## <a name="networking-infrastructure"></a>Infraestrutura de rede

Estes são os elementos de rede que vinculam escritórios da Contoso em todo o mundo:

- Rede WAN de Comutação de Rótulos Multiprotocolo (MPLS)

  Uma rede de WAN MPLS conecta a sede de Paris a escritórios regionais e escritórios regionais a escritórios satélites em uma configuração de spoke e Hub. A rede permite que os usuários acessem servidores locais que fazem parte dos aplicativos de linha de negócios na sede de Paris. Ele também roteia qualquer tráfego genérico da Internet para o escritório de Paris, onde os dispositivos de segurança de rede desdepurar as solicitações. Dentro de cada escritório, os roteadores entregam o tráfego para hosts com fio ou pontos de acesso sem fio em sub-redes, que usam o espaço de endereço IP privado.

- Acesso à Internet direto local para o tráfego do Microsoft 365

  Cada Office tem um dispositivo WAN (SD-WAN) definido pelo software que tem um ou mais circuitos de rede de Internet ISP locais com sua própria conectividade com a Internet por meio de um servidor proxy. Isso é normalmente implementado como um link WAN para um provedor de Internet local que também fornece endereços IP públicos e um servidor DNS local.

- Presença na Internet

  A contoso é proprietária do \. nome de domínio público da contoso. O site público da Contoso para pedidos de produtos é um conjunto de servidores em um datacenter conectado à Internet no campus de Paris. A contoso usa a/24 intervalo de endereços IP públicos na Internet.

A Figura 1 mostra a infraestrutura de rede da Contoso e suas conexões com a Internet.

![A rede contoso](../media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: a rede contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso de SD-WAN para conectividade de rede ideal para a Microsoft

A Contoso seguiu os [Princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md) para:

- Identificar e diferenciar o tráfego de rede do Microsoft 365
- Enviar conexões de rede de saída localmente
- Evitar hairpins de rede
- Ignorar dispositivos de segurança de rede duplicados

Há três categorias de tráfego de rede para o Microsoft 365: *otimizar*, *permitir*e *padrão*. Otimizar e permitir tráfego é o tráfego de rede confiável criptografado e protegido nos pontos de extremidade e destinado à rede 365 da Microsoft.

A Contoso decidiu:

- Use o egresso de Internet direto para otimizar e permitir o tráfego de categoria e encaminhar todo o tráfego de categoria padrão para a conexão de Internet central baseada em Paris.

- Implantar os dispositivos SD-WAN em cada escritório como uma maneira simples de seguir estes princípios e obter o melhor desempenho da rede para os serviços baseados em nuvem da Microsoft 365.

  Os dispositivos SD-WAN possuem uma porta LAN para a rede do escritório local e várias portas WAN. Uma porta WAN conecta-se à sua rede MPLS. Outro se conecta a um circuito de provedor local. O dispositivo SD-WAN roteia o tráfego de rede da categoria Otimizar e Permitir através do link ISP.



## <a name="the-contoso-line-of-business-app-infrastructure"></a>A infraestrutura de aplicativos de linha de negócios da contoso

A contoso arquitetau a infraestrutura de intranet de servidor e aplicativos de linha de negócios para o seguinte:

- As filiais usam servidores de cache locais para armazenar documentos acessados com frequência e sites internos.
- Os hubs regionais usam servidores de aplicativo regionais para os escritórios regionais e as filiais. Esses servidores sincronizam-se com os servidores da matriz de Paris.
- Os datacenters de campus de Paris contêm servidores de aplicativos centralizados que atendem a toda a organização.

A Figura 2 mostra a porcentagem de capacidade de tráfego de rede usada ao acessar servidores na intranet da contoso.

![A infraestrutura da Contoso para aplicativos internos](../media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: infraestrutura da Contoso para aplicativos internos**

Para os escritórios de Hub satélite ou regional, 60% dos recursos necessários para os funcionários podem ser servidos por satélite e servidores de Hub regionais do Office. A porcentagem adicional de solicitações de recursos de 40% deve passar pelo link WAN para o campus de Paris.

## <a name="network-analysis-and-preparation-for-microsoft-365-for-enterprise"></a>Análise de rede e preparação para o Microsoft 365 para empresas

A adoção bem-sucedida do Microsoft 365 for Enterprise Services por usuários da Contoso depende da conectividade de alta disponibilidade e desempenho à Internet ou diretamente aos serviços de nuvem da Microsoft. A contoso adotou estas etapas para planejar e implementar a conectividade otimizada para o Microsoft 365 para serviços de nuvem corporativa:

1. Criar um diagrama de rede WAN da empresa para ajudar no planejamento

   Para iniciar o planejamento de rede, a contoso criou um diagrama mostrando seus locais de escritório, a conectividade de rede existente, os dispositivos de perímetro de rede existentes e as classes de serviço que são gerenciadas na rede. Ela usou este diagrama para cada etapa subsequente no planejamento e na implementação da conectividade de rede.

2. Criar um plano para o Microsoft 365 para conectividade de rede corporativa

   A contoso usou os [princípios de conectividade de rede do Microsoft 365](microsoft-365-network-connectivity-principles.md) e as arquiteturas de rede de referência de exemplo para identificar o SD-WAN como sua topologia preferencial para a conectividade do Microsoft 365.

3. Analisar utilização de conexão com a Internet e largura de banda de MPLS-WAN em cada escritório e aumentar a largura de banda conforme necessário

   Cada uso atual do Office foi analisado, e os circuitos foram aumentados para que o tráfego da Microsoft 365 em nuvem previsto opere com uma média de 20% de capacidade não usada.

4. Otimizar o desempenho para os serviços de rede da Microsoft

   A contoso determinou o conjunto de pontos de extremidade do Office 365, do Intune e do Azure e dos firewalls configurados, dos dispositivos de segurança e de outros sistemas no caminho da Internet para obter o melhor desempenho. Pontos de extremidade do Office 365 otimizar e permitir tráfego de categoria foram configurados nos dispositivos SD-WAN para roteamento através do circuito ISP.

5. Configurar DNS interno

   O DNS precisa ser funcional e ser pesquisado localmente para o tráfego do Microsoft 365.

6. Validar o ponto de extremidade de rede e a conectividade de porta

   A contoso executou ferramentas de teste de conectividade de rede da Microsoft para validar a conectividade para o Microsoft 365 para serviços de nuvem corporativos.

7. Otimizar os computadores do funcionário para conectividade de rede

   Os computadores individuais foram verificados para garantir que as atualizações mais recentes do sistema operacional foram instaladas e que o monitoramento de segurança do ponto de extremidade estava ativo em todos os clientes.

## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-identity.md) como a Contoso está aproveitando seus Serviços de Domínio Active Directory (AD DS) na nuvem para funcionários e autenticação de federação para clientes e parceiros de negócios.

## <a name="see-also"></a>Confira também

[Mapa de rede para o Microsoft 365](networking-roadmap-microsoft-365.md)

[Visão geral do Microsoft 365 para empresas](microsoft-365-overview.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
