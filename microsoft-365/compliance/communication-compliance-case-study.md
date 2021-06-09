---
title: Estudo de caso - a Contoso configura rapidamente uma política de linguagem ofensiva para comunicações Microsoft Teams, Exchange e Yammer comunicações
description: Um estudo de caso para a Contoso e como eles configuram rapidamente uma política de conformidade de comunicação para monitorar a linguagem ofensiva em Microsoft Teams, Exchange Online e Yammer comunicações.
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
# <a name="case-study---contoso-quickly-configures-an-offensive-language-policy-for-microsoft-teams-exchange-and-yammer-communications"></a>Estudo de caso - a Contoso configura rapidamente uma política de linguagem ofensiva para comunicações Microsoft Teams, Exchange e Yammer comunicações

A conformidade de comunicação Microsoft 365 ajuda a minimizar os riscos de comunicação, ajudando você a detectar, capturar e agir em mensagens inadequadas em sua organização. Políticas predefinidas e personalizadas permitem que você verifique as comunicações internas e externas em busca de correspondências de políticas, para que possam ser examinadas por revisores designados. Os revisadores podem investigar emails verificados, Microsoft Teams, Yammer ou comunicações de terceiros em sua organização e tomar ações de correção apropriadas para garantir que eles estão em conformidade com os padrões de mensagens da sua organização.

A Contoso Corporation é uma organização fictícia que precisa configurar rapidamente uma política para monitorar o idioma ofensivo. Eles têm usado o Microsoft 365 principalmente para email, Microsoft Teams e Yammer suporte para seus usuários, mas têm novos requisitos para impor a política da empresa em relação ao assédio no local de trabalho. Os administradores de TI e especialistas em conformidade da Contoso têm uma compreensão básica dos fundamentos de trabalhar com o Microsoft 365 e estão procurando orientações de ponta a ponta sobre como começar rapidamente com a conformidade de comunicação.

Este estudo de caso abrange as noções básicas para configurar rapidamente uma política de conformidade de comunicação para monitorar as comunicações com linguagem ofensivo. Essas orientações incluem:

- Etapa 1 - Planejamento para conformidade de comunicação
- Etapa 2: acessando a conformidade de comunicação no Microsoft 365
- Etapa 3 - Configurar pré-requisitos e criar uma política de conformidade de comunicação
- Etapa 4 - Investigação e mediação de alertas

## <a name="step-1-planning-for-communication-compliance"></a>Etapa 1: Planejamento para conformidade de comunicação

Os administradores de TI e especialistas em conformidade da Contoso participaram de webinars online sobre soluções de conformidade no Microsoft 365 e decidiram que as políticas de conformidade de comunicação os ajudarão a atender aos requisitos de política corporativa atualizados para reduzir o assédio no local de trabalho. Trabalhando em conjunto, eles desenvolveram um plano para criar e habilitar uma política de conformidade de comunicação que monitorará a linguagem ofensiva para chats enviados no Microsoft Teams, mensagens privadas e conversas da comunidade no Yammer e em mensagens de email enviadas no Exchange Online. O plano inclui a identificação de:

- Os administradores de IT que precisam de acesso aos recursos de conformidade de comunicação.
- Os especialistas em conformidade que precisam criar e gerenciar políticas de comunicação.
- Os especialistas em conformidade e outros colegas em outros departamentos (Recursos Humanos, Jurídicos etc.) que precisam investigar e correção de alertas de conformidade de comunicação.
- Os usuários que estarão no escopo da política de linguagem ofensiva de conformidade de comunicação.

### <a name="licensing"></a>Licenciamento

A primeira etapa é confirmar se o licenciamento Microsoft 365 da Contoso inclui suporte para a solução de conformidade de comunicação. Para acessar e usar a conformidade de comunicação, os administradores de IT da Contoso precisam verificar se a Contoso tem um dos seguintes:

