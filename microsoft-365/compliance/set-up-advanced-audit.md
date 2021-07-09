---
title: Configurar Auditoria Avançada no Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-audit
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: Este artigo descreve como configurar a Auditoria Avançada para que você possa realizar investigações forenses quando contas de usuário são comprometidas ou para investigar outros incidentes relacionados à segurança.
ms.openlocfilehash: 825dadee5260a263d005eb3a37f280381f9425a2
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339221"
---
# <a name="set-up-advanced-audit-in-microsoft-365"></a>Configurar Auditoria Avançada no Microsoft 365

Se sua organização tiver uma assinatura e um licenciamento de usuário final compatível com Auditoria Avançada, execute as etapas a seguir para configurar e usar os recursos adicionais na Auditoria Avançada.

![Fluxo de trabalho para configurar a Auditoria Avançada](../media/AdvancedAuditWorkflow.png)

## <a name="step-1-set-up-advanced-audit-for-users"></a>Etapa 1: Configurar a Auditoria Avançada para usuários

Recursos de Auditoria Avançada, como a capacidade de registrar eventos cruciais, como MailItemsAccessed e Send, exigem uma licença E5 apropriada atribuída aos usuários. Além disso, o aplicativo/plano de serviço de Auditoria Avançada deve ser habilitado para esses usuários. Para verificar se o aplicativo Auditoria Avançada está atribuído aos usuários, execute as seguintes etapas para cada usuário:

1. No [Centro de administração do Microsoft 365](https://admin.microsoft.com/Adminportal), acesse **Usuários** > **Ativar usuários** e selecione um usuário.

2. Na página flyout de propriedades do usuário, clique em **Licenças e aplicativos**.

3. Na seção **Licenças,** verifique se o usuário recebe uma licença E5 ou recebe uma licença de complemento apropriada. Para ver uma lista de licenças que suportam Auditoria Avançada, consulte [Requisitos avançados de licenciamento de auditoria.](auditing-solutions-overview.md#advanced-audit-1)

4. Expanda a seção **Aplicativos** e verifique se a caixa de seleção **Auditoria Avançada do Microsoft 365** está marcada.

5. Se a caixa de seleção não estiver selecionada, selecione-a e clique em **Salvar alterações.**

   O registro em log de registros de auditoria para MailItemsAccessed e Send começará dentro de 24 horas. Você precisa executar a Etapa 3 para iniciar o log de dois outros eventos cruciais de Auditoria Avançada: SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint.

Para organizações que atribuem licenças a grupos de usuários usando o licenciamento baseado em grupo, é necessário desativar a atribuição de licenciamento da Auditoria avançada do Microsoft 365 do grupo. Depois de salvar as alterações, verifique se a Auditoria Avançada do Microsoft 365 está desativada para o grupo. Em seguida, ative novamente a atribuição de licenciamento do grupo. Para obter mais instruções do licenciamento baseado em grupo, consulte [Atribuir licenças a usuários por membro de grupo no Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).

Além disso, se você tiver personalizado as ações de caixa de correio que estão registradas em caixas de correio de usuário ou caixas de correio compartilhadas, quaisquer novos eventos cruciais lançados pela Microsoft não serão auditados automaticamente nessas caixas de correio. Para obter informações sobre como alterar as ações da caixa de correio que são auditadas para cada tipo de logon, confira a seção "Alterar ou restaurar ações da caixa de correio registradas por padrão" em [Gerenciar auditoria de caixa de correio](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default).

## <a name="step-2-enable-crucial-events"></a>Etapa 2: Habilitar eventos cruciais

Você precisa habilitar dois eventos cruciais (SearchQueryInitiatedExchange e SearchQueryInitiatedSharePoint) a serem registrados quando os usuários realizam pesquisas no Exchange Online e SharePoint Online. Para permitir que esses dois eventos sejam auditados para usuários, execute o seguinte comando (para cada usuário) no [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <user> -AuditOwner @{Add="SearchQueryInitiated"}
```

Em um ambiente multi-geo, você deve executar o comando **Set-Mailbox** anterior na floresta onde a caixa de correio do usuário está localizada. Para identificar o local da caixa de correio do usuário, execute o seguinte comando: 

```powershell
Get-Mailbox <user identity> | FL MailboxLocations
```

Se o comando para habilitar a auditoria de consultas de pesquisa foi executado anteriormente em uma floresta diferente da que a caixa de correio do usuário está localizada, você deve remover o valor SearchQueryInitiated da caixa de correio do usuário executando e, em seguida, adicioná-lo à caixa de correio do usuário na floresta onde a caixa de correio do usuário está `Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` localizada.

## <a name="step-3-set-up-audit-retention-policies"></a>Etapa 3: Configurar políticas de retenção de auditoria

Além da política padrão que retém os registros de auditoria do Exchange, SharePoint e Azure AD por um ano, você pode criar políticas adicionais de retenção do log de auditoria para atender aos requisitos das operações de segurança, TI e das equipes de conformidade de sua organização. Para saber mais, confira [Gerenciar políticas de retenção de log de auditoria](audit-log-retention-policies.md).

## <a name="step-4-search-for-crucial-events"></a>Etapa 4: Pesquisar eventos cruciais

Agora que você tem a Auditoria Avançada configurada para sua organização, você pode pesquisar eventos cruciais e outras atividades ao conduzir investigações forenses. Após concluir a Etapa 1 e a Etapa 2, você pode pesquisar no log de auditoria eventos cruciais e outras atividades durante investigações forenses de contas comprometidas e outros tipos de investigações de segurança ou conformidade. Para obter mais informações sobre como conduzir uma investigação forense de contas de usuário comprometidas usando o evento crucial MailItemsAccessed, consulte [Use Advanced Audit to investigate compromised accounts](mailitemsaccessed-forensics-investigations.md).
