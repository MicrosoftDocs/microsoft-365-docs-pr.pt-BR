---
title: Serviço de processador de dados da notificação do Windows Enterprise no âmbito do GDPR
description: Como o serviço de processador de dados do Windows Enterprise protege contra uma violação de dados pessoais e como a Microsoft responderá e o notificará se ocorrer uma violação.
keywords: Serviço de processador de dados do Windows Enterprise, Microsoft 365, documentação do Microsoft 365, GDPR
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: siosulli
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 5d0a5563de2443e5af0f3b7efda0947d4f669cee
ms.sourcegitcommit: e03bc2945e63f7f2638257e530056ae9283b45d9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49070895"
---
# <a name="data-processor-service-for-windows-enterprise-breach-notification-under-the-gdpr"></a>Serviço de processamento de dados da notificação de violação do Windows Enterprise sob o GDPR

>[!NOTE]
>This topic is intended for participants in the data processor service for Windows Enterprise preview program and requires acceptance of specific terms of use. To learn more about the program and agree to the terms of use, see [https://aka.ms/WindowsEnterprisePublicPreview](https://aka.ms/WindowsEnterprisePublicPreview).

Microsoft data processor service for Windows Enterprise takes its obligations under the General Data Protection Regulation (GDPR) seriously. Microsoft data processor service for Windows Enterprise takes extensive security measures to protect against data breaches. These include dedicated threat management teams that proactively anticipate, prevent, and mitigate malicious access.  Internal security measures such as port scanning, perimeter vulnerability scanning, and intrusion detection detect and prevent malicious access, as well as automated security processes, comprehensive information security and privacy policies, and security and privacy training for all personnel. 

Security is built into the Microsoft data processor service for Windows Enterprise from the ground up, starting with the [Security Development Lifecycle](https://www.microsoft.com/sdl/), a mandatory development process that incorporates privacy-by-design and privacy-by-default methodologies. The guiding principle of Microsoft's security strategy is to 'assume breach', which is an extension of the defense-in-depth strategy. By constantly challenging the security capabilities of the data processor service for Windows Enterprise, Microsoft can stay ahead of emerging threats. For more information on the data processor service for Windows Enterprise security, please review these [resources](https://www.microsoft.com/TrustCenter/Security/windows10-security) the data processor service for Windows Enterprise responds to a potential data breach according to the security incident response process. The data processor service for Windows Enterprise security incident response is implemented using a five-stage process: Detect, Assess, Diagnose, Stabilize, and Close. The Security Incident Response Team may alternate between the diagnose and stabilize stages as the investigation progresses. An overview of the security incident response process is below: 

|**Stage**|**Descrição**|
| ------- | ------------- |
| **_1 — Detecção_* _ | Primeira indício de um possível incidente. |
| _*_2 - Avaliação_*_ | Um membro de plantão da equipe de resposta a incidentes avalia o impacto e a gravidade do evento. Com base em evidências, a avaliação pode ou não resultar num escalonamento à equipe de resposta de segurança. |
| _*_3 — Diagnóstico_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 - Estabilização e Recuperação_*_ | A equipe de resposta a incidentes cria um plano de recuperação para atenuar o problema. As etapas de contenção de crise, como colocar em quarentena os sistemas afetados, podem ocorrer imediatamente e em paralelo com o diagnóstico. As atenuações de longo prazo podem ser planejadas, e ocorrer após o risco imediato ter passado. |
| _*_5 — Fechamento e Post-mortem_*_ | A equipe de resposta a incidentes cria um post-mortem que descreve os detalhes do incidente com a intenção de revisar políticas, procedimentos e processos para evitar a recorrência do evento. |

The detection processes used by Microsoft data processor service for Windows Enterprise are designed to discover events that risk the confidentiality, integrity, and availability of the data processor service for Windows Enterprise. Several events can trigger an investigation: 

 - Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
 - Relatórios internos dos Serviços da Microsoft em execução no Microsoft Azure e no Azure Governamental.
 - Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com] (mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
 - Relatórios de cliente via Portal de Suporte ao Cliente ou via Portal de Gerenciamento do Azure Governamental ou do Microsoft Azure, que descrevem as atividades suspeitas atribuídas à infraestrutura do Azure (em vez das atividades que ocorrem dentro do escopo de responsabilidade do cliente).
 - Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team’s activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
 - Escalonamentos por operadores de Serviços do Azure. Os funcionários da Microsoft fazem treinamentos para identificar e escalonar possíveis problemas de segurança.

 ## <a name="data-processor-service-for-windows-enterprise-data-breach-response"></a>Serviço de processador de dados para a resposta da violação de dados do Windows Enterprise 

 Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. Microsoft data processor service for Windows Enterprise categorizes the information impact of the incident into the following breach categories: 

| _ *Categoria**             | **Definição**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Nenhum_* _               | Nenhuma informação foi removida, alterada, apagada ou de outra forma comprometida. |
| _*_Violação de Privacidade_*_     | Dados pessoais confidenciais de contribuintes, funcionários, beneficiários, etc., foram acessados ou removidos. |
| _*_Violação de Propriedade_*_ | Informações proprietárias não-classificadas, tais como informações de infra-estrutura crítica protegida (PCII), foram acessadas ou removidas. |
| _*_Perda de integridade_*_     | Informações confidenciais ou proprietárias foram alteradas ou excluídas. |

The Security Response Team works with Microsoft data processor service for Windows Enterprise Security Engineers and SMEs to classify the event based on factual data from the evidence. A security event may be classified as: 

 - _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team will identify the root cause for false positives and will address them in a systematic way leveraging detection sources and fine-tuning them as needed. 
 - **Incidente de Segurança** : Um incidente em que houve acesso criminoso aos Dados do Cliente ou Dados de Suporte armazenados em equipamentos ou instalações da Microsoft, ou acesso não autorizado a tais equipamentos ou instalações resultando na perda, divulgação ou alteração dos Dados do Cliente ou Dados de Suporte. 
 - **Incidente de Segurança Relatável para o Cliente (CRSI)** : um acesso ilegal ou não autorizado ou uso não autorizado dos sistemas, equipamentos ou instalações da Microsoft que resultem em divulgação, modificação ou perda de dados do cliente. 
 - **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident. 

 Para um CRSI ser declarado, a Microsoft deve determinar que o acesso não autorizado aos dados do cliente ocorreu, ou que muito provavelmente ocorreu e/ou que há um compromisso jurídico ou contratual exigindo a notificação. É desejado, mas não obrigatório, que as etapas de impacto, acesso a recursos e reparo de um cliente específico sejam notificadas. Um incidente geralmente é declarado como CRSI após a conclusão do estágio Diagnóstico de um incidente de segurança. No entanto, a declaração pode ocorrer a qualquer momento quando todas as informações pertinentes estiverem disponíveis. O gerente de incidentes de segurança deve estabelecer evidências acima da dúvida razoável de que um evento a ser relatado ocorreu, a fim de começar a execução do processo de notificação do incidente de cliente. 

Durante a investigação, a equipe de resposta de segurança trabalha com consultores jurídicos globais para ajudar a garantir que a análise forense seja executada de acordo com as obrigações e compromissos legais para com os clientes. Também há restrições significativas sobre a visualização e o tratamento de sistemas e dados do cliente em diversos ambientes operacionais. Dados confidenciais ou sensíveis, bem como dados do cliente não são transferidos do ambiente de produção sem a expressa aprovação por escrito do Gerente de Incidentes registrado no tíquete de incidente correspondente. 

A Microsoft confirma que o risco à empresa e ao cliente foi suprimido com êxito e que foram implementadas medidas corretivas. Se necessário, realizam-se etapas de atenuação emergenciais para resolver riscos de segurança imediatos associados ao evento. 

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of the data processor service for Windows Enterprise routine audit cycle. 

## <a name="customer-notice"></a>Notificação ao cliente

Microsoft data processor service for Windows Enterprise notifies customers and regulatory authorities of data breaches as required. Microsoft relies on heavy internal compartmentalization in the operation of the data processor service for Windows Enterprise. Data flow logs are also robust. As a benefit of this design, most incidents can be scoped to specific customers. The goal is to provide impacted customers with an accurate, actionable, and timely notice when their data has been breached. 

After the declaration of a CRSI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach except for the following circumstances: 

 - A Microsoft acredita que a notificação aumentará o risco para outros clientes. Por exemplo, após uma notificação, um adversário pode ficar sabendo de informações que utilizará para impossibilitar a correção. 
 - Outras circunstâncias extremas ou incomuns investigadas pelo departamento jurídico da Microsoft, o Corporate External and Legal Affairs (CELA) e pelo Gerente de Incidentes Executivo. 

 O serviço de processador de dados da Microsoft para o Windows Enterprise fornece aos clientes informações detalhadas, permitindo que eles realizem investigações internas e os ajudem a cumprir os compromissos do usuário final, sem atrasar indevidamente o processo de notificação. 

A notificação de uma violação de dados pessoais será enviada ao cliente da forma escolhida pela Microsoft, inclusive por email. A notificação de uma violação de dados será enviada à lista de contatos de segurança fornecida no Azure Defender, que pode ser configurada seguindo-se as [diretrizes de implementação](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se não houver informações de contato na Azure Defender, a notificação será enviada a um ou mais administradores em uma assinatura do Azure. Para garantir que a notificação possa ser entregue, é responsabilidade do cliente garantir que as informações do contato administrativo em cada assinatura aplicável e portal de serviços online estejam corretas.

A equipe do serviço de processador de dados do Windows Enterprise também pode optar por notificar outras equipes da Microsoft, como o Atendimento ao cliente (CSS) e os Gerentes de contas (AM) ou Gerentes Técnicos da Conta (TAM) do cliente. Essas pessoas geralmente mantêm um relacionamento próximo com o cliente e podem facilitar uma correção mais rápida. 

Para obter mais informações sobre como a Microsoft detecta e responde a uma violação de dados pessoais, confira [Notificação de violação de dados no RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) no Portal de Confiança do Serviço.