- Microsoft 365 E5 assinatura (versão paga ou de avaliação)
- Microsoft 365 E3 assinatura + o Microsoft 365 E5 Compliance complemento
- Microsoft 365 E3 assinatura + o complemento Microsoft 365 E5 Gerenciamento de Riscos do Insider
- Microsoft 365 Assinatura A5 (versão paga ou avaliação)
- Microsoft 365 Assinatura A3 + o complemento Microsoft 365 conformidade do A5
- Microsoft 365 Assinatura A3 + o complemento Microsoft 365 A5 Insider Risk Management
- Microsoft 365 Assinatura G5 (versão paga ou de avaliação)
- Microsoft 365 Assinatura do G5 + o complemento Microsoft 365 conformidade do G5
- Microsoft 365 Assinatura do G5 + o complemento Microsoft 365 G5 Insider Risk Management
- Office 365 Enterprise Assinatura E5 (versão paga ou avaliação)
- Office 365 Enterprise Assinatura E3 + o Conformidade Avançada do Office 365 complemento (não está mais disponível para novas assinaturas, consulte observação)

Eles também devem confirmar que os usuários incluídos nas políticas de conformidade de comunicação devem ser atribuídos a uma das licenças acima.

>[!IMPORTANT]
>Conformidade Avançada do Office 365 não é mais vendida como uma assinatura autônoma. Quando as assinaturas atuais expirarem, os clientes devem fazer a transição para uma das assinaturas acima, que contêm os mesmos recursos de conformidade ou adicionais.

Os administradores de IT da Contoso seguem as seguintes etapas para verificar o suporte ao licenciamento da Contoso:

