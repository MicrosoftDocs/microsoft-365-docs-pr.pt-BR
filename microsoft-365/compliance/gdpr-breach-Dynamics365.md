---
title: Dynamics 365 e notificação de violação no RGPD
description: Como o Dynamics 365 protege contra uma violação de dados pessoais e como a Microsoft responderá e notificará você se ocorrer uma falha.
keywords: Dynamics 365, Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 92979fd66ac2d51c48b7a0836be5eb1133ae242a
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "39266084"
---
# <a name="dynamics-365-and-breach-notification-under-the-gdpr"></a>Dynamics 365 e notificação de violação no RGPD

O Dynamics 365 assume suas obrigações na norma de proteção de dados gerais (RGPD) com seriedade e exige grandes medidas de segurança para proteger contra violações de dados. A Microsoft funciona continuamente para fornecer serviços altamente seguros e de nível empresarial para clientes do Dynamics 365. As informações nesta seção apresentam um resumo da proteção do Microsoft Dynamics 365 contra incidentes de segurança/violação de dados, bem como o processo que adotamos para responder e notificar os clientes.

## <a name="microsoft-dynamics-365-built-in-security-features"></a>Recursos de segurança internos do Microsoft Dynamics 365

O Microsoft Dynamics 365 utiliza a infraestrutura de serviços na nuvem e os recursos de segurança internos para proteger dados usando medidas e mecanismos de segurança. Além disso, o Dynamics 365 fornece um acesso a dados eficiente e colaboração com privacidade e integridade de dados nas seguintes áreas: [identidade segura, proteção de dados, segurança baseada em função e gerenciamento de ameaças](https://www.microsoft.com/trustcenter/security/dynamics365-security).

## <a name="incident-response-training"></a>Treinamento sobre resposta a incidentes

Todo funcionário que trabalha no Microsoft Dynamics 365 faz um treinamento sobre incidentes de segurança e procedimentos de resposta adequados à função desempenhada. Todo funcionário do Microsoft Dynamics 365 faz um treinamento ao iniciar o trabalho e um treinamento anual de atualização nos anos seguintes. O objetivo do treinamento é fornecer ao funcionário uma compreensão básica da abordagem de segurança da Microsoft para que, após a conclusão do treinamento, todos os funcionários entendam:

- A definição de um incidente de segurança.
- A responsabilidade de todos os funcionários quanto ao relato de incidentes de segurança.
- Como escalonar um possível incidente de segurança para a equipe de resposta a incidentes de segurança do Dynamics 365.
- Como a equipe de resposta a incidentes de segurança do Dynamics 365 responde aos incidentes de segurança.
- Preocupações especiais em relação à privacidade, especialmente à privacidade do cliente.
- Onde encontrar informações adicionais sobre segurança e privacidade e contatos de escalonamento.

## <a name="how-does-microsoft-dynamics-365-define-security-incidentpotential-breaches"></a>Como o Microsoft Dynamics 365 define incidentes de segurança/possíveis violações

Um incidente de segurança/uma violação de dados refere-se a eventos como acesso criminoso aos dados do cliente armazenados nos equipamentos ou instalações da Microsoft ou acesso não autorizado a tais equipamentos ou recursos que possa resultar em perda, divulgação ou alteração de dados do cliente. O objetivo da Microsoft ao responder a incidentes de segurança/violação de dados é proteger os dados do cliente e os serviços do Dynamics 365. A abordagem da Microsoft ao gerenciamento de um incidente de segurança está em conformidade com o [National Institute of Standards and Technology](https://www.nist.gov/) (NIST), Special Publication (SP) [800 61](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-61r2.pdf).

A Microsoft não monitora nem responde a incidentes de segurança no domínio de responsabilidade do cliente. Um comprometimento da segurança de responsabilidade somente do cliente não seria processado como um incidente de segurança do Dynamics 365 e exigiria do locatário do cliente o gerenciamento do esforço de resposta. A resposta a incidentes do cliente pode envolver a colaboração com o atendimento ao cliente do Microsoft Dynamics 365, à luz de contratos de serviço adequados.

## <a name="detection-of-potential-breaches"></a>Detecção de possíveis violações

O Dynamics 365 responde a uma possível violação de dados de acordo com o processo de resposta a incidentes de segurança, que é um subconjunto do plano de gerenciamento de incidentes do Microsoft Dynamics 365. A resposta a incidentes de segurança do Dynamics 365 é implementada usando-se um processo de cinco etapas: Detecção, Avaliação, Diagnóstico, Estabilização e Fechamento. A equipe de resposta a incidentes de segurança pode alternar entre as etapas de diagnóstico e estabilização conforme o andamento de investigação. Vejamos abaixo um panorama do processo de resposta a incidentes de segurança:

|**Etapa**|**Descrição**|
|:-----|:-----|
| ***1 - Detecção*** | Primeira indicação de um possível incidente. |
| ***2 - Avaliação*** | Um membro de plantão da equipe de resposta a incidentes avalia o impacto e a gravidade do evento. Com base em evidências, a avaliação pode ou não resultar num escalonamento para a equipe de resposta de segurança. |
| ***3 - Diagnóstico*** | Os especialistas em resposta de segurança realizam a investigação técnica ou forense, identificam estratégias de confinamento, de atenuação e de solução alternativa. Se a equipe de segurança achar que os dados do cliente podem ter sido expostos a um indivíduo criminoso ou não autorizado, a execução do processo de notificação de incidente do cliente começa em paralelo.|
| ***4 - Estabilização e Recuperação*** | A equipe de resposta a incidentes cria um plano de recuperação para atenuar o problema. As etapas de contenção de crise, como colocar em quarentena os sistemas afetados, podem ocorrer imediatamente e em paralelo com o diagnóstico. As atenuações de longo prazo podem ser planejadas, e ocorrer após o risco imediato ter passado. |
| ***5 - Fechamento e Post-mortem*** | A equipe de resposta a incidentes cria um post-mortem que descreve os detalhes do incidente com a intenção de revisar políticas, procedimentos e processos para evitar a recorrência do evento. |

O white paper [Gerenciamento de incidente de segurança do Dynamics](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=266d445f-ea95-42de-9124-4b2118a639ee&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) apresenta mais detalhes sobre como a Microsoft investiga, gerencia e responde a incidentes de segurança no Dynamics 365.

Os processos de detecção usados pelo Microsoft Dynamics 365 foram projetados para detectar eventos que põem em risco a confidencialidade, a integridade e a disponibilidade dos serviços do Dynamics 365. Vários eventos podem provocar o início de uma investigação:

- Alertas de sistema automáticos por monitoramento interno e estruturas de alerta. Esses alertas podem vir na forma de alarmes baseados em assinatura, como antimalware, detecção de invasão ou via algoritmos projetados para analisar a atividade esperada e alertar sobre anomalias.
- Relatórios internos que executam serviços do Microsoft Dynamics 365 implantados na nuvem pública e serviços do Microsoft Dynamics 365 implantados em nuvem soberana.
- As vulnerabilidades de segurança são relatadas ao [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via <secure@microsoft.com>. O MSRC funciona com parceiros e pesquisadores de segurança de diferentes pontos do mundo para ajudar a evitar incidentes de segurança e fazer progredir a segurança dos produtos da Microsoft.
- Os relatórios de cliente que descrevem as atividades suspeitas atribuídas aos serviços do Microsoft Dynamics 365 (em vez de atividades que ocorrem no escopo de responsabilidade do cliente).
- Atividade de segurança da [Equipe Azul e da Equipe Vermelha](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Essa estratégia usa uma equipe Vermelha ofensiva altamente especializada em segurança para descobrir e tratar de falhas possíveis nos serviços do Microsoft Dynamics 365. A equipe Azul de resposta de segurança deve detectar e se proteger contra as atividades da Equipe Vermelha. As ações tanto da Equipe Vermelha quanto da Equipe Azul são usadas para verificar se os esforços de resposta de segurança do Microsoft Dynamics 365 estão gerenciando com eficiência os incidentes de segurança. As atividades de segurança da Equipe Vermelha e da Equipe Azul são operadas de acordo com as exigências de responsabilidade para ajudar a garantir a proteção dos dados do cliente.
- Escalonamentos por operadores de serviços do Microsoft Dynamics 365. Os funcionários da Microsoft realizam treinamentos para identificar e escalonar possíveis problemas de segurança.

## <a name="microsoft-dynamics-365-data-breach-response"></a>Resposta de violação de dados do Microsoft Dynamics 365

A Microsoft atribui a prioridade de investigação e níveis de gravidade adequados determinando o impacto funcional, a capacidade de recuperação e impacto de informações do incidente. Tanto a prioridade quanto a gravidade podem mudar ao longo da investigação, com base em novas descobertas e conclusões. Eventos de segurança que envolvam risco iminente ou confirmado aos dados do cliente são considerados como de alta gravidade e tratados ininterruptamente até a resolução. O Microsoft Dynamics 365 define a violação de privacidade como uma violação de "dados pessoais de um usuário final de serviço online ou de funcionários da Microsoft".

A equipe de resposta de segurança trabalha com os engenheiros de segurança do Microsoft Dynamics 365 e Especialistas no Assunto (EAs) para classificar o evento com base em dados concretos das evidências. Um evento de segurança pode ser classificado como:

- **Falso positivo:** um evento que atende aos critérios de detecção, mas que é considerado como parte de uma prática empresarial normal e talvez precise ser filtrado. A equipe de serviços identificará a causa raiz dos falsos positivos e os abordará de maneira sistemática, aproveitando as fontes de detecção e ajustando-as conforme for necessário.
- **Incidente de segurança:** um incidente em que houve acesso criminoso a dados do cliente ou dados de suporte armazenados em equipamentos ou instalações da Microsoft, ou houve acesso não autorizado a tais equipamentos ou instalações resultando na perda, divulgação ou alteração de Dados do cliente ou Dados de suporte.
- **Incidente de segurança a ser relatado ao cliente (CRSI):** Acesso ilegal ou não autorizado ou uso de sistemas, equipamentos ou instalações da Microsoft que resultem em divulgação, modificação ou perda de dados do cliente.
- **Incidente de Privacidade** : Um subtipo de Incidente de Segurança que envolve dados pessoais. Manipular procedimentos não é diferente de um incidente de segurança.

Para um CRSI ser declarado, a Microsoft deve determinar que o acesso não autorizado aos dados do cliente ocorreu ou muito provavelmente ocorreu e/ou que há um compromisso jurídico ou contratual exigindo a notificação. É recomendável, mas não obrigatório, que as etapas de impacto, acesso a recursos e reparo de um cliente específico sejam notificadas. Um incidente geralmente é declarado como CRSI após a conclusão da etapa Diagnosticar um incidente de segurança. No entanto, a declaração pode ocorrer a qualquer momento em que todas as informações pertinentes estiverem disponíveis. O gerente de incidentes de segurança deve estabelecer evidências acima de dúvida razoável de que um evento a ser relatado ocorreu, a fim de começar a execução do Processo de Notificação do Incidente do Cliente.

Durante a investigação, a equipe de resposta de segurança trabalha com consultores jurídicos globais para ajudar a garantir que a análise forense seja executada de acordo com as obrigações e compromissos legais para com os clientes. Também há restrições significativas sobre a visualização e o tratamento de sistemas e dados do cliente em diversos ambientes operacionais. Dados confidenciais ou sensíveis, bem como dados do cliente não são transferidos do ambiente de produção sem a expressa aprovação por escrito do Gerente de Incidentes registrado no tíquete de incidente correspondente.

A Microsoft confirma que o risco à empresa e ao cliente foi suprimido com êxito e que foram implementadas medidas corretivas. Se necessário, realizam-se etapas de atenuação emergenciais para resolver riscos de segurança imediatos associados ao evento.

A Microsoft também concluiu um post-mortem interno para violações de dados. Como parte deste exercício, a suficiência de respostas e os procedimentos operacionais são avaliados e todas as atualizações que possam ser necessárias para as políticas de segurança interna da Microsoft ou processos relacionados são identificados e implementados. Os postmortems internos para violações de dados são registros altamente confidenciais que não estão disponíveis para os clientes. No entanto, postmortems podem ser resumidos e incluídos nas notificações de evento de outro cliente. Esses relatórios são fornecidos para auditores externos para revisão como parte do ciclo de auditoria de rotina do Dynamics 365.

## <a name="customer-notification"></a>Notificação de cliente

O Microsoft Dynamics 365 notifica os clientes e as autoridades regulamentadoras sobre as violações de dados, conforme necessário. A Microsoft conta com uma pesada compartimentalização interna na operação dos serviços do Dynamics 365. Os logs de fluxo de dados também são robustos. Como benefício desse design, a maioria das ocorrências pode estar limitada a clientes específicos. O objetivo é fornecer aos clientes afetados um aviso preciso, acionável e oportuno quando da violação dos seus dados.

O processo de notificação em um CRSPI declarado ocorrerá o mais rapidamente possível, considerando os riscos de segurança da mudança rápida. Geralmente, o processo de redação de notificações acontece quando a investigação do incidente está em andamento. As notificações dos clientes são entregues imediatamente no momento em que uma violação é declarada, *com exceção* das seguintes circunstâncias:

- A Microsoft acredita que a notificação aumentará o risco para outros clientes. Por exemplo, após uma notificação, um adversário pode ficar sabendo de informações que utilizará para impossibilitar a correção.
- Outras circunstâncias extremas ou incomuns investigadas pelo departamento jurídico da Microsoft e pelo gerente de incidentes executivo.

O Microsoft Dynamics 365 fornece aos clientes informações detalhadas permitindo que executem investigações internas e ajudando-os a atender aos compromissos com o usuário final, sem atrasar o processo de notificação.

A notificação de uma violação de dados pessoais será enviada ao cliente da forma escolhida pela Microsoft, inclusive por email. A notificação de uma violação de dados será enviada à lista de administradores/contatos do cliente (somente os locatários afetados) fornecida na Central de Segurança do Office, configurável pelo administrador do locatário/cliente. Para garantir que a notificação possa ser entregue, é responsabilidade do cliente garantir que as informações de contato administrativas em cada assinatura aplicável e portal de serviços online estejam corretas.

A equipe do Microsoft Dynamics 365 também pode optar por notificar equipes adicionais da Microsoft, como Atendimento ao Cliente (AC) e Gestor(es) de Contas (GC) ou Gestor(es) Técnico(s) de Contas (TC) do cliente. Esses indivíduos geralmente têm um relacionamento próximo com o cliente e podem facilitar uma correção mais rápida.

## <a name="learn-more"></a>Saiba mais

- [Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)