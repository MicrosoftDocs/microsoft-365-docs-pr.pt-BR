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
- M365-security-compliance
localization_priority: Normal
description: Saiba mais sobre tarefas que ajudarão você a começar a usar rapidamente a conformidade no Microsoft 365.
ms.openlocfilehash: d2399b65e6f8d2765d3fc8691b0e395f113092f1
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200834"
---
# <a name="quick-tasks-for-getting-started-with-microsoft-365-compliance"></a>Tarefas rápidas de introdução ao Centro de conformidade do Microsoft 365.

Se você é novo na conformidade com a Microsoft 365 e está imaginando onde começar, este artigo fornece orientação sobre as noções básicas e prioriza tarefas de conformidade importantes. Este artigo ajudará você a começar rapidamente a gerenciar e monitorar seus dados, proteger as informações e minimizar os riscos Insider.

Este artigo também será útil se você estiver descobrindo a melhor maneira de gerenciar riscos, proteger seus dados e permanecer em conformidade com regulamentos e padrões com uma força de obra recentemente remota. Os funcionários agora estão colaborando e se conectando uns com os outros de novas maneiras, e isso significa que os processos e os controles de conformidade existentes podem precisar de adaptação. A identificação e o gerenciamento desses novos riscos de conformidade dentro da sua organização é fundamental para proteger seus dados e minimizar ameaças e riscos.

Depois de concluir essas tarefas básicas de conformidade, considere a expansão da cobertura de conformidade em sua organização implementando soluções adicionais de conformidade do Microsoft 365.

## <a name="task-1-configure-compliance-permissions"></a>Tarefa 1: configurar permissões de conformidade

É importante gerenciar quem em sua organização tem acesso ao centro de conformidade da Microsoft 365 para exibir conteúdo e realizar tarefas de gerenciamento. A Microsoft 365 fornece funções administrativas específicas para conformidade e para usar as ferramentas incluídas no centro de conformidade da Microsoft 365.

Comece atribuindo permissões de conformidade às pessoas em sua organização para que eles possam executar essas tarefas e impedir que pessoas não autorizadas tenham acesso a áreas fora de suas responsabilidades. Você deve ter certeza de que atribuiu as pessoas adequadas às funções de **administrador de dados de conformidade** e administrador de **conformidade** antes de começar a configurar e implementar as soluções de conformidade incluídas no Microsoft 365. Você também precisará atribuir usuários à função leitor global do Azure Active Directory para exibir dados no Gerenciador de conformidade.

Para obter uma orientação passo a passo para configurar permissões e atribuir pessoas a funções de administrador, consulte [permissões no centro de conformidade de & de segurança](../security/office-365-security/permissions-in-the-security-and-compliance-center.md).

## <a name="task-2-know-your-state-of-compliance"></a>Tarefa 2: saiba seu estado de conformidade

É difícil saber onde ir se você não sabe onde você está. Atender às suas necessidades de conformidade inclui entender seu nível atual de risco e quais atualizações podem ser necessárias nesses horários que estão sempre mudando. Se sua organização é nova para os requisitos de conformidade ou se apresenta uma experiência profunda com padrões e regulamentações que governam seu setor, a melhor maneira de melhorar a conformidade é entender onde a sua organização se refere.

O [Microsoft Compliance Manager](compliance-manager.md) pode ajudá-lo a entender a postura de conformidade da sua organização e destacar áreas que podem precisar de melhorias. O Gerenciador de conformidade usa um painel centralizado para calcular uma pontuação baseada em riscos, medindo seu progresso no preenchimento de ações que ajudam a reduzir os riscos relacionados à proteção de dados e aos padrões normativos. Você também pode usar o Gerenciador de conformidade como uma ferramenta para rastrear todas as avaliações de risco. Ele fornece recursos de fluxo de trabalho para ajudá-lo a concluir com eficiência as avaliações de riscos por meio de uma ferramenta comum.

