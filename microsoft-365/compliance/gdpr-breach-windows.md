---
title: Notificações do serviço de processador de dados para Windows no âmbito do RGPD
description: Como o serviço de processador de dados para Windows protege contra uma violação de dados pessoais e como a Microsoft irá responder e notificá-lo se uma violação ocorrer.
keywords: Serviço de processador de dados para Windows, Microsoft 365, documentação do Microsoft 365, RGPD
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: bfadeae0f4f0b01197f58f0610d1040da3080922
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023586"
---
# <a name="data-processor-service-for-windows-breach-notification-under-the-gdpr"></a>Notificação de violação do serviço de processador de dados para Windows no âmbito do RGPD

>[!NOTE]
>Este tópico se destina aos participantes do programa de pré-visualização do serviço de processador de dados para Windows e requer a aceitação de termos de uso específicos. Para saber mais sobre o programa e concordar com os termos de uso, acesse [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview).

O serviço de processador de dados para Windows da Microsoft leva muito a sério suas obrigações no âmbito do Regulamento Geral sobre a Proteção de Dados (RGPD). O serviço de processador de dados para Windows da Microsoft adota medidas de segurança abrangentes para protegê-lo contra violações de dados. Essas medidas incluem equipes dedicadas de gerenciamento de ameaças que atuam proativamente para prever, impedir e atenuar acessos mal-intencionados.Medidas de segurança interna como a verificação de portas, verificação de vulnerabilidades de perímetro e detecção de invasores detectam e impedem acessos mal-intencionados, além de processos de segurança automatizados, políticas abrangentes de privacidade e segurança da informação e treinamento de segurança e privacidade para todo o pessoal. 

