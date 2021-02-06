---
title: Estudo de caso – a Contoso configura rapidamente uma política de linguagem ofensiva para comunicações do Microsoft Teams, Exchange e Yammer
description: Um estudo de caso para a Contoso e como eles configuram rapidamente uma política de conformidade de comunicação para monitorar o idioma ofensivo nas comunicações do Microsoft Teams, do Exchange Online e do Yammer.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- remotework
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 1b9bef180fed9c3afa3b3d8d2319a1fa0260ed14
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126590"
---
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Estudo de caso – a Contoso configura rapidamente uma política de linguagem ofensiva para comunicações do Microsoft Teams, Exchange e Yammer

A conformidade de comunicação no Microsoft 365 ajuda a minimizar os riscos de comunicação, ajudando você a detectar, capturar e agir em mensagens inadequadas em sua organização. Políticas pré-definidas e personalizadas permitem que você examine as comunicações internas e externas para que elas possam ser examinadas por revisores designados. Os revisadores podem investigar emails verificados, o Microsoft Teams, o Yammer ou comunicações de terceiros em sua organização e tomar as ações de correção apropriadas para garantir que eles estão em conformidade com os padrões de mensagens da sua organização.

A Contoso Corporation é uma organização fictícia que precisa configurar rapidamente uma política para monitorar o idioma ofensivo. Eles têm usado o Microsoft 365 principalmente para o suporte a email, Microsoft Teams e Yammer para seus usuários, mas têm novos requisitos para impor a política da empresa em relação ao local de trabalho. Os administradores de TI e especialistas em conformidade da Contoso têm uma compreensão básica dos conceitos básicos de como trabalhar com o Microsoft 365 e estão procurando orientações de ponta a ponta sobre como começar rapidamente com a conformidade de comunicação.

Este estudo de caso abrange as noções básicas para configurar rapidamente uma política de conformidade de comunicação para monitorar as comunicações para linguagem ofensiva. Essas diretrizes incluem:

- Etapa 1 - Planejamento de conformidade de comunicação
- Etapa 2: acessar a conformidade de comunicação no Microsoft 365
- Etapa 3: configurar pré-requisitos e criar uma política de conformidade de comunicação
- Etapa 4 - Investigação e correção de alertas

## <a name="step-1-planning-for-communication-compliance"></a>Etapa 1: Planejamento de conformidade de comunicação

Os administradores de TI e especialistas em conformidade da Contoso participaram de webinars online sobre soluções de conformidade no Microsoft 365 e decidiram que as políticas de conformidade de comunicação os ajudarão a atender aos requisitos de política corporativa atualizados para reduzir o abuso no local de trabalho. Trabalhando juntos, eles desenvolveram um plano para criar e habilitar uma política de conformidade de comunicação que monitorará um idioma ofensivo para chats enviados no Microsoft Teams, mensagens privadas e conversas da comunidade no Yammer e em mensagens de email enviadas no Exchange Online. O plano inclui a identificação:

- Os administradores de IT que precisam de acesso aos recursos de conformidade de comunicação.
- Os especialistas em conformidade que precisam criar e gerenciar políticas de comunicação.
- Os especialistas em conformidade e outros colegas de outros departamentos (recursos humanos, jurídicos etc.) que precisam investigar e remediar alertas de conformidade de comunicação.
- Os usuários que estarão no escopo da política de linguagem ofensiva de conformidade de comunicação.

### <a name="licensing"></a>Licenciamento

A primeira etapa é confirmar se o licenciamento do Microsoft 365 da Contoso inclui suporte para a solução de conformidade de comunicação. Para acessar e usar a conformidade de comunicação, os administradores de IT da Contoso precisam verificar se a Contoso tem um dos seguintes:

- Assinatura do Microsoft 365 E5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 E3 + complemento de Conformidade do Microsoft 365 E5
- Assinatura do Microsoft 365 E3 + o complemento Microsoft 365 E5 Insider Risk Management
- Assinatura do Microsoft 365 A5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 A3 + complemento de Conformidade do Microsoft 365 A5
- Assinatura do Microsoft 365 A3 + o complemento Microsoft 365 A5 Insider Risk Management
- Assinatura do Microsoft 365 G5 (versão paga ou de avaliação)
- Assinatura do Microsoft 365 G5 + o complemento de Conformidade do Microsoft 365 G5
- Assinatura do Microsoft 365 G5 + o complemento Microsoft 365 G5 Insider Risk Management
- Assinatura do Office 365 Enterprise E5 (versão paga ou de avaliação)
- Assinatura do Office 365 Enterprise E3 + complemento de Conformidade Avançada do Office 365 (não está mais disponível para novas assinaturas, confira a observação)

