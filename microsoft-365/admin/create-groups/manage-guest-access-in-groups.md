---
title: Gerenciar o acesso de convidados Microsoft 365 grupos
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
description: Saiba como adicionar convidados a um grupo Microsoft 365, exibir usuários convidados e usar o PowerShell para controlar o acesso de convidados.
ms.openlocfilehash: 00a6353f02ae7f3675961c3ee2ee31e3715652f2
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635757"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gerenciar o acesso de convidados Microsoft 365 grupos

Por padrão, o acesso de convidados Microsoft 365 grupos está ligado para sua organização. Os administradores podem controlar se é possível permitir o acesso de convidados a grupos para toda a organização ou para grupos individuais.

Quando ele está ligado, os membros do grupo podem convidar usuários convidados para um grupo Microsoft 365 por meio Outlook na Web. Os convites são enviados ao proprietário do grupo para aprovação.

Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.

> [!Note]
> Yammer Enterprise redes que estão no Modo Nativo ou na [UE Geo](/yammer/manage-security-and-compliance/manage-data-compliance) não suportam convidados de rede.
> Microsoft 365 Os grupos Yammer conectados atualmente não suportam o acesso de convidados, mas você pode criar grupos externos não conectados em sua Yammer rede. Consulte [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) para obter instruções.

O acesso de convidados em grupos geralmente é usado como parte de um cenário mais amplo que inclui SharePoint ou Teams. Esses serviços têm suas próprias configurações de compartilhamento de convidados. Para obter instruções completas sobre como configurar o compartilhamento de convidados entre grupos, SharePoint e Teams, consulte:

- [Colaborar com convidados em um site](../../solutions/collaborate-in-site.md)
- [Colaborar com convidados em uma equipe](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gerenciar o acesso de convidados de grupos

Se você quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazer isso no centro de administração Microsoft 365 local.

1. No centro de administração, vá para **Mostrar todas** as configurações Configurações Org e, na guia \>  \>  **Serviços,** selecione **Microsoft 365 grupos**.
  
2. Na página **Microsoft 365 Grupos,** escolha se deseja permitir que pessoas de fora da sua organização acessem recursos de grupo ou permitir que os proprietários do grupo adicionem pessoas de fora da sua organização a grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Adicionar convidados a um grupo Microsoft 365 do centro de administração

Se o convidado já existir em seu diretório, você poderá adicioná-los aos seus grupos Microsoft 365 centro de administração. (Grupos com associação dinâmica devem ser [gerenciados Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. No centro de administração, vá para a página **Grupos**  >  **grupos.**
  
2. Clique no grupo ao que deseja adicionar o convidado e selecione **Exibir todos** e gerenciar membros na **guia** Membros. 
  
4. Selecione **Adicionar membros** e escolha o nome do convidado que você deseja adicionar.
    
5. Selecione **Salvar**.

Se você quiser adicionar um convidado ao diretório diretamente, você pode adicionar Azure Active Directory usuários de colaboração [B2B no portal do Azure](/azure/active-directory/b2b/add-users-administrator).

Se você quiser editar qualquer uma das informações de um convidado, poderá [adicionar](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)ou atualizar as informações de perfil de um usuário usando Azure Active Directory .

## <a name="related-content"></a>Conteúdo relacionado

[Bloquear usuários convidados de um grupo específico](../../solutions/per-group-guest-access.md) (artigo)\
[Gerenciar associação de grupo no Microsoft 365 de administração](add-or-remove-members-from-groups.md) (artigo)\
[Azure Active Directory de acesso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artigo)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artigo)