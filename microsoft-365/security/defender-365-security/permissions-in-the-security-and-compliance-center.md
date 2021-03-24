---
title: Permissões - Centro de Conformidade & segurança
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.AdminRoleGroups
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
description: Os administradores podem saber mais sobre as permissões disponíveis no Centro de Conformidade & segurança no Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 769396dc2c39b5b0efe2f1141f07e6c05f6a43bd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052815"
---
# <a name="permissions-in-the-security--compliance-center"></a>Permissões no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

O Centro de Conformidade & segurança permite conceder permissões a pessoas que executam tarefas de conformidade, como gerenciamento de dispositivos, prevenção contra perda de dados, Descoberta Eletrônico, retenção e assim por diante. Essas pessoas podem realizar apenas as tarefas para as quais você concedeu acesso especificamente. Para acessar o Centro de Conformidade & segurança, os usuários precisam ser um administrador global ou membro de um ou mais grupos de função do Centro de Conformidade & segurança.

As permissões no Centro de Conformidade & segurança se baseiam no modelo de permissões de controle de acesso baseado em função (RBAC). O RBAC é o mesmo modelo de permissões usado pelo Exchange, portanto, se você estiver familiarizado com o Exchange, conceder permissões no Centro de Conformidade & segurança será muito semelhante. No entanto, é importante lembrar que os grupos de função do Exchange e os grupos de função & de Segurança do Centro de Conformidade não compartilham associações ou permissões. Eles não são os mesmos, visto que ambos possuem um grupo de funções de Gerenciamento de Organização. As permissões que concedem e os membros dos grupos de função são diferentes. Há uma lista de grupos de função do Centro de Conformidade & Segurança abaixo.

