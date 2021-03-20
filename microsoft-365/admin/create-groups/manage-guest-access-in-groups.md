---
title: Gerenciar o acesso de convidados em grupos do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Saiba como adicionar convidados a um grupo do Microsoft 365, exibir usuários convidados e usar o PowerShell para controlar o acesso de convidados.
ms.openlocfilehash: 114fc1b5262f1632c7e7a8d1aa339c2470223288
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908601"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gerenciar o acesso de convidados em grupos do Microsoft 365

Por padrão, o acesso de convidados para grupos do Microsoft 365 está ligado para sua organização. Os administradores podem controlar se é possível permitir o acesso de convidados a grupos para toda a organização ou para grupos individuais.

Quando ele está ligado, os membros do grupo podem convidar usuários convidados para um grupo do Microsoft 365 por meio do Outlook na Web. Os convites são enviados ao proprietário do grupo para aprovação.

Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.

> [!Note]
> As redes do Yammer Enterprise que estão no Modo Nativo ou na [UE Geo](/yammer/manage-security-and-compliance/manage-data-compliance) não suportam convidados de rede.
> Os grupos do Microsoft 365 Connected Yammer atualmente não suportam o acesso de convidados, mas você pode criar grupos externos não conectados em sua rede do Yammer. Consulte [Criar e gerenciar grupos externos no Yammer para](/yammer/work-with-external-users/create-and-manage-external-groups) obter instruções.

O acesso de convidados em grupos geralmente é usado como parte de um cenário mais amplo que inclui o SharePoint ou o Teams. Esses serviços têm suas próprias configurações de compartilhamento de convidados. Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e Teams, consulte:

- [Colaborar com convidados em um site](../../solutions/collaborate-in-site.md)
- [Colaborar com convidados em uma equipe](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gerenciar o acesso de convidados de grupos

Se quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no Centro de administração do Microsoft 365.

1. No centro de administração, vá para **Mostrar todas as** configurações da Organização de Configurações e, na guia Serviços, selecione Grupos do Microsoft \>  \>  **365**. 
  
2. Na página Grupos do **Microsoft 365,** escolha se deseja permitir que pessoas de fora da sua organização acessem recursos de grupo ou permitir que os proprietários do grupo adicionem pessoas de fora da sua organização a grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Adicionar convidados a um grupo do Microsoft 365 do centro de administração

Se o convidado já existir em seu diretório, você poderá adicioná-los aos seus grupos do Centro de administração do Microsoft 365. (Grupos com associação dinâmica devem ser [gerenciados no Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. No centro de administração, vá para a página **Grupos**  >  **grupos.**
  
2. Clique no grupo ao que deseja adicionar o convidado e selecione **Exibir todos** e gerenciar membros na **guia** Membros. 
  
4. Selecione **Adicionar membros** e escolha o nome do convidado que você deseja adicionar.
    
5. Selecione **Salvar**.

Se quiser adicionar um convidado ao diretório diretamente, você pode adicionar usuários de colaboração [B2B do Azure Active Directory no portal do Azure.](/azure/active-directory/b2b/add-users-administrator)

Se você quiser editar qualquer uma das informações de um convidado, poderá adicionar ou atualizar as informações de perfil de um usuário usando o [Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="see-also"></a>Confira também

[Bloquear usuários convidados de um grupo específico](../../solutions/per-group-guest-access.md)

[Gerenciar associação de grupo no centro de administração do Microsoft 365](add-or-remove-members-from-groups.md)
  
[Avaliações de acesso do Azure Active Directory](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser)