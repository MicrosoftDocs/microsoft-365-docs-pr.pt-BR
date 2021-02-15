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
description: Saiba mais sobre as tarefas que ajudarão você a começar a trabalhar rapidamente com conformidade no Microsoft 365.
ms.openlocfilehash: 36b6e2bd0d0339241748499826edf061a7259317
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928625"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Tarefas rápidas de introdução ao Centro de conformidade do Microsoft 365.

Se você é novo na conformidade com o Microsoft 365 e quer saber por onde começar, este artigo fornece orientações sobre noções básicas e prioriza tarefas de conformidade importantes. Este artigo ajudará você a começar rapidamente a gerenciar e monitorar seus dados, proteger as informações e minimizar os riscos insider.

Este artigo também é útil se você estiver descobrindo a melhor maneira de gerenciar riscos, proteger seus dados e permanecer em conformidade com regulamentos e padrões com uma força de trabalho recém-remota. Os funcionários agora estão colaborando e se conectando entre si de novas maneiras, e isso significa que seus processos e controles de conformidade existentes talvez precisem se adaptar. Identificar e gerenciar esses novos riscos de conformidade em sua organização é fundamental para proteger seus dados e minimizar ameaças e riscos.

Depois de concluir essas tarefas básicas de conformidade, considere expandir a cobertura de conformidade em sua organização implementando soluções adicionais de conformidade do Microsoft 365.

## <a name="task-1-configure-compliance-permissions"></a>Tarefa 1: Configurar permissões de conformidade

É importante gerenciar quem em sua organização tem acesso ao centro de conformidade do Microsoft 365 para exibir conteúdo e executar tarefas de gerenciamento. O Microsoft 365 fornece funções administrativas específicas para conformidade e para usar as ferramentas incluídas no centro de conformidade do Microsoft 365.

Comece atribuindo permissões de conformidade às pessoas em sua organização para que elas possam executar essas tarefas e evitar que pessoas não autorizadas tenham acesso a áreas fora de suas responsabilidades. Você deve ter certeza de que atribuiu as pessoas  adequadas ao  administrador de dados de Conformidade e às funções de administrador de Conformidade antes de começar a configurar e implementar soluções de conformidade incluídas no Microsoft 365. Você também precisará atribuir usuários à função de leitor global do Azure Active Directory para exibir dados no Gerenciador de Conformidade.

Para obter orientações passo a passo para configurar permissões e atribuir funções de administrador a pessoas, consulte Permissões no Centro de Conformidade e [Segurança & Segurança.](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)

## <a name="task-2-know-your-state-of-compliance"></a>Tarefa 2: conhecer seu estado de conformidade

É difícil saber para onde ir se você não sabe onde está. Atender às suas necessidades de conformidade inclui compreender seu nível de risco atual e quais atualizações podem ser necessárias nesses tempos em constante mudança. Se sua organização é nova em requisitos de conformidade ou tem uma experiência profunda com padrões e regulamentos que governam seu setor, a melhor coisa que você pode fazer para melhorar a conformidade é entender onde sua organização está.

[O Gerenciador de Conformidade da Microsoft](compliance-manager.md) pode ajudá-lo a entender a postura de conformidade da sua organização e destacar áreas que podem precisar de melhorias. O Gerenciador de Conformidade usa um painel centralizado para calcular uma pontuação baseada em risco, medindo seu progresso na conclusão de ações que ajudam a reduzir os riscos em torno da proteção de dados e padrões regulatórios. Você também pode usar o Gerenciador de Conformidade como uma ferramenta para controlar todas as avaliações de risco. Ele fornece recursos de fluxo de trabalho para ajudá-lo a concluir com eficiência suas avaliações de risco por meio de uma ferramenta comum.

Para obter orientações passo a passo para começar a trabalhar com o Gerenciador de Conformidade, confira Começar a trabalhar [com o Gerenciador de Conformidade.](compliance-manager-setup.md)

