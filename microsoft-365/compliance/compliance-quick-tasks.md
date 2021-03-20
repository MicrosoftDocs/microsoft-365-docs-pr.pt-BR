---
title: Tarefas rápidas de introdução ao Centro de conformidade do Microsoft 365.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- m365-security-compliance
- m365initiative-compliance
localization_priority: Normal
description: Saiba mais sobre tarefas que ajudarão você a começar rapidamente com a conformidade no Microsoft 365.
ms.openlocfilehash: 69aef07e65f5644f9aa294025c8388410f160243
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908581"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Tarefas rápidas de introdução ao Centro de conformidade do Microsoft 365.

Se você é novo na conformidade do Microsoft 365 e quer saber por onde começar, este artigo fornece orientações sobre as noções básicas e prioriza tarefas importantes de conformidade. Este artigo ajudará você a começar rapidamente a gerenciar e monitorar seus dados, proteger informações e minimizar riscos insider.

Este artigo também será útil se você estiver descobrindo a melhor maneira de gerenciar riscos, proteger seus dados e permanecer em conformidade com regulamentos e padrões com uma força de trabalho recém-remota. Os funcionários agora estão colaborando e se conectando entre si de novas maneiras, e isso significa que seus processos e controles de conformidade existentes podem precisar se adaptar. Identificar e gerenciar esses novos riscos de conformidade em sua organização é fundamental para proteger seus dados e minimizar ameaças e riscos.

Depois de concluir essas tarefas básicas de conformidade, considere expandir a cobertura de conformidade em sua organização implementando soluções adicionais de conformidade do Microsoft 365.

## <a name="task-1-configure-compliance-permissions"></a>Tarefa 1: Configurar permissões de conformidade

É importante gerenciar quem na sua organização tem acesso ao centro de conformidade do Microsoft 365 para exibir conteúdo e executar tarefas de gerenciamento. O Microsoft 365 fornece funções administrativas específicas para conformidade e para usar as ferramentas incluídas no centro de conformidade do Microsoft 365.

Comece atribuindo permissões de conformidade às pessoas em sua organização para que possam executar essas tarefas e impedir que pessoas não autorizadas tenham acesso a áreas fora de suas responsabilidades. Certifique-se de que as pessoas adequadas foram atribuídas ao administrador  de dados de Conformidade e às funções de administrador de Conformidade antes de começar a configurar e implementar soluções de conformidade incluídas no Microsoft 365.  Você também precisará atribuir usuários à função de leitor global do Azure Active Directory para exibir dados no Gerenciador de Conformidade.

