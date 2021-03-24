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
description: Saiba mais sobre a permissão necessária para tarefas na Proteção autônoma do Exchange Online
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 212a109c792522270b7e5000747bec950b7f4fe2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51053183"
---
# <a name="permissions-in-standalone-eop"></a>Permissões no EOP autônomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Aplica-se a**
-  [Proteção autônoma do Exchange Online](exchange-online-protection-overview.md)

O EOP (Proteção autônoma do Exchange Online) sem caixas de correio do Exchange Online usa o modelo de permissões controle de acesso baseado em função (RBAC) para conceder permissões facilmente aos administradores. Você pode usar os recursos de permissão no EOP autônomo para fazer sua nova organização funcionar rapidamente.

Para conceder permissões aos usuários, consulte [Manage admin role groups in EOP](manage-admin-role-group-permissions-in-eop.md).

Para obter mais informações sobre permissões no Microsoft 365, consulte [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

## <a name="role-based-permissions"></a>Permissões baseadas em função

As permissões de administrador que você concede aos usuários se baseiam em funções de gerenciamento. Uma função de gerenciamento define os cmdlets que estão disponíveis para um conjunto de tarefas determinadas. Como o Centro de administração do Exchange (EAC) e o PowerShell autônomo do EOP usam cmdlets, conceder acesso a um cmdlet dá ao usuário permissão para realizar as tarefas relacionadas no EAC ou no EOP PowerShell autônomo. Por exemplo, a função Destinatários de Email define os cmdlets necessários para modificar usuários de email.

No EOP autônomo, as funções administrativas são o único tipo de função de gerenciamento disponível (não há funções de usuário final ou políticas de atribuição de função).

## <a name="role-groups"></a>Grupos de função

Para facilitar a atribuição de funções aos usuários, o EOP autônomo usa grupos de função. As funções de gerenciamento são atribuídas a grupos de funções, e os membros do grupo de função têm as permissões associadas às funções. Em outras palavras, as funções de gerenciamento não são atribuídas diretamente aos usuários; eles são atribuídos ao grupo de funções. Este modelo permite que você atribua muitas funções a muitos membros do grupo de funções ao mesmo tempo. Membros do grupo de funções podem ser usuários de email, grupos de segurança habilitados para email, usuários do Centro de administração do Microsoft 365 e outros grupos de função.

A figura a seguir mostra a relação entre usuários, grupos de função e funções.

![Função, grupo de funções e relacionamentos de membros](../../media/ITPro_Security_RBAC_EXO_SimplifiedRoleGroupRelationship.png)

Os grupos de função disponíveis no EOP autônomo são descritos na tabela a seguir.

****

|Grupo de função|Descrição|Funções padrão atribuídas|
|---|---|---|
|ComplianceManagement|Configure e gerencie as configurações de conformidade dentro da organização, incluindo a prevenção contra perda de dados (DLP) se sua assinatura tiver recursos de DLP. <p> Os membros da [função Administrador de](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#compliance-administrator) Conformidade no Azure AD obterão automaticamente as permissões desse grupo de função.|Logs de auditoria <p> Administração de Conformidade <p> Gerenciamento de Direitos de Informação <p> Gerenciamento de retenção <p> View-Only Logs de Auditoria <p> Configuração Somente para Exibição <p> Destinatários Somente para Exibição|
|ContentExplorerContentViewer|Não usado.|Visualizador de Conteúdo de Classificação de Dados|
|ContentExplorerListViewer|Não usado.|Visualizador de Lista de Classificação de Dados|
|HelpDesk|Exibir e gerenciar usuários de email.|Redefinir Senha <p> Opções do usuário <p> Destinatários Somente para Exibição|
|HygieneManagement|Gerenciar recursos de proteção (anti-spam, anti-malware, etc.).|Higienização de Transporte <p> Configuração Somente para Exibição <p> Destinatários Somente para Exibição|
|MailFlowAdministrator|Exibir e gerenciar domínios e conectores aceitos|Domínios remotos e aceitos <p> Destinatários Somente para Exibição|
|OrganizationManagement|Acesso de administrador a toda a organização e a capacidade de executar quase qualquer tarefa. <p> Os membros da [função administrador global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) no Azure AD automaticamente obterão as permissões desse grupo de função. <p> **Importante**: como o grupo de função OrganizationManagement é uma função poderosa, somente os usuários que executam tarefas administrativas de nível organizacional devem ser membros desse grupo de função.|AntiMalware <p> AntiSpam <p> Logs de auditoria <p> Administrador de Conformidade <p> Grupos dinâmicos de distribuição <p> Gerenciamento de Direitos de Informação <p> Criação de Destinatário de Email <p> Destinatários de Email <p> Controle de Mensagens <p> Migração <p> Acesso para Cliente da Organização <p> Configuração da Organização <p> Configurações de Transporte da Organização <p> Quarentena <p> Diretivas de Destinatário <p> Domínios remotos e aceitos <p> Redefinir Senha <p> Gerenciamento de retenção <p> Gerenciamento de Função <p> Administrador de Segurança <p> Criação e associação de grupos de segurança <p> Leitor de segurança <p> Administrador de rótulos de sensibilidade <p> Supervisão <p> Higienização de Transporte <p> Regras de Transporte <p> Opções do usuário <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only Logs de Auditoria <p> Configuração Somente para Exibição <p> View-Only Quarentena <p> Destinatários Somente para Exibição <p> View-Only Inteligência contra Ameaças|
|QuarantineAdministrator|Gerenciar mensagens em quarentena para todos os destinatários.|Quarentena|
|RecipientManagement|Crie, gerencie e remova objetos de destinatário na organização.|Grupos dinâmicos de distribuição <p> Criação de Destinatário de Email <p> Destinatários de Email <p> Controle de Mensagens <p> Migração <p> Diretivas de Destinatário <p> Redefinir Senha|
|RecordsManagement|Configure recursos de conformidade, como marcas de política de retenção, classificações de mensagens e regras de fluxo de emails (também conhecidas como regras de transporte).|Rastreamento de Mensagem <p> Gerenciamento de retenção <p> Regras de Transporte|
|SecurityAdministrator|Configure todos os aspectos de proteção na organização (anti-spam, anti-malware, anti-spoofing, quarentena etc.). <p> Os membros da [função Administrador de](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-administrator) Segurança no Azure AD obterão automaticamente as permissões desse grupo de função.|AntiMalware <p> AntiSpam <p> Logs de auditoria <p> Quarentena <p> Administrador de Segurança <p> Administrador de rótulos de sensibilidade <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only Logs de Auditoria <p> View-Only Quarentena <p> View-Only Inteligência contra Ameaças|
|SecurityReader|Acesso somente de exibição a todos os aspectos de proteção na organização (anti-spam, anti-malware, anti-spoofing, quarentena etc.). <p> Os membros da [função Leitor de](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#security-reader) Segurança no Azure AD obterão automaticamente as permissões desse grupo de função.|Leitor de segurança <p> View-Only AntiMalware <p> View-Only AntiSpam <p> View-Only Quarentena <p> View-Only Inteligência contra Ameaças|
|TenantAdmins|A associação neste grupo de funções é sincronizada entre serviços e gerenciada centralmente. Por padrão, esse grupo de funções não recebe nenhuma função. No entanto, ele será membro do grupo de função Gerenciamento da Organização e herdará essas permissões.|nenhuma|
|ViewOnlyOrganizationManagement|Exibir objetos de destinatário, proteção e configuração e suas propriedades na organização.|Administrador de Conformidade <p> Administrador de Segurança <p> Leitor de segurança <p> Administrador de rótulos de sensibilidade <p> Configuração Somente para Exibição <p> Destinatários Somente para Exibição|
|

Se você trabalhar em uma pequena organização que tenha apenas alguns administradores, talvez seja necessário adicionar esses usuários apenas ao grupo de função Gerenciamento da Organização e talvez nunca precise usar os outros grupos de função. Se você trabalhar em uma organização maior, poderá ter administradores que executam tarefas específicas, como a configuração do destinatário. Nesses casos, você pode adicionar um administrador ao grupo de função Gerenciamento de Destinatários e outro administrador ao grupo de função Gerenciamento da Organização. Esses administradores podem gerenciar suas áreas específicas, mas não terão permissões para gerenciar áreas pelas que não são responsáveis.

Se is grupos de função internos no Exchange Online não corresponderem à função de trabalho de seus administradores, você poderá criar grupos de função e adicionar funções a eles. Para obter mais informações, consulte [Manage role groups in standalone EOP](manage-admin-role-group-permissions-in-eop.md).

## <a name="roles"></a>Funções

As funções autônomas que estão disponíveis no EOP autônomo são descritas na tabela a seguir.

****

|Role**|Descrição|Atribuições de grupo de função padrão|
|---|---|---|
|AntiMalware|Exibir e modificar a configuração e os relatórios para recursos anti-malware.|OrganizationManagement <p> SecurityAdministrator|
|AntiSpam|Exibir e modificar a configuração e os relatórios para recursos anti-spam.|OrganizationManagement <p> SecurityAdministrator|
|Logs de auditoria|Pesquise o log de auditoria do administrador e veja os resultados.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Administrador de Conformidade<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|Visualizador de Conteúdo de Classificação de Dados<sup>\*</sup>||ContentExplorerContentViewer|
|Visualizador de Lista de Classificação de Dados<sup>\*</sup>||
|Grupos dinâmicos de distribuição|Crie e gerencie todos os grupos de distribuição, grupos de segurança habilitados para email e membros.|OrganizationManagement <p> RecipientManagement|
|Gerenciamento de Direitos de Informação<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement|
|Criação de Destinatário de Email|Criar e remover usuários de email.|OrganizationManagement <p> RecipientManagement|
|Destinatários de Email|Modificar usuários de email existentes.|OrganizationManagement <p> RecipientManagement|
|Rastreamento de mensagens<sup>\*</sup>||OrganizationManagement <p> RecipientManagement <p> Gerenciamento de Registros|
|Migração<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|MyBaseOptions|Permite que os usuários exibirem suas próprias mensagens em quarentena. <p> Essa função é atribuída automaticamente aos usuários e você não pode atribuí-la manualmente.|nenhuma|
|Acesso para Cliente da Organização<sup>\*</sup>||OrganizationManagement|
|Configuração da Organização|Exibir relatórios.|OrganizationManagement|
|Configurações de Transporte da Organização<sup>\*</sup>||OrganizationManagement|
|Quarentena|Gerencie todos os tipos de mensagem em quarentena para todos os destinatários.|OrganizationManagement <p> QuarantineAdministrator <p> SecurityAdministrator|
|Políticas de destinatário<sup>\*</sup>||OrganizationManagement <p> RecipientManagement|
|Domínios remotos e aceitos|Gerenciar domínios remotos, domínios aceitos e conectores.|MailFlowAdministrator <p> OrganizationManagement|
|Redefinir Senha<sup>\*</sup>||HelpDesk <p> OrganizationManagement <p> RecipientManagement|
|Gerenciamento de retenção<sup>\*</sup>||ComplianceManagement <p> OrganizationManagement <p> RecordsManagement|
|Gerenciamento de Função|Criar e gerenciar grupos de função.|OrganizationManagement|
|Administrador de Segurança|Gerencie a configuração e os relatórios de todos os recursos de segurança e proteção.|OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Criação e associação de grupos de segurança|Crie e gerencie grupos de segurança habilitados para email.|OrganizationManagement|
|Leitor de segurança|Exibir a configuração e os relatórios para recursos de segurança e proteção.|Gerenciamento de Organização <p> SecurityReader <p> ViewOnlyOrganizationManagement|
|Administrador de rótulos de sensibilidade<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> ViewOnlyOrganizationManagement|
|Supervisão<sup>\*</sup>||OrganizationManagement|
|Higienização de Transporte|Gerencie recursos anti-malware, anti-spam e anti-spoofing.|HygieneManagement <p> OrganizationManagement|
|Regras de Transporte|Criar e gerenciar regras de fluxo de emails (também conhecidas como regras de transporte).|OrganizationManagement <p> RecordsManagement|
|Opções do usuário|Modificar usuários de email existentes.|HelpDesk <p> OrganizationManagement|
|View-Only AntiMalware|Exibir a configuração e os relatórios para recursos anti-malware.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only AntiSpam|Exibir a configuração e os relatórios para recursos anti-spam.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|View-Only Logs de Auditoria|Pesquise o log de auditoria do administrador e veja os resultados.|ComplianceManagement <p> OrganizationManagement <p> SecurityAdministrator|
|Configuração Somente para Exibição|Exibir todas as configurações de organização e fluxo de email (não destinatário) na organização.|ComplianceManagement <p> HygieneManagement <p> OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Quarentena|Exibir todas as mensagens em quarentena para todos os destinatários.|OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|Destinatários Somente para Exibição|Exibir propriedades do destinatário e executar rastreamento de mensagens.|ComplianceManagement <p> HelpDesk <p> HygieneManagement <p> MailFlowAdministrator <p>  OrganizationManagement <p> ViewOnlyOrganizationManagement|
|View-Only Inteligência contra Ameaças<sup>\*</sup>||OrganizationManagement <p> SecurityAdministrator <p> SecurityReader|
|

<sup>\*</sup> Embora essa função seja disponível, ela basicamente não faz nada útil no EOP autônomo.

## <a name="microsoft-365-permissions-in-standalone-eop"></a>Permissões do Microsoft 365 no EOP autônomo

Ao criar um usuário no Centro de administração do Microsoft 365, você pode escolher se deve atribuir várias funções administrativas, como Administrador global, administrador de serviço, administrador de senha e assim por diante, ao usuário. Algumas, mas não todas, funções do Microsoft 365 concedem ao usuário permissões administrativas no EOP.

> [!NOTE]
> A conta usada para criar sua organização EOP autônoma é atribuída automaticamente à função de administrador global.

A tabela a seguir lista as funções do Microsoft 365 e os grupos de função EOP autônomos aos quais eles correspondem. Para obter mais informações sobre essas funções, consulte [Sobre funções de administrador](../../admin/add-users/about-admin-roles.md).

****

|Função do Microsoft 365|Grupo de função EOP|
|---|---|
|Administrador do Exchange|OrganizationManagement|
|Administrador global|OrganizationManagement <p> **Observação**: a função de administrador global e o grupo de função OrganizationManagement são vinculados usando um grupo de função especial administrador da empresa. O grupo de função Administrador da Empresa é gerenciado internamente e não pode ser modificado diretamente.|
|Administrador de senha|HelpDesk|
|Leitor global|ViewOnlyOrganizationManagement|
|Administrador de segurança|SecurityAdministrator|
|Leitor de segurança|SecurityReader|
|

Outras funções do Microsoft 365 não têm um grupo de função EOP correspondente e não concedem permissões administrativas no EOP. Para obter mais informações sobre como atribuir uma função do Microsoft 365 a um usuário, consulte [Atribuir funções de administrador](../../admin/add-users/assign-admin-roles.md).

Os usuários podem ter direitos administrativos no EOP sem adi adiá-los às funções do Microsoft 365. Você faz isso adicionando o usuário como membro de um grupo de função EOP. O usuário receberá permissões no EOP, mas não receberá permissões em outras cargas de trabalho do Microsoft 365.

### <a name="how-do-you-know-this-worked"></a>Como saber se funcionou?

Para verificar se você copiou com êxito um grupo de funções, faça uma das seguintes etapas:

- No EAC, vá para **Permissões** Funções de Administrador e verifique se o grupo de funções \> está listado (ou não listado). Selecione o grupo de funções e verifique as configurações no painel Detalhes ou clique em **Editar** Ícone editar ![ para verificar as ](../../media/ITPro-EAC-EditIcon.png) configurações.

- No PowerShell do Exchange Online, substitua pelo nome do grupo de funções e execute o seguinte comando para verificar se o grupo de funções existe (ou não existe) e verificar as \<Role Group Name\> configurações:

  ```PowerShell
  Get-RoleGroup -Identity "<Role Group Name>" | Format-List
  ```