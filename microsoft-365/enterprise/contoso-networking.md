---
title: Sistema de rede para a Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Compreenda a infraestrutura de rede da Contoso e como ela usa a tecnologia SD-WAN para ter a conectividade de rede de desempenho ideal para serviços baseados na nuvem do Microsoft 365 Enterprise.
ms.openlocfilehash: 0ef9c37755927444276c83a2c5952b5cb96f22ed
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864673"
---
# <a name="networking-for-the-contoso-corporation"></a>Sistema de rede para a Contoso Corporation

**Resumo:** compreenda a infraestrutura de rede da Contoso e como ela usa a tecnologia SD-WAN para ter a conectividade de rede de desempenho ideal para serviços baseados na nuvem do Microsoft 365 Enterprise.

Para adotar uma infraestrutura que inclua a nuvem, os engenheiros de rede da Contoso perceberam a mudança fundamental na maneira como funciona o tráfego de rede para serviços baseados na nuvem. Em vez de um modelo hub-spoke que concentra a conectividade de rede na matriz, eles trabalharam para mapear locais de usuários para saída de Internet local e conexões locais para os locais de rede da Microsoft na Internet.

## <a name="contosos-networking-infrastructure"></a>Infraestrutura de rede da Contoso

Os elementos de rede da Contoso que vinculam seus escritórios em todo o mundo são os seguintes:

- Rede MPLS WAN

  Uma rede MPLS WAN conecta a sede de Paris aos escritórios regionais e esses a filiais em uma configuração hub-spoke. Isso é para os usuários acessarem os servidores locais que compõem os aplicativos da linha de negócios no escritório de Paris. Ele também roteará qualquer tráfego genérico da Internet para o escritório de Paris, onde os dispositivos de segurança de rede verificam as solicitações. Em cada escritório, os roteadores oferecem tráfego para hosts ou pontos de acesso sem fio em sub-redes que usam o espaço privado de endereço IP.

- Acesso direto local à Internet para tráfego do Office 365

  Cada escritório tem um dispositivo SD-WAN com um dos circuitos de rede Internet ISP mais locais, com sua própria conectividade com a Internet por meio de um servidor proxy. Isso normalmente é implementado como um link de WAN em um ISP local que também fornece endereços IP públicos e endereços IP do servidor DNS local para o servidor proxy.

- Presença na Internet

  A Contoso possui o nome de domínio público contoso.com. O site público da Contoso para fazer o pedido de produtos é um conjunto de servidores em um datacenter conectado à Internet no campus de Paris. A Contoso usa um intervalo de endereço IP público /24 na Internet.

A figura 1 mostra a infraestrutura de rede da Contoso e suas conexões com a Internet.

![](./media/contoso-networking/contoso-networking-fig1.png)
 
**Figura 1: Rede da Contoso**

## <a name="use-of-sd-wan-for-optimal-network-connectivity-to-microsoft"></a>Uso de SD-WAN para conectividade de rede ideal para a Microsoft

A Contoso seguiu os [Princípios de conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles):

1. Identificar e diferenciar tráfego de rede do Office 365
2. Enviar conexões de rede de saída localmente
3. Evitar hairpins de rede
4. Ignorar dispositivos de segurança de rede duplicados

Há três categorias de tráfego de rede do Office 365: Otimizar, Permitir e Padrão. Otimizar e Permitir tráfego é o tráfego de rede confiável que é criptografado e protegido nos pontos de extremidade e destinado a data centers da Microsoft.

A Contoso decidiu usar saída direta de Internet para o tráfego de categoria Otimizar e Permitir e para encaminhar todo o tráfego de categoria Padrão para a conexão de Internet central com base em Paris.

A empresa optou por implantar os dispositivos SD-WAN em cada escritório como uma maneira simples de seguir estes princípios e atingir um desempenho ideal de rede para os serviços baseados em nuvem do Microsoft 365.

Os dispositivos SD-WAN têm uma porta LAN para a rede local e várias portas WAN. Uma porta WAN conecta-se à sua rede MPLS e outras portas WAN se conectam aos circuitos ISP locais. O dispositivo SD-WAN direciona o tráfego de rede de categoria Otimizar e Permitir para os links do ISP.