![Página Permissões no Centro de Conformidade & Segurança](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relação de membros, funções e grupos de função

Uma **função** concede permissões para realizar um conjunto de tarefas; por exemplo, a função de Gerenciamento de Casos permite que as pessoas trabalhem em casos de Descoberta Eletrônica.

Um **grupo de funções** é um conjunto de funções que permite que as pessoas faça seus trabalhos no Centro de Conformidade & Segurança. Por exemplo, o grupo de função Administrador de Conformidade inclui (entre outras funções) as funções para Gerenciamento de Caso, Pesquisa de Conteúdo e Configuração da Organização (além de outras) porque alguém que é um administrador de conformidade precisará das permissões para essas tarefas realizarem seu trabalho.

O Centro de & de Conformidade inclui grupos de funções padrão para as tarefas e funções mais comuns às que você precisará atribuir às pessoas. Recomendamos simplesmente adicionar usuários individuais como **membros** aos grupos de função padrão.

![Diagrama que mostra a relação de grupos de funções para membros e funções](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Permissões necessárias para usar recursos no Centro de Conformidade & Segurança

A tabela a seguir lista os grupos de função padrão que estão disponíveis no Centro de Conformidade & Segurança e as funções atribuídas aos grupos de função por padrão. Para conceder permissões a um usuário para executar uma tarefa de conformidade, adicione-as ao grupo de função & Centro de Conformidade e Segurança apropriado.

O gerenciamento de permissões no Centro de Conformidade & segurança só dá aos usuários acesso aos recursos de conformidade disponíveis no Centro de Conformidade & segurança. Se você quiser conceder permissões a outros recursos de conformidade que não estão no Centro de Conformidade do & segurança, como regras de fluxo de emails do Exchange (também conhecidas como regras de transporte), você precisa usar o Centro de administração do Exchange.

Para ver como conceder acesso ao Centro de Conformidade & Segurança, confira Dar aos usuários acesso ao Centro de administração de [Conformidade do Microsoft 365](grant-access-to-the-security-and-compliance-center.md).

> [!NOTE]
> Para exibir a **guia Permissões** no Centro de Conformidade & segurança, você precisa ser um administrador. Especificamente, você precisa ter  a função gerenciamento de função e essa  função é atribuída apenas ao grupo de função Gerenciamento da Organização no Centro de Conformidade e Segurança & por padrão. Além disso, a **função Gerenciamento de** Função permite que os usuários visualizam, criem e modifiquem grupos de função.

<br><br>

****

|Grupo de função|Descrição|Funções padrão atribuídas|
|---|---|---|
|**Conformidade de comunicação**|Fornece permissão para todas as funções de conformidade de comunicação: administrador, analista, pesquisador e visualizador.|Gerenciamento de Casos <p> Administrador de Conformidade de Comunicação <p> Análise de Conformidade de Comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação <p> Investigação de Conformidade de Comunicação <p> Visualizador de Conformidade de Comunicação <p> Provedor de feedback de classificação de dados <p> View-Only Caso|
|**Administradores de Conformidade de Comunicação**|Administradores de conformidade de comunicação que podem criar/editar políticas e definir configurações globais.|Administrador de Conformidade de Comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação|
|**Analistas de Conformidade de Comunicação**|Analistas de conformidade de comunicação que podem investigar as combinações de política, exibir os dados de meta de mensagens e realizar ações de correção.|Análise de Conformidade de Comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação|
|**Investigadores de Conformidade de Comunicação**|Analistas de conformidade de comunicação que podem investigar as combinações de política, exibir o conteúdo da mensagem e realizar ações de correção.|Gerenciamento de Casos <p> Análise de Conformidade de Comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação <p> Investigação de Conformidade de Comunicação <p> Provedor de feedback de classificação de dados <p> View-Only Caso|
|**Visualizadores de Conformidade de Comunicação**|Visualizador de conformidade de comunicação que pode acessar os relatórios e widgets disponíveis.|Gerenciamento de Caso de Conformidade de Comunicação <p> Visualizador de Conformidade de Comunicação|
|**Administrador de Conformidade**<sup>1</sup>|Os membros podem gerenciar configurações para gerenciamento de dispositivos, prevenção de perda de dados, relatórios e preservação.|Gerenciamento de Casos <p> Administrador de Conformidade <p> Pesquisa de Conformidade <p> Provedor de feedback de classificação de dados <p> Revisador de comentários de classificação de dados <p> Gerenciamento de dispositivo <p> Gerenciamento de disposição <p> Gerenciamento de Conformidade de DLP <p> Retenção <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Configuração da Organização <p> RecordManagement <p> Gerenciamento de retenção <p> View-Only Logs de Auditoria <p> View-Only Caso <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only Gerenciamento de Retenção|
|**Administrador de Dados de Conformidade**|Os membros podem gerenciar configurações para gerenciamento de dispositivos, proteção de dados, prevenção de perda de dados, relatórios e preservação.|Administrador de Conformidade <p> Pesquisa de Conformidade <p> Gerenciamento de dispositivo <p> Gerenciamento de Conformidade de DLP <p> Gerenciamento de disposição <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Configuração da Organização <p> RecordManagement <p> Gerenciamento de retenção <p> Administrador de rótulos de sensibilidade <p> View-Only Logs de Auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only Gerenciamento de Retenção|
|**Administradores do Gerenciador de Conformidade**|Gerenciar a criação e modificação do modelo.|Administração do Gerenciador de Conformidade <p> Avaliação do Gerenciador de Conformidade <p> Contribuição do Gerenciador de Conformidade <p> Leitor do Gerenciador de Conformidade|
|**Avaliadores do Gerenciador de Conformidade**|Crie avaliações, implemente ações de melhoria e atualize o status do teste para ações de melhoria.|Avaliação do Gerenciador de Conformidade <p> Contribuição do Gerenciador de Conformidade <p> Leitor do Gerenciador de Conformidade|
|**Colaboradores do Gerenciador de Conformidade**|Crie avaliações e realize um trabalho para implementar ações de melhoria.|Contribuição do Gerenciador de Conformidade <p> Leitor do Gerenciador de Conformidade|
|**Leitores do Gerenciador de Conformidade**|Exibir todo o conteúdo do Gerenciador de Conformidade, exceto para funções de administrador.|Leitor do Gerenciador de Conformidade|
|**Visualizador de Conteúdo do Explorador de Conteúdo**|Exibir os arquivos de conteúdo no Explorador de conteúdo.|Visualizador de Conteúdo de Classificação de Dados|
|**Visualizador de Lista do Explorador de Conteúdo**|Exibir todos os itens no Explorador de conteúdo somente no formato de lista.|Visualizador de Lista de Classificação de Dados|
|**Gerente de Descoberta Eletrônica**|Os membros podem realizar pesquisas e colocar bloqueios em caixas de correio, sites do SharePoint Online e locais do OneDrive for Business. Os membros também podem criar e gerenciar casos de Descoberta eDiscovery, adicionar e remover membros a uma ocorrência, criar e editar Pesquisas de Conteúdo associadas a uma ocorrência e acessar dados de caso em Descoberta Avançada. <p> Um Administrador de Descoberta Eletrônica é um membro do grupo de função de Gerente de Descoberta Eletrônica que recebeu permissões adicionais. Além das tarefas que um Gerenciador de Descobertas Desconhecidas pode executar, um Administrador de Descoberta De eDiscovery pode:<ul><li>Exibir todos os casos de Descoberta e Na organização.</li><li>Gerencie qualquer caso de Descoberta e Depois que eles se adicionarem como um membro do caso.</li></ul> <p> A principal diferença entre um Gerente de Descoberta Digital e um Administrador de Descoberta eDiscovery é  que um Administrador de Descoberta Digital pode acessar todos os casos listados na página Casos de Descoberta eDiscovery no Centro de Conformidade & Segurança. Um gerente de Descoberta Desdiscovery só pode acessar os casos que criaram ou casos dos quais é membro. Para obter mais informações sobre como tornar um usuário um Administrador de Descoberta Digital, consulte [Assign eDiscovery permissions in the Security & Compliance Center](../../compliance/assign-ediscovery-permissions.md).|Gerenciamento de Casos <p> Comunicação <p> Pesquisa de Conformidade <p> Custodian <p> Exportar <p> Retenção <p> Visualização <p> Analisar <p> RMS Decrypt|
|**Leitor Global**|Os membros têm acesso somente leitura a relatórios, alertas e podem ver todas as configurações e configurações.<p> A principal diferença entre Leitor Global e Leitor de Segurança é que um Leitor Global pode acessar configurações **e configurações.**|Leitor de segurança <p> Leitor de rótulos de sensibilidade <p> Exibição de Garantia de Serviço <p> View-Only Logs de Auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only Gerenciamento de Retenção|
|**Gerenciamento de riscos do Insider**|Use este grupo de função para gerenciar o gerenciamento de risco inerno da sua organização em um único grupo. Ao adicionar todas as contas de usuários para administradores, analistas e administradores designados, você pode configurar permissões de gerenciamento de riscos internas em um único grupo. Esse grupo de função contém todas as funções de permissão de gerenciamento de riscos internas. Essa é a maneira mais fácil de começar rapidamente com o gerenciamento de riscos internas e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos de usuários separados.|Gerenciamento de Casos <p> Administrador de Gerenciamento de Riscos do Insider <p> Análise de Gerenciamento de Riscos do Insider <p> Investigação de Gerenciamento de Riscos do Insider <p> View-Only Caso|
|**Administradores de Gerenciamento de Riscos do Insider**|Use esse grupo de funções para configurar inicialmente o gerenciamento de riscos insider e posteriormente para segregar administradores de riscos insider em um grupo definido. Os usuários deste grupo de função podem criar, ler, atualizar e excluir políticas de gerenciamento de risco internas, configurações globais e atribuições de grupo de função.|Gerenciamento de Casos <p> Administrador de Gerenciamento de Riscos do Insider <p> View-Only Caso|
|**Analistas do Gerenciamento de Risco Interno**|Use este grupo para atribuir permissões aos usuários que atuarão como analistas de casos de risco internos. Os usuários deste grupo de função podem acessar todos os modelos de avisos, casos e alertas de gerenciamento de riscos internos. Eles não podem acessar o Explorador de Conteúdo de risco interno.|Gerenciamento de Casos <p> Análise de Gerenciamento de Riscos do Insider <p> View-Only Caso|
|**Auditores de Gerenciamento de Riscos do Insider**|Auditores do gerenciamento de riscos insider que podem exibir os logs de auditoria das ações executadas por Analistas, Investigadores e Administradores.|Auditoria de Gerenciamento de Riscos do Insider|
|**Investigadores do Gerenciamento de Risco Interno**|Use este grupo para atribuir permissões aos usuários que atuarão como investigadores de dados do risco interno. Os usuários deste grupo de função podem acessar todos os alertas de gerenciamento de riscos interno, casos, modelos de avisos e o Explorador de Conteúdo para todos os casos.|Gerenciamento de Casos <p> Investigação de Gerenciamento de Riscos do Insider <p> View-Only Caso|
|**Colaboradores do IRM**|Esse grupo de funções está visível, mas é usado somente por serviços em segundo plano.|Contribuição permanente do Insider Risk Management <p> Contribuição temporária do Insider Risk Management|
|**Administrador do MailFlow**|Os membros podem monitorar e exibir informações e relatórios de fluxo de emails no Centro de Conformidade & Segurança. Os administradores globais podem adicionar usuários comuns a esse grupo, mas, se o usuário não for membro do grupo administrador do Exchange, o usuário não terá acesso a tarefas relacionadas ao administrador do Exchange.|Destinatários Somente para Exibição|
|**Gerenciamento de Organização**<sup>1</sup>|Os membros podem & controlar permissões para acessar recursos no Centro de Conformidade e segurança e também gerenciar configurações para gerenciamento de dispositivos, prevenção de perda de dados, relatórios e preservação. <p> Os usuários que não são administradores globais devem ser administradores do Exchange para ver e tomar medidas em dispositivos gerenciados pela Mobilidade Básica e Segurança do Microsoft 365 (anteriormente conhecido como Gerenciamento de Dispositivo Móvel ou MDM). <p> Os administradores globais são adicionados automaticamente como membros desse grupo de funções.|Logs de auditoria <p> Gerenciamento de Casos <p> Administrador de Conformidade <p> Pesquisa de Conformidade <p> Gerenciamento de dispositivo <p> Gerenciamento de Conformidade de DLP <p> Retenção <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Configuração da Organização <p> Quarentena <p> RecordManagement <p> Gerenciamento de retenção <p> Gerenciamento de Função <p> Pesquisar e limpar <p> Administrador de Segurança <p> Leitor de segurança <p> Administrador de rótulos de sensibilidade <p> Leitor de rótulos de sensibilidade <p> Exibição de Garantia de Serviço <p> Colaborador de Marca <p> Gerenciador de Marcações <p> Leitor de marca <p> View-Only Logs de Auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Caso <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only Gerenciamento de Retenção|
|**Administrador de Quarentena**|Os membros podem acessar todas as ações de Quarentena. Para obter mais informações, consulte [Manage quarantined messages and files as an admin in EOP](manage-quarantined-messages-and-files.md)|Quarentena|
|**Gerenciamento de Registros**|Os membros podem configurar todos os aspectos do gerenciamento de registros, incluindo rótulos de retenção e avaliações de disposição.|Gerenciamento de disposição <p> RecordManagement <p> Gerenciamento de retenção|
|**Revisor**|Os membros podem acessar conjuntos de revisão [em casos de Descoberta Avançada.](../../compliance/overview-ediscovery-20.md) Os membros desse grupo de funções podem ver e abrir a lista de casos na página Descoberta **> Avançado** no centro de conformidade do Microsoft 365 do que são membros. Depois que o usuário acessar um caso de Descoberta Avançada, ele poderá selecionar **Revisar conjuntos** para acessar dados de caso. Essa função não permite que o usuário visualize os resultados de uma pesquisa de coleção associada ao caso ou faça outras tarefas de pesquisa ou gerenciamento de caso. Os membros desse grupo de funções só podem acessar os dados em um conjunto de revisão.|Analisar|
|**Administrador de Segurança**|Os membros têm acesso a vários recursos de segurança do Centro de Proteção de Identidade, Gerenciamento de Identidade Privilegiada, Monitorar a Saúde do Serviço do Microsoft 365 e o Centro de Conformidade & Segurança. <p> Por padrão, esse grupo de função pode não parecer ter membros. No entanto, a função de Administrador de Segurança do Azure Active Directory é atribuída a esse grupo de funções. Portanto, esse grupo de funções herda os recursos e a associação da função administrador de segurança do Azure Active Directory. <p> Para gerenciar permissões centralmente, adicione e remova membros do grupo no centro de administração do Azure Active Directory. Para obter mais informações, consulte [Permissões de função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se você editar esse grupo de função no Centro de Conformidade & segurança (associação ou funções), essas alterações se aplicarão somente ao Centro de Conformidade e & Segurança e não a quaisquer outros serviços. <p> Esse grupo de funções inclui todas as permissões somente leitura da função de leitor de segurança, além de várias permissões administrativas adicionais para os mesmos serviços: Proteção de Informações do Azure, Centro de Proteção de Identidade, Gerenciamento de Identidade Privilegiada, Monitorar a Saúde do Serviço do Microsoft 365 e o Centro de Conformidade & Segurança.|Logs de auditoria <p> Gerenciamento de dispositivo <p> Gerenciamento de Conformidade de DLP <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Quarentena <p> Administrador de Segurança <p> Administrador de rótulos de sensibilidade <p> Colaborador de Marca <p> Gerenciador de Marcações <p> Leitor de marca <p> View-Only Logs de Auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas|
|**Operador de Segurança**|Os membros podem gerenciar alertas de segurança e também exibir relatórios e configurações de recursos de segurança.|Pesquisa de Conformidade <p> Gerenciar Alertas <p> Leitor de segurança <p> Colaborador de Marca <p> Leitor de marca <p> View-Only Logs de Auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas|
|**Leitor de Segurança**|Os membros têm acesso somente leitura a vários recursos de segurança do Centro de Proteção de Identidade, Gerenciamento de Identidade Privilegiada, Monitorar a Saúde do Serviço do Microsoft 365 e o Centro de Conformidade & Segurança. <p> Por padrão, esse grupo de função pode não parecer ter membros. No entanto, a função leitor de segurança do Azure Active Directory é atribuída a esse grupo de funções. Portanto, esse grupo de funções herda os recursos e a associação da função leitor de segurança do Azure Active Directory. <p> Para gerenciar permissões centralmente, adicione e remova membros do grupo no centro de administração do Azure Active Directory. Para obter mais informações, consulte [Permissões de função de administrador no Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles). Se você editar esse grupo de função no Centro de Conformidade & segurança (associação ou funções), essas alterações se aplicarão somente ao Centro de Conformidade e & Segurança e não a quaisquer outros serviços.|Leitor de segurança <p> Leitor de rótulos de sensibilidade <p> Leitor de marca <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas|
|**Usuário da Garantia do Serviço**|Os membros podem acessar a seção Garantia de serviço no Centro de Conformidade & Segurança. A garantia de serviço fornece relatórios e documentos que descrevem as práticas de segurança da Microsoft para dados do cliente armazenados no Microsoft 365. Ele também fornece relatórios de auditoria independentes de terceiros no Microsoft 365. Para obter mais informações, consulte [Garantia de serviço no Centro de Conformidade & Segurança.](../../compliance/service-assurance.md)|Exibição de Garantia de Serviço|
|**Revisão de Supervisão**|Os membros podem criar e gerenciar as políticas que definem quais comunicações estão sujeitas a revisão em uma organização. Para obter mais informações, consulte [Configure communication compliance policies for your organization](../../compliance/communication-compliance-configure.md).|Administrador de Revisão de Supervisão|
|

> [!NOTE]
> <sup>1</sup> Esse grupo de funções não atribui aos membros as permissões necessárias para pesquisar o log de auditoria ou para usar relatórios que possam incluir dados do Exchange, como os relatórios DLP ou Defender para Office 365. Para pesquisar o log de auditoria ou para exibir todos os relatórios, um usuário precisa ter permissões atribuídas no Exchange Online. Isso ocorre porque o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet Exchange Online. Os administradores globais podem pesquisar o log de auditoria e exibir todos os relatórios porque eles são adicionados automaticamente como membros do grupo de função Gerenciamento da Organização no Exchange Online. Para obter mais informações, [consulte Pesquisar o log de auditoria no Centro de Conformidade & Segurança.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="roles-in-the-security--compliance-center"></a>Funções no Centro de Conformidade & segurança

A tabela a seguir lista as funções disponíveis e os grupos de função aos quais são atribuídas por padrão.

Observe que as seguintes funções não são atribuídas ao grupo de função Gerenciamento da Organização por padrão:

- Administrador do Simulador de Ataques
- Autor da carga do simulador de ataque
- Comunicação
- Administrador de Conformidade de Comunicação
- Análise de Conformidade de Comunicação
- Gerenciamento de Caso de Conformidade de Comunicação
- Investigação de Conformidade de Comunicação
- Visualizador de Conformidade de Comunicação
- Administração do Gerenciador de Conformidade
- Avaliação do Gerenciador de Conformidade
- Contribuição do Gerenciador de Conformidade
- Leitor do Gerenciador de Conformidade
- Custodian
- Visualizador de Conteúdo de Classificação de Dados
- Provedor de feedback de classificação de dados
- Revisador de comentários de classificação de dados
- Visualizador de Lista de Classificação de Dados
- Gerenciamento de disposição
- Exportar
- Administrador de Gerenciamento de Riscos do Insider
- Análise de Gerenciamento de Riscos do Insider
- Auditoria de Gerenciamento de Riscos do Insider
- Investigação de Gerenciamento de Riscos do Insider
- Contribuição permanente do Insider Risk Management
- Contribuição temporária do Insider Risk Management
- Visualização
- Analisar
- RMS Decrypt
- Administrador de Revisão de Supervisão

<br><br>

****

|Role|Descrição|Atribuições de grupo de função padrão|
|---|---|---|
|**Administrador do Simulador de Ataques**|Usado para criar e gerenciar todos os aspectos de campanhas de simulação de ataque.||
|**Autor da carga do simulador de ataque**|Usado para criar e gerenciar cargas de ataque que podem ser implantadas pelo administrador do simulador de ataque.||
|**Logs de auditoria**|A ligue e configure a auditoria para a organização, veja os relatórios de auditoria da organização e exporte esses relatórios para um arquivo.|Gerenciamento de Organização <p> Administrador de Segurança|
|**Gerenciamento de Casos**|Crie, edite, exclua e controle o acesso a casos de Descoberta e.|Conformidade em comunicações <p> Investigadores de Conformidade de Comunicação <p> Administrador de Conformidade <p>Gerente de Descoberta Eletrônica <p> Gerenciamento de riscos internos <p> Administradores de Gerenciamento de Riscos do Insider <p> Analistas de Gerenciamento de Riscos do Insider <p> Insider Risk Management Investigators <p> Gerenciamento de Organização|
|**Comunicação**|Gerencie todas as comunicações com os custodiantes identificados em um caso de Descoberta Eletrônica Avançada.  Crie notificações de espera, lembretes de espera e escalonamentos para o gerenciamento. Acompanhe o reconhecimento de custodiante de notificações de responsabilidade e gerencie o acesso ao portal custodiante usado por cada custodiante em um caso para rastrear comunicações para os casos em que foram identificados como custodiante.|Gerente de Descoberta Eletrônica|
|**Administrador de Conformidade de Comunicação**|Usado para gerenciar políticas no recurso Conformidade de Comunicação.|Conformidade em comunicações <p> Administradores de Conformidade de Comunicação|
|**Análise de Conformidade de Comunicação**|Usado para executar investigação, correção das violações de mensagens no recurso Conformidade de Comunicação. Só é possível exibir os dados de meta de mensagem.|Conformidade em comunicações <p> Analistas de Conformidade de Comunicação <p> Investigadores de Conformidade de Comunicação|
|**Gerenciamento de Caso de Conformidade de Comunicação**|Usado para acessar casos de Conformidade de Comunicação.|Conformidade em comunicações <p> Administradores de Conformidade de Comunicação <p> Analistas de Conformidade de Comunicação <p> Investigadores de Conformidade de Comunicação <p> Visualizadores de Conformidade de Comunicação|
|**Investigação de Conformidade de Comunicação**|Usado para executar a investigação, a correção e a revisão de violações de mensagens no recurso Conformidade de Comunicação. Pode exibir dados de meta de mensagem e mensagem.|Conformidade em comunicações <p> Investigadores de Conformidade de Comunicação|
|**Visualizador de Conformidade de Comunicação**|Usado para acessar relatórios e widgets no recurso Conformidade de Comunicação.|Conformidade em comunicações <p> Visualizadores de Conformidade de Comunicação|
|**Administrador de Conformidade**|Exibir e editar configurações e relatórios para recursos de conformidade.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização|
|**Administração do Gerenciador de Conformidade**|Gerenciar a criação e modificação do modelo.|Administradores do Gerenciador de Conformidade|
|**Avaliação do Gerenciador de Conformidade**|Crie avaliações, implemente ações de melhoria e atualize o status do teste para ações de melhoria.|Administradores do Gerenciador de Conformidade <p> Avaliadores do Gerenciador de Conformidade|
|**Contribuição do Gerenciador de Conformidade**|Crie avaliações e realize um trabalho para implementar ações de melhoria.|Administradores do Gerenciador de Conformidade <p> Avaliadores do Gerenciador de Conformidade <p> Colaboradores do Gerenciador de Conformidade|
|**Leitor do Gerenciador de Conformidade**|Exibir todo o conteúdo do Gerenciador de Conformidade, exceto para funções de administrador.|Administradores do Gerenciador de Conformidade <p> Avaliadores do Gerenciador de Conformidade <p> Colaboradores do Gerenciador de Conformidade <p> Leitores do Gerenciador de Conformidade|
|**Pesquisa de Conformidade**|Execute pesquisas em caixas de correio e obter uma estimativa dos resultados.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p>Gerente de Descoberta Eletrônica <p> Gerenciamento de Organização <p> Operador de segurança|
|**Custodian**|Identifique e gerencie os custodiantes para casos de Descoberta Avançada e use as informações do Azure Active Directory e outras fontes para encontrar fontes de dados associadas aos custodiantes. Associe outras fontes de dados, como caixas de correio, sites do SharePoint e Teams a custodiantes em um caso.  Coloque uma posição legal nas fontes de dados associadas aos custodiantes para preservar o conteúdo no contexto de um caso.|Gerente de Descoberta Eletrônica|
|**Visualizador de Conteúdo de Classificação de Dados**|Exibir a renderização in-local de arquivos no Explorador de conteúdo.|Visualizador de Conteúdo do Explorador de Conteúdo|
|**Provedor de feedback de classificação de dados**|Permite fornecer comentários aos classificadores no explorador de conteúdo.|Conformidade em comunicações <p> Investigadores de Conformidade de Comunicação <p> Administrador de Conformidade|
|**Revisador de comentários de classificação de dados**|Permite analisar comentários de classificadores no explorador de comentários.|Administrador de Conformidade|
|**Visualizador de Lista de Classificação de Dados**|Exibir a lista de arquivos no explorador de conteúdo.|Visualizador de Lista do Explorador de Conteúdo|
|**Gerenciamento de Dispositivos**|Exibir e editar configurações e relatórios para recursos de gerenciamento de dispositivos.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Gerenciamento de disposição**|Permissões de controle para acessar a Disposição Manual no Centro de Conformidade & Segurança.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Registros|
|**Gerenciamento de Conformidade de DLP**|Exibir e editar configurações e relatórios para políticas de prevenção contra perda de dados (DLP).|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Exportar**|Exportar conteúdo de caixa de correio e site retornado das pesquisas.|Gerente de Descoberta Eletrônica|
|**Reter**|Coloque o conteúdo em caixas de correio, sites e pastas públicas em espera. Quando em espera, uma cópia do conteúdo é armazenada em um local seguro. Os proprietários de conteúdo ainda poderão modificar ou excluir o conteúdo original.|Administrador de Conformidade <p>Gerente de Descoberta Eletrônica <p> Gerenciamento de Organização|
|**Gerenciamento de Conformidade do IB**|Exibir, criar, remover, modificar e testar políticas de Barreira de Informações.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Administrador de Gerenciamento de Riscos do Insider**|Criar, editar, excluir e controlar o acesso ao recurso Gerenciamento de Riscos do Insider.|Gerenciamento de riscos internos <p> Administradores de Gerenciamento de Riscos do Insider|
|**Análise de Gerenciamento de Riscos do Insider**|Acesse todos os modelos de alertas, casos e avisos de gerenciamento de riscos insider.|Gerenciamento de riscos internos <p> Analistas de Gerenciamento de Riscos do Insider|
|**Auditoria de Gerenciamento de Riscos do Insider**|Permitir a exibição de trilhas de auditoria de risco do Insider.|Auditores de Gerenciamento de Riscos do Insider|
|**Investigação de Gerenciamento de Riscos do Insider**|Acesse todos os alertas de gerenciamento de risco interno, casos, modelos de avisos e o Explorador de Conteúdo para todos os casos.|Gerenciamento de riscos internos <p> Insider Risk Management Investigators|
|**Contribuição permanente do Insider Risk Management**|Esse grupo de funções está visível, mas é usado somente por serviços em segundo plano.|Colaboradores do IRM|
|**Contribuição temporária do Insider Risk Management**|Esse grupo de funções está visível, mas é usado somente por serviços em segundo plano.|Colaboradores do IRM|
|**Gerenciar Alertas**|Exibir e editar configurações e relatórios para alertas.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança|
|**Configuração da Organização**|Execute, exibir e exportar relatórios de auditoria e gerencie políticas de conformidade para DLP, dispositivos e preservação.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização|
|**Visualização**|Exibir uma lista de itens retornados de pesquisas de conteúdo e abrir cada item da lista para exibir seu conteúdo.|Gerente de Descoberta Eletrônica|
|**Quarentena**|Permite a exibição e a liberação de emails em quarentena.|Administrador de Quarentena <p> Administrador de Segurança <p> Gerenciamento de Organização|
|**RecordManagement**|Exibir e editar a configuração do recurso de gerenciamento de registros.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Gerenciamento de Registros|
|**Gerenciamento de retenção**|Gerenciar políticas de retenção, rótulos de retenção e políticas de rótulo de retenção.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Gerenciamento de Registros|
|**Análise**|Essa função permite que os usuários acessem conjuntos de revisão em casos avançados de Descoberta eDiscovery. Os usuários que são atribuídos a essa função podem ver e abrir a lista de casos na página Descoberta **> Avançado** no centro de conformidade do Microsoft 365 dos quais são membros. Depois que o usuário acessar um caso de Descoberta Avançada, ele poderá selecionar **Revisar conjuntos** para acessar dados de caso. Essa função não permite que o usuário visualize os resultados de uma pesquisa de coleção associada ao caso ou faça outras tarefas de pesquisa ou gerenciamento de caso. Os usuários com essa função só podem acessar os dados em um conjunto de revisão.|Gerente de Descoberta Eletrônica <p> Revisor|
|**RMS Decrypt**|Descriptografar conteúdo protegido por RMS ao exportar resultados da pesquisa.|Gerente de Descoberta Eletrônica|
|**Gerenciamento de Função**|Gerencie a associação ao grupo de funções e crie ou exclua grupos de função personalizados.|Gerenciamento de Organização|
|**Pesquisar e limpar**|Permite que as pessoas removam dados em massa que corresponde aos critérios de uma pesquisa de conteúdo.|Gerenciamento de Organização|
|**Administrador de Segurança**|Exibir e editar a configuração e os relatórios para recursos de Segurança.|Gerenciamento de Organização <p> Administrador de Segurança|
|**Leitor de Segurança**|Exibir a configuração e os relatórios dos recursos de Segurança.|Leitor Global <p> Gerenciamento de Organização <p> Operador de segurança <p> Leitor de segurança|
|**Administrador de rótulos de sensibilidade**|Exibir, criar, modificar e remover rótulos de sensibilidade.|Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Leitor de rótulos de sensibilidade**|Exibir a configuração e o uso de rótulos de sensibilidade.|Leitor Global <p> Gerenciamento de Organização <p> Leitor de segurança|
|**Exibição de Garantia de Serviço**|Baixe os documentos disponíveis na seção Garantia de Serviço. O conteúdo inclui auditoria independente, documentação de conformidade e orientações relacionadas à confiança para usar recursos do Microsoft 365 para gerenciar riscos de conformidade e segurança regulamentar.|Leitor Global <p> Gerenciamento de Organização <p> Usuário da Garantia do Serviço|
|**Administrador de Revisão de Supervisão**|Gerencie políticas de revisão de supervisão, incluindo quais comunicações revisar e quem deve fazer a revisão.|Revisão de Supervisão|
|**Colaborador de Marca**|Exibir e atualizar a associação de marcas de usuário existentes.|Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança|
|**Gerenciador de Marcações**|Exibir, atualizar, criar e excluir marcas de usuário.|Gerenciamento de Organização <p> Administrador de Segurança|
|**Leitor de marca**|Acesso somente leitura a marcas de usuário existentes.|Leitor de segurança|
|**Logs de auditoria somente exibição**|Exibir e exportar relatórios de auditoria. Como esses relatórios podem conter informações confidenciais, você só deve atribuir essa função a pessoas com uma necessidade explícita de exibir essas informações.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor Global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança|
|**Caso somente exibição**||Conformidade em comunicações <p> Investigadores de Conformidade de Comunicação <p> Administrador de Conformidade <p> Gerenciamento de riscos internos <p> Administradores de Gerenciamento de Riscos do Insider <p> Analistas de Gerenciamento de Riscos do Insider <p> Insider RiskManagement Investigators <p> Gerenciamento de Organização|
|**Gerenciamento de dispositivo somente exibição**|Exibir a configuração e os relatórios do recurso Gerenciamento de Dispositivos.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor Global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Gerenciamento de conformidade de DLP somente exibição**|Exibir as configurações e relatórios para políticas de prevenção contra perda de dados (DLP).|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor Global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Gerenciamento de conformidade de IB somente exibição**|Exibir a configuração e os relatórios do recurso Barreiras de Informações.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor Global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Somente exibição Gerenciar alertas**|Exibir a configuração e os relatórios do recurso Gerenciar Alertas.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor Global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Destinatários Somente para Exibição**|Exibir informações sobre usuários e grupos.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor Global <p> Administrador do MailFlow <p> Gerenciamento de Organização|
|**Gerenciamento de registro somente exibição**|Exibir a configuração do recurso de gerenciamento de registros.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> <p> Leitor Global <p> Gerenciamento de Organização|
|**Gerenciamento de retenção somente exibição**|Exibir a configuração de políticas de retenção, rótulos de retenção e políticas de rótulo de retenção.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Administrador Global <p> Gerenciamento da Organização|
|