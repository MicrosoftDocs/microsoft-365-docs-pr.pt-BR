---
title: Gerenciar o acesso de hóspedes em grupos Microsoft 365
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
description: Aprenda a adicionar hóspedes a um grupo de Microsoft 365, visualize os usuários convidados e use o PowerShell para controlar o acesso dos hóspedes.
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571932"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gerenciar o acesso de hóspedes em grupos Microsoft 365

Por padrão, o acesso de hóspedes para grupos Microsoft 365 é ligado para sua organização. Os administradores podem controlar se permitem o acesso dos hóspedes a grupos para toda a sua organização ou para grupos individuais.

Quando ele está ligado, os membros do grupo podem convidar os usuários convidados para um grupo Microsoft 365 através de Outlook na Web. Os convites são enviados ao dono do grupo para aprovação.

Uma vez aprovado, o usuário convidado é adicionado ao diretório e ao grupo.

> [!Note]
> Yammer Enterprise redes que estão no Modo Nativo ou no [Geo da UE](/yammer/manage-security-and-compliance/manage-data-compliance) não suportam hóspedes da rede.
> Microsoft 365 Os grupos de Yammer conectados não suportam atualmente o acesso aos hóspedes, mas você pode criar grupos externos não conectados em sua rede Yammer. Consulte [Criar e gerenciar grupos externos em Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) para obter instruções.

O acesso de hóspedes em grupos é frequentemente usado como parte de um cenário mais amplo que inclui SharePoint ou Teams. Esses serviços têm suas próprias configurações de compartilhamento de hóspedes. Para obter instruções completas para configurar o compartilhamento de hóspedes entre grupos, SharePoint e Teams, consulte:

- [Colaborar com convidados em um site](../../solutions/collaborate-in-site.md)
- [Colaborar com convidados em uma equipe](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gerenciar grupos de acesso a hóspedes

Se você quiser ativar ou desativar o acesso de hóspedes em grupos, você pode fazê-lo no centro administrativo Microsoft 365.

1. No centro administrativo, vá para **Mostrar todas as** \> configurações **Configurações** Org e na guia \> **Serviços,** selecione **Microsoft 365 grupos**. 
  
2. Na página **Microsoft 365 Grupos,** escolha se você quer deixar as pessoas fora da sua organização acessar os recursos do grupo ou permitir que os proprietários de grupos adicionem pessoas fora de sua organização a grupos.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Adicione os hóspedes a um grupo de Microsoft 365 do centro administrativo

Se o convidado já existir em seu diretório, você pode adicioná-los aos seus grupos do centro administrativo Microsoft 365. (Grupos com membros dinâmicos devem ser [gerenciados em Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)
  
1. No centro administrativo, acesse a página **Grupos**  >  **grupos.**
  
2. Clique no grupo ao que deseja adicionar o convidado e selecione **Exibir todos e gerenciar membros** na guia **Membros.** 
  
4. Selecione **Adicionar membros** e escolha o nome do convidado que deseja adicionar.
    
5. Selecione **Salvar**.

Se você quiser adicionar um convidado ao diretório diretamente, você pode [adicionar Azure Active Directory usuários de colaboração B2B no portal Azure](/azure/active-directory/b2b/add-users-administrator).

Se você quiser editar qualquer uma das informações de um convidado, você pode [adicionar ou atualizar as informações do perfil de um usuário usando Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>Conteúdo relacionado

[Bloqueie os usuários convidados de um grupo específico](../../solutions/per-group-guest-access.md) (artigo)

[Gerenciar a adesão do grupo no centro administrativo Microsoft 365](add-or-remove-members-from-groups.md) (artigo)
  
[Azure Active Directory comentários de acesso](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (artigo)

[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (artigo)