## <a name="contosos-line-of-business-app-infrastructure"></a>Infraestrutura do aplicativo de linha de negócios da Contoso

A Contoso projetou sua infraestrutura de aplicativo e servidor de linha de negócios para o seguinte:

- As filiais usam servidores de cache locais para armazenar documentos acessados com frequência e sites internos.
- Os hubs regionais usam servidores de aplicativo regionais para os escritórios regionais e as filiais. Esses servidores sincronizam-se com os servidores da matriz de Paris.
- O campus de Paris tem os datacenters que contêm os servidores de aplicativo centralizados que atendem toda a organização.

A Figura 2 mostra a porcentagem do tráfego de rede ao acessar os servidores na intranet da Contoso.

![](./media/contoso-networking/contoso-networking-fig2.png)
 
**Figura 2: Infraestrutura da Contoso para aplicativos internos**

Para usuários nas filiais ou hubs regionais, 60% dos recursos de que os funcionários precisam podem ser atendidos por servidores de filiais e hubs regionais. Os outros 40% das solicitações de recursos devem ir pelo link de WAN para o campus de Paris.

## <a name="contosos-network-analysis-and-preparation-of-their-network-for-microsoft-365-enterprise"></a>A preparação e a análise de rede da Contoso para o Microsoft 365 Enterprise

A adoção bem-sucedida dos serviços do Microsoft 365 Enterprise por usuários da Contoso dependem da conectividade de alta disponibilidade e eficaz com a Internet ou diretamente com os serviços em nuvem da Microsoft. A Contoso realizou estas etapas para planejar e implementar a conectividade otimizada com serviços de nuvem do Microsoft 365 Enterprise:

1. Criou um diagrama de rede WAN da empresa para ajudar a planejar

   A Contoso iniciou seu planejamento de rede criando um diagrama que mostra seus locais, a conectividade de rede existente, os dispositivos de perímetro de rede existentes e as classes de serviço que são gerenciadas na rede. Eles usaram este diagrama para cada etapa subsequente no planejamento e na implementação da conectividade de rede.

2. Criou um plano para conectividade de rede do Microsoft 365 Enterprise

   A Contoso usou os [princípios de conectividade de rede do Office 365](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles) e forneceu arquiteturas de rede de referência para determinar o SD-WAN como a topologia preferencial para a conectividade do Office 365.

3. Analisou a utilização da conexão de Internet e a largura de banda MPLS WAN em cada escritório e aumentou a largura de banda conforme o necessário

   Cada escritório foi analisado em relação ao uso atual e os circuitos foram aumentados para que o tráfego com base em nuvem previsto do Microsoft 365 funcionasse com uma média de 20% da capacidade não utilizada.

4. Otimizou o desempenho para os serviços de rede da Microsoft

   A Contoso determinou o conjunto de pontos de extremidade do Office 365, do Intune e do Azure e firewalls configurados, dispositivos de segurança e outros sistemas no caminho da Internet para obter um desempenho ideal. Os pontos de extremidade para o tráfego de categoria Otimizar e Permitir do Office 365 foram configurados para os dispositivos SD-WAN que receberam acesso direto à Internet.

5. Configurou DNS interno

   O DNS precisa ser funcional e ser pesquisado localmente para o tráfego do Office 365.

6. Validou o ponto de extremidade de rede e a conectividade da porta

   A Contoso executou ferramentas de teste de conectividade de rede fornecidas pela Microsoft para validar a conectividade de serviços de nuvem do Microsoft 365 Enterprise.

7. Otimizou computadores de funcionários para a conectividade de rede

   Os computadores individuais foram verificados para garantir que as atualizações mais recentes do sistema operacional foram instaladas e o monitoramento de segurança do ponto de extremidade estava ativo em todos os clientes.

## <a name="next-step"></a>Próxima etapa

[Saiba](contoso-identity.md) como a Contoso está aproveitando o seu provedor de identidade local na nuvem para os funcionários e realizando a federação de autenticação para clientes e parceiros de negócios.

## <a name="see-also"></a>Confira também

[Sistema de rede para o Microsoft 365 Enterprise](networking-infrastructure.md)

[Guia de implantação](deploy-microsoft-365-enterprise.md)

[Guias de laboratório de teste](m365-enterprise-test-lab-guides.md)