>[!IMPORTANT]
>A segurança e a conformidade estão totalmente integradas para a maioria das organizações. É importante que sua organização aborde as áreas básicas de segurança, proteção contra ameaças e gerenciamento de identidades e acesso para ajudar a fornecer uma abordagem de defesa abrangente à segurança e à conformidade.
>
>Verifique a Classificação de Segurança do [Microsoft 365](../security/mtp/microsoft-secure-score.md) no centro de segurança do Microsoft 365 e a conclusão das tarefas descritas nos seguintes artigos:
>
> - [Roteiro de segurança – principais prioridades para os primeiros 30 dias, 90 dias e depois](../security/office-365-security/security-roadmap.md)
> - [12 principais tarefas para as equipes de segurança dar suporte ao trabalho em casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Tarefa 3: Habilitar a auditoria para sua organização

Agora que você determinou o estado atual da sua organização e quem pode gerenciar as funções de conformidade, a próxima etapa é garantir que você tenha os dados para conduzir investigações de conformidade e gerar relatórios para atividades de rede e usuário em sua organização. A habilitação da auditoria também é um pré-requisito importante para soluções de conformidade abordadas posteriormente neste artigo.

Insights fornecidos pelo log de auditoria são uma ferramenta valiosa para ajudar a corresponder seus requisitos de conformidade a soluções que podem ajudá-lo a gerenciar e monitorar áreas de conformidade que precisam de melhoria. O log de auditoria deve ser habilitado antes que as atividades sejam registradas e antes que você possa pesquisar o log de auditoria. Quando habilitada, a atividade de usuários e administradores da sua organização é registrada no log de auditoria e retida por 90 dias e até um ano, dependendo da licença atribuída aos usuários.

Para obter instruções passo a passo para ativar a auditoria, consulte Ativar ou desativar a pesquisa de [log de auditoria.](turn-audit-log-search-on-or-off.md)

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Tarefa 4: Criar políticas para alertá-lo sobre possíveis problemas de conformidade

A Microsoft fornece várias políticas de alerta internas que ajudam a identificar o abuso de permissões de administrador, a atividade de malware, possíveis ameaças externas e internas e riscos de governança de informações. Essas políticas estão tivas por padrão, mas talvez seja necessário configurar alertas personalizados para ajudar a gerenciar os requisitos de conformidade específicos da sua organização.

Use as ferramentas de política de alerta e painel de alertas para criar políticas de alerta personalizadas e exibir os alertas gerados quando os usuários executam atividades que corresponderem às condições da política. Alguns exemplos podem ser o uso de políticas de alerta para rastrear atividades de usuários e administradores que afetam os requisitos de conformidade, permissões e incidentes de perda de dados em sua organização.

Para obter orientações passo a passo para criar políticas de alerta personalizadas, consulte Políticas de alerta no centro de conformidade [e segurança.](alert-policies.md)

## <a name="task-5-classify-and-protect-sensitive-data"></a>Tarefa 5: Classificar e proteger dados confidenciais

Para realizar o trabalho, as pessoas da organização colaboram com outras pessoas dentro e fora da organização. Isso significa que o conteúdo não fica mais atrás de um firewall, ele pode circular em qualquer lugar, em dispositivos, aplicativos e serviços. E quando estiver em roaming, você quer fazê-lo de uma maneira segura e protegida que atenda às políticas de negócios e conformidade da organização.

[Os rótulos de](sensitivity-labels.md) sensibilidade permitem classificar e proteger os dados da sua organização, ao mesmo tempo em que garantem que a produtividade do usuário e sua capacidade de colaboração não são prejudicadas. Use rótulos de sensibilidade para impor restrições de criptografia e uso para aplicar marcações visuais e proteger informações entre plataformas e dispositivos, no local e na nuvem.

Para obter orientações passo a passo para configurar e usar rótulos de sensibilidade, confira Começar a usar [rótulos de sensibilidade.](get-started-with-sensitivity-labels.md) Para saber mais sobre licenciamento de rótulos de sensibilidade, confira as diretrizes de licenciamento do [Microsoft 365 para](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)segurança & conformidade.

## <a name="task-6-configure-a-retention-policy"></a>Tarefa 6: Configurar uma política de retenção

Uma [política de](retention.md) retenção permite que você decida proativamente se deve reter o conteúdo, excluí-lo ou ambos, reter e, em seguida, excluir o conteúdo no final de um período de retenção especificado. Essas ações podem ser necessárias para estar em conformidade com regulamentos do setor e políticas internas, bem como reduzir o risco em caso de litígio ou violação de segurança.

Quando o conteúdo está sujeito a uma política de retenção, as pessoas podem continuar a editar e trabalhar com o conteúdo como se nada tivesse mudado. O conteúdo é mantido no local, em seu local original. Mas se alguém editar ou excluir o conteúdo sujeito à política de retenção, uma cópia do conteúdo original será salva em um local seguro, onde será mantida enquanto a política de retenção desse conteúdo estiver em vigor.

Você pode rapidamente colocar uma política de retenção em local para vários locais em seu ambiente do Microsoft 365, como email do Exchange, sites do SharePoint, contas do OneDrive e grupos do Microsoft 365. Não há limites para o número de caixas de correio ou sites que essa política pode incluir automaticamente. Porém, se precisar ser mais seletivo, você poderá fazer isso configurando uma política de retenção para locais específicos e incluir ou excluir sites ou usuários.

Para obter orientações passo a passo para configurar uma política de retenção, consulte [Criar e configurar políticas de retenção.](create-retention-policies.md) Se você é novo na configuração de retenção no Microsoft 365, consulte [Iniciar com políticas de retenção e rótulos de retenção](get-started-with-retention.md).

## <a name="task-7-configure-sensitive-information-and-offensive-language-policies"></a>Tarefa 7: Configurar informações confidenciais e políticas de idioma ofensivo

Proteger informações confidenciais e detectar e agir sobre incidentes de abuso no local de trabalho é uma parte importante da conformidade com políticas e padrões internos. [A conformidade de](communication-compliance-feature-reference.md) comunicação no Microsoft 365 ajuda a minimizar esses riscos, ajudando você a detectar, capturar e tomar ações de correção rapidamente para comunicações de email e do Microsoft Teams. Isso inclui comunicações inadequadas que contêm profanação, ameaças e abuso e comunicações que compartilham informações confidenciais dentro e fora da sua organização.

Um modelo  de política anti-ofensivo e linguagem ofensiva predefinida permite que você examine as comunicações internas e externas para que elas possam ser examinadas por revisores designados. Os revisadores podem investigar emails verificados, Microsoft Teams, Yammer ou comunicações de terceiros em sua organização e tomar as medidas de correção apropriadas para garantir que eles estão em conformidade com os padrões da sua organização.

O modelo  de política de informações confidenciais pré-definido ajuda você a criar rapidamente uma política para verificar emails e comunicações do Microsoft Teams que contenham tipos de informações confidenciais ou palavras-chave definidos para ajudar a garantir que dados importantes não são compartilhados com pessoas que não devem ter acesso. Essas atividades podem incluir comunicações não autorizadas sobre projetos confidenciais ou regras específicas do setor sobre troca de informações internas ou outras atividades de colusão.

Para obter orientações passo a passo para planejar e configurar a conformidade de comunicação, consulte [Planejar](communication-compliance-plan.md) a conformidade de comunicação e [começar a trabalhar com a conformidade de comunicação.](communication-compliance-configure.md) Para obter informações de licenciamento de conformidade de comunicação, confira as diretrizes de licenciamento do [Microsoft 365 para segurança & conformidade.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance)

## <a name="task-8-see-whats-happening-with-your-sensitive-items"></a>Tarefa 8: Veja o que está acontecendo com seus itens confidenciais

Rótulos de sensibilidade, tipos de informações confidenciais, rótulos e políticas de retenção e classificadores de treinamento podem ser usados para classificar e rotular itens confidenciais no Exchange, no SharePoint e no OneDrive como você viu nas tarefas anteriores. A última etapa em sua jornada rápida de tarefas é ver quais itens foram rotulados e quais ações seus usuários estão tomando em relação a esses itens confidenciais. [o explorador de conteúdo](data-classification-content-explorer.md) [e o explorador de](data-classification-activity-explorer.md) atividades fornecem essa visibilidade.

### <a name="content-explorer"></a>Explorador de conteúdo
 O Explorador de conteúdo permite que você veja, em seu formato nativo, todos os itens que foram classificados como um tipo de informação confidencial ou pertencentes a uma determinada classificação por um classificador de treinamento, bem como todos os itens que têm rótulo de confidencialidade ou retenção aplicados.

Para obter orientações passo a passo sobre como usar o Explorador de conteúdo, consulte Saber seus dados [-](data-classification-overview.md)visão geral da classificação de dados e Começar a [usar o explorador de conteúdo.](data-classification-content-explorer.md)

### <a name="activity-explorer"></a>Explorador de atividades
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

Para obter orientações passo a passo sobre como usar o explorador de atividades, confira [Começar a usar o explorador de atividades.](data-classification-activity-explorer.md)

## <a name="next-steps"></a>Próximas etapas

Agora que você configurou as noções básicas de gerenciamento de conformidade para sua organização, considere as seguintes soluções de conformidade no Microsoft 365 para ajudá-lo a proteger informações confidenciais e detectar e agir sobre riscos de informações internas adicionais.

### <a name="configure-retention-labels"></a>Configurar rótulos de retenção

Embora as políticas de retenção se apliquem no nível do contêiner a locais como sites do SharePoint e caixas de correio do [Exchange,](retention.md#retention-labels) os rótulos de retenção permitem um direcionamento mais específico para suas políticas de retenção e exclusão. Por exemplo, no nível do documento ou da mensagem de email que os usuários finais podem aplicar manualmente, além do aplicativo automático pelos administradores. Você também pode aplicar um rótulo de retenção a uma biblioteca de documentos, pasta ou conjunto de documentos no SharePoint, para que todos os documentos armazenados nesse local herdem o rótulo de retenção padrão.

Além disso, os rótulos de retenção suportam [o gerenciamento de](records-management.md) registros para marcar o conteúdo como um registro. Quando isso acontece, o rótulo coloca restrições adicionais sobre o conteúdo que pode ser necessário para ajudar sua organização a cumprir os requisitos regulatórios.

Para obter orientações passo a passo para criar e publicar rótulos de retenção, consulte as seguintes diretrizes:
- [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
- [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)

Para começar a trabalhar com o gerenciamento de registros, [consulte Começar a trabalhar com o gerenciamento de registros.](get-started-with-records-management.md)

### <a name="identify-and-define-sensitive-information-types"></a>Identificar e definir tipos de informações confidenciais

Defina tipos de informações confidenciais com base no padrão contido nas informações dos dados da sua organização. Usar [tipos de informações confidenciais integrados](what-the-sensitive-information-types-look-for.md) ajudam a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaporte e muito mais. Ou crie seus próprios [tipos de informações de sensibilidade personalizados](create-a-custom-sensitive-information-type.md) específicos para sua organização.

Para obter orientações passo a passo para definir tipos personalizados de informações confidenciais, consulte Criar um tipo personalizado de informações confidenciais no Centro de Conformidade e Segurança & [Segurança.](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type)

### <a name="prevent-data-loss"></a>Evita a perda de dados

As políticas de prevenção contra perda de dados [(DLP)](data-loss-prevention-policies.md) permitem identificar, monitorar e proteger automaticamente informações confidenciais em toda a organização do Microsoft 365. Use políticas DLP para identificar itens confidenciais nos serviços Microsoft, evitar o compartilhamento acidental de itens confidenciais e ajudar os usuários a aprender a manter a conformidade sem interromper o fluxo de trabalho.

Para obter orientações passo a passo para configurar políticas de DLP, criar, testar e [ajustar uma política de DLP.](create-test-tune-dlp-policy.md) Para obter informações de licenciamento de gerenciamento de perda de dados, confira as diretrizes de licenciamento do [Microsoft 365 para segurança & conformidade.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)

### <a name="detect-and-act-on-insider-risks"></a>Detectar e agir em riscos de usuário interno

Cada vez mais, os funcionários têm acesso crescente para criar, gerenciar e compartilhar dados em uma ampla gama de plataformas e serviços. Na maioria dos casos, as organizações têm recursos e ferramentas limitados para identificar e reduzir os riscos em toda a organização, além de atender aos requisitos de conformidade e aos padrões de privacidade dos funcionários. Esses riscos podem incluir roubo de dados ao separar funcionários e vazamentos de dados de informações fora da sua organização por excesso de compartilhamento acidental ou intenção mal-intencionada.

[O gerenciamento de](insider-risk-management-policies.md) riscos insider no Microsoft 365 usa a abrangência completa dos indicadores de serviço e de terceiros para ajudá-lo a identificar, triagem e agir rapidamente sobre atividades arriscadas do usuário. Usando logs do Microsoft 365 e do Microsoft Graph, o gerenciamento de riscos insider permite definir políticas específicas para identificar indicadores de risco e tomar medidas para reduzir esses riscos.

Para obter orientações passo a passo para planejar e configurar políticas de gerenciamento de riscos [insider,](insider-risk-management-plan.md) consulte Planejar o gerenciamento de riscos insider e começar a trabalhar com o [gerenciamento de riscos insider.](insider-risk-management-configure.md) Para obter informações de licenciamento de gerenciamento de riscos insider, confira as diretrizes de licenciamento do [Microsoft 365 para segurança & conformidade.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management)
