---
title: Azure e notificação de violação no RGPD
description: Como o Azure protege contra uma violação de dados pessoais e como a Microsoft responderá e notificará você se ocorrer uma falha.
keywords: Azure, Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: GDPR
ms.openlocfilehash: 7e614554f73f154828536cb4064a5dcf9ec23c26
ms.sourcegitcommit: 6e2a54ec395eaef4c4658ca52322c3d0f184ca02
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34698323"
---
# <a name="azure-and-breach-notification-under-the-gdpr"></a>Azure e notificação de violação no RGPD

O Microsoft Azure leva a sério as suas obrigações estabelecidas pelo Regulamento Geral sobre a Proteção de Dados (RGPD). O Microsoft Azure implanta medidas de segurança amplas para evitar violações de dados. Entre essas medidas, podemos citar controles de segurança físicos e lógicos, bem como processos de segurança automáticos, abrangentes políticas de privacidade e segurança das informações e treinamento sobre privacidade para todos os funcionários.

A segurança está integrada ao Microsoft Azure desde o início, começando com o [Security Development Lifecycle](https://www.microsoft.com/sdl/), um processo de desenvolvimento obrigatório que incorpora metodologias de privacidade por design por padrão. O princípio básico da estratégia de segurança da Microsoft é a "suposição de violação", extensão da estratégia de defesa profunda. Ao desafiar constantemente os recursos de segurança do Azure, a Microsoft permanece à frente das ameaças emergentes. Para saber mais sobre a segurança do Azure, veja estes [recursos](https://www.microsoft.com/trustcenter/security/azure-security).

A Microsoft tem um serviço de resposta a incidentes global, 24 horas por dia, 7 dias por semana, que funciona para minimizar os efeitos de ataques ao Microsoft Azure. Certificado por várias auditorias de segurança e conformidade (por exemplo, [ISO/IEC 27018](https://www.microsoft.com/trustcenter/compliance/iso-iec-27018)), a Microsoft emprega operações e processos rigorosos em seus datacenters para impedir o acesso não autorizado, incluindo o monitoramento de vídeo 24 horas por dia, 7 dias por semana, funcionários de segurança treinados, cartões inteligentes e controles biométricos.

## <a name="detection-of-potential-breaches"></a>Detecção de possíveis violações

Devido à natureza da computação em nuvem moderna, nem todas as violações de dados que ocorrem em um ambiente de nuvem de cliente envolvem serviços do Microsoft Azure. A Microsoft emprega um modelo de responsabilidade compartilhada para os serviços do Azure definirem as responsabilidades operacionais e de segurança. A responsabilidade compartilhada é particularmente importante quando se discute a segurança de um serviço de nuvem, porque tanto o provedor de serviços de nuvem quanto o cliente têm a sua cota de responsabilidade pela segurança na nuvem.

A Microsoft não monitora nem responde a incidentes de segurança no domínio de responsabilidade do cliente. Um comprometimento de segurança causado pelo cliente não seria processado como um incidente de segurança do Azure e exigiria do locatário do cliente o gerenciamento do esforço de resposta. A resposta a incidentes do cliente pode envolver a colaboração com o [atendimento ao cliente](https://azure.microsoft.com/support/options/) do Microsoft Azure, à luz de contratos de serviço adequados. O Microsoft Azure também oferece vários serviços (por exemplo, a [Central de Segurança do Azure](https://azure.microsoft.com/services/security-center/)) que os clientes podem usar para desenvolver e gerenciar respostas a incidentes de segurança.

O Azure responde a uma possível violação de dados de acordo com o processo de resposta a incidentes de segurança, que é um subconjunto do plano de gerenciamento de incidentes do Microsoft Azure. A resposta a incidentes de segurança do Azure é implementada usando-se um processo de cinco etapas: Detecção, Avaliação, Diagnóstico, Estabilização e Fechamento. A equipe de resposta a incidentes de segurança pode alternar entre as etapas de diagnóstico e estabilização conforme o andamento de investigação. Vejamos abaixo um panorama do processo de resposta a incidentes de segurança:

|**Etapa**|**Descrição**|
|:-----|:-----|
| ***1 - Detecção*** | Primeira indicação de um possível incidente. |
| ***2 - Avaliação*** | Um membro de plantão da equipe de resposta a incidentes avalia o impacto e a gravidade do evento. Com base em evidências, a avaliação pode ou não resultar num escalonamento para a equipe de resposta de segurança. |
| ***3 - Diagnóstico*** | Os especialistas em resposta de segurança realizam a investigação técnica ou forense, identificam estratégias de confinamento, de atenuação e de solução alternativa. Se a equipe de segurança achar que os dados do cliente podem ter sido expostos a um indivíduo criminoso ou não autorizado, a execução do processo de notificação de incidente do cliente começa em paralelo.|
| ***4 - Estabilização e Recuperação*** | A equipe de resposta a incidentes cria um plano de recuperação para atenuar o problema. As etapas de contenção de crise, como colocar em quarentena os sistemas afetados, podem ocorrer imediatamente e em paralelo com o diagnóstico. As atenuações de longo prazo podem ser planejadas, e ocorrer após o risco imediato ter passado. |
| ***5 - Fechamento e Post-mortem*** | A equipe de resposta a incidentes cria um post-mortem que descreve os detalhes do incidente com a intenção de revisar políticas, procedimentos e processos para evitar a recorrência do evento. |

O white paper [Resposta de segurança do Microsoft Azure na nuvem](https://gallery.technet.microsoft.com/Azure-Security-Response-in-dd18c678) apresenta mais detalhes sobre como a Microsoft investiga, gerencia e responde a incidentes de segurança no Azure.

Os processos de detecção usados pelo Microsoft Azure foram projetados para detectar eventos que põem em risco a confidencialidade, a integridade e a disponibilidade dos serviços do Azure. Vários eventos podem provocar o início de uma investigação:

- Alertas de sistema automatizados por monitoramento interno e estruturas de alerta. Esses alertas podem vir na forma de alarmes baseados em assinatura, como anti-malware, detecção de invasão ou via algoritmos projetados para analisar a atividade esperada e alertar sobre anomalias.
- Relatórios internos dos serviços Microsoft em execução no Microsoft Azure e no Azure Governamental.
- As vulnerabilidades de segurança são relatadas ao [Microsoft Security Response Center (MSRC)](https://technet.microsoft.com/security/dn440717) via <secure@microsoft.com>. O MSRC funciona com parceiros e pesquisadores de segurança de diferentes pontos do mundo para ajudar a evitar incidentes de segurança e fazer progredir a segurança dos produtos da Microsoft.
- Relatórios de cliente via [Portal de suporte ao cliente](http://www.windowsazure.com/support/contact/) ou o Portal de Gerenciamento do Azure Governamental ou do Microsoft Azure, que descrevem as atividades suspeitas atribuídas à infraestrutura do Azure (em vez das atividades que ocorrem dentro do escopo de responsabilidade do cliente).
- Atividade de segurança da [Equipe Azul e da Equipe Vermelha](https://azure.microsoft.com/blog/red-teaming-using-cutting-edge-threat-simulation-to-harden-the-microsoft-enterprise-cloud/). Essa estratégia usa uma Equipe Vermelha ofensiva altamente especializada em segurança da Microsoft para descobrir e tratar de falhas possíveis no Azure. A Equipe Azul de resposta de segurança deve detectar e se proteger contra atividades da Equipe Vermelha. As ações tanto da Equipe Vermelha quanto da Equipe Azul são usadas para verificar se os esforços de resposta de segurança do Azure estão gerenciando com eficiência os incidentes de segurança. As atividades de segurança da Equipe Vermelha e da Equipe Azul são operadas de acordo com regras de interação para ajudar a garantir a proteção dos dados do cliente.

-   Escalonamentos por operadores de Serviços do Azure. Os funcionários da Microsoft fazem treinamentos para identificar e escalonar possíveis problemas de segurança.

## <a name="azures-data-breach-response"></a>Resposta de violação de dados do Azure

A Microsoft atribui a prioridade de investigação e níveis de gravidade adequados determinando o impacto funcional, a capacidade de recuperação e impacto de informações do incidente. Tanto a prioridade quanto a gravidade podem mudar ao longo da investigação, com base em novas descobertas e conclusões. Eventos de segurança que envolvam risco iminente ou confirmado aos dados do cliente são considerados como de alta gravidade e tratados ininterruptamente até a resolução. O Microsoft Azure categoriza o impacto de informações do incidente nas seguintes categorias da violação:

|**Categoria**|**Definição**|
|:-----|:-----|
| ***Nenhum*** | Nenhuma informação foi vazada, alterada, excluída ou comprometida de outra forma. |
| ***Violação de privacidade*** | Dados pessoais confidenciais de contribuintes tributários, funcionários, beneficiários, etc. foram acessados ou vazados. |
| ***Violação proprietária*** | Informações proprietárias não classificadas, como informações de infraestrutura crítica protegida (PCII), foram acessadas ou vazadas. |
| ***Perda de integridade*** | Informações confidenciais ou proprietárias foram alteradas ou excluídas. |

A equipe de resposta de segurança trabalha com os engenheiros de segurança do Microsoft Azure e Especialistas no Assunto (EAs) para classificar o evento com base em dados concretos das evidências. Um evento de segurança pode ser classificado como:

- **Falso positivo:** um evento que atende aos critérios de detecção, mas se descobre que ele faz parte da prática normal de negócios e talvez precise ser filtrado. A equipe de serviços identificará a causa raiz de falsos positivos e os resolverá de forma sistemática, aproveitando as fontes de detecção e <span id="_Toc350859432" class="anchor"></span>ajustando-as conforme necessário.
- **Incidente de segurança:** um incidente em que houve acesso criminoso a dados do cliente ou dados de suporte armazenados em equipamentos ou instalações da Microsoft, ou houve acesso não autorizado a tais equipamentos ou instalações resultando na perda, divulgação ou alteração de Dados do cliente ou Dados de suporte.
- **Incidente de segurança a ser relatado ao cliente (CRSI):** um acesso ou uso criminoso ou não autorizado de sistemas, equipamentos ou instalações da Microsoft que resultem em divulgação, modificação ou perda de dados do cliente.
- **Violação de privacidade:** um subtipo do incidente de segurança que envolve dados pessoais. Os procedimentos de tratamento são os mesmos que os de um incidente de segurança.

Para um CRSI ser declarado, a Microsoft deve determinar que o acesso não autorizado aos dados do cliente ocorreu e/ou que há um compromisso jurídico ou contratual exigindo a notificação. É desejado, mas não obrigatório, que as etapas de impacto, acesso a recursos e reparo de um cliente específico sejam notificadas. Um incidente geralmente é declarado como CRSI após a conclusão da etapa Diagnóstico de um incidente de segurança. No entanto, a declaração pode ocorrer a qualquer momento quando todas as informações pertinentes estiverem disponíveis. O gerente de incidentes de segurança deve estabelecer evidências acima de dúvida razoável de que um evento a ser relatado ocorreu, a fim de começar a execução do Processo de Notificação do Incidente do Cliente.

Durante a investigação, a equipe de resposta de segurança trabalha com consultores jurídicos globais para ajudar a garantir que a análise forense seja executada de acordo com as obrigações e compromissos legais para com os clientes. Também há restrições significativas sobre a visualização e o tratamento de sistemas e dados do cliente em diversos ambientes operacionais. Dados confidenciais ou sensíveis, bem como dados do cliente não são transferidos do ambiente de produção sem a expressa aprovação por escrito do Gerente de Incidentes registrado no tíquete de incidente correspondente.

A Microsoft confirma que o risco à empresa e ao cliente foi suprimido com êxito e que foram implementadas medidas corretivas. Se necessário, realizam-se etapas de atenuação emergenciais para resolver riscos de segurança imediatos associados ao evento.

A Microsoft também concluiu um post-mortem interno para violações de dados. Como parte deste exercício, a suficiência de respostas e os procedimentos operacionais são avaliados e todas as atualizações que possam ser necessárias para o SOP de Resposta a Incidentes de Segurança ou processos relacionados são identificados e implementados. Os postmortems internos para violações de dados são registros altamente confidenciais que não estão disponíveis para os clientes. No entanto, postmortems podem ser resumidos e incluídos nas notificações de evento de outro cliente. Esses relatórios são fornecidos para auditores externos para revisão como parte do ciclo de auditoria de rotina do Azure.

## <a name="customer-notification"></a>Notificação de cliente

O Microsoft Azure notifica os clientes e as autoridades regulamentadoras sobre as violações de dados, conforme necessário. A Microsoft conta com uma pesada compartimentalização interna na operação do Azure. Os logs de fluxo de dados também são robustos. Como benefício desse design, a maioria das ocorrências pode estar limitada a clientes específicos. O objetivo é fornecer aos clientes afetados um aviso preciso, acionável e oportuno quando da violação dos seus dados.

Após a declaração de um CRSI, o processo de notificação ocorrerá da forma mais eficiente possível, levando em conta os riscos de segurança de um trabalho agilizado. Em geral, o processo de criação de notificações ocorre durante o andamento da investigação do incidente. As notificações ao cliente são realizadas dentro de 72 horas após declararmos uma violação, *exceto* nas seguintes circunstâncias:

- A Microsoft acredita que o ato de executar uma notificação aumentará o risco para outros clientes. Por exemplo, o ato de notificar pode alertar algum adversário, causando uma incapacidade de remediar.

- Outras circunstâncias extremas ou incomuns investigadas pelo departamento jurídico da Microsoft Corporate External and Legal Affairs (CELA) e pelo gerente de incidentes executivo.

O Microsoft Azure fornece aos clientes informações detalhadas permitindo que executem investigações internas e ajudando-os a atender os compromissos com o usuário final, sem atrasar o processo de notificação.

A notificação de uma violação de dados pessoal será enviada ao cliente por qualquer meio que a Microsoft selecionar, incluindo via email. A notificação de falha de dados será entregue à lista de contatos de segurança fornecida na central de segurança do Azure, que pode ser configurada seguindo as[diretrizes de implementação](https://docs.microsoft.com/azure/security-center/security-center-provide-security-contact-details). Se as informações de contato não forem fornecidas na central de segurança do Azure, a notificação será enviada para um ou mais administradores em uma assinatura do Azure. Para garantir que as notificações possam ser entregues com êxito, é responsabilidade do cliente garantir que as informações de contato administrativas em cada assinatura aplicável e o portal de serviços online estejam corretas.

A equipe do Microsoft Azure ou do Azure Governamental também pode optar por notificar outros funcionários da Microsoft, como o Serviço de Atendimento ao Consumidor (SAC) e os Gerentes de contas do cliente ou os Gerentes técnicos de contas. Normalmente, essas pessoas têm uma relação próxima com o cliente e podem facilitar a correção mais rápida.<span id="_Appendix_A" class="anchor"></span>

## <a name="microsoft-intune-data-breach"></a>Violação de dados do Microsoft InTune

O Microsoft Intune é um componente essencial da oferta de serviço em nuvem do Microsoft Enterprise Mobility e da Security Suite. Para dar suporte à estratégia de governança de dados, todos os serviços em nuvem da Microsoft são desenvolvidos com a Privacidade da Microsoft e as metodologias de Segurança por design e por padrão.

Como a oferta do serviço de nuvem do Microsoft Intune acompanha as mesmas medidas Técnicas e Organizacionais, uma ou mais equipes de serviços do Microsoft Azure usam para proteger contra os processos de violação de dados. Portanto, qualquer informação documentada no documento de notificação “Violação de Dados do Microsoft Azure” aqui também é análoga ao serviço do Microsoft Intune. Por exemplo, o Microsoft Intune tem o mesmo Ciclo de Vida e Processo de Resposta do Incidente de Segurança (Estágio 1: Detecção por meio do estágio 5<strong>:</strong>: Fechar e Postmortem) e também o mesmo processo de Notificação de Incidente de Segurança do Cliente. Além disso, o Microsoft Intune também preenche suas obrigações de Notificação de Violação para todos os clientes do Microsoft O365 que usam o Intune ao trabalhar diretamente com a equipe do Microsoft O365.

Para obter mais informações sobre como a Microsoft detecta e responde a uma violação de dados pessoais, confira [Notificação de violação de dados no RGPD](https://servicetrust.microsoft.com/ViewPage/GDPRBreach) no Portal de Confiança do Serviço.


## <a name="learn-more"></a>Saiba mais

[Central de Confiabilidade da Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