Eles também devem confirmar se os usuários incluídos nas políticas de conformidade de comunicação devem ter uma das licenças atribuídas acima.

>[!IMPORTANT]
>A Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma. Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.

Os administradores de IT da Contoso seguem as seguintes etapas para verificar o suporte de licenciamento para a Contoso:

1. Os administradores de IT entrarão no Centro de administração do **Microsoft 365** [( https://admin.microsoft.com)](https://admin.microsoft.com) e naveguem até Licenças de Cobrança do Centro de administração do Microsoft **365.**  >    >  

2. Aqui, eles confirmam que têm uma das opções [de licença](communication-compliance-configure.md#subscriptions-and-licensing) que inclui suporte para conformidade de comunicação.

![Licenciamento de conformidade de comunicação](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Permissões para conformidade de comunicação

Há cinco grupos de função usados para configurar permissões para gerenciar recursos de conformidade de comunicação. Para **disponibilizar** a conformidade de comunicação como uma opção de menu no centro de conformidade do Microsoft 365 e continuar com essas etapas de configuração, os administradores da Contoso são atribuídos com a função de Administrador de Conformidade *de* Comunicação.

A Contoso decide usar o grupo *de* função conformidade de comunicação para atribuir todos os administradores de conformidade de comunicação, analistas, investigadores e visualizadores ao grupo. Isso torna mais fácil para a Contoso começar de forma rápida e melhor atendendo aos seus requisitos de gerenciamento de conformidade.

|**Função**|**Permissões de função**|
|:-----|:-----|
| **Conformidade de Comunicação** | Use esse grupo de função para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de função para configurar inicialmente a conformidade de comunicação e posteriormente segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de função podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagem. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas às quais são atribuídos como Revisadores, exibir metadados de mensagem (não conteúdo de mensagem), escalonar para revistores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Investigador de conformidade de comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados e conteúdo de mensagens, escalonar para revistores adicionais, escalonar para um caso de Descoberta Avançada, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões a usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de função podem acessar todos os widgets de relatórios na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

1. Os administradores de IT da Contoso podem entrar na página de permissões do Centro de Conformidade e Segurança do **Office 36 & 5** [(usando https://protection.office.com/permissions)](https://protection.office.com/permissions) credenciais para uma conta de administrador global e selecionar o link para exibir e gerenciar funções no Microsoft 365.
2. No Centro **de Conformidade &** segurança,  eles vão para Permissões e selecionam o link para exibir e gerenciar funções no Office 365.
3. Os administradores selecionam o *grupo de função Conformidade* de Comunicação e, em seguida, **selecionam Editar grupo de funções.**
4. Os administradores **selecionam Escolher membros** no painel de navegação esquerdo e, em seguida, selecione **Editar.**
5. Eles **selecionam Adicionar** e marcar a caixa de seleção para todos os usuários da Contoso que gerenciarão a conformidade de comunicação, investigarão e analisarão os alertas.
6. Os administradores **selecionam Adicionar** e, em seguida, **Pronto.**
7. Eles **selecionam Salvar** para adicionar usuários contoso ao grupo de funções. Eles **selecionam Fechar** para concluir as etapas.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Etapa 2: Acessar a conformidade de comunicação no Microsoft 365

Depois de configurar as permissões para conformidade de comunicação, os administradores de TI e especialistas em conformidade da Contoso atribuídos ao grupo de função conformidade de comunicação podem acessar a solução de conformidade de comunicação no Microsoft 365. Os administradores de TI e especialistas em conformidade da Contoso têm várias maneiras de acessar a conformidade de comunicação e começar a criar uma nova política:

- Iniciando diretamente da solução de conformidade de comunicação
- A partir do centro de conformidade do Microsoft 365
- A partir do catálogo de soluções do Microsoft 365
- A partir do Centro de administração do Microsoft 365

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Iniciando diretamente da solução de conformidade de comunicação

A maneira mais rápida de acessar a solução é entrar diretamente na solução de conformidade **() de** <https://compliance.microsoft.com/supervisoryreview> comunicação. Usando este link, os administradores de TI e especialistas em conformidade da Contoso serão direcionados para o painel visão geral de conformidade de comunicações, onde você pode analisar rapidamente o status de alertas e criar novas políticas a partir dos modelos predefinidas.

![Visão geral da conformidade de comunicação](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>A partir do centro de conformidade do Microsoft 365

Outra maneira fácil para os administradores de TI e especialistas em conformidade da Contoso acessarem a solução de conformidade de comunicação é entrar diretamente no centro de conformidade do **Microsoft 365** [( https://compliance.microsoft.com)](https://compliance.microsoft.com). Depois de entrar, os usuários  simplesmente precisam selecionar Mostrar todo o  controle para exibir todas as soluções de conformidade e, em seguida, selecionar a solução de conformidade de comunicação para começar.

![Centro de conformidade](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>A partir do catálogo de soluções do Microsoft 365

Os administradores de TI e especialistas em conformidade da Contoso também podem optar por acessar a solução de conformidade de comunicação selecionando o catálogo de soluções do Microsoft 365. Selecionando **a** seção Catálogo em Soluções da navegação à esquerda no centro de conformidade do **Microsoft 365,** eles podem abrir o catálogo de soluções listando todas as soluções de conformidade do Microsoft 365.  Scrolling down to the **Insider risk management** section, Contoso IT administrators can select Communication compliance to get started. Os administradores de IT da Contoso também decidem usar o controle mostrar na navegação para fixar a solução de conformidade de comunicação no painel de navegação à esquerda para acesso mais rápido quando eles entrarem no futuro.

![Catálogo de soluções](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>A partir do centro de administração do Microsoft 365

Para acessar a conformidade de comunicação ao iniciar pelo centro de administração do Microsoft 365, os administradores de TI e especialistas em conformidade da Contoso acessam o centro de administração do Microsoft 365 [( https://admin.microsoft.com)](https://admin.microsoft.com) e naveguem até o Centro de Administração do **Microsoft 365.**  >  

![Link de conformidade de comunicação](../media/communication-compliance-case-compliance-link.png)

Essa ação abre o Centro de Conformidade e Segurança do **Office 365,** e eles devem selecionar o link para o centro de conformidade do **Microsoft 365** fornecido na faixa na parte superior da página.

![Centro de conformidade e segurança do Office 365](../media/communication-compliance-case-scc.png)

Uma vez no centro **de conformidade do Microsoft 365,** os administradores de TI da Contoso selecionam Mostrar tudo para exibir a lista completa de soluções de conformidade. 

![Menu de conformidade de comunicação](../media/communication-compliance-case-show-all.png)

Depois de **selecionar Mostrar tudo,** os administradores de IT da Contoso podem acessar a solução de conformidade de comunicação.

![Visão geral da conformidade de comunicação](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Etapa 3: Configurar pré-requisitos e criar uma política de conformidade de comunicação

Para começar a trabalhar com uma política de conformidade de comunicação, há vários pré-requisitos que os administradores de IT da Contoso precisam configurar antes de configurar a nova política para monitorar o idioma ofensivo. Depois que esses pré-requisitos são concluídos, os administradores de TI e especialistas em conformidade da Contoso podem configurar a nova política e os especialistas em conformidade podem iniciar a investigação e a correção de quaisquer alertas gerados.

### <a name="enabling-auditing-in-microsoft-365"></a>Habilitando a auditoria no Microsoft 365

A conformidade de comunicação requer logs de auditoria para mostrar alertas e rastrear ações de correção tomadas pelos revisadores. Os logs de auditoria são um resumo de todas as atividades associadas a uma política organizacional definida ou sempre que há uma alteração em uma política de conformidade de comunicação.

Os administradores de IT da Contoso revisam e concluem as instruções passo a [passo](turn-audit-log-search-on-or-off.md) para ativar a auditoria. Depois que eles ativarem a auditoria, será exibida uma mensagem informando que o log de auditoria está sendo preparado e que eles podem executar uma pesquisa em algumas horas após a conclusão da preparação. Os administradores de IT da Contoso só terão que fazer essa ação uma vez.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Configurando o locatário do Yammer para o Modo Nativo

A conformidade de comunicação requer que o locatário do Yammer de uma organização está no modo Nativo para monitorar o idioma ofensivo em mensagens privadas e conversas públicas da comunidade.

Os administradores de TI da Contoso garantem que revisem as informações no artigo Visão geral do Modo Nativo do Yammer no [Microsoft 365](/yammer/configure-your-yammer-network/overview-native-mode) e siga as etapas para executar a ferramenta de migração no artigo Configurar sua rede do Yammer para o Modo Nativo do [Microsoft 365.](/yammer/configure-your-yammer-network/native-mode)

### <a name="setting-up-a-group-for-in-scope-users"></a>Configurando um grupo para usuários no escopo

Os especialistas em conformidade da Contoso querem adicionar todos os usuários à política de comunicação que monitorará o idioma ofensivo. Eles podem optar por adicionar cada conta de usuário à política separadamente, mas decidiram  que é muito mais fácil e economiza tempo para usar um grupo de distribuição Todos os Usuários para os usuários dessa política.

Eles precisam criar um novo grupo para incluir todos os usuários da Contoso, portanto, eles devem seguir as seguintes etapas:

1. Os administradores de IT da Contoso se ins login no centro de administração do **Microsoft 365** [( https://admin.microsoft.com)](https://admin.microsoft.com) e navegue até Grupos do Centro de administração do Microsoft **365.**  >    >  
2. Eles **selecionam Adicionar um grupo** e concluem o assistente para criar um novo grupo ou grupo de *distribuição* do *Microsoft 365.*

    ![Grupos](../media/communication-compliance-case-all-employees.png)

3. Depois que o novo grupo é criado, eles precisam adicionar todos os usuários da Contoso ao novo grupo. Eles abrem o **Centro de administração do Exchange** ( [e https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) navegam para grupos de destinatários do Centro de administração do   >    >  Exchange. Os administradores de IT da Contoso  selecionam a área  Associação e o novo grupo Todos os Funcionários que criaram e selecionam o controle Editar para adicionar todos os usuários da Contoso ao novo grupo no assistente.

    ![Centro de administração do Exchange](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Criando a política a ser monitorada para linguagem ofensiva

Com todos os pré-requisitos concluídos, os administradores de TI e os especialistas em conformidade da Contoso estão prontos para configurar a política de conformidade de comunicação para monitorar o idioma ofensivo. Usando o novo modelo de política de idioma ofensivo, a configuração dessa política é simples e rápida.

1. Os administradores de TI e especialistas em conformidade da Contoso  se instalam no centro de conformidade do **Microsoft 365** e selecionam a conformidade de comunicação no painel de navegação esquerdo. Essa ação abre o painel **Visão geral** com links rápidos para modelos de política de conformidade de comunicação. Eles escolhem o **modelo De monitoramento de idioma** ofensivo **selecionando Começar** para o modelo.

    ![Modelo de linguagem ofensiva de conformidade de comunicação](../media/communication-compliance-case-template.png)

2. No assistente de modelo de política, os administradores de TI e especialistas em conformidade da Contoso trabalham juntos para concluir os três campos obrigatórios: nome da **política,** usuários ou grupos para supervisionar e **Revisadores.**
3. Como o assistente de política já sugere um nome para a política, os administradores de TI e especialistas em conformidade decidem manter o nome sugerido e se concentrar nos campos restantes. Eles selecionam o grupo  Todos os usuários dos Usuários ou grupos para supervisionar o campo e selecionar os especialistas em conformidade que devem investigar e remediar alertas de política para o campo Revisadores.   A última etapa para configurar a política e começar a coletar informações de alerta é selecionar Criar **política.**

    ![Assistente de linguagem ofensiva de conformidade de comunicação](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Etapa 4: investigar e remediar alertas

Agora que a política de conformidade de comunicação a ser monitorada para linguagem ofensiva está configurada, a próxima etapa para os especialistas em conformidade da Contoso será investigar e remediar quaisquer alertas gerados pela política. Levará até 24 horas para que a política processe totalmente as comunicações em todos os canais de origem de comunicação e para que os alertas aparecem no **painel alerta.**

Depois que os alertas são gerados, os especialistas em conformidade da Contoso seguirão as instruções do fluxo de trabalho para investigar e resolver problemas de linguagem ofensiva. [](communication-compliance-investigate-remediate.md)