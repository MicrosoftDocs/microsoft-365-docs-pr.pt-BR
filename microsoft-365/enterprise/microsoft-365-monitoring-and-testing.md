---
title: Limites de locatário de monitoramento e teste do Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
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
description: Neste artigo, saiba como a Microsoft monitora e testa continuamente os limites do locatário para o Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd0aa3f88de3a8e22ef67283b20ecfae9959cb05
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686884"
---
# <a name="monitoring-and-testing-tenant-boundaries"></a>Monitorando e testando limites do locatário

A Microsoft monitora continuamente e testa explicitamente os pontos fracos e as vulnerabilidades nos limites do locatário, incluindo o monitoramento de invasão, tentativas de violação de permissão e consumo de recursos. Também usamos vários sistemas internos para monitorar continuamente a utilização inadequada dos recursos, o que, se for detectado, acionará a limitação interna.

O Microsoft 365 tem sistemas de monitoramento internos que monitoram continuamente qualquer falha e orientam a recuperação automatizada quando uma falha é detectada. Os sistemas Microsoft 365 analisam desvios no comportamento do serviço e iniciam processos de auto-recuperação internos que estão incorporados ao sistema. O Microsoft 365 também usa o monitoramento externo no qual o monitoramento é realizado de vários locais, tanto de serviços confiáveis de terceiros (para verificação de SLA independente) e de nossos próprios datacenters para gerar alertas. Para diagnósticos, temos logs extensivos, auditoria e rastreamento. Rastreamento e monitoramento granulares nos ajuda a isolar problemas e realizar análise rápida e eficaz de causa raiz.

Embora o Microsoft 365 tenha ações de recuperação automatizadas, sempre que possível, os engenheiros de chamada da Microsoft estão disponíveis 24x7 para investigar todos os escalonamentos de segurança de gravidade 1, e as revisões post-mortem de cada incidente de serviço contribui para o aprendizado e aprimoramento contínuos. Essa equipe inclui engenheiros de suporte, desenvolvedores de produtos, gerentes de programas, gerentes de produtos e liderança sênior. Nossos profissionais on-Call fornecem um backup oportuno e muitas vezes podem automatizar as ações de recuperação, para que, na próxima vez que um evento ocorra, ele possa ser reparado automaticamente.

