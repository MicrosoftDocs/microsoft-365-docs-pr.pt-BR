---
title: Permissões de recurso no EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Saiba mais sobre a permissão necessária para tarefas no Exchange Online Protection autônomo
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4f1f364e684f2d1d76f26f573e66fbd50bf5138b
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167390"
---
# <a name="permissions-in-standalone-eop"></a>Permissões no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção do Exchange Online autônoma](https://go.microsoft.com/fwlink/?linkid=2148611)

O EOP (Proteção do Exchange Online Autônomo) sem caixas de correio do Exchange Online usa o modelo de permissões RBAC (Controle de Acesso Baseado na Função) para conceder permissões facilmente aos administradores. Você pode usar os recursos de permissão no EOP autônomo para fazer sua nova organização funcionar rapidamente.

Para conceder permissões aos usuários, consulte [Gerenciar grupos de função de administrador no EOP](manage-admin-role-group-permissions-in-eop.md).

Para saber mais sobre permissões no Microsoft 365, confira [Sobre funções de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

## <a name="role-based-permissions"></a>Permissões baseadas em função

As permissões de administrador que você concede aos usuários são baseadas em funções de gerenciamento. Uma função de gerenciamento define os cmdlets que estão disponíveis para um conjunto de determinadas tarefas. Como o Centro de administração do Exchange (EAC) e o PowerShell do EOP autônomo usam cmdlets, conceder acesso a um cmdlet dá ao usuário permissão para realizar as tarefas relacionadas no EAC ou no EOP PowerShell autônomo. Por exemplo, a função Destinatários de Email define os cmdlets necessários para modificar usuários de email.

No EOP autônomo, as funções administrativas são o único tipo de função de gerenciamento disponível (não há funções de usuário final ou políticas de atribuição de função).

## <a name="role-groups"></a>Grupos de função

Para facilitar a atribuição de funções aos usuários, o EOP autônomo usa grupos de função. As funções de gerenciamento são atribuídas a grupos de funções, e os membros do grupo de função têm as permissões associadas às funções. Em outras palavras, as funções de gerenciamento não são atribuídas diretamente aos usuários; eles são atribuídos ao grupo de funções. Esse modelo permite que você atribua muitas funções a vários membros do grupo de funções ao mesmo tempo. Os membros do grupo de funções podem ser usuários de email, grupos de segurança habilitados para email, usuários do centro de administração do Microsoft 365 e outros grupos de função.

A figura a seguir mostra a relação entre usuários, grupos de função e funções.

![Função, grupo de funções e relacionamentos de membros](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

Os grupos de função disponíveis no EOP autônomo são descritos na tabela a seguir.

****

|Grupo de função|Descrição|Funções padrão atribuídas|
|---|---|---|
|ComplianceManagement|Configure e gerencie as configurações de conformidade dentro da organização, incluindo a prevenção de perda de dados (DLP) se sua assinatura tiver recursos de DLP. <p> Os membros da [função Administrador de](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) Conformidade no Azure AD automaticamente têm as permissões desse grupo de funções.|Logs de auditoria <p> Administração de Conformidade <p> Gerenciamento de Direitos de Informação <p> Gerenciamento de retenção <p> View-Only logs de auditoria <p> Configuração Somente para Exibição <p> Destinatários Somente para Exibição|
|ContentExplorerContentViewer|Não usado.|Visualizador de Conteúdo de Classificação de Dados|
|ContentExplorerListViewer|Não usado.|Visualizador da Lista de Classificação de Dados|
|HelpDesk|Exibir e gerenciar usuários de email.|Redefinir Senha <p> Opções do usuário <p> Destinatários Somente para Exibição|
|HygieneManagement|Gerenciar recursos de proteção (anti-spam, anti-malware, etc.).|Higienização de Transporte <p> Configuração Somente para Exibição <p> Destinatários Somente para Exibição|
|MailFlowAdministrator|Exibir e gerenciar domínios e conectores aceitos|Domínios Remotos e Aceitos <p> Destinatários Somente para Exibição|
|OrganizationManagement|Acesso de administrador a toda a organização e a capacidade de executar quase todas as tarefas. <p> Os membros da [função administrador global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) no Azure AD automaticamente obter as permissões desse grupo de função. <p> **Importante:** como o grupo de função OrganizationManagement é uma função poderosa, somente os usuários que executam tarefas administrativas de nível organizacional devem ser membros desse grupo de função.|AntiMalware <p> AntiSpam <p> Logs de auditoria <p> Administrador de Conformidade <p> Grupos dinâmicos de distribuição <p> Gerenciamento de Direitos de Informação <p> Criação de Destinatário de Email <p> Destinatários de Email <p> Controle de Mensagens <p> Migração <p> Acesso para Cliente da Organização <p> Configuração da Organização <p> Configurações de Transporte da Organização <p> Quarentena <p> Diretivas de Destinatário <p> Domínios Remotos e Aceitos <p> Redefinir Senha <p> Gerenciamento de retenção <p> Gerenciamento de Função <p> Administrador de Segurança <p> Criação e associação de grupos de segurança <p> Leitor de segurança <p> Administrador de Rótulos de Sensibilidade <p> Supervisão <p> Higienização de Transporte <p> Regras de Transporte <p> Opções do usuário <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only logs de auditoria <p> Configuração Somente para Exibição <p> View-Only quarentena <p> Destinatários Somente para Exibição <p> View-Only inteligência contra ameaças|
|QuarantineAdministrator|Gerenciar mensagens em quarentena para todos os destinatários.|Quarentena|
|RecipientManagement|Criar, gerenciar e remover objetos de destinatário na organização.|Grupos dinâmicos de distribuição <p> Criação de Destinatário de Email <p> Destinatários de Email <p> Controle de Mensagens <p> Migração <p> Diretivas de Destinatário <p> Redefinir Senha|
|RecordsManagement|Configurar recursos de conformidade, como marcas de política de retenção, classificações de mensagens e regras de fluxo de emails (também conhecidas como regras de transporte).|Rastreamento de Mensagem <p> Gerenciamento de retenção <p> Regras de Transporte|
|SecurityAdministrator|Configure todos os aspectos de proteção na organização (anti-spam, anti-malware, anti-spoofing, quarentena etc.). <p> Os membros da [função Administrador de](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) Segurança no Azure AD automaticamente têm as permissões desse grupo de funções.|AntiMalware <p> AntiSpam <p> Logs de auditoria <p> Quarentena <p> Administrador de Segurança <p> Administrador de Rótulos de Sensibilidade <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only logs de auditoria <p> View-Only quarentena <p> View-Only inteligência contra ameaças|
|SecurityReader|Acesso somente exibição a todos os aspectos de proteção na organização (anti-spam, anti-malware, anti-spoofing, quarentena etc.). <p> Os membros da [função Leitor de](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) Segurança no Azure AD automaticamente têm as permissões desse grupo de funções.|Leitor de segurança <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only quarentena <p> View-Only inteligência contra ameaças|
|TenantAdmins|A associação nesse grupo de função é sincronizada entre serviços e gerenciada centralmente. Por padrão, esse grupo de funções não recebe nenhuma função. No entanto, ele será membro do grupo de função Gerenciamento da Organização e herdará essas permissões.|nenhum|
|ViewOnlyOrganizationManagement|Exibir objetos de destinatário, proteção e configuração e suas propriedades na organização.|Administrador de Conformidade <p> Administrador de Segurança <p> Leitor de segurança <p> Administrador de Rótulos de Sensibilidade <p> Configuração Somente para Exibição <p> Destinatários Somente para Exibição|
|

Se você trabalha em uma organização pequena que tem apenas alguns administradores, talvez seja necessário adicionar esses usuários apenas ao grupo de funções Gerenciamento da Organização e talvez nunca precise usar os outros grupos de função. Se você trabalha em uma organização maior, pode ter administradores que realizam tarefas específicas, como a configuração do destinatário. Nesses casos, você pode adicionar um administrador ao grupo de funções Gerenciamento de Destinatários e outro administrador ao grupo de funções Gerenciamento da Organização. Esses administradores podem gerenciar suas áreas específicas, mas não terão permissões para gerenciar áreas pelas que não são responsáveis.

Se is grupos de função internos no Exchange Online não corresponderem à função de trabalho de seus administradores, você poderá criar grupos de função e adicionar funções a eles. Para obter mais informações, [consulte Gerenciar grupos de função no EOP autônomo.](manage-admin-role-group-permissions-in-eop.md)

## <a name="roles"></a>Funções

As funções integrados que estão disponíveis no EOP autônomo são descritas na tabela a seguir.

****

|Função**|Descrição|Atribuições de grupo de função padrão|
|---|---|---|
|AntiMalware|Exibir e modificar a configuração e os relatórios de recursos anti-malware.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|Exibir e modificar a configuração e os relatórios de recursos anti-spam.|OrganizationManagement <p> SecurityAdministrator|
|Logs de auditoria|Pesquise o log de auditoria do administrador e veja os resultados.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Administrador de Conformidade<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|Visualizador de Conteúdo de Classificação de Dados<sup>\*</sup>||ContentExplorerContentViewer|
|Visualizador da Lista de Classificação de Dados<sup>\*</sup>||
|Grupos dinâmicos de distribuição|Crie e gerencie todos os grupos de distribuição, grupos de segurança habilitados para email e membros.|OrganizationManagement <p> RecipientManagement|
|Gerenciamento de Direitos de Informação<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|Criação de Destinatário de Email|Criar e remover usuários de email.|OrganizationManagement <p> RecipientManagement|
|Destinatários de Email|Modificar usuários de email existentes.|OrganizationManagement <p> RecipientManagement|
|Controle de Mensagens<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> Gerenciamento de Registros|
|Migração<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|Permite que os usuários vejam suas próprias mensagens em quarentena. <p> Essa função é atribuída automaticamente aos usuários, e você não pode atribuí-la manualmente.|nenhum|
|Acesso para Cliente da Organização<sup>\*</sup>||OrganizationManagement|
|Configuração da Organização|Exibir relatórios.|OrganizationManagement|
|Configurações de Transporte da Organização<sup>\*</sup>||OrganizationManagement|
|Quarentena|Gerenciar todos os tipos de mensagem em quarentena para todos os destinatários.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|Políticas de Destinatário<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|Domínios Remotos e Aceitos|Gerenciar domínios remotos, domínios aceitos e conectores.|MailFlowAdministrator <p> OrganizationManagement|
|Redefinir Senha<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|Gerenciamento de retenção<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|Gerenciamento de Função|Criar e gerenciar grupos de função.|OrganizationManagement|
|Administrador de Segurança|Gerencie a configuração e os relatórios de todos os recursos de segurança e proteção.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Criação e associação de grupos de segurança|Criar e gerenciar grupos de segurança habilitados para email.|OrganizationManagement|
|Leitor de segurança|Exibir a configuração e os relatórios de recursos de segurança e proteção.|Gerenciamento de Organização <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Administrador de Rótulos de Sensibilidade<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Supervisão<sup>\*</sup>||OrganizationManagement|
|Higienização de Transporte|Gerenciar recursos anti-malware, anti-spam e anti-spoofing.|HygieneManagement <p> OrganizationManagement|
|Regras de Transporte|Criar e gerenciar regras de fluxo de emails (também conhecidas como regras de transporte).|OrganizationManagement <p> RecordsManagement|
|Opções do usuário|Modificar usuários de email existentes.|HelpDesk <p> OrganizationManagement|
|View-Only AntiMalware|Exibir a configuração e os relatórios de recursos anti-malware.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|Exibir a configuração e os relatórios de recursos anti-spam.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only logs de auditoria|Pesquise o log de auditoria do administrador e veja os resultados.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Configuração Somente para Exibição|Exibir todas as configurações da organização e do fluxo de emails (não destinatário) na organização.|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only quarentena|Exibir todas as mensagens em quarentena para todos os destinatários.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|Destinatários Somente para Exibição|Exibir propriedades de destinatário e executar rastreamento de mensagem.|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only inteligência contra ameaças<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Embora essa função seja disponível, ela basicamente não faz nada útil no EOP autônomo.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Permissões do Microsoft 365 no EOP autônomo

Ao criar um usuário no centro de administração do Microsoft 365, você pode optar por atribuir várias funções administrativas, como Administrador global, Administrador de serviço, Administrador de senha e assim por diante, ao usuário. Algumas, mas não todas, as funções do Microsoft 365 concedem ao usuário permissões administrativas no EOP.

> [!NOTE]
> A conta usada para criar sua organização autônoma do EOP é atribuída automaticamente à função de administrador Global.

A tabela a seguir lista as funções do Microsoft 365 e os grupos de função EOP autônomos aos quais correspondem. Para obter mais informações sobre essas funções, consulte [Sobre funções de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

****

|Função do Microsoft 365|Grupo de função EOP|
|---|---|
|Administrador do Exchange|OrganizationManagement|
|Administrador global|OrganizationManagement <p> **Observação:** a função de administrador global e o grupo de função OrganizationManagement são vinculados usando um grupo de função especial administrador da empresa. O grupo de função Administrador da Empresa é gerenciado internamente e não pode ser modificado diretamente.|
|Administrador de senha|HelpDesk|
|Leitor global|ViewOnlyOrganizationManagement|
|Administrador de segurança|SecurityAdministrator|
|Leitor de segurança|SecurityReader|
|

Outras funções do Microsoft 365 não têm um grupo de funções do EOP correspondente e não concederão permissões administrativas no EOP. Para saber mais sobre como atribuir uma função do Microsoft 365 a um usuário, confira [Atribuir funções de administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles)

Os usuários podem ter direitos administrativos no EOP sem adições às funções do Microsoft 365. Para fazer isso, adicione o usuário como membro de um grupo de funções do EOP. O usuário receberá permissões no EOP, mas não receberá permissões em outras cargas de trabalho do Microsoft 365.

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você copiou com êxito um grupo de funções, faça uma das seguintes etapas:

- No EAC, vá para Funções **de** Administrador de Permissões e verifique se \> o grupo de funções está listado (ou não listado). Selecione o grupo de funções e verifique as configurações no painel Detalhes ou clique no ícone Editar  ![ para verificar as ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No PowerShell do Exchange Online, substitua pelo nome do grupo de função e execute o seguinte comando para verificar se o grupo de funções existe (ou não existe) e verificar as \<Role Group Name\> configurações:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```