Para obter orientações passo a passo para configurar permissões e atribuir pessoas a funções de administrador, consulte [Permissions in the Security & Compliance Center](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="task-2-know-your-state-of-compliance"></a>Tarefa 2: Conheça seu estado de conformidade

É difícil saber para onde ir se você não sabe onde está. Atender às suas necessidades de conformidade inclui compreender seu nível de risco atual e quais atualizações podem ser necessárias nesses tempos em constante mudança. Se sua organização é nova em requisitos de conformidade ou tem uma experiência profunda com padrões e regulamentos que governam seu setor, a melhor coisa que você pode fazer para melhorar a conformidade é entender onde sua organização está.

[O Microsoft Compliance Manager](compliance-manager.md) pode ajudá-lo a entender a postura de conformidade da sua organização e destacar áreas que podem precisar de melhorias. O Gerenciador de Conformidade usa um painel centralizado para calcular uma pontuação baseada em risco, medindo seu progresso na conclusão de ações que ajudam a reduzir os riscos em torno da proteção de dados e dos padrões regulatórios. Você também pode usar o Gerenciador de Conformidade como uma ferramenta para acompanhar todas as avaliações de risco. Ele fornece recursos de fluxo de trabalho para ajudá-lo a concluir com eficiência suas avaliações de risco por meio de uma ferramenta comum.

Para obter orientações passo a passo para começar a trabalhar com o Gerenciador de Conformidade, consulte [Get started with Compliance Manager](compliance-manager-setup.md).

>[!IMPORTANT]
>A segurança e a conformidade são fortemente integradas para a maioria das organizações. É importante que sua organização aborda as áreas básicas de segurança, proteção contra ameaças e gerenciamento de identidade e acesso para ajudar a fornecer uma abordagem aprofundada de defesa à segurança e à conformidade.
>
>Verifique sua Pontuação Segura do [Microsoft 365](../security/mtp/microsoft-secure-score.md) no centro de segurança do Microsoft 365 e concluindo as tarefas descritas nos seguintes artigos:
>
> - [Roteiro de segurança - Principais prioridades para os primeiros 30 dias, 90 dias e além](../security/office-365-security/security-roadmap.md)
> - [Principais 12 tarefas para equipes de segurança para dar suporte ao trabalho em casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Tarefa 3: Habilitar a auditoria para sua organização

Agora que você determinou o estado atual da sua organização e quem pode gerenciar funções de conformidade, a próxima etapa é garantir que você tenha os dados para conduzir investigações de conformidade e gerar relatórios para atividades de rede e usuários em sua organização. Habilite a auditoria também é um pré-requisito importante para soluções de conformidade abordadas posteriormente neste artigo.

Os insights fornecidos pelo log de auditoria são uma ferramenta valiosa para ajudar a corresponder seus requisitos de conformidade a soluções que podem ajudá-lo a gerenciar e monitorar áreas de conformidade que precisam de aperfeiçoamento. O log de auditoria deve ser habilitado antes que as atividades sejam gravadas e antes que você possa pesquisar o log de auditoria. Quando habilitada, a atividade do usuário e do administrador da sua organização é registrada no log de auditoria e mantida por 90 dias e até um ano, dependendo da licença atribuída aos usuários.

Para obter instruções passo a passo para ativar a auditoria, consulte Ativar ou desativar a pesquisa de [log de auditoria.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Tarefa 4: criar políticas para alertá-lo sobre possíveis problemas de conformidade

A Microsoft fornece várias políticas de alerta internas que ajudam a identificar abuso de permissões de administrador, atividade de malware, possíveis ameaças externas e internas e riscos de governança de informações. Essas políticas são ativas por padrão, mas você pode precisar configurar alertas personalizados para ajudar a gerenciar requisitos de conformidade específicos da sua organização.

Use as ferramentas de política de alerta e painel de alertas para criar políticas de alerta personalizadas e exibir os alertas gerados quando os usuários executam atividades que corresponderem às condições da política. Alguns exemplos podem ser usar políticas de alerta para controlar as atividades de usuário e administrador que afetam os requisitos de conformidade, permissões e incidentes de perda de dados em sua organização.

Para obter orientações passo a passo para criar políticas de alerta personalizadas, consulte Políticas de alerta [no centro](alert-policies.md)de conformidade e segurança.

## <a name="task-5-classify-and-protect-sensitive-data"></a>Tarefa 5: Classificar e proteger dados confidenciais

Para realizar o trabalho, as pessoas da organização colaboram com outras pessoas dentro e fora da organização. Isso significa que o conteúdo não fica mais atrás de um firewall, ele pode circular em qualquer lugar, em dispositivos, aplicativos e serviços. E quando estiver em roaming, você quer fazê-lo de uma maneira segura e protegida que atenda às políticas de negócios e conformidade da organização.

[Os rótulos de](sensitivity-labels.md) sensibilidade permitem que você classifique e proteja os dados da sua organização, ao mesmo tempo em que garante que a produtividade do usuário e sua capacidade de colaboração não são prejudicadas. Use rótulos de sensibilidade para impor restrições de criptografia e uso aplicam marcações visuais e proteger informações em plataformas e dispositivos, no local e na nuvem.

Para obter orientações passo a passo para configurar e usar rótulos de sensibilidade, consulte [Get started with sensitivity labels](get-started-with-sensitivity-labels.md). Para obter informações sobre licenciamento de rótulos de sensibilidade, consulte Diretrizes de licenciamento do [Microsoft 365 para segurança & conformidade.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="task-6-configure-a-retention-policy"></a>Tarefa 6: Configurar uma política de retenção

Uma [política de](retention.md) retenção permite que você decida proativamente se deve reter conteúdo, excluir conteúdo ou ambos— reter e excluir o conteúdo no final de um período de retenção especificado. Essas ações podem ser necessárias para estar em conformidade com os regulamentos e políticas internas do setor, bem como reduzir o risco em caso de litígio ou violação de segurança.

Quando o conteúdo está sujeito a uma política de retenção, as pessoas podem continuar a editar e trabalhar com o conteúdo como se nada tivesse sido alterado. O conteúdo é mantido no local, em seu local original. Porém, se alguém editar ou excluir conteúdo sujeito à política de retenção, uma cópia do conteúdo original será salva em um local seguro onde ele será mantido enquanto a política de retenção desse conteúdo estiver em vigor.

Você pode colocar rapidamente uma política de retenção em vários locais em seu ambiente do Microsoft 365, como email do Exchange, sites do SharePoint, contas do OneDrive e grupos do Microsoft 365. Não há limites para o número de caixas de correio ou sites que essa política pode incluir automaticamente. Mas, se precisar ser mais seletivo, você pode fazer isso configurando uma política de retenção para locais específicos e incluir ou excluir sites ou usuários.

Para obter orientações passo a passo para configurar uma política de retenção, consulte [Create and configure retention policies](create-retention-policies.md). Se você é novo na configuração de retenção no Microsoft 365, consulte [Iniciar com políticas de retenção e rótulos de retenção](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Tarefa 7: Configurar informações confidenciais e políticas de idioma ofensivo

Proteger informações confidenciais e detectar e agir em incidentes de assédio no local de trabalho é uma parte importante da conformidade com as políticas e padrões internos. [A conformidade de](communication-compliance-feature-reference.md) comunicação no Microsoft 365 ajuda a minimizar esses riscos, ajudando você a detectar, capturar e realizar ações de correção rapidamente para emails e comunicações do Microsoft Teams. Eles incluem comunicações inadequadas que contêm profanidade, ameaças e assédio e comunicações que compartilham informações confidenciais dentro e fora da sua organização.

Um modelo de política anti-assédio e idioma ofensivo *pré-definido* permite que você examine as comunicações internas e externas para que elas possam ser examinadas por revisores designados. Os revisadores podem investigar emails verificados, Microsoft Teams, Yammer ou comunicações de terceiros em sua organização e tomar ações de correção apropriadas para garantir que eles estão em conformidade com os padrões da sua organização.

O modelo  de política de informações confidenciais pré-definido ajuda você a criar rapidamente uma política para verificar emails e comunicações do Microsoft Teams contendo tipos de informações confidenciais ou palavras-chave definidos para ajudar a garantir que dados importantes não são compartilhados com pessoas que não devem ter acesso. Essas atividades podem incluir comunicação não autorizada sobre projetos confidenciais ou regras específicas do setor sobre insider trading ou outras atividades de conluio.

Para obter orientações passo a passo para planejar e configurar a conformidade de [comunicação,](communication-compliance-configure.md)consulte Plan for communication [compliance](communication-compliance-plan.md) e Get started with communication compliance . Para obter informações de licenciamento de conformidade de comunicação, consulte Diretrizes de licenciamento do [Microsoft 365 para segurança & conformidade.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Tarefa 8: veja o que está acontecendo com seus itens confidenciais

Rótulos de sensibilidade, tipos de informações confidenciais, rótulos e políticas de retenção e classificadores de treinamento podem ser usados para classificar e rotular itens confidenciais no Exchange, no SharePoint e no OneDrive, como você viu nas tarefas anteriores. A última etapa em sua jornada rápida de tarefas é ver quais itens foram rotulados e quais ações seus usuários estão fazendo nesses itens confidenciais. [O explorador de](data-classification-content-explorer.md) conteúdo [e o explorador](data-classification-activity-explorer.md) de atividades fornecem essa visibilidade.

### <a name="content-explorer"></a>Explorador de conteúdo
 O explorador de conteúdo permite que você veja, no formato nativo, todos os itens que foram classificados como um tipo de informação confidencial ou pertencentes a uma determinada classificação por um classificador treinável, bem como todos os itens que tenham confidencialidade ou rótulo de retenção aplicados.

Para obter orientações passo a passo sobre como usar o explorador de conteúdo, consulte Know your [data - data classification overview](data-classification-overview.md), and Get started with content [explorer](data-classification-content-explorer.md).

### <a name="activity-explorer"></a>Explorador de atividade 
O Explorador de Atividades ajuda você a monitorar o que está sendo feito com seus itens confidenciais classificados e rotulados em:
- SharePoint
- Exchange
- OneDrive

Há mais de 30 filtros diferentes disponíveis para uso, alguns são:

- intervalo de datas
- tipo de atividade
- localização
- usuário
- rótulo de confidencialidade
- rótulo de retenção
- caminho do arquivo
- Política de DLP

Para obter orientações passo a passo sobre como usar o explorador de atividades, consulte [Get started with activity explorer](data-classification-activity-explorer.md).

## <a name="next-steps"></a>Próximas etapas

Agora que você configurou os conceitos básicos de gerenciamento de conformidade para sua organização, considere as seguintes soluções de conformidade no Microsoft 365 para ajudá-lo a proteger informações confidenciais e detectar e agir sobre riscos insider adicionais.

### <a name="configure-retention-labels"></a>Configurar rótulos de retenção

Embora as políticas de retenção se apliquem no nível do contêiner a locais como sites do SharePoint e caixas de correio do [Exchange,](retention.md#retention-labels) os rótulos de retenção permitem direcionamento mais específico para suas políticas de retenção e exclusão. Por exemplo, no nível de documento ou mensagem de email que os usuários finais podem aplicar manualmente, além do aplicativo automático pelos administradores. Você também pode aplicar um rótulo de retenção a uma biblioteca de documentos, pasta ou conjunto de documentos no SharePoint, para que todos os documentos armazenados nesse local herdem o rótulo de retenção padrão.

Além disso, os rótulos de retenção suportam [o gerenciamento](records-management.md) de registros para marcar o conteúdo como um registro. Quando isso acontece, o rótulo coloca restrições adicionais sobre o conteúdo que pode ser necessário para ajudar sua organização a cumprir os requisitos regulatórios.

Para obter orientações passo a passo para criar e publicar rótulos de retenção, consulte as seguintes diretrizes:
- [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
- [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)

Para começar com o gerenciamento de registros, consulte [Começar com o gerenciamento de registros](get-started-with-records-management.md).

### <a name="identify-and-define-sensitive-information-types"></a>Identificar e definir tipos de informações confidenciais

Defina tipos de informações confidenciais com base no padrão contido nas informações nos dados da sua organização. Usar [tipos de informações confidenciais](./sensitive-information-type-entity-definitions.md) integrados ajudam a identificar e proteger números de cartão de crédito, números de conta bancária, números de passaporte e muito mais. Ou crie seus próprios tipos de informações de [sensibilidade personalizadas](create-a-custom-sensitive-information-type.md) específicos à sua organização.

Para obter orientações passo a passo para definir tipos de informações confidenciais personalizados, consulte Create a custom sensitive information [type in the Security & Compliance Center](./create-a-custom-sensitive-information-type.md).

### <a name="prevent-data-loss"></a>Evita a perda de dados

As políticas de prevenção contra perda de dados [(DLP)](data-loss-prevention-policies.md) permitem identificar, monitorar e proteger automaticamente informações confidenciais em sua organização do Microsoft 365. Use políticas de DLP para identificar itens confidenciais em todos os serviços da Microsoft, impedir o compartilhamento acidental de itens confidenciais e ajudar os usuários a aprender a manter a conformidade sem interromper o fluxo de trabalho.

Para obter orientações passo a passo para configurar políticas de DLP, Crie, teste e [ajuste uma política DLP.](create-test-tune-dlp-policy.md) Para obter informações de licenciamento de gerenciamento de perda de dados, consulte Diretrizes de licenciamento do [Microsoft 365 para conformidade & segurança.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

### <a name="detect-and-act-on-insider-risks"></a>Detectar e agir em riscos insider

Cada vez mais, os funcionários têm acesso crescente para criar, gerenciar e compartilhar dados em um amplo espectro de plataformas e serviços. Na maioria dos casos, as organizações têm recursos e ferramentas limitados para identificar e reduzir riscos em toda a organização, além de atender aos requisitos de conformidade e aos padrões de privacidade dos funcionários. Esses riscos podem incluir roubo de dados ao separar funcionários e vazamentos de dados de informações fora da sua organização por excesso acidental ou intenção mal-intencionada.

[O gerenciamento de](insider-risk-management-policies.md) riscos insider no Microsoft 365 usa toda a amplitude de serviços e indicadores de terceiros para ajudá-lo a identificar, triagem e agir rapidamente em atividades de risco do usuário. Usando logs do Microsoft 365 e do Microsoft Graph, o gerenciamento de riscos insider permite definir políticas específicas para identificar indicadores de risco e tomar medidas para mitigar esses riscos.

Para obter orientações passo a passo para planejar e configurar políticas de gerenciamento de riscos internas, consulte [Plan for insider risk management](insider-risk-management-plan.md) e Get started with [insider risk management](insider-risk-management-configure.md). Para obter informações de licenciamento de gerenciamento de riscos insider, consulte Diretrizes de licenciamento do [Microsoft 365 para segurança & conformidade.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)