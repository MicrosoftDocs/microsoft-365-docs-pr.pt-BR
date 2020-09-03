---
title: Defendendo os serviços de nuvem da Microsoft 365 contra ataques de negação de serviço
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Neste artigo, saiba como a Microsoft defende seus serviços em nuvem contra ataques de negação de serviço (DoS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21b38950ec06874f8c1d959eeb6a8b60179636e3
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332491"
---
# <a name="defending-microsoft-365-cloud-services-against-denial-of-service-attacks"></a>Defendendo os serviços de nuvem da Microsoft 365 contra ataques de negação de serviço

Os datacenters da Microsoft são protegidos por segurança de defesa profunda que inclui isolamento de perímetro, câmeras de vídeo, equipe de segurança e entradas seguras que usam biometria, SmartCard e autenticação multifator. A segurança de proteção em camadas continua através de cada área do recurso e de cada unidade de servidor físico. A [infraestrutura de nuvem da Microsoft e o grupo de operações](https://www.microsoft.com/cloud-platform/global-datacenters) oferecem a infraestrutura principal e as tecnologias fundamentais para nossos serviços em nuvem. Nossos data centers estão em conformidade com os padrões do setor para segurança física e confiabilidade e são gerenciados, monitorados e administrados pela equipe de operações da Microsoft.

Para proteger ainda mais nossos serviços em nuvem, a Microsoft fornece um sistema de defesa contra DDoS que faz parte dos processos de monitoramento contínuo e teste de penetração do Microsoft Azure. O sistema de defesa de DDoS do Azure é projetado para não apenas resistir a ataques de fora, mas também de outros locatários do Azure. O Azure usa técnicas de detecção e atenuação padrão, como cookies SYN, limitação de taxa e limites de conexão para proteção contra ataques de DDoS.

Os serviços de nuvem da Microsoft estão sujeitos à ameaça de ataques de várias fontes. Para reduzir e proteger contra as várias ameaças de DoS, um sistema de mitigação e detecção de ameaças com base no Azure altamente escalonável e dinâmico foi desenvolvido e implementado com o principal objetivo de proteger a infraestrutura subjacente contra ataques de DoS e ajudar a evitar interrupções de serviço para clientes de serviços de nuvem. O sistema de mitigação do Azure DoS protege o tráfego de entrada, de saída e de região para região.

A maioria dos ataques de DoS é iniciado em relação aos destinos nas camadas de rede (L3) e transporte (L4) do modelo de [interconexão de sistemas abertos](https://docs.microsoft.com/windows-hardware/drivers/network/windows-network-architecture-and-the-osi-model) (OSI). Os ataques direcionados às camadas de L3 e L4 foram projetados para inundar uma interface de rede ou serviço com tráfego de ataques para sobrecarregar recursos e negar a capacidade de responder a tráfego legítimo. Especificamente, os ataques de L3 e L4 tentam saturar a capacidade de links de rede, dispositivos ou serviços ou saturar as CPUs de servidores ou máquinas virtuais que dão suporte a um aplicativo.

Para se proteger contra ataques de L3 e L4, a Microsoft projetou, desenvolveu e implantou uma solução voltada especificamente para proteger a infraestrutura e os alvos de clientes que estão em ataque protegendo essas camadas. A proteção da infra-estrutura garante que o tráfego de ataque destinado a um cliente não resulte em danos de material de apoio ou a qualidade de serviço de rede reduzida para outros clientes. A solução usa dados de amostragem de tráfego de roteadores do datacenter. Esses dados são analisados por um serviço de monitoramento de rede para detectar ataques. Quando um ataque é detectado, os mecanismos de defesa automatizada são necessários.

## <a name="application-level-defenses"></a>Defesas no nível do aplicativo
As equipes de engenharia da Microsoft seguem os padrões rigorosos definidos pela [garantia operacional de segurança da Microsoft](https://www.microsoft.com/SDL/OperationalSecurityAssurance) para ajudar a proteger os dados do cliente. Os serviços de nuvem da Microsoft são criados intencionalmente para suportar uma carga muito alta, bem como para proteger e reduzir contra ataques de negação de serviço de nível de aplicativo. Implementamos uma arquitetura escalada em que os serviços são distribuídos por vários datacenters globais com isolamento regional e recursos de limitação em algumas das cargas de trabalho.

O país ou a região de cada cliente, que o administrador do cliente identifica durante a configuração inicial dos serviços, determina o local de armazenamento principal para os dados do cliente. Os dados do cliente são replicados entre datacenters redundantes de acordo com uma estratégia principal/de backup. Um datacenter principal hospeda o software do aplicativo junto com todos os dados principais do cliente em execução no software. Um data center de backup fornece failover automático. Se o datacenter principal parar de funcionar por qualquer motivo, as solicitações serão redirecionadas para a cópia do software e dos dados do cliente no datacenter de backup. A qualquer momento, os dados do cliente podem ser processados no datacenter principal ou de backup. Distribuir dados entre vários datacenters reduz a área de superfície afetada, caso um datacenter seja atacado. Além disso, os serviços no datacenter afetado podem ser rapidamente redirecionados para o datacenter secundário como um dos mecanismos de recuperação e vice-versa (Redirecionado para o data center principal depois que o serviço é restaurado).

As cargas de trabalho individuais incluem recursos internos que gerenciam a utilização de recursos. Por exemplo, os mecanismos de limitação no Exchange Online e no SharePoint Online fazem parte de uma abordagem em várias camadas para se defender contra ataques de DoS. A limitação para os usuários do Exchange Online baseia-se no nível dos recursos consumidos pelo usuário final, independentemente de os recursos estarem no Active Directory, no armazenamento de informações do Exchange Online ou em qualquer outro lugar. Um orçamento é alocado para cada cliente para limitar os recursos consumidos por um usuário. A limitação do Exchange Online para a atividade do usuário e componentes do sistema baseia-se no [Gerenciamento de carga de trabalho](https://technet.microsoft.com/library/jj150503(v=exchg.150).aspx). Uma carga de trabalho do Exchange Online é um recurso, protocolo ou serviço do Exchange Online que foi explicitamente definido para as finalidades do gerenciamento de recursos do sistema do Exchange Online. Cada carga de trabalho do Exchange Online requer recursos do sistema, como CPU, operações de banco de dados de caixa de correio ou solicitações do Active Directory para executar solicitações de usuário ou trabalho em segundo plano. Exemplos de cargas de trabalho do Exchange Online incluem Outlook na Web, Exchange ActiveSync, migração de caixa de correio e assistentes de caixa de correio. Os administradores de locatários podem gerenciar as configurações de limitação de gerenciamento de carga de trabalho para usuários com o Shell de gerenciamento do Exchange. Há várias formas de limitação que foram implementadas no Exchange Online, incluindo o PowerShell, serviços Web do Exchange e POP e IMAP, Exchange ActiveSync, conexões de dispositivos móveis, destinatários e muito mais. Embora os administradores de implantações locais do Exchange possam configurar políticas de limitação, os administradores não podem configurar políticas de limitação para o Exchange Online.

O gatilho mais comum para limitação no SharePoint Online é o código do modelo de objeto do cliente (CSOM) que executa muitas ações em uma frequência muito alta. Com o CSOM, muitas ações podem ser executadas com uma única solicitação, que pode exceder os limites de uso e fazer com que a limitação por usuário.

Independentemente da atividade que pode resultar em limitação, quando um usuário exceder os limites de uso, o SharePoint Online limita qualquer solicitação adicional dessa conta de usuário, geralmente por um curto período. Enquanto um acelerador de usuário está em vigor, todas as ações desse usuário são limitadas até que a limitação expire, de acordo com os seguintes critérios:
- Para solicitações realizadas pelo usuário diretamente em um navegador, o SharePoint Online redireciona para uma página de informações de limitação e as solicitações falham.
- Para todas as outras solicitações, incluindo chamadas CSOM, o SharePoint Online retorna o código de status HTTP 429 ("muitas solicitações") e as solicitações falham.

Se o processo transgressor continuar a exceder os limites de uso, o SharePoint Online pode bloquear completamente o processo e retornar o código de status HTTP 503 ("serviço não disponível").

## <a name="vulnerability-and-penetration-testing"></a>Teste de vulnerabilidade e penetração
A Microsoft usa muitas [tecnologias e práticas de segurança](https://www.microsoft.com/trustcenter/security/threatmanagement) para [proteger sua infraestrutura de nuvem](https://blogs.technet.microsoft.com/hybridcloud/2015/05/05/protecting-your-datacenter-and-cloud-from-emerging-threats/) e redes locais contra ameaças modernas e sofisticadas, incluindo o uso de componentes e serviços antimalware para serviços de nuvem, máquinas virtuais (VMS) e outros sistemas. Análise avançada de ameaças, que monitora padrões de uso normais para redes, sistemas e usuários e emprega o aprendizado da máquina para sinalizar qualquer comportamento que não seja o teste de penetração comum e normal.

Além de realizar nossos próprios testes de penetração e oferta para nossos clientes em um [programa de teste de penetração unificado de nuvem da Microsoft](https://technet.microsoft.com/mt784683), também envolvemos profissionais de segurança de terceiros que realizam avaliações regulares de vulnerabilidade e testes de penetração em nossos serviços de nuvem. Disponibilizamos os relatórios dessas avaliações de vulnerabilidade de terceiros para download na base de serviços de [confiança de serviço](https://aka.ms/STP) e os portais de [garantia de serviço](https://aka.ms/ServiceAssurance) .
