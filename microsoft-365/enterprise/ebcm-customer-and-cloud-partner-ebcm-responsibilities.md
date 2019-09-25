---
title: Responsabilidades do parceiro de nuvem e do cliente sobre a continuidade de negócios corporativos
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Entenda o que a Microsoft faz durante um incidente de serviço para que você possa preparar melhor seus planos de continuidade de negócios.
ms.openlocfilehash: 9bbf73c736a4391a51edd451db7d23869aa36603
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122341"
---
# <a name="enterprise-business-continuity-management-customer-and-cloud-partner-responsibilities"></a>Responsabilidades do parceiro de nuvem e do cliente sobre o gerenciamento da continuidade de negócios corporativos

Obter os serviços de nuvem da Microsoft 365 para seus usuários é uma parceria entre a sua organização e a Microsoft. A Microsoft fornece os serviços e você é responsável pela conexão de pontos de extremidade do cliente, gerenciando as identidades, o acesso e como esses serviços são usados. Há responsabilidades compartilhadas, como a infraestrutura de diretórios e de identidade. Este artigo aborda alguns dos itens fundamentais que você precisa considerar para manter sua empresa funcionando em caso de um incidente de serviço; ele ajuda a definir expectativas em relação ao que a Microsoft fará durante um incidente de serviço.

## <a name="transparency-during-service-incidents"></a>Transparência durante incidentes de serviço

Como um parceiro confiável, a Microsoft cria serviços de nuvem altamente resistentes e acompanha procedimentos estruturados para resolver incidentes de serviço, caso aconteçam. Quando um incidente de serviço ocorre, a Microsoft reconhece que comunicações **em tempo**, **direcionadas** e **precisas** são essenciais para os clientes.

## <a name="timely"></a>Em tempo
A Microsoft notifica os administradores do Microsoft 365 atualizando o SDH (Painel de Integridade do Serviço) específico dos locatários no Portal de administração do Microsoft 365. As atualizações do incidente do serviço normalmente são fornecidas a cada hora. Se um período diferente for necessário, manteremos você informado sobre alterações nas postagens de comunicação do SHD.

## <a name="targeted"></a>Direcionadas
Na maioria dos casos, quando nossos sistemas de monitoramento detectam um problema, podemos identificar a base de clientes afetada, seja de um único cliente ou mesmo de uma região, e direcionar as comunicações necessárias para esses clientes. Assim você consegue saber o que precisa sobre a sua empresa e não se distrai com notificações de ruído que não causam impacto sobre você. Por exemplo, se o banco de dados de uma caixa de correio específica for afetado, podemos identificar com exatidão quais clientes têm usuários na infraestrutura afetada e direcionar nossas comunicações para eles. Se o escopo do impacto do incidente não estiver claro, ampliaremos nossas comunicações para o grupo mais amplo de clientes que possam ser afetados.

## <a name="highly-avaliable"></a>Altamente disponível
A Microsoft mantém vários canais para comunicações de status de serviço que os clientes podem usar.