A Microsoft executa uma revisão completa de incidentes a cada vez que um incidente de segurança do Microsoft 365 ocorre independentemente da magnitude do impacto. Uma revisão pós-incidente consiste em uma análise do que aconteceu, como respondemos e como impedimos incidentes semelhantes no futuro. No interesse da transparência e da responsabilidade, compartilhamos a análise de pós-incidente para qualquer incidente de serviço importante com clientes afetados. Para obter detalhes específicos, confira o [Gerenciamento de incidentes de segurança do Office 365](https://aka.ms/Office365SIM).

## <a name="assume-breach-methodology"></a>Supor metodologia de violação

Com base na análise detalhada de tendências de segurança, a Microsoft defende e destaca a necessidade de investimentos adicionais em processos de segurança reativos e tecnologias que se concentram na detecção e resposta a ameaças emergentes, em vez de apenas a prevenção dessas ameaças. Devido às alterações no panorama de ameaças e na análise detalhada, a Microsoft refinou sua estratégia de segurança para além de evitar brechas de segurança para uma melhor maneira de lidar com violações quando ocorrerem, uma estratégia que considera os principais eventos de segurança não como uma questão de If, mas quando.

Embora as práticas de [brechas de pressuposto](https://www.microsoft.com/TrustCenter/Security/default.aspx) da Microsoft tenham sido realizadas por muitos anos, muitos clientes não sabem do trabalho que está sendo feito nos bastidores para reforçar a nuvem da Microsoft. Supor que a violação é um pensamento que orienta os investimentos em segurança, decisões de design e práticas de segurança operacional. Suponha que a violação seja colocada em aplicativos, serviços, identidades e redes, tratando-os de todos eles, internos e externos, como inseguro e que já foram comprometidos. Embora a estratégia de brechas de supor não tenha sido originada de uma violação real de qualquer serviço de nuvem ou de empresa da Microsoft, foi um reconhecimento de que muitas organizações, no setor, estavam sendo violados apesar de todas as tentativas de evitá-lo. Ao mesmo tempo em que evitar violações é uma parte crucial das operações da organização, essas práticas devem ser continuamente testadas e aumentadas para lidar efetivamente com os adversários modernos e ameaças persistentes avançadas. Para qualquer organização preparar-se para uma violação, ela deve primeiro criar e manter procedimentos de resposta de segurança robustos, repetíveis e totalmente testados.

Embora os processos de segurança de violação, como a modelagem de ameaças, as revisões de código e o teste de segurança sejam muito úteis como parte do [ciclo de vida do desenvolvimento da segurança](https://www.microsoft.com/securityengineering/sdl/), supomos que a violação forneça várias vantagens que ajudam a considerar a segurança geral ao exercer e medir recursos reativos no caso de uma violação.

Na Microsoft, definimos para fazer isso por meio de exercícios de jogos de guerra permanentes e testes de penetração no local de nossos planos de resposta de segurança com o objetivo de melhorar nossa capacidade de detecção e resposta. A Microsoft regularamente simula violações do mundo real, realiza o monitoramento contínuo de segurança e o gerenciamento de incidentes de segurança de práticas para validar e aprimorar a segurança do Microsoft 365, Azure e outros serviços de nuvem da Microsoft.

A Microsoft executa sua estratégia de segurança de brechas usando dois grupos principais:
- Equipes vermelhas (invasores)
- Equipes azuis (defensores)

O Microsoft Azure e o Microsoft 365 Teams separam equipes vermelha de tempo integral e equipes azuis.

Chamado de "[equipe vermelha](https://go.microsoft.com/fwlink/?linkid=518599)", a abordagem é testar sistemas e operações do Azure e Microsoft 365 usando a mesma tática, técnicas e procedimentos que os adversários reais, contra a infraestrutura de produção ao vivo, sem o foreknowledge das equipes de engenharia ou operações. Isso testa os recursos de detecção e resposta de segurança da Microsoft e ajuda a identificar vulnerabilidades de produção, erros de configuração, suposições inválidas e outros problemas de segurança de forma controlada. Cada violação de equipe vermelha é seguida pela divulgação completa entre as duas equipes para identificar lacunas, lidar com as descobertas e melhorar a resposta à violação.

**Observação**: nenhum dado do cliente é direcionado deliberadamente durante a equipe vermelha ou o teste de penetração do site. Os testes são relacionados à infraestrutura e plataformas do Microsoft 365 e do Azure, bem como aos próprios locatários, aplicativos e dados da Microsoft. Os locatários, aplicativos e conteúdo do cliente hospedados no Microsoft 365 ou no Azure nunca são direcionados.

## <a name="red-teams"></a>Equipes vermelhas

A equipe vermelha é um grupo de funcionários em tempo integral dentro da Microsoft que se concentra na violação da infraestrutura, da plataforma e dos próprios locatários e aplicativos da Microsoft. Eles são o adversário dedicado (um grupo de hackers éticos) realizando ataques direcionados e persistentes contra serviços online (infraestrutura, plataformas e aplicativos da Microsoft, mas não para os aplicativos ou conteúdo dos clientes finais).

A função da equipe vermelha é atacar e penetrar em ambientes usando as mesmas etapas que um adversário:
 
![Estágios de violação](../media/office-365-isolation-breach-stages.png)

Entre outras funções, as equipes vermelhas tentam especificamente violar os limites de isolamento de locatários para encontrar bugs ou falhas no nosso design de isolamento.

## <a name="blue-teams"></a>Equipes azuis

A equipe azul é composta de um conjunto dedicado de respondentes de segurança ou membros de todas as organizações de resposta, engenharia e operações de incidentes de segurança. Independentemente de sua forma de fazer, eles são independentes e operam separadamente da equipe vermelha. A equipe azul segue os processos de segurança estabelecidos e usa as ferramentas e tecnologias mais recentes para detectar e responder a ataques e penetração. Da mesma forma que os ataques do mundo real, a equipe azul não sabe quando ou como os ataques da equipe vermelha ocorrerão ou quais métodos podem ser usados. Seu trabalho, seja um ataque de equipe vermelho ou um ataque real, é detectar e responder a todos os incidentes de segurança. Por esse motivo, a equipe azul é continuamente chamada e deve reagir às violações de equipe vermelhas da mesma forma que fariam com qualquer outra violação.

Quando um adversário, como uma equipe vermelha, violou um ambiente, a equipe azul deve:

- Reunir evidências deixadas pelo adversário
- Detectar a evidência como uma indicação de comprometimento
- Alertar a equipe de engenharia e operação adequada (s)
- Fazer a triagem dos alertas para determinar se eles garantem mais investigações
- Coletar o contexto do ambiente para escopo a violação
- Formar um plano de correção para conter ou remover o adversário
- Executar o plano de correção e recuperar de violações

Estas etapas formam a resposta de incidente de segurança que é executada paralelamente ao adversário, conforme mostrado abaixo:
 
![Estágios de resposta de violação](../media/office-365-isolation-breach-response-stages.png)

As violações de equipe vermelhas permitem o exercício da capacidade da equipe azul para detectar e responder a ataques reais de ponta a ponta. O mais importante é que ele permite a resposta de incidentes de segurança do Practiced antes de uma violação autêntica. Além disso, por causa de brechas de equipe vermelhas, a equipe azul aprimora o reconhecimento de situação, que pode ser valioso ao lidar com falhas futuras (seja da equipe vermelha ou de outro adversário). Durante todo o processo de detecção e resposta, a equipe azul produz inteligência acionável e obtém visibilidade sobre as condições reais do (s) ambiente (s) que estão tentando defender. Com frequência, isso é realizado por meio de análise de dados e forenses, realizado pela equipe azul, ao responder a ataques de equipe vermelhos e estabelecer indicadores de ameaça, como indicadores de comprometimento. Assim como a equipe vermelha identifica lacunas na história de segurança, as equipes azuis identificam lacunas em sua capacidade de detectar e responder. Além disso, como as equipes vermelhas modelam ataques do mundo real, a equipe azul pode ser avaliada com precisão em sua capacidade, ou incapacidade, de lidar com adversários determinados e persistentes. Por fim, as violações de equipe vermelhas medem tanto a prontidão quanto o impacto da nossa resposta de violação.
