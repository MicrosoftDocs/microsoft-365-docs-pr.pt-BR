---
title: Gerenciar o acesso de convidados nos grupos do Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326514"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gerenciar o acesso de convidados nos grupos do Microsoft 365

Por padrão, o acesso de convidados para os grupos do Microsoft 365 está ativado para sua organização. Os administradores podem controlar a possibilidade de permitir o acesso de convidados a grupos para toda a sua organização ou para grupos individuais.

Quando ele está ativado, os membros do grupo podem convidar usuários convidados para um grupo do Microsoft 365 por meio do Outlook na Web. Os convites são enviados ao proprietário do grupo para aprovação.

Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.

> [!Note]
> As redes corporativas do Yammer que estão no modo nativo ou na [Geografia da UE](https://go.microsoft.com/fwlink/?linkid=2107357) não dão suporte a convidados de rede.
> Os grupos do Yammer conectados ao Microsoft 365 atualmente não dão suporte ao acesso de convidados, mas você pode criar grupos externos não conectados na sua rede do Yammer. Veja [criar e gerenciar grupos externos no Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) para obter instruções.

O acesso de convidados em grupos é geralmente usado como parte de um cenário mais amplo que inclui o SharePoint ou o Teams. Esses serviços têm suas próprias configurações de compartilhamento de convidados. Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e equipes, consulte:

- [Colaborar com convidados em um site](../../solutions/collaborate-in-site.md)
- [Colaborar com convidados em uma equipe](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gerenciar o acesso de convidados a grupos

Se quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no centro de administração do Microsoft 365.

1. No centro de administração, vá para **Mostrar todas** as \> **Settings** \> **configurações da organização** configurações e, na guia **Serviços** , selecione **Microsoft 365 grupos**.
  
2. Na página de **grupos do Microsoft 365** , escolha se você deseja permitir que as pessoas de fora de sua organização acessem os recursos do grupo ou permitir que os proprietários de grupos adicionem pessoas de fora da sua organização a grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Adicionar convidados a um grupo do Microsoft 365 a partir do centro de administração

Se o convidado já existir no seu diretório, você poderá adicioná-lo aos seus grupos no centro de administração do Microsoft 365.
  
1. No centro de administração, vá para a página grupos de **grupos**  >  **Groups** .
  
2. Clique no grupo ao qual você deseja adicionar o convidado e selecione **Exibir todos e gerenciar Membros** na guia **Membros** . 
  
4. Selecione **adicionar membros**e escolha o nome do convidado que você deseja adicionar.
    
5. Selecione **Salvar**.

Se quiser adicionar um convidado ao diretório diretamente, você poderá [Adicionar usuários de colaboração B2B do Azure Active Directory no portal do Azure](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).

Se quiser editar as informações de um convidado, você poderá [Adicionar ou atualizar as informações de perfil de um usuário usando o Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="see-also"></a>Confira também

[Bloquear usuários convidados de um grupo específico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Gerenciar a associação de grupo no centro de administração do Microsoft 365](add-or-remove-members-from-groups.md)
  
[Revisões do acesso ao Active Directory do Azure](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