- Caso o Centro de administração ou o Painel de integridade do serviço no Centro de administração não estejam disponíveis, você pode monitorar o status do serviço usando nosso [site de backup](https://status.office365.com/).
- Mantemos a conta [@MSFT365Status](https://twitter.com/msft365status?lang=en) no Twitter, pela qual responderemos aos relatórios de impacto e postaremos atualizações de eventos de impacto do SHD.
- O aplicativo de Administração para administradores de locatários do Microsoft 365 permite que você se conecte com o status do serviço do Microsoft 365 da sua organização em qualquer lugar. Os administradores de locatários poderão visualizar nos seus dispositivos móveis as informações sobre a integridade do serviço e as atualizações de status de manutenção. Para saber mais, visite as [Perguntas frequentes do aplicativo de administração](https://docs.microsoft.com/pt-BR/office365/admin/admin-overview/admin-mobile-app?view=o365-worldwide).
- A [API de Comunicações do Serviço do Microsoft 365](https://docs.microsoft.com/pt-BR/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity#office-365-service-communications-api) permite acessar as comunicações do serviço para que você possa monitorar o seu ambiente com mais facilidade. Você pode se conectar à API, receber dados de integridade de serviço em tempo real e publicar as informações em um painel interno para informar os incidentes aos usuários corporativos. Distribuir internamente as informações pode diminuir seu tráfego de assistência técnica durante uma falha.
- Para grandes incidentes, a Microsoft publica PIR (Revisões Pós-Incidente) no SHD do Centro de administração. As PIRs contêm informações importantes sobre o incidente para ajudá-lo a entender a natureza da falha. Normalmente ela inclui as seguintes seções:
    - impacto ao usuário
    - escopo de impacto
    - data e hora de início do incidente
    - causa principal
    - ações tomadas
    - próximas etapas
- As comunicações auxiliares, como avisos de alterações futuras, novos recursos ou manutenções planejadas, ficam disponíveis no Centro de Mensagens do Microsoft 365.
- Para obter mais informações, confira o [Guia de Continuidade e Integridade do Serviço](https://docs.microsoft.com/pt-BR/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) para saber mais sobre os diferentes canais de comunicação e como monitorar a integridade do serviço.
 
O fornecimento de acesso aos serviços online da Microsoft 365 é uma parceria entre a sua organização e a Microsoft. O gráfico a seguir resume o equilíbrio de responsabilidade da Microsoft e do cliente durante um incidente de serviço e durante as operações regulares.

![equilíbrio de responsabilidades do cliente e da Microsoft](media\ebcm\responsibilities.png)

## <a name="your-environment---service-continuity"></a>Seu ambiente – continuidade do serviço
Ao pensar no seu plano de continuidade, tome cuidado com os eventos que possam afetar sua organização e a capacidade geral de se comunicar. Em um alto nível, há três fatores que podem afetar sua empresa.

### <a name="people"></a>Pessoas
Considere os eventos que causam impacto à sua força de trabalho, como um desastre natural ou uma epidemia. Geralmente isso é ignorado, devido à natureza improvável de um impacto em larga escala, se a sua força de trabalho estiver amplamente distribuída. No entanto, se uma grande porcentagem da força de trabalho não estivesse ativa, sua empresa continuaria funcionando? Como atenuar isso?

### <a name="location"></a>Locais
Muitas organizações exigem que os funcionários estejam em locais físicos ou de rede específicos para se conectarem aos sistemas corporativos e serviços de nuvem.  
A Microsoft publica os [princípios de conectividade de rede](https://docs.microsoft.com/pt-BR/office365/enterprise/office-365-network-connectivity-principles) que orientam as empresas, com as práticas recomendadas para a configuração de conectividade de rede para os recursos de nuvem. Entre os exemplos de otimização estão a implementação das VPNs de túnel dividido para permitir conexões diretamente da rede de um usuário, em vez de um túnel VPN.  Embora esses princípios de conectividade sejam importantes para a manutenção de conexões de baixa latência, a resiliência de serviços exige métodos alternativos de se conectar a recursos corporativos para colaboração geral.

### <a name="systems"></a>Sistemas
Muitas soluções de colaboração dependem de sistemas, como a WAN (rede de longa distância) da empresa. Como sua organização responderia, caso esses sistemas não estivessem disponíveis?
Esse gráfico representa os problemas que podem afetar mais de uma área. A tabela a seguir fornece exemplos a considerar

![venn-diagram](media\ebcm\venn-diagram.png)

Seus planos de continuidade devem considerar todas essas áreas. Por exemplo, se você quiser que os usuários estejam na rede corporativa e uma tempestade de neve ocorrer, como os usuários terão acesso aos principais recursos? Se a neve impedir o acesso ao escritório e houver a necessidade de que os engenheiros de serviço se conectem à rede corporativa, existe uma política que impõe que eles estejam em posse de seus laptops corporativos em suas residências?
