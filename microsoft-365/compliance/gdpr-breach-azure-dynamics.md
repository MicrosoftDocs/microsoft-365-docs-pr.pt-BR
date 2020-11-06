---
title: Notificação de Violação do Azure e do Dynamics 365 no GDPR
description: Como o Azure e o Dynamics 365 protegem contra a violação de dados pessoais e como a Microsoft responderá e notificará se ocorrer uma violação.
keywords: Azure, Microsoft 365, Dynamics 365, documentação da Microsoft 365, GDPR
localization_priority: Priority
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 0cdd3a2d8e158800cef534a1488df0f25e3d232f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920253"
---
# <a name="azure-and-dynamics-365-breach-notification-under-the-gdpr"></a>Notificação de Violação do Azure e do Dynamics 365 no GDPR

O Microsoft Azure leva a sério as suas obrigações estabelecidas pelo Regulamento Geral sobre a Proteção de Dados (RGPD). O Microsoft Azure implanta medidas de segurança amplas para evitar violações de dados. Entre essas medidas, podemos citar controles de segurança físicos e lógicos, bem como processos de segurança automáticos, abrangentes políticas de privacidade e segurança das informações e treinamento sobre privacidade para todos os funcionários.

A segurança está integrada ao Microsoft Azure desde o início, começando com o [Security Development Lifecycle](https://www.microsoft.com/sdl/), um processo de desenvolvimento obrigatório que incorpora metodologias de privacidade por design e privacidade por padrão. O princípio básico da estratégia de segurança da Microsoft é a "suposição de violação", extensão da estratégia de defesa profunda. Ao desafiar constantemente os recursos de segurança do Azure, a Microsoft permanece à frente das ameaças emergentes. Para saber mais sobre a segurança do Azure, veja esses [recursos](https://www.microsoft.com/trustcenter/security/azure-security).

A Microsoft tem um serviço de resposta a incidentes global, 24 horas por dia, 7 dias por semana, que funciona para minimizar os efeitos de ataques ao Microsoft Azure. Certificado por várias auditorias de segurança e conformidade (por exemplo, [ISO/IEC 27018](offering-iso-27018.md)), a Microsoft emprega operações e processos rigorosos em seus datacenters para impedir o acesso não autorizado, incluindo o monitoramento de vídeo 24 horas por dia, 7 dias por semana, funcionários de segurança treinados, cartões inteligentes e controles biométricos.

## <a name="detection-of-potential-breaches"></a>Detecção de possíveis violações

Due to the nature of modern cloud computing, not all data breaches occurring in a customer cloud environment involve Microsoft Azure services. Microsoft employs a shared responsibility model for Azure services to define security and operational accountabilities. Shared responsibility is important when discussing security of a cloud service, because both the cloud services provider and the customer are accountable for portions of cloud security.

Microsoft does not monitor for or respond to security incidents within the customer's realm of responsibility. A customer-only security compromise would not be processed as an Azure security incident and would require the customer tenant to manage the response effort. Customer incident response may involve collaboration with Microsoft Azure [customer support](https://azure.microsoft.com/support/options/), given appropriate service contracts. O Microsoft Azure também oferece vários serviços (por exemplo, [Azure Defender](https://azure.microsoft.com/services/security-center/)) que os clientes podem usar para desenvolver e gerenciar respostas a incidentes de segurança.

O Azure responde a uma possível violação de dados de acordo com o processo de resposta a incidentes de segurança, que é um subconjunto do plano de gerenciamento de incidentes do Microsoft Azure. A resposta a incidentes de segurança do Azure é implementada usando um processo de cinco etapas: Detecção, Avaliação, Diagnóstico, Estabilização e Fechamento. A Equipe de Resposta a Incidentes de Segurança pode alternar entre as etapas de diagnóstico e estabilização conforme o andamento de investigação. Vejamos abaixo um panorama do processo de resposta a incidentes de segurança:

|**Stage**|**Descrição**|
| ------- | ------------- |
| **_1 — Detecção_* _ | Primeira indício de um possível incidente. |
| _*_2 - Avaliação_*_ | Um membro de plantão da equipe de resposta a incidentes avalia o impacto e a gravidade do evento. Com base em evidências, a avaliação pode ou não resultar num escalonamento à equipe de resposta de segurança. |
| _*_3 — Diagnóstico_*_ | Security response experts conduct the technical or forensic investigation, identify containment, mitigation, and workaround strategies. If the security team believes that customer data may have become exposed to an unlawful or unauthorized individual, execution of the Customer Incident Notification process begins in parallel. |
| _*_4 - Estabilização e Recuperação_*_ | A equipe de resposta a incidentes cria um plano de recuperação para atenuar o problema. As etapas de contenção de crise, como colocar em quarentena os sistemas afetados, podem ocorrer imediatamente e em paralelo com o diagnóstico. As atenuações de longo prazo podem ser planejadas, e ocorrer após o risco imediato ter passado. |
| _*_5 - Fechamento e Post-mortem_*_ | A equipe de resposta a incidentes cria um post-mortem que descreve os detalhes do incidente, com a intenção de revisar políticas, procedimentos e processos para evitar a recorrência do evento. |

O white paper [Resposta de segurança do Microsoft Azure na nuvem](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) apresenta mais detalhes sobre como a Microsoft investiga, gerencia e responde a incidentes de segurança no Azure.

Os processos de detecção usados pelo Microsoft Azure foram projetados para detectar eventos que põem em risco a confidencialidade, a integridade e a disponibilidade dos serviços do Azure. Vários eventos podem provocar o início de uma investigação:

- Automated system alerts via internal monitoring and alerting frameworks. These alerts could come in the way of signature-based alarms such as anti-malware, intrusion detection or via algorithms designed to profile expected activity and alert upon anomalies.
- Relatórios internos dos Serviços da Microsoft em execução no Microsoft Azure e no Azure Governamental.
- Security vulnerabilities are reported to the [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via [secure@microsoft.com](mailto:secure@microsoft.com). MSRC works with partners and security researchers around the world to help prevent security incidents and to advance Microsoft product security.
- Relatórios de cliente via [Portal de suporte ao cliente](https://www.windowsazure.com/support/contact/) ou via Portal de Gerenciamento do Azure Governamental ou do Microsoft Azure, que descrevem as atividades suspeitas atribuídas à infraestrutura do Azure (em vez das atividades que ocorrem dentro do escopo de responsabilidade do cliente).
- Security [Red Team and Blue Team](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/) activity. This strategy uses a highly skilled Red Team of offensive Microsoft security experts to uncover and attack potential weaknesses in Azure. The security response Blue Team must detect and defend against the Red Team's activity. Both Red and Blue Team actions are used to verify that Azure security response efforts are effectively managing security incidents. Security Red Team and Blue Team activities are operated under rules of engagement to help ensure the protection of customer data.
- Escalonamentos por operadores de Serviços do Azure. Os funcionários da Microsoft fazem treinamentos para identificar e escalonar possíveis problemas de segurança.

## <a name="azures-data-breach-response"></a>Resposta à violação de dados do Azure

Microsoft assigns the investigation appropriate priority and severity levels by determining the functional impact, recoverability, and information impact of the incident. Both the priority and severity may change over the course of the investigation, based on new findings and conclusions. Security events involving imminent or confirmed risk to customer data are treated as high severity and worked around the clock to resolution. 

O Microsoft Azure categoriza o impacto das informações do incidente nas seguintes categorias de violação:

| _ *Categoria**             | **Definição**                                                                                                                   |
| ------------------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **_Nenhum_* _               | Nenhuma informação foi vazada, alterada, excluída ou comprometida de outra forma.                                                      |
| _*_Violação de Privacidade_*_     | Dados pessoais confidenciais de contribuintes tributários, funcionários, beneficiários, etc. foram acessados ou vazados.                                |
| _*_Violação Proprietária_*_ | Informações confidenciais não classificadas, como informações de infraestrutura crítica protegida (PCII), foram acessadas ou vazadas. |
| _*_Perda de Integridade_*_     | Informações confidenciais ou proprietárias foram alteradas ou excluídas.                                                                     |

A Equipe de Resposta de Segurança trabalha com os engenheiros de segurança do Microsoft Azure e Especialistas no Assunto (EAs) para classificar o evento com base em dados concretos das evidências. Um evento de segurança pode ser classificado como:

- _*False Positive**: An event that meets detection criteria but is found to be part of a normal business practice and may need to be filtered. The service team identifies the root cause for false positives and will address them in a systematic way using detection sources and fine-tuning them as needed.
- **Incidente de Segurança** : Um incidente em que houve acesso criminoso aos Dados do Cliente ou Dados de Suporte armazenados em equipamentos ou instalações da Microsoft, ou acesso não autorizado a tais equipamentos ou instalações resultando na perda, divulgação ou alteração dos Dados do Cliente ou Dados de Suporte.
- **Incidente de Segurança Relatado pelo Cliente (CRSPI)** : Um acesso ilegal ou não autorizado ou o uso de sistemas, equipamentos ou recursos da Microsoft que resultem em divulgação, modificação ou perda de dados de clientes.
- **Privacy Breach** : A subtype of Security Incident involving personal data. Handling procedures are no different than a security incident.

For a CRSPI to be declared, Microsoft must determine that unauthorized access to customer data has or has likely occurred and/or that there is a legal or contractual commitment that notification must occur. It is desired, but not required, that specific customer impact, resource access, and repair steps be known. An incident is generally declared a CRSPI after the conclusion of the Diagnose stage of a security incident. However, the declaration may happen at any point that all pertinent information is available. The security incident manager must establish evidence beyond reasonable doubt that a reportable event has occurred to begin execution of the Customer Incident Notification Process.

Durante a investigação, a equipe de resposta de segurança trabalha com consultores jurídicos globais para ajudar a garantir que a análise forense seja executada de acordo com as obrigações e compromissos legais para com os clientes. Também há restrições significativas sobre a visualização e o tratamento de sistemas e dados do cliente em diversos ambientes operacionais. Dados confidenciais ou sensíveis, bem como dados do cliente não são transferidos do ambiente de produção sem a expressa aprovação por escrito do Gerente de Incidentes registrado no tíquete de incidente correspondente.

A Microsoft confirma que o risco à empresa e ao cliente foi suprimido com êxito e que foram implementadas medidas corretivas. Se necessário, realizam-se etapas de atenuação emergenciais para resolver riscos de segurança imediatos associados ao evento.

Microsoft also completes an internal post-mortem for data breaches. As a part of this exercise, sufficiency of response and operating procedures are evaluated, and any updates that may be necessary to the Security Incident Response SOP or related processes are identified and implemented. Internal postmortems for data breaches are highly confidential records not available to customers. Postmortems may, however, be summarized and included in other customer event notifications. These reports are provided to external auditors for review as part of Azure's routine audit cycle.

## <a name="customer-notification"></a>Notificação de cliente

O Microsoft Azure notifica os clientes e as autoridades regulamentadoras sobre as violações de dados, conforme necessário. A Microsoft conta com uma pesada compartimentalização interna na operação do Azure. Os logs de fluxo de dados também são robustos. Como benefício desse design, a maioria das ocorrências pode estar limitada a clientes específicos. O objetivo é fornecer aos clientes afetados um aviso preciso, acionável e oportuno quando da violação dos seus dados.

After the declaration of a CRSPI, the notification process takes place as expeditiously as possible while still considering the security risks of moving quickly. Generally, the process of drafting notifications occurs as the incident investigation is ongoing. Customer notices are delivered in no more than 72 hours from the time we declared a breach *except* in the following circumstances:

- Microsoft believes that the act of performing a notification increases the risk to other customers. For example, the act of notifying may tip off an adversary causing an inability to remediate.
- Outras circunstâncias extremas ou incomuns investigadas pelo departamento jurídico da Microsoft, o Corporate External and Legal Affairs (CELA) e pelo Gerente de Incidentes Executivo.
- The 72-hour timeline may leave some incident details available. These are provided to customers and regulatory authorities as the investigation proceeds.

O Microsoft Azure fornece aos clientes informações detalhadas permitindo que executem investigações internas e ajudando-os a atender os compromissos com o usuário final, sem atrasar o processo de notificação.

A notificação de uma violação de dados pessoais será enviada ao cliente da forma escolhida pela Microsoft, inclusive por email. A notificação de uma violação de dados será enviada à lista de contatos de segurança fornecida no Azure Defender, que pode ser configurada seguindo-se as [diretrizes de implementação](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se não houver informações de contato na Azure Defender, a notificação será enviada a um ou mais administradores em uma assinatura do Azure. Para garantir que a notificação possa ser entregue, é responsabilidade do cliente garantir que as informações do contato administrativo em cada assinatura aplicável e portal de serviços online estejam corretas.

A equipe do Microsoft Azure ou do Azure Governamental também pode optar por notificar equipes adicionais da Microsoft, como Atendimento ao Cliente (AC) e Gestor(es) de Contas (GC) ou Gestor(es) Técnico(s) de Contas (TC) do cliente. Essas pessoas geralmente mantêm um relacionamento próximo com o cliente e podem facilitar uma correção mais rápida.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Recursos de segurança internos do Microsoft Dynamics 365

O Microsoft Dynamics 365 utiliza a infraestrutura de serviços na nuvem e os recursos de segurança internos para proteger dados usando medidas e mecanismos de segurança. Além disso, o Dynamics 365 fornece um acesso a dados eficiente e colaboração com privacidade e integridade de dados nas seguintes áreas: [identidade segura, proteção de dados, segurança baseada em função e gerenciamento de ameaças](https://www.microsoft.com/trustcenter/security/dynamics365-security).

O Microsoft Dynamics 365 acompanha as mesmas medidas Técnicas e Organizacionais, uma ou mais equipes de serviços do Microsoft Azure assumem a proteção contra os processos de violação de dados. Portanto, qualquer informação documentada no documento de notificação “Violação de Dados do Microsoft Azure” aqui também é análoga ao serviço do Microsoft Dynamics 365.

## <a name="learn-more"></a>Saiba mais

[Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