Para obter uma orientação passo a passo para começar a usar o Gerenciador de conformidade, confira [introdução ao Gerenciador de conformidade](compliance-manager-setup.md).

>[!IMPORTANT]
>A segurança e a conformidade estão totalmente integradas à maioria das organizações. É importante que sua organização atenda às áreas de segurança básica, proteção contra ameaças e identidade e gerenciamento de acesso para ajudar a fornecer uma abordagem de defesa profunda para segurança e conformidade.
>
>Verifique sua [Pontuação segura do microsoft 365](../security/mtp/microsoft-secure-score.md) no centro de segurança da Microsoft 365 e conclua as tarefas descritas nos seguintes artigos:
>
> - [Mapa de segurança-principais prioridades para os primeiros 30 dias, 90 dias e depois](../security/office-365-security/security-roadmap.md)
> - [As 12 principais tarefas para equipes de segurança dar suporte ao trabalho de casa](../security/top-security-tasks-for-remote-work.md)

## <a name="task-3-enable-auditing-for-your-organization"></a>Tarefa 3: habilitar a auditoria para sua organização

Agora que você determinou o estado atual da sua organização e quem pode gerenciar as funções de conformidade, a próxima etapa é garantir que você tenha os dados para realizar investigações de conformidade e gerar relatórios para atividades de rede e de usuário em sua organização. Habilitar a auditoria também é um pré-requisito importante para as soluções de conformidade abordadas posteriormente neste artigo.

As ideias fornecidas pelo log de auditoria são uma ferramenta valiosa para ajudar a atender aos requisitos de conformidade com as soluções que podem ajudá-lo a gerenciar e monitorar áreas de conformidade que precisam de melhorias. O registro em log de auditoria deve ser ativado antes de as atividades serem gravadas e antes de você poder pesquisar o log de auditoria. Quando habilitada, a atividade de usuário e administrador de sua organização é registrada no log de auditoria e retida por 90 dias, e até um ano, dependendo da licença atribuída aos usuários.

Para obter instruções passo a passo para ativar a auditoria, consulte [Ativar ou desativar a pesquisa de log de auditoria](turn-audit-log-search-on-or-off.md).

## <a name="task-4-create-policies-to-alert-you-about-potential-compliance-issues"></a>Tarefa 4: criar políticas para alertá-lo sobre possíveis problemas de conformidade

A Microsoft fornece várias políticas de alerta internas que ajudam a identificar abuso de permissões de administrador, atividade de malware, ameaças externas e internas possíveis e riscos de governança de informações. Essas políticas são ativadas por padrão, mas talvez seja necessário configurar alertas personalizados para ajudar a gerenciar requisitos de conformidade específicos para sua organização.

Use a política de alerta e as ferramentas de painel de alerta para criar políticas de alerta personalizadas e exibir os alertas gerados quando os usuários executarem atividades que correspondam às condições da política. Alguns exemplos podem ser o uso de políticas de alerta para controlar as atividades do usuário e do administrador que afetam os requisitos de conformidade, permissões e incidentes de perda de dados em sua organização.

Para obter uma orientação passo a passo para criar políticas de alerta personalizadas, consulte [políticas de alerta no centro de segurança e conformidade](alert-policies.md).

## <a name="task-5-configure-just-in-time-access-for-your-administrators"></a>Tarefa 5: configurar o acesso just-in-time para seus administradores

Ter acesso à parte de alguns usuários a informações confidenciais ou configurações de rede críticas é um possível caminho para as contas comprometidas ou atividades internas de ameaça. O [Gerenciamento de acesso privilegiado](privileged-access-management-overview.md) ajuda a proteger sua organização contra violações e ajuda a atender às práticas recomendadas de conformidade, limitando o acesso à posição de dados confidenciais ou ao acesso a definições de configuração críticas. Em vez de os administradores terem acesso constante, as regras de acesso just-in-time são implementadas para tarefas que precisam de permissões elevadas. Habilitar o gerenciamento de acesso privilegiado no Microsoft 365 permite que sua organização opere com nenhum privilégio de pé e forneça uma camada de defesa contra vulnerabilidades de acesso administrativo.

