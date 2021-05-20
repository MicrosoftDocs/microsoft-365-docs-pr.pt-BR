---
title: Criar, editar ou excluir um grupo de segurança no Microsoft 365 de administração
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Aprenda a criar, editar ou excluir um grupo de segurança.
ms.openlocfilehash: 8f76b5fa803ea43e53e89cf6479eb7572a2857c2
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537590"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Criar, editar ou excluir um grupo de segurança no Microsoft 365 de administração

Na página Microsoft 365 **Grupos,** você pode criar grupos de contas de usuário que você pode usar para atribuir as mesmas permissões ao SharePoint Online e CRM Online. Por exemplo, um administrador pode criar um grupo de segurança para conceder a um determinado grupo de pessoas acesso a um site do SharePoint. Somente os administradores globais e de gerenciamento de usuários têm permissões para criar, editar ou excluir grupos de segurança; para obter mais informações sobre funções de administrador, consulte [Atribuir funções de administrador](../add-users/assign-admin-roles.md). 
  
Você também pode usar [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para enviar email ou atribuir permissões a um grupo de usuários e [Grupos do Exchange Online e do SharePoint Online](#groups-in-exchange-online-and-sharepoint-online) para conceder aos usuários direitos e acesso a sites e conjuntos de sites. 
  
> [!IMPORTANT]
>  Planejando usar caixas de correio de sites? Todos os usuários adicionados a um site do SharePoint por meio de um grupo de segurança, em vez de individualmente, podem usar a caixa de correio do site no SharePoint. Esses usuários não poderão acessar a caixa de correio do site no Outlook. Para obter mais informações, [consulte Use Microsoft 365 Grupos em vez de Caixas de Correio de Site](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b). 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Gerenciar grupos de segurança no centro de administração

### <a name="add-a-security-group"></a>Adicionar um grupo de segurança

1. No centro Microsoft 365 de administração, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a>
  
2. Na página **Grupos,** selecione **Adicionar um grupo**.
    
3. Na página **Escolher um tipo de** grupo, escolha **Segurança**. 
    
4. Siga as etapas para concluir a criação do grupo. 
 
### <a name="add-members-to-a-security-group"></a>Adicionar membros a um grupo de segurança
    
1. Selecione o nome do grupo de segurança na página **Grupos** e, na guia **Membros,** selecione **Exibir tudo e gerenciar membros**. 
    
2. No painel de grupo, selecione Adicionar membros e escolha a pessoa na lista ou  digite o nome da pessoa que você deseja adicionar na caixa Pesquisa e selecione **Salvar**. 
    
    Para remover membros, selecione o X ao lado de seu nome. 
  
### <a name="edit-a-security-group"></a>Editar um grupo de segurança

1. No centro de administração, vá para a página **Grupos** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a>
  
2. Na página **Grupos,** selecione o nome do grupo. 
    
3. No painel de configurações, selecione a guia **Geral** ou a guia **Membros** para editar os detalhes do grupo ou os membros.

### <a name="delete-a-security-group"></a>Excluir um grupo de segurança

1. No centro de administração, vá para a página **Grupos**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">grupos.</a>
    
2. Na página **Grupos,** selecione o nome do grupo. 
    
3. Selecione **Excluir grupo** (ícone de wasetbin) e confirme selecionando **Excluir**.
    
    Selecione **Fechar** quando o grupo for excluído. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Grupos do Exchange Online e do SharePoint Online

Se você quiser criar grupos de usuários para que possa enviar emails a todos eles ao mesmo tempo, faça isso no centro de administração do Exchange indo para **Admin** \> **Exchange** \> **Recipients** \> **Groups**. Em seguida, **selecione Novo** ![ Adicionar e selecione o tipo de grupo que você ](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) deseja criar: 
  
- **Grupo de distribuição**: usado para distribuir mensagens para um grupo de usuários. Também é chamado de grupo de distribuição habilitado para *email* ou uma lista *de distribuição.* Para obter mais informações, consulte [Gerenciar grupos de distribuição](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).
    
- **Grupo de segurança**: pode ser usado para distribuir mensagens para um grupo de usuários ou conceder permissões de acesso a recursos. Esse grupo também é chamado de grupo de segurança habilitado *para email.* Para mais informações, consulte [Gerenciar grupos de segurança habilitados para email](/Exchange/recipients/mail-enabled-security-groups).
    
- **Grupo dinâmico de distribuição**: um tipo de grupo de distribuição cuja lista de destinatários é recalculada toda vez que você envia uma mensagem com base nos filtros e nas condições definidos. Para obter mais informações, consulte [Gerenciar grupos dinâmicos de distribuição](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).
    
Depois de criar grupos de distribuição e grupos de segurança habilitados para email no centro de administração Exchange, seus nomes e listas de usuários aparecem na página **Grupos de** segurança. Você poderá excluir esses grupos em ambos os locais, mas só poderá editá-los no centro de administração do Exchange. Grupos dinâmicos de distribuição não aparecem na página **Grupos de** segurança. 
  
 Quando você cria um conjunto de sites, grupos do SharePoint são criados automaticamente. Os grupos padrão usam os níveis de permissão padrão do SharePoint  algumas vezes chamados de funções do SharePoint  para conceder direitos e acesso aos usuários. Para obter mais informações, consulte [Default SharePoint groups in SharePoint Online](/sharepoint/default-sharepoint-groups).
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>Como um grupo de segurança é diferente dos grupos de segurança que eu SharePoint?

Os grupos de segurança podem ser usados com SharePoint, Exchange, MDM, Windows e muito mais. Um grupo de segurança criado em SharePoint é reconhecido apenas por esse conjunto SharePoint site.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>Preciso usar grupos de segurança para minha organização ser segura?

Não. Essa é apenas mais uma maneira de gerenciar a segurança da sua organização. Você sempre pode conceder permissões de usuário e acesso a sites individualmente. Mas com grupos de segurança, você pode gerenciar facilmente grupos maiores de usuários.
  
## <a name="can-i-send-email-to-a-security-group"></a>Posso enviar emails para um grupo de segurança?

Sim. Mas se você quiser usar grupos para email e colaboração, recomendamos que você crie um Microsoft 365 [grupo.](../create-groups/create-groups.md) 
