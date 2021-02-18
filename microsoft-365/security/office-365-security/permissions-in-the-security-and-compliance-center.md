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
ms.openlocfilehash: 170183cd31a770812f8bf59153123ffc66c8640c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288832"
---
# <a name="permissions-in-the-security--compliance-center"></a>Permissões no Centro de Conformidade e Segurança

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
- [Proteção do Exchange Online](exchange-online-protection-overview.md)
- [Plano 1 e plano 2 do Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

O Centro de Conformidade & segurança permite conceder permissões a pessoas que realizam tarefas de conformidade, como gerenciamento de dispositivos, prevenção contra perda de dados, Descoberta eDiscovery, retenção e assim por diante. Essas pessoas podem realizar apenas as tarefas para as quais você concedeu acesso especificamente. Para acessar o Centro de Conformidade & segurança, os usuários precisam ser um administrador global ou um membro de um ou mais grupos de função do Centro de Conformidade & segurança.

As permissões no Centro de Conformidade & segurança são baseadas no modelo de permissões de controle de acesso baseado em função (RBAC). O RBAC é o mesmo modelo de permissões usado pelo Exchange, portanto &, se você estiver familiarizado com o Exchange, a concessão de permissões no Centro de Conformidade e Segurança será muito semelhante. No entanto, é importante lembrar que os grupos de função do Exchange e os grupos de função & de segurança do Centro de Conformidade não compartilham associações ou permissões. Eles não são os mesmos, visto que ambos possuem um grupo de funções de Gerenciamento de Organização. As permissões que concedem e os membros dos grupos de função são diferentes. Há uma lista de grupos de função do Centro de Conformidade & segurança abaixo.

![Página Permissões no Centro de Conformidade e Segurança & segurança](../../media/992c20ca-e82e-497c-9c8d-6fab212deb80.png)

## <a name="relationship-of-members-roles-and-role-groups"></a>Relação de membros, funções e grupos de função

Uma **função** concede permissões para realizar um conjunto de tarefas; por exemplo, a função de Gerenciamento de Casos permite que as pessoas trabalhem em casos de Descoberta Eletrônica.

Um **grupo de** funções é um conjunto de funções que permite que as pessoas fazem seus trabalhos no Centro de & Conformidade e Segurança. Por exemplo, o grupo de funções Administrador de Conformidade inclui (entre outras funções) as funções de Gerenciamento de Caso, Pesquisa de Conteúdo e Configuração da Organização (além de outras) porque alguém que seja um administrador de conformidade precisará das permissões para essas tarefas para realizar seu trabalho.

O Centro de & de Conformidade inclui grupos de função padrão para as tarefas e funções mais comuns que você precisará atribuir às pessoas. Recomendamos simplesmente adicionar usuários individuais **como membros** aos grupos de função padrão.

![Diagrama que mostra a relação de grupos de funções para membros e funções](../../media/2a16d200-968c-4755-98ec-f1862d58cb8b.png)

## <a name="permissions-needed-to-use-features-in-the-security--compliance-center"></a>Permissões necessárias para usar recursos no Centro de Conformidade e & Segurança

A tabela a & seguir lista os grupos de função padrão que estão disponíveis no Centro de Conformidade e Segurança e as funções atribuídas aos grupos de função por padrão. Para conceder permissões a um usuário para executar uma tarefa de conformidade, adicione-o ao grupo de funções apropriado do Centro de & Conformidade e Segurança.

O gerenciamento de permissões no Centro de Conformidade e Segurança & oferece aos usuários acesso apenas aos recursos de conformidade que estão disponíveis no Centro de Conformidade e Segurança & em si. Se você quiser conceder permissões a outros recursos de conformidade que não estão no Centro de Conformidade e Segurança, como regras de fluxo de emails do Exchange (também conhecida & s como regras de transporte), você precisará usar o Centro de administração do Exchange.

Para ver como conceder acesso ao Centro de Conformidade e Segurança &, confira Conceder aos usuários acesso ao Centro de administração de Conformidade [do Microsoft 365.](grant-access-to-the-security-and-compliance-center.md)

> [!NOTE]
> Para exibir a **guia Permissões** no Centro de Conformidade & segurança, você precisa ser um administrador. Especificamente, você precisa ter  a função Gerenciamento de Função atribuída,  e essa função é atribuída apenas ao grupo de função Gerenciamento da Organização no Centro de Conformidade e Segurança &, por padrão. Além disso, a **função gerenciamento de** função permite que os usuários exibir, criar e modificar grupos de função.

<br><br>

****

|Grupo de função|Descrição|Funções padrão atribuídas|
|---|---|---|
|**Conformidade de Comunicação**|Fornece permissão a todas as funções de conformidade de comunicação: administrador, analista, investigador e visualizador.|Gerenciamento de Casos <p> Administrador de Conformidade de Comunicação <p> Análise de conformidade de comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação <p> Investigação de Conformidade de Comunicação <p> Visualizador de Conformidade de Comunicação <p> Provedor de Comentários sobre Classificação de Dados <p> View-Only caso|
|**Administradores de Conformidade de Comunicação**|Administradores de conformidade de comunicação que podem criar/editar políticas e definir configurações globais.|Administrador de Conformidade de Comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação|
|**Analistas de Conformidade de Comunicação**|Analistas de conformidade de comunicação que podem investigar as políticas de responsabilidade, exibir metadados de mensagens e realizar ações de correção.|Análise de conformidade de comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação|
|**Investigadores de conformidade de comunicação**|Analistas de conformidade de comunicação que podem investigar as políticas de conformidade, exibir o conteúdo da mensagem e tomar ações de correção.|Gerenciamento de Casos <p> Análise de conformidade de comunicação <p> Gerenciamento de Caso de Conformidade de Comunicação <p> Investigação de Conformidade de Comunicação <p> Provedor de Comentários sobre Classificação de Dados <p> View-Only caso|
|**Visualizadores de Conformidade de Comunicação**|Visualizador de conformidade de comunicação que pode acessar os relatórios e widgets disponíveis.|Gerenciamento de Caso de Conformidade de Comunicação <p> Visualizador de Conformidade de Comunicação|
|**Administrador de Conformidade**<sup>1</sup>|Os membros podem gerenciar configurações de gerenciamento de dispositivos, prevenção contra perda de dados, relatórios e preservação.|Gerenciamento de Casos <p> Administrador de Conformidade <p> Pesquisa de Conformidade <p> Provedor de Comentários sobre Classificação de Dados <p> Analisador de Comentários de Classificação de Dados <p> Gerenciamento de dispositivo <p> Gerenciamento de disposição <p> Gerenciamento de Conformidade de DLP <p> Retenção <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Configuração da Organização <p> RecordManagement <p> Gerenciamento de retenção <p> View-Only logs de auditoria <p> View-Only caso <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only gerenciamento de retenção|
|**Administrador de Dados de Conformidade**|Os membros podem gerenciar configurações de gerenciamento de dispositivos, proteção de dados, prevenção contra perda de dados, relatórios e preservação.|Administrador de Conformidade <p> Pesquisa de Conformidade <p> Gerenciamento de dispositivo <p> Gerenciamento de Conformidade de DLP <p> Gerenciamento de disposição <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Configuração da Organização <p> RecordManagement <p> Gerenciamento de retenção <p> Administrador de Rótulos de Sensibilidade <p> View-Only logs de auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only gerenciamento de retenção|
|**Administradores do Gerenciador de Conformidade**|Gerencie a criação e modificação do modelo.|Administração do Gerenciador de Conformidade <p> Avaliação do Gerenciador de Conformidade <p> Contribuição do Gerenciador de Conformidade <p> Leitor do Gerenciador de Conformidade|
|**Avaliadores do Gerenciador de Conformidade**|Crie avaliações, implemente ações de melhoria e atualize o status do teste para ações de melhoria.|Avaliação do Gerenciador de Conformidade <p> Contribuição do Gerenciador de Conformidade <p> Leitor do Gerenciador de Conformidade|
|**Colaboradores do Gerenciador de Conformidade**|Crie avaliações e realize um trabalho para implementar ações de melhoria.|Contribuição do Gerenciador de Conformidade <p> Leitor do Gerenciador de Conformidade|
|**Leitores do Gerenciador de Conformidade**|Exibir todo o conteúdo do Gerenciador de Conformidade, exceto funções de administrador.|Leitor do Gerenciador de Conformidade|
|**Visualizador de Conteúdo do Explorador de Conteúdo**|Exibir os arquivos de conteúdo no Explorador de conteúdo.|Visualizador de Conteúdo de Classificação de Dados|
|**Visualizador de Lista do Explorador de Conteúdo**|Exibir todos os itens no Explorador de conteúdo somente no formato de lista.|Visualizador da Lista de Classificação de Dados|
|**Gerente de Descoberta Eletrônica**|Os membros podem realizar pesquisas e colocar bloqueios em caixas de correio, sites do SharePoint Online e locais do OneDrive for Business. Os membros também podem criar e gerenciar ocorrências de Descobertas e, em seguida, adicionar e remover membros de uma ocorrência, criar e editar Pesquisas de Conteúdo associadas a uma ocorrência e acessar dados de ocorrência na Descoberta Avançada. <p> Um Administrador de Descoberta Eletrônica é um membro do grupo de função de Gerente de Descoberta Eletrônica que recebeu permissões adicionais. Além das tarefas que um Gerente de DescobertaScoberta pode executar, um Administrador de Descobertas e Descobertas Pode:<ul><li>Exibir todas as ocorrências de DescobertaScoberta na organização.</li><li>Gerencie qualquer caso de Descoberta e Depois de adicionar a si mesmo como um membro da ocorrência.</li></ul> <p> A principal diferença entre um Gerente de Descoberta EDiscovery e um Administrador de Descobertas é que um Administrador de Descoberta eDiscovery pode acessar todos os casos listados na página de ocorrências de Descoberta eDiscover **& y** no Centro de Conformidade e Segurança. Um gerente de Descoberta eDiscovery só pode acessar os casos que criou ou dos quais é membro. Para obter mais informações sobre como tornar um usuário um Administrador de Descoberta [eDiscovery,](../../compliance/assign-ediscovery-permissions.md)consulte Atribuir permissões de Descoberta & Segurança no Centro de Conformidade.|Gerenciamento de Casos <p> Comunicação <p> Pesquisa de Conformidade <p> Custodian <p> Exportar <p> Retenção <p> Visualização <p> Analisar <p> Descriptografar RMS|
|**Leitor Global**|Os membros têm acesso somente leitura a relatórios, alertas e podem ver todas as configurações e configurações.<p> A principal diferença entre Leitor Global e Leitor de Segurança é que um Leitor Global pode acessar **configurações e configurações.**|Leitor de segurança <p> Leitor de rótulos de sensibilidade <p> Exibição de Garantia de Serviço <p> View-Only logs de auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only gerenciamento de retenção|
|**Gerenciamento de riscos do Insider**|Use esse grupo de função para gerenciar o gerenciamento de riscos insider para sua organização em um único grupo. Ao adicionar todas as contas de usuário para administradores designados, analistas e investigadores, você pode configurar permissões de gerenciamento de riscos interno em um único grupo. Esse grupo de funções contém todas as funções de permissão de gerenciamento de risco interno. Essa é a maneira mais fácil de começar rapidamente com o gerenciamento de riscos insider e é uma boa opção para organizações que não precisam de permissões separadas definidas para grupos separados de usuários.|Gerenciamento de Casos <p> Administrador de Gerenciamento de Riscos Do Insider <p> Análise de Gerenciamento de Riscos Insider <p> Investigação de Gerenciamento de Riscos Insider <p> View-Only caso|
|**Administradores de Gerenciamento de Riscos Insider**|Use esse grupo de função para configurar inicialmente o gerenciamento de riscos insider e posteriormente segregar os administradores de risco interno em um grupo definido. Os usuários desse grupo de função podem criar, ler, atualizar e excluir políticas de gerenciamento de riscos insider, configurações globais e atribuições de grupo de função.|Gerenciamento de Casos <p> Administrador de Gerenciamento de Riscos Do Insider <p> View-Only caso|
|**Analistas do Gerenciamento de Risco Interno**|Use esse grupo para atribuir permissões aos usuários que atuarão como analistas de caso de risco interno. Os usuários desse grupo de função podem acessar todos os alertas, ocorrências e modelos de avisos de gerenciamento de riscos insider. Eles não podem acessar o Explorador de Conteúdo de risco interno.|Gerenciamento de Casos <p> Análise de Gerenciamento de Riscos Insider <p> View-Only caso|
|**Auditores do Gerenciamento de Riscos Insider**|Auditores do gerenciamento de riscos insider que podem exibir os logs de auditoria de ações executadas por Analistas, Investigadores e Administradores.|Auditoria de Gerenciamento de Riscos Insider|
|**Investigadores do Gerenciamento de Risco Interno**|Use esse grupo para atribuir permissões aos usuários que atuarão como investigadores de dados de risco interno. Os usuários desse grupo de função podem acessar todos os alertas, casos, modelos de avisos e o Explorador de Conteúdo de gerenciamento de riscos interno para todos os casos.|Gerenciamento de Casos <p> Investigação de Gerenciamento de Riscos Insider <p> View-Only caso|
|**Colaboradores do IRM**|Esse grupo de funções está visível, mas é usado somente por serviços em segundo plano.|Contribuição permanente do Gerenciamento de Riscos Insider <p> Contribuição temporária do Gerenciamento de Riscos Insider|
|**Administrador do Fluxo de Mensagens**|Os membros podem monitorar e exibir informações e relatórios de fluxo de emails no Centro de Conformidade e & Segurança. Os administradores globais podem adicionar usuários comuns a esse grupo, mas, se o usuário não for membro do grupo De administração do Exchange, o usuário não terá acesso a tarefas relacionadas ao administrador do Exchange.|Destinatários Somente para Exibição|
|**Gerenciamento da Organização**<sup>1</sup>|Os membros & podem controlar permissões para acessar recursos no Centro de Conformidade e Segurança e também gerenciar configurações de gerenciamento de dispositivos, prevenção contra perda de dados, relatórios e preservação. <p> Os usuários que não são administradores globais devem ser administradores do Exchange para ver e tomar medidas em dispositivos gerenciados pela Mobilidade Básica e Segurança do Microsoft 365 (anteriormente conhecido como Gerenciamento de Dispositivo Móvel ou MDM). <p> Os administradores globais são adicionados automaticamente como membros desse grupo de função.|Logs de auditoria <p> Gerenciamento de Casos <p> Administrador de Conformidade <p> Pesquisa de Conformidade <p> Gerenciamento de dispositivo <p> Gerenciamento de Conformidade de DLP <p> Retenção <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Configuração da Organização <p> Quarentena <p> RecordManagement <p> Gerenciamento de retenção <p> Gerenciamento de Função <p> Pesquisar e limpar <p> Administrador de Segurança <p> Leitor de segurança <p> Administrador de Rótulos de Sensibilidade <p> Leitor de rótulos de sensibilidade <p> Exibição de Garantia de Serviço <p> Colaborador de Marca <p> Gerenciador de Marca <p> Leitor de Marca <p> View-Only logs de auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only caso <p> View-Only Gerenciar Alertas <p> Destinatários Somente para Exibição <p> View-Only gerenciamento de registros <p> View-Only gerenciamento de retenção|
|**Administrador de Quarentena**|Os membros podem acessar todas as ações de Quarentena. Para obter mais informações, consulte Gerenciar mensagens e arquivos em [quarentena como administrador no EOP](manage-quarantined-messages-and-files.md)|Quarentena|
|**Gerenciamento de Registros**|Os membros podem configurar todos os aspectos do gerenciamento de registros, incluindo rótulos de retenção e revisões de disposição.|Gerenciamento de disposição <p> RecordManagement <p> Gerenciamento de retenção|
|**Revisor**|Os membros podem acessar conjuntos de revisão [em casos de Descobertas Avançadas.](../../compliance/overview-ediscovery-20.md) Os membros desse grupo de função podem ver e abrir a lista de ocorrências na página de descoberta > **Avançado** no centro de conformidade do Microsoft 365 dos quais eles são membros. Depois que o usuário acessar um caso de Descoberta Avançada, ele poderá selecionar Conjuntos **de** revisão para acessar dados de ocorrência. Essa função não permite que o usuário visualize os resultados de uma pesquisa de coleção associada ao caso ou faça outras tarefas de gerenciamento de caso ou pesquisa. Os membros desse grupo de função só podem acessar os dados em um conjunto de revisão.|Analisar|
|**Administrador de Segurança**|Os membros têm acesso a vários recursos de segurança do Centro de Proteção de Identidade, privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center. <p> Por padrão, esse grupo de função pode não parecer ter membros. No entanto, a função administrador de segurança do Azure Active Directory é atribuída a esse grupo de função. Portanto, esse grupo de funções herda os recursos e a associação da função Administrador de Segurança do Azure Active Directory. <p> Para gerenciar permissões centralmente, adicione e remova membros do grupo no centro de administração do Azure Active Directory. Para saber mais, confira [Permissões de função de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Se você editar esse grupo de funções no Centro de Conformidade e Segurança & (associação ou funções), essas alterações se aplicarão somente ao Centro de Conformidade e & Segurança e não a nenhum outro serviço. <p> Esse grupo de funções inclui todas as permissões somente leitura da função leitor de segurança, além de várias permissões administrativas adicionais para os mesmos serviços: Proteção de Informações do Azure, Centro de Proteção de Identidade, Privileged Identity Management, Monitorar a Saúde do Serviço do Microsoft 365 e Centro de Conformidade de & Segurança.|Logs de auditoria <p> Gerenciamento de dispositivo <p> Gerenciamento de Conformidade de DLP <p> Gerenciamento de Conformidade do IB <p> Gerenciar Alertas <p> Quarentena <p> Administrador de Segurança <p> Administrador de Rótulos de Sensibilidade <p> Colaborador de Marca <p> Gerenciador de Marca <p> Leitor de Marca <p> View-Only logs de auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas|
|**Operador de segurança**|Os membros podem gerenciar alertas de segurança e também exibir relatórios e configurações de recursos de segurança.|Pesquisa de Conformidade <p> Gerenciar Alertas <p> Leitor de segurança <p> Colaborador de Marca <p> Leitor de Marca <p> View-Only logs de auditoria <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas|
|**Leitor de Segurança**|Os membros têm acesso somente leitura a vários recursos de segurança do Centro de Proteção de Identidade, Privileged Identity Management, Monitor Microsoft 365 Service Health e Security & Compliance Center. <p> Por padrão, esse grupo de função pode não parecer ter membros. No entanto, a função Leitor de Segurança do Azure Active Directory é atribuída a esse grupo de funções. Portanto, esse grupo de funções herda os recursos e a associação da função Leitor de Segurança do Azure Active Directory. <p> Para gerenciar permissões centralmente, adicione e remova membros do grupo no centro de administração do Azure Active Directory. Para saber mais, confira [Permissões de função de administrador no Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Se você editar esse grupo de funções no Centro de Conformidade e Segurança & (associação ou funções), essas alterações se aplicarão somente ao Centro de Conformidade e & Segurança e não a nenhum outro serviço.|Leitor de segurança <p> Leitor de rótulos de sensibilidade <p> Leitor de Marca <p> View-Only gerenciamento de dispositivos <p> View-Only gerenciamento de conformidade de DLP <p> View-Only gerenciamento de conformidade do IB <p> View-Only Gerenciar Alertas|
|**Usuário da Garantia do Serviço**|Os membros podem acessar a seção Garantia de serviço no Centro de Conformidade & segurança. A garantia de serviço fornece relatórios e documentos que descrevem as práticas de segurança da Microsoft para dados do cliente armazenados no Microsoft 365. Ele também fornece relatórios de auditoria independentes de terceiros no Microsoft 365. Para obter mais informações, consulte [Garantia de serviço no Centro de Conformidade & segurança.](../../compliance/service-assurance.md)|Exibição de Garantia de Serviço|
|**Revisão de Supervisão**|Os membros podem criar e gerenciar as políticas que definem quais comunicações estão sujeitas a revisão em uma organização. Para obter mais informações, consulte [Configurar políticas de conformidade de comunicação para sua organização.](../../compliance/communication-compliance-configure.md)|Administrador de Revisão de Supervisão|
|

> [!NOTE]
> <sup>1</sup> Esse grupo de função não atribui aos membros as permissões necessárias para pesquisar o log de auditoria ou usar relatórios que possam incluir dados do Exchange, como os relatórios DLP ou Defender para Office 365. Para pesquisar o log de auditoria ou exibir todos os relatórios, um usuário precisa ter permissões atribuídas no Exchange Online. Isso ocorre porque o cmdlet subjacente usado para pesquisar o log de auditoria é um cmdlet Exchange Online. Os administradores globais podem pesquisar o log de auditoria e exibir todos os relatórios porque eles são adicionados automaticamente como membros do grupo de função Gerenciamento da Organização no Exchange Online. Para obter mais informações, [consulte Pesquisar o log de auditoria no Centro de Conformidade & segurança.](../../compliance/search-the-audit-log-in-security-and-compliance.md)

## <a name="roles-in-the-security--compliance-center"></a>Funções no Centro de Conformidade & segurança

A tabela a seguir lista as funções disponíveis e os grupos de função aos quais elas estão atribuídas por padrão.

Observe que as seguintes funções não são atribuídas ao grupo de funções Gerenciamento da Organização por padrão:

- Administrador do Simulador de Ataque
- Autor da carga do simulador de ataque
- Comunicação
- Administrador de Conformidade de Comunicação
- Análise de conformidade de comunicação
- Gerenciamento de Caso de Conformidade de Comunicação
- Investigação de Conformidade de Comunicação
- Visualizador de Conformidade de Comunicação
- Administração do Gerenciador de Conformidade
- Avaliação do Gerenciador de Conformidade
- Contribuição do Gerenciador de Conformidade
- Leitor do Gerenciador de Conformidade
- Custodian
- Visualizador de Conteúdo de Classificação de Dados
- Provedor de Comentários sobre Classificação de Dados
- Analisador de Comentários de Classificação de Dados
- Visualizador da Lista de Classificação de Dados
- Gerenciamento de disposição
- Exportar
- Administrador de Gerenciamento de Riscos Do Insider
- Análise de Gerenciamento de Riscos Insider
- Auditoria de Gerenciamento de Riscos Insider
- Investigação de Gerenciamento de Riscos Insider
- Contribuição permanente do Gerenciamento de Riscos Insider
- Contribuição temporária do Gerenciamento de Riscos Insider
- Visualização
- Analisar
- Descriptografar RMS
- Administrador de Revisão de Supervisão

<br><br>

****

|Função|Descrição|Atribuições de grupo de função padrão|
|---|---|---|
|**Administrador do Simulador de Ataque**|Usado para criar e gerenciar todos os aspectos de campanhas de simulação de ataque.||
|**Autor da carga do simulador de ataque**|Usado para criar e gerenciar cargas de ataque que podem ser implantadas pelo administrador do simulador de ataque.||
|**Logs de auditoria**|Ativar e configurar a auditoria para a organização, exibir os relatórios de auditoria da organização e exportar esses relatórios para um arquivo.|Gerenciamento de Organização <p> Administrador de Segurança|
|**Gerenciamento de Casos**|Criar, editar, excluir e controlar o acesso a ocorrências de Descobertas e Descobertas.|Conformidade em comunicações <p> Investigadores de conformidade de comunicação <p> Administrador de Conformidade <p>Gerente de Descoberta Eletrônica <p> Gerenciamento de riscos internos <p> Administradores de Gerenciamento de Riscos Insider <p> Analistas do Gerenciamento de Risco Interno <p> Investigadores do Gerenciamento de Risco Interno <p> Gerenciamento de Organização|
|**Comunicação**|Gerencie todas as comunicações com os custodiantes identificados em um caso de Descoberta Eletrônica Avançada.  Criar notificações de espera, manter lembretes e escalonamentos para o gerenciamento. Acompanhe a confirmação custodiante de notificações de isenção e gerencie o acesso ao portal custodiante usado por cada custodiante em um caso para controlar as comunicações dos casos em que foram identificados como custodiante.|Gerente de Descoberta Eletrônica|
|**Administrador de Conformidade de Comunicação**|Usado para gerenciar políticas no recurso de Conformidade de Comunicação.|Conformidade em comunicações <p> Administradores de Conformidade de Comunicação|
|**Análise de conformidade de comunicação**|Usado para executar investigação, correção das violações de mensagem no recurso de Conformidade de Comunicação. Só pode exibir metadados de mensagem.|Conformidade em comunicações <p> Analistas de Conformidade de Comunicação <p> Investigadores de conformidade de comunicação|
|**Gerenciamento de Caso de Conformidade de Comunicação**|Usado para acessar casos de Conformidade de Comunicação.|Conformidade em comunicações <p> Administradores de Conformidade de Comunicação <p> Analistas de Conformidade de Comunicação <p> Investigadores de conformidade de comunicação <p> Visualizadores de Conformidade de Comunicação|
|**Investigação de Conformidade de Comunicação**|Usado para executar investigação, correção e revisão de violações de mensagens no recurso de Conformidade de Comunicação. Pode exibir metadados de mensagens e mensagens.|Conformidade em comunicações <p> Investigadores de conformidade de comunicação|
|**Visualizador de Conformidade de Comunicação**|Usado para acessar relatórios e widgets no recurso Conformidade de Comunicação.|Conformidade em comunicações <p> Visualizadores de Conformidade de Comunicação|
|**Administrador de Conformidade**|Exibir e editar configurações e relatórios para recursos de conformidade.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização|
|**Administração do Gerenciador de Conformidade**|Gerencie a criação e modificação do modelo.|Administradores do Gerenciador de Conformidade|
|**Avaliação do Gerenciador de Conformidade**|Crie avaliações, implemente ações de melhoria e atualize o status do teste para ações de melhoria.|Administradores do Gerenciador de Conformidade <p> Avaliadores do Gerenciador de Conformidade|
|**Contribuição do Gerenciador de Conformidade**|Crie avaliações e realize um trabalho para implementar ações de melhoria.|Administradores do Gerenciador de Conformidade <p> Avaliadores do Gerenciador de Conformidade <p> Colaboradores do Gerenciador de Conformidade|
|**Leitor do Gerenciador de Conformidade**|Exibir todo o conteúdo do Gerenciador de Conformidade, exceto funções de administrador.|Administradores do Gerenciador de Conformidade <p> Avaliadores do Gerenciador de Conformidade <p> Colaboradores do Gerenciador de Conformidade <p> Leitores do Gerenciador de Conformidade|
|**Pesquisa de Conformidade**|Execute pesquisas em caixas de correio e faça uma estimativa dos resultados.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p>Gerente de Descoberta Eletrônica <p> Gerenciamento de Organização <p> Operador de segurança|
|**Custodian**|Identifique e gerencie custodiantes para ocorrências de Descoberta Avançada e use as informações do Azure Active Directory e de outras fontes para encontrar fontes de dados associadas aos custodiantes. Associe outras fontes de dados, como caixas de correio, sites do SharePoint e Teams, a custodiantes em uma ocorrência.  Coloque uma espera legal nas fontes de dados associadas aos responsáveis para preservar o conteúdo no contexto de um caso.|Gerente de Descoberta Eletrônica|
|**Visualizador de Conteúdo de Classificação de Dados**|Exibir a renderização in-line de arquivos no Explorador de conteúdo.|Visualizador de Conteúdo do Explorador de Conteúdo|
|**Provedor de Comentários sobre Classificação de Dados**|Permite fornecer comentários aos classificadores no Explorador de Conteúdo.|Conformidade em comunicações <p> Investigadores de conformidade de comunicação <p> Administrador de Conformidade|
|**Analisador de Comentários de Classificação de Dados**|Permite analisar os comentários dos classificadores no Explorador de comentários.|Administrador de Conformidade|
|**Visualizador da Lista de Classificação de Dados**|Exibir a lista de arquivos no Explorador de conteúdo.|Visualizador de Lista do Explorador de Conteúdo|
|**Gerenciamento de Dispositivos**|Exibir e editar configurações e relatórios para recursos de gerenciamento de dispositivos.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Gerenciamento de disposição**|Controlar permissões para acessar a Disposição Manual no Centro de Conformidade & segurança.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Registros|
|**Gerenciamento de Conformidade de DLP**|Exibir e editar configurações e relatórios para políticas de prevenção de perda de dados (DLP).|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Export**|Exportar conteúdo de site e caixa de correio que é retornado das pesquisas.|Gerente de Descoberta Eletrônica|
|**Reter**|Colocar conteúdo em caixas de correio, sites e pastas públicas em espera. Quando em espera, uma cópia do conteúdo é armazenada em um local seguro. Os proprietários de conteúdo ainda poderão modificar ou excluir o conteúdo original.|Administrador de Conformidade <p>Gerente de Descoberta Eletrônica <p> Gerenciamento de Organização|
|**Gerenciamento de Conformidade do IB**|Exibir, criar, remover, modificar e testar políticas de Barreira de Informações.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Administrador de Gerenciamento de Riscos Do Insider**|Criar, editar, excluir e controlar o acesso ao recurso Gerenciamento de Riscos Do Insider.|Gerenciamento de riscos internos <p> Administradores de Gerenciamento de Riscos Insider|
|**Análise de Gerenciamento de Riscos Insider**|Acessar todos os modelos de alertas, casos e avisos de gerenciamento de riscos insider.|Gerenciamento de riscos internos <p> Analistas do Gerenciamento de Risco Interno|
|**Auditoria de Gerenciamento de Riscos Insider**|Permitir a exibição de trilhas de auditoria de Risco Interno.|Auditores do Gerenciamento de Riscos Insider|
|**Investigação de Gerenciamento de Riscos Insider**|Acesse todos os alertas de gerenciamento de riscos, casos, modelos de avisos e o Explorador de Conteúdo para todos os casos.|Gerenciamento de riscos internos <p> Investigadores do Gerenciamento de Risco Interno|
|**Contribuição permanente do Gerenciamento de Riscos Insider**|Esse grupo de funções está visível, mas é usado somente por serviços em segundo plano.|Colaboradores do IRM|
|**Contribuição temporária do Gerenciamento de Riscos Insider**|Esse grupo de funções está visível, mas é usado somente por serviços em segundo plano.|Colaboradores do IRM|
|**Gerenciar Alertas**|Exibir e editar configurações e relatórios de alertas.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança|
|**Configuração da Organização**|Executar, exibir e exportar relatórios de auditoria e gerenciar políticas de conformidade para DLP, dispositivos e preservação.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização|
|**Visualização**|Exibir uma lista de itens que são retornados de pesquisas de conteúdo e abrir cada item da lista para exibir seu conteúdo.|Gerente de Descoberta Eletrônica|
|**Quarentena**|Permite exibir e liberar emails em quarentena.|Administrador de Quarentena <p> Administrador de Segurança <p> Gerenciamento de Organização|
|**RecordManagement**|Exibir e editar a configuração do recurso de gerenciamento de registros.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Gerenciamento de Registros|
|**Gerenciamento de retenção**|Gerenciar políticas de retenção, rótulos de retenção e políticas de rótulo de retenção.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Gerenciamento de Registros|
|**Examinar**|Essa função permite que os usuários acessem conjuntos de revisão em casos de Descoberta Avançada. Os usuários aos quais essa função foi atribuída podem ver e abrir a lista de ocorrências na página de descoberta > **Avançado** no centro de conformidade do Microsoft 365 dos quais eles são membros. Depois que o usuário acessar um caso de Descoberta Avançada, ele poderá selecionar Conjuntos **de** revisão para acessar dados de ocorrência. Essa função não permite que o usuário visualize os resultados de uma pesquisa de coleção associada ao caso ou faça outras tarefas de gerenciamento de caso ou pesquisa. Os usuários com essa função só podem acessar os dados em um conjunto de revisão.|Gerente de Descoberta Eletrônica <p> Revisor|
|**Descriptografar RMS**|Descriptografar conteúdo protegido por RMS ao exportar resultados de pesquisa.|Gerente de Descoberta Eletrônica|
|**Gerenciamento de Função**|Gerencie a associação ao grupo de funções e crie ou exclua grupos de função personalizados.|Gerenciamento de Organização|
|**Pesquisar e limpar**|Permite que as pessoas removam dados em massa que corresponde aos critérios de uma pesquisa de conteúdo.|Gerenciamento de Organização|
|**Administrador de Segurança**|Exibir e editar a configuração e os relatórios dos recursos de Segurança.|Gerenciamento de Organização <p> Administrador de Segurança|
|**Leitor de Segurança**|Exibir a configuração e os relatórios dos recursos de segurança.|Leitor global <p> Gerenciamento de Organização <p> Operador de segurança <p> Leitor de segurança|
|**Administrador de Rótulos de Sensibilidade**|Exibir, criar, modificar e remover rótulos de sensibilidade.|Administrador de Dados de Conformidade <p> Gerenciamento de Organização <p> Administrador de Segurança|
|**Leitor de rótulos de sensibilidade**|Exibir a configuração e o uso de rótulos de sensibilidade.|Leitor global <p> Gerenciamento de Organização <p> Leitor de segurança|
|**Exibição de Garantia de Serviço**|Baixe os documentos disponíveis na seção Garantia do Serviço. O conteúdo inclui auditoria independente, documentação de conformidade e diretrizes relacionadas à confiança para usar recursos do Microsoft 365 para gerenciar a conformidade regulatória e os riscos de segurança.|Leitor global <p> Gerenciamento de Organização <p> Usuário da Garantia do Serviço|
|**Administrador de Revisão de Supervisão**|Gerencie políticas de revisão de supervisão, incluindo quais comunicações revisar e quem deve fazer a revisão.|Revisão de Supervisão|
|**Colaborador de Marca**|Exibir e atualizar a associação de marcas de usuário existentes.|Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança|
|**Gerenciador de Marca**|Exibir, atualizar, criar e excluir marcas de usuário.|Gerenciamento de Organização <p> Administrador de Segurança|
|**Leitor de Marca**|Acesso somente leitura a marcas de usuário existentes.|Leitor de segurança|
|**Logs de auditoria somente exibição**|Exibir e exportar relatórios de auditoria. Como esses relatórios podem conter informações confidenciais, você só deve atribuir essa função às pessoas com uma necessidade explícita de exibir essas informações.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança|
|**Caso somente exibição**||Conformidade em comunicações <p> Investigadores de conformidade de comunicação <p> Administrador de Conformidade <p> Gerenciamento de riscos internos <p> Administradores de Gerenciamento de Riscos Insider <p> Analistas do Gerenciamento de Risco Interno <p> Investigadores do Insider RiskManagement <p> Gerenciamento de Organização|
|**Gerenciamento de dispositivos somente exibição**|Exibir a configuração e os relatórios do recurso Gerenciamento de Dispositivos.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Gerenciamento de conformidade de DLP somente exibição**|Exibir as configurações e relatórios para políticas de prevenção de perda de dados (DLP).|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Gerenciamento de conformidade do IB somente exibição**|Exibir a configuração e os relatórios do recurso Barreiras de Informações.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Gerenciar Alertas Somente Exibição**|Exibir a configuração e os relatórios do recurso Gerenciar Alertas.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor global <p> Gerenciamento de Organização <p> Administrador de Segurança <p> Operador de segurança <p> Leitor de segurança|
|**Destinatários Somente para Exibição**|Exibir informações sobre usuários e grupos.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Leitor global <p> Administrador do Fluxo de Mensagens <p> Gerenciamento de Organização|
|**Gerenciamento de Registros Somente Exibição**|Exibir a configuração do recurso de gerenciamento de registros.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> <p> Leitor global <p> Gerenciamento de Organização|
|**Gerenciamento de retenção somente exibição**|Exibir a configuração de políticas de retenção, rótulos de retenção e políticas de rótulo de retenção.|Administrador de Conformidade <p> Administrador de Dados de Conformidade <p> Administrador Global <p> Gerenciamento da Organização|
|