1. Os administradores de IT entrar no **centro** de administração do Microsoft 365 [ https://admin.microsoft.com) (](https://admin.microsoft.com) e navegar **até** o centro de administração Microsoft 365  >  **Cobrança de**  >  **Licenças**.

2. Aqui, eles confirmam que têm uma das opções [de licença](communication-compliance-configure.md#subscriptions-and-licensing) que inclui suporte para conformidade de comunicação.

![Licenciamento de conformidade de comunicação](../media/communication-compliance-case-licenses.png)

### <a name="permissions-for-communication-compliance"></a>Permissões para conformidade de comunicação

Há cinco grupos de função usados para configurar permissões para gerenciar recursos de conformidade de comunicação. Para **disponibilizar** a conformidade de comunicação como uma opção de menu no centro de conformidade Microsoft 365 e continuar com essas etapas de configuração, os administradores da Contoso são atribuídos à função Administrador de *Conformidade de* Comunicação.

A Contoso decide usar o grupo de *função Conformidade* de Comunicação atribui todos os administradores de conformidade de comunicação, analistas, investigadores e visualizadores ao grupo. Isso torna mais fácil para a Contoso começar rapidamente e se adequar melhor aos requisitos de gerenciamento de conformidade.

|**Função**|**Permissões de função**|
|:-----|:-----|
| **Conformidade de comunicação** | Use esse grupo de funções para gerenciar a conformidade de comunicação para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas, investigadores e visualizadores, você pode configurar permissões de conformidade de comunicação em um único grupo. Esse grupo de função contém todas as funções de permissão de conformidade de comunicação. Essa configuração é a maneira mais fácil de começar rapidamente com a conformidade de comunicação e é um bom ajuste para organizações que não precisam de permissões separadas definidas para grupos separados de usuários. |
| **Administrador de Conformidade de Comunicação** | Use esse grupo de funções para configurar inicialmente a conformidade de comunicação e posteriormente para segregar os administradores de conformidade de comunicação em um grupo definido. Os usuários atribuídos a esse grupo de funções podem criar, ler, atualizar e excluir políticas de conformidade de comunicação, configurações globais e atribuições de grupo de função. Os usuários atribuídos a esse grupo de funções não podem exibir alertas de mensagens. |
| **Analista de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir políticas nas quais são atribuídos como Revistores, exibir metadados de mensagens (não conteúdo de mensagem), escalonar para revisadores adicionais ou enviar notificações aos usuários. Os analistas não podem resolver alertas pendentes. |
| **Pesquisador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de conformidade de comunicação. Os usuários atribuídos a esse grupo de funções podem exibir metadados de mensagens e conteúdo, escalonar para revisadores adicionais, escalonar para um caso Advanced eDiscovery, enviar notificações aos usuários e resolver o alerta. |
| **Visualizador de Conformidade de Comunicação** | Use esse grupo para atribuir permissões aos usuários que gerenciarão relatórios de comunicação. Os usuários atribuídos a esse grupo de funções podem acessar todos os widgets de relatório na home page de conformidade de comunicação e podem exibir todos os relatórios de conformidade de comunicação. |

1. Os administradores de IT da Contoso entrarão na página permissões do Centro de Conformidade e Segurança Office 365 **&** [( https://protection.office.com/permissions)](https://protection.office.com/permissions) usando credenciais para uma conta de administrador global e selecione o link para exibir e gerenciar funções no Microsoft 365.
2. No Centro **de Conformidade &** segurança, eles vão para **Permissões** e selecionam o link para exibir e gerenciar funções em Office 365.
3. Os administradores selecionam o grupo *de função Conformidade* de Comunicação e, em seguida, selecione Editar grupo de **função**.
4. Os administradores **selecionam Escolher membros** no painel de navegação esquerdo e, em seguida, selecione **Editar**.
5. Eles **selecionam Adicionar** e, em seguida, selecione a caixa de seleção para todos os usuários da Contoso que gerenciarão a conformidade de comunicação, investigarão e revisarão alertas.
6. Os administradores **selecionam Adicionar**, em seguida, selecione **Feito**.
7. Eles **selecionam Salvar** para adicionar usuários contoso ao grupo de funções. Eles **selecionam Fechar** para concluir as etapas.

## <a name="step-2-accessing-communication-compliance-in-microsoft-365"></a>Etapa 2: Acessar a conformidade de comunicação no Microsoft 365

Depois de configurar as permissões de conformidade de comunicação, os administradores de TI e especialistas em conformidade da Contoso atribuídos ao grupo de função conformidade de comunicação podem acessar a solução de conformidade de comunicação no Microsoft 365. Os administradores de TI e especialistas em conformidade da Contoso têm várias maneiras de acessar a conformidade de comunicação e começar a criar uma nova política:

- Começando diretamente da solução de conformidade de comunicação
- A partir do Microsoft 365 de conformidade
- A partir do catálogo de Microsoft 365 de soluções
- A partir do Microsoft 365 de administração

### <a name="starting-directly-from-the-communication-compliance-solution"></a>Começando diretamente da solução de conformidade de comunicação

A maneira mais rápida de acessar a solução é entrar diretamente na solução **de conformidade** de comunicação ( <https://compliance.microsoft.com/supervisoryreview> ) Usando este link, os administradores de TI e especialistas em conformidade da Contoso serão direcionados para o painel Visão geral da conformidade de comunicação, onde você pode revisar rapidamente o status dos alertas e criar novas políticas a partir dos modelos pré-definidos.

![Visão geral da conformidade de comunicações](../media/communication-compliance-case-overview.png)

### <a name="starting-from-the-microsoft-365-compliance-center"></a>A partir do Microsoft 365 de conformidade

Outra maneira fácil para os administradores de TI e especialistas em conformidade da Contoso acessarem a solução de conformidade de comunicação é entrar diretamente no Microsoft 365 **de conformidade** [( https://compliance.microsoft.com)](https://compliance.microsoft.com). Depois de entrar, os usuários precisam simplesmente selecionar o controle **Mostrar todos** para exibir todas as soluções de conformidade e, em seguida, selecionar a solução de **Conformidade de comunicações** para começar.

![Centro de conformidade](../media/communication-compliance-case-center.png)

### <a name="starting-from-the-microsoft-365-solution-catalog"></a>A partir do catálogo de Microsoft 365 de soluções

Os administradores de TI e especialistas em conformidade da Contoso também podem optar por acessar a solução de conformidade de comunicação selecionando o catálogo Microsoft 365 solução. Selecionando a seção **Catálogo** em **Soluções** da navegação à esquerda enquanto estiver no centro de conformidade do Microsoft 365 **,** eles podem abrir o catálogo de soluções listando todas as Microsoft 365 de conformidade. Rolar para baixo até a seção Gerenciamento de riscos **do Insider,** os administradores de IT da Contoso podem selecionar Conformidade de comunicação para começar. Os administradores de IT da Contoso também decidem usar o controle de navegação Mostrar na navegação para fixar a solução de conformidade de comunicação ao painel de navegação à esquerda para acesso mais rápido quando eles entrarem em avançar.

![Catálogo de soluções](../media/communication-compliance-case-solution.png)

### <a name="starting-from-the-microsoft-365-admin-center"></a>A partir do Microsoft 365 de administração

Para acessar a conformidade de comunicação ao iniciar a partir do centro de administração do Microsoft 365, os administradores de TI e especialistas em conformidade da Contoso entrarão no centro de administração do Microsoft 365 [( https://admin.microsoft.com)](https://admin.microsoft.com) e navegue até o centro de administração Microsoft 365   >  **Conformidade**.

![Link de conformidade de comunicação](../media/communication-compliance-case-compliance-link.png)

Essa ação abre **Office 365** Central de Conformidade e Segurança e deve  selecionar o link para o centro de conformidade Microsoft 365 fornecido na faixa na parte superior da página.

![Office 365 de conformidade e segurança](../media/communication-compliance-case-scc.png)

Uma vez no **Microsoft 365 de conformidade,** os administradores de TI da Contoso **selecionam Mostrar** tudo para exibir a lista completa de soluções de conformidade.

![Menu de conformidade de comunicação](../media/communication-compliance-case-show-all.png)

Depois de **selecionar Mostrar tudo**, os administradores de IT da Contoso podem acessar a solução de conformidade de comunicação.

![Visão geral da conformidade de comunicações](../media/communication-compliance-case-overview.png)

## <a name="step-3-configuring-prerequisites-and-creating-a-communication-compliance-policy"></a>Etapa 3: Configurar pré-requisitos e criar uma política de conformidade de comunicação

Para começar a trabalhar com uma política de conformidade de comunicação, há vários pré-requisitos que os administradores de IT da Contoso precisam configurar antes de configurar a nova política para monitorar o idioma ofensivo. Depois que esses pré-requisitos foram concluídos, os administradores de TI e especialistas em conformidade da Contoso podem configurar a nova política e especialistas em conformidade podem iniciar a investigação e remediar todos os alertas gerados.

### <a name="enabling-auditing-in-microsoft-365"></a>Habilitando a auditoria no Microsoft 365

A Conformidade de comunicações requer logs de auditoria para mostrar alertas e controlar as ações de correção realizadas por revistores. Os logs de auditoria são um resumo de todas as atividades associadas a uma política organizacional definida ou a qualquer momento em que houver uma alteração em uma política de conformidade de comunicação.

Os administradores de IT da Contoso analisam e concluem [instruções passo a passo](turn-audit-log-search-on-or-off.md) ativar a auditoria. Após ativarem a auditoria, será exibida uma mensagem informando que o log de auditoria está sendo preparado e que é possível executar uma pesquisa dentro algumas horas após a conclusão da preparação. Os administradores de IT da Contoso só têm que fazer essa ação uma vez.

### <a name="configuring-yammer-tenant-for-native-mode"></a>Configurando Yammer locatário para Modo Nativo

A conformidade de comunicação requer que o Yammer locatário de uma organização está no Modo Nativo para monitorar o idioma ofensivo em mensagens privadas e conversas da comunidade pública.

Os administradores de IT da Contoso devem revisar as informações no artigo Visão geral do modo nativo do Yammer no Microsoft 365 e seguir as etapas para [executar a](/yammer/configure-your-yammer-network/overview-native-mode) ferramenta de migração no artigo Configurar sua rede [Yammer](/yammer/configure-your-yammer-network/native-mode) para Modo Nativo para Microsoft 365.

### <a name="setting-up-a-group-for-in-scope-users"></a>Configurar um grupo para usuários no escopo

Os especialistas em conformidade da Contoso querem adicionar todos os usuários à política de comunicação que monitorará o idioma ofensivo. Eles podem optar por adicionar cada conta de usuário à política separadamente, mas decidiram  que é muito mais fácil e economiza tempo para usar um grupo de distribuição Todos os Usuários para os usuários dessa política.

Eles precisam criar um novo grupo para incluir todos os usuários da Contoso, para que eles deem as seguintes etapas:

1. Os administradores de IT da Contoso entrar no centro **de** administração Microsoft 365 [( https://admin.microsoft.com)](https://admin.microsoft.com) e navegar até Microsoft 365 grupos do centro de **administração**  >    >  .
2. Eles **selecionam Adicionar um grupo** e concluem o assistente para criar um novo *grupo Microsoft 365 ou* grupo *de Distribuição.*

    ![Grupos](../media/communication-compliance-case-all-employees.png)

3. Depois que o novo grupo for criado, eles precisarão adicionar todos os usuários da Contoso ao novo grupo. Eles abrem o **Exchange de** [administração ( https://outlook.office365.com/ecp)](https://outlook.office365.com/ecp) e navegam para Exchange grupos de **destinatários** do centro  >  **de**  >  **administração.** Os administradores de IT da Contoso  selecionam a área Associação e o novo grupo Todos os Funcionários que eles criaram e selecione o controle **Editar** para adicionar todos os usuários contoso ao novo grupo no assistente.

    ![Centro de administração do Exchange](../media/communication-compliance-case-eac.png)

### <a name="creating-the-policy-to-monitor-for-offensive-language"></a>Criando uma política para monitorar o idioma ofensivo

Com todos os pré-requisitos concluídos, os administradores de TI e os especialistas em conformidade da Contoso estão prontos para configurar a política de conformidade de comunicação para monitorar o idioma ofensivo. Usar o novo modelo de política de linguagem ofensivo, configurar essa política é simples e rápido.

1. Os administradores de TI e especialistas em conformidade da Contoso no **Centro de conformidade do Microsoft 365** e selecione **Conformidade de comunicações** no painel de navegação à esquerda. Esta ação abre o painel **visão** links rápidos para modelos de política de Conformidade de comunicações. Ele escolhe o **Monitor para usar** idioma ofensivo selecionando **Começar a** para o modelo.

    ![Modelo de idioma ofensivo de conformidade de comunicação](../media/communication-compliance-case-template.png)

2. No assistente de modelo de política, os administradores de TI e especialistas em conformidade da Contoso trabalham juntos para preencher os três campos necessários: **Nome da política**, **usuários ou grupos para supervisão** e **revistores**.
3. Como o assistente de política já sugere um nome para a política, os administradores de TI e especialistas em conformidade decidem manter o nome sugerido e se concentrar nos campos restantes. Eles *selecionam* o grupo  Todos os usuários para o campo Usuários ou grupos para supervisionar e selecionar os especialistas em conformidade que devem investigar e correção de alertas de política para o campo **Revistores.** A última etapa para configurar a política e começar a coletar informações de alerta é selecionar **Criar política**.

    ![Assistente de linguagem ofensiva de conformidade de comunicação](../media/communication-compliance-case-wizard.png)

## <a name="step-4-investigate-and-remediate-alerts"></a>Etapa 4: investigar e correção de alertas

Agora que a política de conformidade de comunicação para monitorar o idioma ofensivo está configurada, a próxima etapa para os especialistas em conformidade da Contoso será investigar e remediar todos os alertas gerados pela política. Levará até 24 horas para que a política processe totalmente as comunicações em todos os canais de origem de comunicação e alertas aparecerem no painel de alerta do **para**.

Depois que os alertas são gerados, os especialistas em conformidade da Contoso seguirão as instruções de fluxo de trabalho para investigar e resolver problemas de idioma ofensivo. [](communication-compliance-investigate-remediate.md)