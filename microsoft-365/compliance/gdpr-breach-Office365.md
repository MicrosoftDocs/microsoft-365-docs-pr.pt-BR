---
title: Notificação de violação do Office 365 segundo o RGPD
description: Como a Microsoft protege contra uma violação de dados pessoais e como a Microsoft responderá e notificará você se ocorrer uma violação.
keywords: Office 365, Microsoft 365, Microsoft 365 Education, documentação do Microsoft 365, RGPD
author: BrendaCarter
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.date: 04/13/2018
ms.author: bcarter
manager: laurawi
ms.collection: GDPR
ms.openlocfilehash: c2ee959aad883516f03e903d34f517b4e76e4864
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865151"
---
# <a name="office-365-breach-notification-under-the-gdpr"></a>Notificação de violação do Office 365 segundo o RGPD

Como um processador de dados, o Office 365 garante que nossos clientes possam atender aos requisitos de notificação de violação de RGPD como controladores de dados. Para essa finalidade, estamos comprometidos com o seguinte:

-   Em fornecer aos clientes a capacidade de especificar um contato de privacidade dedicado que será notificado sobre a violação. Os clientes podem especificar este contato no Azure Active Directory (AAD).

-   Em notificar os clientes até 72 horas após uma violação de dados pessoais ser declarada. A notificação será feita por email para o contato especificado pelo cliente.

-   A notificação inicial incluirá ao menos uma descrição da natureza da violação, a aproximação de impacto sobre o usuário e as etapas de mitigação (se aplicável). Se nossa investigação não for concluída até o momento da notificação inicial, podemos indicar as próximas etapas e linhas de tempo para comunicação subsequente em nossa notificação inicial.

A Microsoft reconhece que os controladores de dados são responsáveis por conduzir avaliações de risco e determinar se uma violação requer a notificação de DPA ao cliente e a nossa notificação aos clientes fornece as informações necessárias para executar tal avaliação. Portanto, a Microsoft avisará aos clientes sobre qualquer violação de dados pessoais, exceto nesses casos em que os dados pessoais confirmados sejam incompreensíveis (por exemplo, dados altamente criptografados nos quais a integridade das chaves está confirmada).

## <a name="office-365-investments-in-data-security"></a>Investimentos do Office 365 em segurança de dados

Além do nosso compromisso de fornecer a notificação de violação em tempo hábil, o Office 365 investe fortemente em sistemas, processos e equipes para reduzir a probabilidade de violação de dados pessoais e para rapidamente detectar e reduzir a consequência da violação, caso ocorra.

Veja aqui uma descrição de alguns dos nossos investimentos relacionados:

-   **Sistemas de controle do acesso.** O Office 365 mantém uma política de "acesso zero", o que significa que os engenheiros não têm acesso ao serviço, a menos que seja concedido explicitamente em resposta a uma ocorrência específica que exija um acesso elevado. Sempre que o acesso for concedido, será feito seguindo o princípio de privilégios mínimos: a permissão é concedida para uma solicitação específica a fim de permitir apenas um conjunto mínimo de ações necessárias para o serviço solicitado. Para isso, o Office 365 mantém uma separação estrita entre "funções de elevação", com cada função permitindo apenas a execução de determinadas ações predefinidas. A função "Acessar dados do cliente" é distinta de outras funções geralmente usadas para administrar o serviço e sua inspeção é considerada com muito mais atenção antes da aprovação. Em conjunto, esses investimentos no controle do acesso reduzem muito a probabilidade de que um engenheiro do Office 365 acesse dados de clientes de forma inadequada.

-   **Sistemas de monitoramento de segurança e automação:** o Office 365 mantém sistemas de monitoramento de segurança robustos em tempo real. Entre outros problemas, esses sistemas geram alertas por tentativas ilícitas de acessar dados de clientes ou de transferir dados de nosso serviço. Relacionados aos pontos de controle de acesso mencionados acima, nossos sistemas de monitoramento de segurança mantêm registros detalhados das solicitações de elevação realizadas e das ações tomadas para uma determinada solicitação de elevação. O Office 365 também investe em resoluções automáticas que atuam automaticamente para mitigar as ameaças em resposta aos problemas detectados e equipes dedicadas para responder a alertas que não possam ser solucionados automaticamente. Para validar os sistemas de monitoramento de segurança, o Office 365 conduz regularmente exercícios em equipe, nos quais uma equipe de testes de invasão interna simula um comportamento invasor em relação ao ambiente ao vivo. Esses exercícios levam a melhorias regulares dos nossos recursos de resposta e do monitoramento da segurança.

-   **Equipe e processos:** além da automação descrita acima, o Office 365 mantém os processos e as equipes responsáveis por educar as organizações de forma mais ampla sobre a privacidade e os processos de gerenciamento de incidentes, e por executar esses processos durante uma violação. Por exemplo, o procedimento operacional padrão (SOP) detalhado de uma violação de privacidade é mantido e compartilhado com as equipes por toda a organização. Este SOP descreve detalhadamente as funções e responsabilidades de equipes individuais do Office 365 e das equipes de resposta a incidentes de segurança centralizada, que abrangem o que as equipes precisam fazer para melhorar suas próprias condições de segurança (realizar análises de segurança, integração com sistemas de monitoramento de segurança central e outras práticas recomendadas) e o que precisam fazer se houver uma violação real (escalonamento rápido da resposta ao incidente, manter e fornecer fontes de dados específicos a serem usados para acelerar o processo de resposta). As equipes recebem treinamento constante sobre a classificação de dados, procedimentos corretos de armazenamento e manipulação de dados pessoais.