Para obter uma orientação passo a passo para configurar o gerenciamento de acesso privilegiado, confira [introdução ao gerenciamento de acesso privilegiado](privileged-access-management-configuration.md). Para obter informações sobre licenciamento de gerenciamento de acesso privilegiado, consulte [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#privileged-access-management-in-office-365).

## <a name="task-6-classify-and-protect-sensitive-data"></a>Tarefa 6: classificar e proteger dados confidenciais

Para realizar o trabalho, as pessoas da sua organização colaboram com outras pessoas dentro e fora da organização. Isso significa que o conteúdo não fica mais atrás de um firewall, ele pode circular em qualquer lugar, em dispositivos, aplicativos e serviços. E quando estiver em roaming, você quer fazê-lo de uma maneira segura e protegida que atenda às políticas de negócios e conformidade da sua organização.

Os [Rótulos de confidencialidade](sensitivity-labels.md) permitem que você classifique e proteja os dados da sua organização, ao mesmo tempo em que a produtividade do usuário e sua capacidade de colaborar não é prejudicada. Use rótulos de confidencialidade para impor restrições de criptografia e uso aplicar marcas visuais e proteger informações entre plataformas e dispositivos, no local e na nuvem.

Para obter uma orientação passo a passo para configurar e usar rótulos de sensibilidade, confira [introdução aos rótulos de confidencialidade](get-started-with-sensitivity-labels.md). Para obter informações sobre licenciamento de rótulo de confidencialidade, confira [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection).

## <a name="task-7-configure-a-retention-policy"></a>Tarefa 7: configurar uma política de retenção

Uma [política de retenção](retention.md) permite que você decida de forma proativa se deseja reter o conteúdo, excluir conteúdo ou ambos – reter e excluir o conteúdo no final de um período de retenção especificado. Essas ações podem ser necessárias para cumprir as políticas internas e regulamentações do setor, além de reduzir o risco no caso de litígio ou uma violação de segurança.

Quando o conteúdo está sujeito a uma política de retenção, as pessoas podem continuar a editar e trabalhar com o conteúdo como se nada fosse alterado. O conteúdo é mantido no lugar, em seu local original. Mas, se alguém editar ou excluir o conteúdo que está sujeito à política de retenção, uma cópia do conteúdo original será salva em um local seguro, onde será mantida enquanto a política de retenção desse conteúdo estiver em vigor.

Você pode colocar rapidamente uma política de retenção em vigor para vários locais no seu ambiente do Microsoft 365, como o email do Exchange, sites do SharePoint, contas do OneDrive e Microsoft 365 grupos. Não há limites para o número de caixas de correio ou sites que essa política pode incluir automaticamente. Mas se você precisar obter mais seletivamente, você pode fazer isso Configurando uma política de retenção para locais específicos e incluir ou excluir sites ou usuários.

Para obter uma orientação passo a passo para configurar uma política de retenção, consulte [Create and configure Retention Policies](create-retention-policies.md). Se você é novo na configuração de retenção no Microsoft 365, consulte [Iniciar com políticas de retenção e rótulos de retenção](get-started-with-retention.md).

## <a name="task-8-configure-sensitive-information-and-offensive-language-policies"></a>Tarefa 8: configurar informações confidenciais e políticas de linguagem ofensivas

Proteger informações confidenciais e detectar e atuar nos incidentes de assédio de área de trabalho é uma parte importante da conformidade com políticas e padrões internos. A [conformidade de Comunicação](communication-compliance-feature-reference.md) no Microsoft 365 ajuda a minimizar esses riscos ajudando-o a detectar, capturar e realizar ações de correção para email e comunicações do Microsoft Teams. Isso inclui comunicações inadequadas contendo profanação, ameaças e assédio e comunicações que compartilham informações confidenciais dentro e fora da sua organização.

Um modelo de política de *linguagem ofensiva e antiassédios* predefinidos permite que você examine comunicações internas e externas para correspondências de política, para que eles possam ser examinados por revisores designados. Os revisores podem investigar emails varridos, Microsoft Teams, Yammer ou comunicações de terceiros em sua organização e tomar as ações de correção apropriadas para garantir que eles estejam em conformidade com os padrões da sua organização.

O modelo de política de *informações confidenciais* predefinido ajuda você a criar rapidamente uma política para verificar emails e comunicações do Microsoft Teams que contêm tipos de informações confidenciais definidos ou palavras-chave para ajudar a garantir que dados importantes não sejam compartilhados com pessoas que não deveriam ter acesso. Essas atividades podem incluir comunicação não autorizada sobre projetos confidenciais ou regras específicas do setor no insider trading ou outras atividades do collusion.

Para obter uma orientação passo a passo para planejar e configurar a conformidade de comunicação, consulte [Plan for Communication Compliance](communication-compliance-plan.md) e [introdução à conformidade de comunicação](communication-compliance-configure.md). Para obter informações sobre licenciamento de conformidade de comunicação, confira [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#communication-compliance).

## <a name="task-9-see-whats-happening-with-your-sensitive-items"></a>Tarefa 9: ver o que está acontecendo com seus itens confidenciais

Os rótulos de confidencialidade, os tipos de informações confidenciais, os rótulos de retenção e as políticas e os classificadores treináveis podem ser usados para classificar e rotular itens confidenciais no Exchange, no SharePoint e no OneDrive, conforme visto nas tarefas anteriores. A última etapa da sua jornada de tarefa rápida é ver quais itens foram rotulados e quais ações seus usuários estão levando nesses itens confidenciais. o [Gerenciador de conteúdo](data-classification-content-explorer.md) e o explorador de [atividade](data-classification-activity-explorer.md) oferecem essa visibilidade.

### <a name="content-explorer"></a>Explorador de conteúdo
 O Gerenciador de conteúdo permite que você visualize, em seu formato nativo, todos os itens que foram classificados como um tipo de informação confidencial ou pertencentes a uma determinada classificação por um classificador treinado, bem como todos os itens que têm sensibilidade ou rótulo de retenção aplicado.

Para obter uma orientação passo a passo sobre como usar o Gerenciador de conteúdo, confira [conhecer a visão geral dos dados-data classificação](data-classification-overview.md)e começar o [Explorador de conteúdo](data-classification-content-explorer.md).

### <a name="activity-explorer"></a>Explorador de atividade
O Gerenciador de atividades ajuda você a monitorar o que está sendo feito com seus itens confidenciais classificados e rotulados em:
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

Para obter uma orientação passo a passo para usar o explorador de atividade, confira [introdução ao explorador de atividade](data-classification-activity-explorer.md).

## <a name="next-steps"></a>Próximas etapas

Agora que você configurou as noções básicas para o gerenciamento de conformidade da sua organização, considere as seguintes soluções de conformidade no Microsoft 365 para ajudá-lo a proteger informações confidenciais e a detectar e a lidar com riscos adicionais Insider.

### <a name="configure-retention-labels"></a>Configurar rótulos de retenção

Enquanto as políticas de retenção são aplicadas no nível do contêiner para locais como sites do SharePoint e caixas de correio do Exchange, os [Rótulos de retenção](retention.md#retention-labels) permitem um direcionamento mais específico para suas políticas de retenção e exclusão. Por exemplo, no nível do documento ou da mensagem de email que os usuários finais podem aplicar manualmente, além do aplicativo automático pelos administradores. Você também pode aplicar um rótulo de retenção a uma biblioteca de documentos, pasta ou conjunto de documentos no SharePoint, para que todos os documentos armazenados nesse local herdem o rótulo de retenção padrão.

Além disso, os rótulos de retenção suportam o [Gerenciamento de registros](records-management.md) para marcar o conteúdo como um registro. Quando isso acontece, o rótulo coloca restrições adicionais sobre o conteúdo que pode ser necessário para ajudar sua organização a cumprir os requisitos normativos.

Para obter uma orientação passo a passo para criar e publicar rótulos de retenção, consulte as orientações a seguir:
- [Criar rótulos de retenção e aplicá-los em aplicativos](create-apply-retention-labels.md)
- [Aplicar um rótulo de retenção automaticamente ao conteúdo](apply-retention-labels-automatically.md)

Para começar a usar o gerenciamento de registros, confira [introdução ao gerenciamento de registros](get-started-with-records-management.md).

### <a name="identify-and-define-sensitive-information-types"></a>Identificar e definir tipos de informações confidenciais

Definir tipos de informações confidenciais com base no padrão contido nas informações dos dados da sua organização. Use [tipos de informações confidenciais internos](what-the-sensitive-information-types-look-for.md) ajuda a identificar e proteger números de cartão de crédito, números de contas bancárias, números de passaportes e muito mais. Ou criar seus próprios [tipos de informações de confidencialidade personalizados](custom-sensitive-info-types.md) específicos para sua organização.

Para obter uma orientação passo a passo para definir tipos de informações confidenciais personalizados, consulte [criar um tipo de informação confidencial personalizado no centro de conformidade de & de segurança](https://docs.microsoft.com/microsoft-365/compliance/create-a-custom-sensitive-information-type).

### <a name="prevent-data-loss"></a>Evita a perda de dados

[As políticas de prevenção contra perda de dados (DLP)](data-loss-prevention-policies.md) permitem identificar, monitorar e proteger automaticamente as informações confidenciais em sua organização do Microsoft 365. Use políticas de DLP para identificar itens confidenciais nos serviços da Microsoft, impedir o compartilhamento acidental de itens confidenciais e ajudar os usuários a aprender a manter a conformidade sem interromper o fluxo de trabalho.

Para obter uma orientação passo a passo para configurar políticas de DLP, confira introdução [às recomendações de política de DLP](get-started-with-dlp-policy-recommendations.md) e comece [a usar a política de DLP padrão](get-started-with-the-default-dlp-policy.md). Para obter informações sobre licenciamento de gerenciamento de perda de dados, confira [diretrizes de licenciamento da Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#office-365-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

### <a name="detect-and-act-on-insider-risks"></a>Detectar e agir em riscos Insider

Cada vez mais, os funcionários têm acesso crescente para criar, gerenciar e compartilhar dados em um amplo espectro de plataformas e serviços. Na maioria dos casos, as organizações têm recursos e ferramentas limitados para identificar e reduzir os riscos da organização e, ao mesmo tempo, atendem aos requisitos de conformidade e aos padrões de privacidade do funcionário. Esses riscos podem incluir roubo de dados, por meio da remoção de funcionários e vazamentos de dados de informações fora da sua organização por meio de sobrecompartilhamento acidental ou intenção mal-intencionada.

O [Gerenciamento de riscos do insider](insider-risk-management-policies.md) no Microsoft 365 usa toda a amplitude dos indicadores de serviço e de terceiros para ajudá-lo a identificar, fazer a triagem e agir rapidamente sobre atividades arriscadas do usuário. Usando logs do Microsoft 365 e Microsoft Graph, o gerenciamento de riscos do insider permite que você defina políticas específicas para identificar os indicadores de risco e realizar ações para reduzir esses riscos.

Para obter orientações passo a passo para planejar e configurar políticas de gerenciamento de risco do Insider, confira [planejar o gerenciamento de risco do insider](insider-risk-management-plan.md) e começar a usar o [Gerenciamento de riscos do insider](insider-risk-management-configure.md). Para informações sobre licenciamento de gerenciamento de risco do Insider, consulte [diretrizes de licenciamento do Microsoft 365 para segurança & conformidade](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#insider-risk-management).
