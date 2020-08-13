---
title: Permissões de recurso no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Saiba mais sobre a permissão necessária para tarefas na proteção do Exchange Online autônoma
ms.openlocfilehash: 2f653fbae49087b8fc1ebc3a97586512965df970
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46652892"
---
# <a name="permissions-in-standalone-eop"></a>Permissões no EOP autônomo

Proteção autônoma do Exchange Online (EOP) sem caixas de correio do Exchange Online usa o modelo de permissões RBAC (controle de acesso baseado em função) para conceder permissões facilmente aos seus administradores. Você pode usar os recursos de permissão em EOP autônomos para colocar sua nova organização em funcionamento rapidamente.

Para conceder permissões aos usuários, consulte [Manage admin role groups in EOP](manage-admin-role-group-permissions-in-eop.md).

Para obter mais informações sobre permissões no Microsoft 365, consulte [about admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

## <a name="role-based-permissions"></a>Permissões baseadas em função

As permissões de administrador concedidas aos usuários são baseadas nas funções de gerenciamento. Uma função de gerenciamento define os cmdlets disponíveis para um conjunto de tarefas determinadas. Como o centro de administração do Exchange (Eat) e o PowerShell autônomo do EOP usam cmdlets, conceder acesso a um cmdlet oferece ao usuário permissão para fazer as tarefas relacionadas no Eat ou no EOP PowerShell autônomo. Por exemplo, a função de destinatários de email define os cmdlets necessários para modificar os usuários de email.

Em EOP autônomos, as funções administrativas são o único tipo de função de gerenciamento disponível (não há funções de usuário final ou diretivas de atribuição de função).

## <a name="role-groups"></a>Grupos de função

Para facilitar a atribuição de funções aos usuários, o EOP autônomo usa grupos de função. As funções de gerenciamento são atribuídas a grupos de função, e os membros do grupo de função obtêm as permissões associadas às funções. Em outras palavras, as funções de gerenciamento não são atribuídas diretamente aos usuários; Eles são atribuídos ao grupo de funções. Esse modelo permite que você atribua muitas funções a vários membros do grupo de função de uma só vez. Os membros do grupo de função podem ser usuários de email, grupos de segurança habilitados para email, usuários do centro de administração do Microsoft 365 e outros grupos de função.

A figura a seguir mostra a relação entre usuários, grupos de função e funções.

![Função, grupo de funções e relacionamentos de membros](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

Os grupos de função disponíveis no EOP autônomo são descritos na tabela a seguir.

****

|Grupo de função|Descrição|Funções padrão atribuídas|
|---|---|---|
|ComplianceManagement|Configure e gerencie as configurações de conformidade dentro da organização, incluindo prevenção de perda de dados (DLP) se sua assinatura tiver recursos de DLP. <br/><br/> Os membros da função de [administrador de conformidade](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) no Azure ad obtêm automaticamente as permissões desse grupo de função.|Logs de auditoria <br/><br/> Administração de conformidade <br/><br/> Gerenciamento de Direitos de Informação <br/><br/> Gerenciamento de retenção <br/><br/> Logs de auditoria somente para exibição <br/><br/> Configuração Somente para Exibição <br/><br/> Destinatários Somente para Exibição|
|ContentExplorerContentViewer|Não usado.|Visualizador de conteúdo de classificação de dados|
|ContentExplorerListViewer|Não usado.|Visualizador de lista de classificação de dados|
|Comunique|Exibir e gerenciar usuários de email.|Redefinir senha <br/><br/> Opções do usuário <br/><br/> Destinatários Somente para Exibição|
|HygieneManagement|Gerenciar recursos de proteção (anti-spam, Antimalware, etc.).|Higiene de transporte <br/><br/> Configuração Somente para Exibição <br/><br/> Destinatários Somente para Exibição|
|MailFlowAdministrator|Exibir e gerenciar domínios e conectores aceitos|Domínios remotos e aceitos <br/><br/> Destinatários Somente para Exibição|
|Gerenciamento|Acesso de administrador a toda a organização e a capacidade de executar praticamente qualquer tarefa. <br/><br/> Os membros da função de [administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) no Azure ad obtêm automaticamente as permissões desse grupo de funções. <br/><br/> **Importante**: como o grupo de função gerenciamento é uma função poderosa, somente os usuários que executam tarefas administrativas em nível organizacional devem ser membros desse grupo de função.|AntiMalware <br/><br/> Anti <br/><br/> Logs de auditoria <br/><br/> Administrador de Conformidade <br/><br/> Grupos dinâmicos de distribuição <br/><br/> Gerenciamento de Direitos de Informação <br/><br/> Criação de Destinatário de Email <br/><br/> Destinatários de Email <br/><br/> Controle de Mensagens <br/><br/> Migração <br/><br/> Acesso para cliente da organização <br/><br/> Configuração da organização <br/><br/> Configurações de transporte da organização <br/><br/> Quarentena <br/><br/> Diretivas de Destinatário <br/><br/> Domínios remotos e aceitos <br/><br/> Redefinir senha <br/><br/> Gerenciamento de retenção <br/><br/> Gerenciamento de função <br/><br/> Administrador de Segurança <br/><br/> Associação e criação de grupos de segurança <br/><br/> Leitor de segurança <br/><br/> Administrador de rótulo de confidencialidade <br/><br/> Supervisão <br/><br/> Higiene de transporte <br/><br/> Regras de Transporte <br/><br/> Opções do usuário <br/><br/> Somente exibição Antimalware <br/><br/> AntiSpam somente para exibição <br/><br/> Logs de auditoria somente para exibição <br/><br/> Configuração Somente para Exibição <br/><br/> Quarentena somente para exibição <br/><br/> Destinatários Somente para Exibição <br/><br/> Inteligência de ameaças somente para exibição|
|QuarantineAdministrator|Gerenciar mensagens em quarentena para todos os destinatários.|Quarentena|
|RecipientManagement|Criar, gerenciar e remover objetos de destinatário na organização.|Grupos dinâmicos de distribuição <br/><br/> Criação de Destinatário de Email <br/><br/> Destinatários de Email <br/><br/> Controle de Mensagens <br/><br/> Migração <br/><br/> Diretivas de Destinatário <br/><br/> Redefinir senha|
|RecordsManagement|Configurar recursos de conformidade, como marcas de política de retenção, classificações de mensagens e regras de fluxo de emails (também conhecidas como regras de transporte).|Rastreamento de Mensagem <br/><br/> Gerenciamento de retenção <br/><br/> Regras de Transporte|
|SecurityAdministrator|Configure todos os aspectos de proteção na organização (antispam, Antimalware, antifalsificação, quarentena, etc.). <br/><br/> Os membros da função de [administrador de segurança](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) no Azure ad obtêm automaticamente as permissões desse grupo de função.|AntiMalware <br/><br/> Anti <br/><br/> Logs de auditoria <br/><br/> Quarentena <br/><br/> Administrador de Segurança <br/><br/> Administrador de rótulo de confidencialidade <br/><br/> Somente exibição Antimalware <br/><br/> AntiSpam somente para exibição <br/><br/> Logs de auditoria somente para exibição <br/><br/> Quarentena somente para exibição <br/><br/> Inteligência de ameaças somente para exibição|
|SecurityReader|Acesso somente de exibição a todos os aspectos de proteção na organização (antispam, Antimalware, antifalsificação, quarentena, etc.). <br/><br/> Os membros da função de [leitor de segurança](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) no Azure ad obtêm automaticamente as permissões desse grupo de função.|Leitor de segurança <br/><br/> Somente exibição Antimalware <br/><br/> AntiSpam somente para exibição <br/><br/> Quarentena somente para exibição <br/><br/> Inteligência de ameaças somente para exibição|
|TenantAdmins|A associação a este grupo de funções é sincronizada de forma centralizada em serviços e gerenciada centralmente. Por padrão, esse grupo de função não recebe nenhuma função. No entanto, ele será um membro do grupo de função gerenciamento da organização e herdará essas permissões.|Nenhuma|
|ViewOnlyOrganizationManagement|Exibir os objetos Recipient, Protection e Configuration e suas propriedades na organização.|Administrador de Conformidade <br/><br/> Administrador de Segurança <br/><br/> Leitor de segurança <br/><br/> Administrador de rótulo de confidencialidade <br/><br/> Configuração Somente para Exibição <br/><br/> Destinatários Somente para Exibição|
|

Se você trabalhar em uma pequena organização que tenha apenas alguns administradores, talvez seja necessário adicionar esses usuários somente ao grupo de função gerenciamento da organização, e talvez nunca seja necessário usar os outros grupos de função. Se você trabalhar em uma organização maior, você pode ter administradores que executam tarefas específicas, como a configuração de destinatários. Nesses casos, você pode adicionar um administrador ao grupo de função de gerenciamento de destinatários e outro administrador ao grupo de função de gerenciamento da organização. Esses administradores podem gerenciar suas áreas específicas, mas não terão permissões para gerenciar áreas que não são responsáveis.

Se is grupos de função internos no Exchange Online não corresponderem à função de trabalho de seus administradores, você poderá criar grupos de função e adicionar funções a eles. Para obter mais informações, consulte [Manage role groups in standalone EOP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Funções

As funções internas que estão disponíveis em EOP autônomo são descritas na tabela a seguir.

****

|Função * *|Descrição|Atribuições de grupo de função padrão|
|---|---|---|
|AntiMalware|Exibir e modificar a configuração e os relatórios de recursos antimalware.|Gerenciamento <br/><br/> SecurityAdministrator|
|Anti|Exibir e modificar a configuração e os relatórios para recursos antispam.|Gerenciamento <br/><br/> SecurityAdministrator|
|Logs de auditoria|Pesquise o log de auditoria do administrador e visualize os resultados.|ComplianceManagement <br/><br/> Gerenciamento <br/><br/> SecurityAdministrator|
|Administrador de conformidade<sup>\*</sup>||ComplianceManagement <br/><br/> Gerenciamento <br/><br/> ViewOnlyOrganizationManagement|
|Visualizador de conteúdo de classificação de dados<sup>\*</sup>||ContentExplorerContentViewer|
|Visualizador de lista de classificação de dados<sup>\*</sup>||
|Grupos dinâmicos de distribuição|Crie e gerencie todos os grupos de distribuição, grupos de segurança habilitados para email e membros.|Gerenciamento <br/><br/> RecipientManagement|
|Gerenciamento de direitos de informação<sup>\*</sup>||ComplianceManagement <br/><br/> Gerenciamento|
|Criação de Destinatário de Email|Criar e remover usuários de email.|Gerenciamento <br/><br/> RecipientManagement|
|Destinatários de Email|Modificar usuários de email existentes.|Gerenciamento <br/><br/> RecipientManagement|
|Controle de mensagens<sup>\*</sup>||Gerenciamento <br/><br/> RecipientManagement <br/><br/> Gerenciamento de Registros|
|Migração<sup>\*</sup>||Gerenciamento <br/><br/> RecipientManagement|
|MyBaseOptions|Permite que os usuários exibam suas próprias mensagens em quarentena. <br/><br/> Essa função é atribuída automaticamente aos usuários, e você não pode atribuí-la manualmente.|Nenhuma|
|Acesso para cliente da organização<sup>\*</sup>||Gerenciamento|
|Configuração da organização|Exibir relatórios.|Gerenciamento|
|Configurações de transporte da organização<sup>\*</sup>||Gerenciamento|
|Quarentena|Gerencie todos os tipos de mensagens em quarentena para todos os destinatários.|Gerenciamento <br/><br/> QuarantineAdministrator <br/><br/> SecurityAdministrator|
|Políticas de destinatário<sup>\*</sup>||Gerenciamento <br/><br/> RecipientManagement|
|Domínios remotos e aceitos|Gerenciar domínios remotos, domínios aceitos e conectores.|MailFlowAdministrator <br/><br/> Gerenciamento|
|Redefinir senha<sup>\*</sup>||Comunique <br/><br/> Gerenciamento <br/><br/> RecipientManagement|
|Gerenciamento de retenção<sup>\*</sup>||ComplianceManagement <br/><br/> Gerenciamento <br/><br/> RecordsManagement|
|Gerenciamento de função|Criar e gerenciar grupos de função.|Gerenciamento|
|Administrador de Segurança|Gerenciar a configuração e os relatórios de todos os recursos de segurança e proteção.|Gerenciamento <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Associação e criação de grupos de segurança|Criar e gerenciar grupos de segurança habilitados para email.|Gerenciamento|
|Leitor de segurança|Exibir a configuração e os relatórios de recursos de segurança e proteção.|Gerenciamento de Organização <br/><br/> SecurityReader <br/><br/> ViewOnlyOrganizationManagement|
|Administrador de rótulo de confidencialidade<sup>\*</sup>||Gerenciamento <br/><br/> SecurityAdministrator <br/><br/> ViewOnlyOrganizationManagement|
|Supervisão<sup>\*</sup>||Gerenciamento|
|Higiene de transporte|Gerencie recursos antimalware, antispam e antifalsificação.|HygieneManagement <br/><br/> Gerenciamento|
|Regras de Transporte|Criar e gerenciar regras de fluxo de emails (também conhecidas como regras de transporte).|Gerenciamento <br/><br/> RecordsManagement|
|Opções do usuário|Modificar usuários de email existentes.|Comunique <br/><br/> Gerenciamento|
|Somente exibição Antimalware|Exibir a configuração e os relatórios dos recursos antimalware.|Gerenciamento <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|AntiSpam somente para exibição|Exibir a configuração e os relatórios para recursos antispam.|Gerenciamento <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Logs de auditoria somente para exibição|Pesquise o log de auditoria do administrador e visualize os resultados.|ComplianceManagement <br/><br/> Gerenciamento <br/><br/> SecurityAdministrator|
|Configuração Somente para Exibição|Exibir todas as configurações de organização e de fluxo de email (não destinatário) na organização.|ComplianceManagement <br/><br/> HygieneManagement <br/><br/> Gerenciamento <br/><br/> ViewOnlyOrganizationManagement|
|Quarentena somente para exibição|Exibir todas as mensagens em quarentena para todos os destinatários.|Gerenciamento <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|Destinatários Somente para Exibição|Exibir Propriedades de destinatário e executar rastreamento de mensagem.|ComplianceManagement <br/><br/> Comunique <br/><br/> HygieneManagement <br/><br/> MailFlowAdministrator <br/><br/>  Gerenciamento <br/><br/> ViewOnlyOrganizationManagement|
|Inteligência de ameaças somente para exibição<sup>\*</sup>||Gerenciamento <br/><br/> SecurityAdministrator <br/><br/> SecurityReader|
|

<sup>\*</sup>Embora essa função esteja disponível, ela basicamente não faz nada útil em EOP autônomos.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Microsoft 365 permissões no EOP autônomo

Ao criar um usuário no centro de administração do Microsoft 365, você pode escolher se deseja atribuir várias funções administrativas, como administrador global, administrador de serviço, administrador de senha e assim por diante, para o usuário. Algumas, mas não todas, as funções do Microsoft 365 concedem permissões administrativas de usuário no EOP.

> [!NOTE]
> A conta que você usou para criar sua organização do EOP autônomo é atribuída automaticamente à função de administrador global.

A tabela a seguir lista as funções do Microsoft 365 e os grupos de funções do EOP autônomos aos quais elas correspondem. Para obter mais informações sobre essas funções, consulte [sobre funções de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).

****

|Função 365 da Microsoft|Grupo de função EOP|
|---|---|
|Administrador do Exchange|Gerenciamento|
|Administrador global|Gerenciamento <br/><br/> **Observação**: a função de administrador global e o grupo de função gerenciamento estão ligados juntos usando um grupo de função de administrador de empresa especial. O grupo de função Administrador da empresa é gerenciado internamente e não pode ser modificado diretamente.|
|Administrador de senha|Comunique|
|Leitor global|ViewOnlyOrganizationManagement|
|Administrador de segurança|SecurityAdministrator|
|Leitor de segurança|SecurityReader|
|

Outras funções do Microsoft 365 não têm um grupo de função EOP correspondente e não concederão permissões administrativas no EOP. Para obter mais informações sobre a atribuição de uma função 365 da Microsoft a um usuário, consulte [assign admin Roles](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles).

Os usuários podem receber direitos administrativos no EOP sem adicioná-los às funções do Microsoft 365. Para fazer isso, adicione o usuário como membro de um grupo de função EOP. O usuário receberá permissões no EOP, mas não obterá permissões em outras cargas de trabalho do Microsoft 365.

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você copiou um grupo de funções com êxito, execute uma das seguintes etapas:

- No Eat, vá para funções de administrador de **permissões** \> **Admin Roles**e verifique se o grupo de função está listado (ou não listado). Selecione o grupo de funções e verifique as configurações no painel de detalhes ou clique em **Editar** ![ ícone de edição ](../../media/ITPro-EAC-EditIcon.png) para verificar as configurações.

- No PowerShell do Exchange Online, substitua o \<Role Group Name\> nome do grupo de função e execute o seguinte comando para verificar se o grupo de função existe (ou não existe) e verifique as configurações:

    ```PowerShell
    Get-RoleGroup -Identity "<Role Group Name>" | Format-List
    ```