O principal argumento é que o Office 365 investe imensamente na redução da probabilidade e nas consequências de violações de dados pessoais que afetem os clientes. Se ocorrer uma violação de dados pessoais, temos o compromisso de notificar rapidamente os nossos clientes, assim que a violação for confirmada.

## <a name="what-to-expect-in-the-event-of-breach"></a>O que esperar no caso de violação

A seção acima descreve investimentos que o Office 365 faz para reduzir a probabilidade de violação de dados. No caso improvável de que uma violação ocorra, os clientes devem aguardar uma experiência previsível em termos do seguinte:

-   Um ciclo de vida consistente de respostas a incidentes no Office 365. Como descrito acima, o Office 365 mantém SOPs detalhados de respostas a incidentes que descrevem como as equipes devem se preparar contra violações e como devem operar se ocorrer uma violação, o que garante que nossos processos e proteções sejam aplicados por todos os serviços.

-   Critérios consistentes para notificar os clientes. Nossos critérios de notificação se concentram na confidencialidade, integridade e disponibilidade de dados de clientes. O Office 365 notifica diretamente os clientes se a confidencialidade ou a integridade de seus dados forem afetadas. Ou seja, notificamos os clientes se seus dados forem acessados sem a adequada autorização ou se houver perdas ou destruição de dados inadequadas. O Office 365 também informa problemas que afetem a disponibilidade de dados, embora isso geralmente seja feito pelo Painel de integridade de serviço (SHD).

-   Detalhes de notificação consistente. Quando o Office 365 faz comunicações sobre violação de dados, os clientes podem esperar que sejam informados detalhes específicos; no mínimo, forneceremos os seguintes detalhes:

    -   O momento da violação e o momento em que a violação foi percebida.

    -   A quantidade aproximada de usuários afetados.

    -   Os tipos de dados do usuário que foram violados.

    -   Ações necessárias para reduzir a violação, seja do controlador ou do processador.

Os clientes também devem observar que o Office 365, como um processador de dados, não determina o risco de violação de dados. Sempre que for detectada uma violação de dados pessoais, notificaremos os clientes e forneceremos os detalhes que eles precisam para determinar com precisão o risco para os usuários afetados e para decidir se é necessário reportar às autoridades regulamentares. Para essa finalidade, espera-se que os controladores de dados determinem o seguinte:

-   Gravidade da violação (ou seja, a determinação do risco).

-   Se é necessário notificar os usuários finais.

-   Se é necessário notificar os reguladores (DPAs).

-   As etapas específicas que o controlador deve tomar para reduzir as consequências da violação.

## <a name="contacting-microsoft"></a>Entrar em contato com a Microsoft

Em alguns cenários, um cliente pode ficar ciente de uma violação e querer notificar a Microsoft. O protocolo atual é para clientes que queiram notificar o Suporte da Microsoft, que interagirá com equipes de engenharia para saber mais. Nesse cenário, as equipes de engenharia da Microsoft têm, da mesma forma, o compromisso de fornecer em tempo hábil as informações que os clientes precisarem.

## <a name="call-to-action-for-customers"></a>Chamada à ação para clientes

Como mencionado acima, o Office 365 está comprometido em notificar os clientes em até 72 horas da declaração de violação. O administrador do locatário do cliente será notificado. Além disso, o Office 365 recomenda que os clientes designem um alias de Contato de privacidade global, o que pode ser feito no portal do Azure Active Directory (AAD). No caso de violação de dados pessoais, este alias pode ser receber a notificação por email, além da notificação a ser enviada aos administradores.

O contato de privacidade do cliente pode ser uma pessoa da organização, uma lista de distribuição (LD) ou alguém de fora da organização. O Office 365 somente solicita que os clientes forneçam um endereço de email para este contato, que os clientes podem especificar no portal do AAD, no campo "Contato de privacidade global". Observe que esse campo é relacionado, mas distinto do campo "Contato técnico" existente no AAD. Se os clientes optarem por especificar uma LD para este contato, devem garantir que a lista de distribuição esteja configurada para habilitar o recebimento de mensagens de remetentes externos.

Para resumir, o Office 365 solicita que os clientes façam o seguinte para receberem os benefícios de nossos processos de notificação de violações:

-   Escolha um contato para receber notificações por email sobre a violação de dados pessoais. Este contato deve estar ciente dos requisitos de controladores, de acordo com o RGPD, e deve estar preparado para interagir com o Responsável pela proteção de dados da organização e até mesmo com a Autoridade de proteção a dados logo após receber a notificação. Os administradores do locatário também receberão as notificações de violação e, da mesma forma, deverão estar cientes dos requisitos do controlador de acordo com o RGPD.

-   Insira o endereço de email do contato de privacidade no portal do AAD. Se nenhuma informação de Contato de privacidade global for fornecida, a Microsoft notificará somente o administrador do locatário.
- <!-- note that there is missing text clipped from the original Word doc -->