A segurança é incorporada ao serviço de processador de dados para Windows da Microsoft desde o primeiro momento, começando pelo [Ciclo de Vida de Desenvolvimento de Segurança](https://www.microsoft.com/sdl/), um processo obrigatório de desenvolvimento que incorpora metodologias de privacidade por design e privacidade por padrão. O princípio orientador da estratégia de segurança da Microsoft é “presumir a violação”, uma extensão da estratégia de defesa em profundidade. Ao desafiar constantemente os recursos de segurança do serviço de processador de dados para Windows da Microsoft, a Microsoft consegue se manter à frente das ameaças que surgem constantemente. Para obter mais informações sobre a segurança do serviço de processador de dados para Windows, confira esses [recursos](https://www.microsoft.com/TrustCenter/Security/windows10-security). O serviço de processador de dados para Windows responde a uma possível violação de dados de acordo com o processo de resposta a incidentes de segurança. A resposta a incidentes de segurança do serviço de processador de dados para Windows é implementada por meio de um processo em cinco etapas: Detecção, Avaliação, Diagnóstico, Estabilização e Fechamento. A equipe de Resposta a Incidentes de Segurança pode alternar entre as etapas Diagnóstico e Estabilização à medida que a investigação progride. Abaixo um resumo do processo de resposta a incidentes de segurança: 

|**Stage**|**Descrição**|
| ------- | ------------- |
| ***1 - Detecção*** | Primeira indicação de um possível incidente. |
| ***2 - Avaliação*** | An on-call incident response team member assesses the impact and severity of the event. Based on evidence, the assessment may or may not result in further escalation to the security response team. |
| ***3 - Diagnóstico*** | Os especialistas em resposta de segurança realizam a investigação técnica ou forense, identificam estratégias de confinamento, de atenuação e de solução alternativa. Se a equipe de segurança achar que os dados do cliente podem ter sido expostos a um indivíduo criminoso ou não autorizado, a execução do processo de notificação de incidente do cliente começa em paralelo. |
| ***4 - Estabilização e Recuperação*** | The incident response team creates a recovery plan to mitigate the issue. Crisis containment steps such as quarantining impacted systems may occur immediately and in parallel with diagnosis. Longer term mitigations may be planned which occur after the immediate risk has passed. |
| ***5 - Fechamento e Post-mortem*** | A equipe de resposta a incidentes cria um post-mortem que descreve os detalhes do incidente com a intenção de revisar políticas, procedimentos e processos para evitar a recorrência do evento. |

Os processos de detecção usados pelo serviço de processador de dados para Windows da Microsoft foram projetados para detectar eventos que põem em risco a confidencialidade, a integridade e a disponibilidade do serviço de processador de dados para Windows. Vários eventos podem desencadear uma investigação: 

 - Alertas de sistema automatizados por monitoramento interno e estruturas de alerta. Esses alertas podem vir na forma de alarmes baseados em assinatura, como anti-malware, detecção de invasão ou via algoritmos projetados para analisar a atividade esperada e alertar sobre anomalias.
 - Relatórios internos dos Serviços da Microsoft em execução no Microsoft Azure e no Azure Governamental.
 - As vulnerabilidades de segurança são notificadas ao [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) pelo email [secure@microsoft.com] (mailto:secure@microsoft.com). O MSRC trabalha com parceiros e pesquisadores de segurança do mundo inteiro para ajudar a impedir incidentes de segurança e aprimorar a segurança dos produtos da Microsoft.
 - Relatórios de cliente via Portal de suporte ao cliente ou o Portal de Gerenciamento do Azure Governamental ou do Microsoft Azure, que descrevem as atividades suspeitas atribuídas à infraestrutura do Azure (em vez das atividades que ocorrem dentro do escopo de responsabilidade do cliente).
 - Atividade de segurança da [Equipe Azul e da Equipe Vermelha](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Essa estratégia usa uma equipe Vermelha ofensiva, da Microsoft, altamente especializada em segurança para descobrir e atacar possíveis falhas no Azure. A equipe Azul de resposta de segurança deve detectar e se defender das atividades da Equipe Vermelha. As ações tanto da Equipe Vermelha quanto da Equipe Azul são usadas para verificar se os esforços de resposta de segurança do Azure estão gerenciando com eficiência os incidentes de segurança. As atividades de segurança da Equipe Vermelha e da Equipe Azul são operadas de acordo com as regras de envolvimento para ajudar a garantir a proteção dos dados do cliente.
 - Escalonamento por operadores de Serviços do Azure. Os funcionários da Microsoft são treinados para identificar e escalonar possíveis problemas de segurança.

 ## <a name="data-processor-service-for-windows-data-breach-response"></a>Resposta a violações de dados do serviço de processador de dados para Windows. 

 A Microsoft atribui a prioridade adequada e os níveis de gravidade ao determinar o impacto funcional, a capacidade de recuperação e o impacto das informações do incidente. A prioridade e a severidade podem mudar durante a investigação, com base nas novas descobertas e conclusões. Os eventos de segurança que envolvem riscos iminentes ou confirmados para os dados dos clientes são tratados como de alta gravidade e trabalham o tempo todo até a resolução. O serviço de processador de dados para Windows da Microsoft classifica o impacto sobre as informações exercido pelo incidente nas seguintes categorias de violação: 

| **Categoria**             | **Definição**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| ***Nenhum***               | Nenhuma informação foi vazada, alterada, excluída ou comprometida de outra forma. |
| ***Violação de privacidade***     | Dados pessoais confidenciais de contribuintes tributários, funcionários, beneficiários, etc. foram acessados ou vazados. |
| ***Violação proprietária*** | Informações proprietárias não classificadas, como informações de infraestrutura crítica protegida (PCII), foram acessadas ou vazadas. |
| ***Perda de integridade***     | Informações confidenciais ou proprietárias foram alteradas ou excluídas. |

A equipe de Resposta de Segurança trabalha com os Engenheiros de Segurança e Especialistas no Assunto (SMEs) do serviço de processador de dados para Windows da Microsoft para classificar o evento com base em dados concretos a partir de evidências. Um evento de segurança pode ser classificado como: 

 - **Falso Positivo**: Um evento que atende aos critérios de detecção, mas que é considerado como parte de uma prática empresarial normal e talvez precise ser filtrado. A equipe de serviços identificará a causa raiz dos falsos positivos e os abordará de maneira sistemática, aproveitando as fontes de detecção e ajustando-as conforme for necessário. 
 - **Incidente de Segurança**: Um incidente em que houve acesso criminoso aos Dados do Cliente ou Dados de Suporte armazenados em equipamentos ou instalações da Microsoft, ou acesso não autorizado a tais equipamentos ou instalações resultando na perda, divulgação ou alteração dos Dados do Cliente ou Dados de Suporte. 
 - **Incidente de Segurança Relatável para o Cliente (CRSI)**: um acesso ilegal ou não autorizado ou uso não autorizado dos sistemas, equipamentos ou instalações da Microsoft que resultem em divulgação, modificação ou perda de dados do cliente. 
 - **Violação de Privacidade**: Um subtipo de Incidente de Segurança que envolve dados pessoais. Manipular procedimentos não é diferente de um incidente de segurança. 

 For a CRSI to be declared, Microsoft must determine that unauthorized access to customer data has or has very likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSI after the conclusion of the Diagnose stage of a security incident; however, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process. 

Throughout the investigation, the security response team works closely with global legal advisors to help ensure that forensics are performed in accordance with legal obligations and commitments to customers. There are also significant restrictions on system and customer data viewing and handling in various operating environments. Sensitive or confidential data, as well as Customer Data, are not transferred out of the production environment without explicit written approval from the Incident Manager recorded in the corresponding incident ticket. 

Microsoft verifies that customer and business risk is successfully contained, and that corrective measures are implemented. If necessary, emergency mitigation steps to resolve immediate security risks associated with the event are taken. 

A Microsoft também concluiu um post-mortem interno para violações de dados. Como parte deste exercício, a suficiência de respostas e os procedimentos operacionais são avaliados e todas as atualizações que possam ser necessárias para o SOP de Resposta a Incidentes de Segurança ou processos relacionados são identificados e implementados. Os post-mortens internos para violações de dados são registros altamente confidenciais que não estão disponíveis para os clientes. Por outro lado, os post-mortens poderão ser resumidos e incluídos em outras notificações de eventos enviadas ao cliente. Esses relatórios são fornecidos aos auditores externos para análise como parte do ciclo de auditorias de rotina do serviço de processador de dados para Windows. 

## <a name="customer-notice"></a>Notificação ao cliente

O serviço de processador de dados para Windows da Microsoft notifica as violações aos clientes e autoridades regulatórias conforme o exigido. A Microsoft conta com uma robusta compartimentalização interna para operar o serviço de processador de dados para Windows. Os logs do fluxo de dados também são consistentes. Uma vantagem desse design é que a maioria dos incidentes pode ser filtrada por um escopo para clientes específicos. O objetivo é notificar os clientes afetados de forma precisa, acionável e em tempo hábil quando seus dados forem violados. 

Após a declaração de um CRSPI, o processo de notificação ocorre o mais rapidamente possível, sem deixar de levar em conta os riscos de segurança de uma movimentação muito rápida. Geralmente, o processo de elaboração das notificações ocorre enquanto a investigação do incidente está em andamento. As notificações aos clientes são entregues no mais tardar 72 horas após a declaração de uma violação, com exceção das seguintes situações: 

 - Microsoft believes the act of performing a notification will increase the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate. 
 - Outras circunstâncias extremas ou incomuns investigadas pelo departamento jurídico da Microsoft Corporate External and Legal Affairs (CELA) e pelo gerente de incidentes executivo. 

 O serviço de processador de dados para Windows da Microsoft fornece aos clientes informações detalhadas, permitindo que executem investigações internas e ajudando-os a cumprir seus compromissos com o usuário final, sem que isso atrase indevidamente o processo de notificação. 

A notificação de uma violação de dados pessoal será enviada ao cliente por qualquer meio que a Microsoft selecionar, incluindo via email. A notificação de violação de dados será entregue à lista de contatos de segurança fornecida na Central de Segurança do Azure, que pode ser configurada seguindo as[diretrizes de implementação](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se as informações de contato não forem fornecidas na Central de Segurança do Azure, a notificação é enviada para um ou mais administradores em uma assinatura do Azure. Para garantir que as notificações possam ser entregues com êxito, é responsabilidade do cliente garantir que as informações de contato administrativas em cada assinatura aplicável e o portal de serviços online estejam corretos.

A equipe do serviço de processador de dados para Windows também pode optar por notificar outras equipes da Microsoft, como o Atendimento ao Cliente (CSS) e os Gerentes de Contas (AM) ou Gerentes Técnicos da Conta (TAM) do cliente. Essas pessoas geralmente mantêm um relacionamento próximo com o cliente e podem facilitar uma correção mais rápida. 

Para obter mais informações sobre como a Microsoft detecta e responde a uma violação de dados pessoais, confira [Notificação de violação de dados no RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) no Portal de Confiança do Serviço.