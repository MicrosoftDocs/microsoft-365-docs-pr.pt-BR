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
ms.openlocfilehash: 3fba6b4498f275b07148c2d879d141474ddf4a13
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753272"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Gerenciar o acesso de convidados em grupos do Microsoft 365

Por padrão, o acesso de convidados para grupos do Microsoft 365 está ligado para sua organização. Os administradores podem controlar se permitem o acesso de convidados a grupos para toda a organização ou para grupos individuais.

Quando ele está ligado, os membros do grupo podem convidar usuários convidados para um grupo do Microsoft 365 por meio do Outlook na Web. Os convites são enviados ao proprietário do grupo para aprovação.

Depois de aprovado, o usuário convidado é adicionado ao diretório e ao grupo.

> [!Note]
> As redes do Yammer Enterprise que estão no Modo Nativo ou na área geográfica da [UE](https://go.microsoft.com/fwlink/?linkid=2107357) não suportam convidados de rede.
> No momento, os grupos do Yammer conectados ao Microsoft 365 não suportam o acesso de convidados, mas você pode criar grupos externos não conectados em sua rede do Yammer. Confira [Criar e gerenciar grupos externos no Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) para obter instruções.

O acesso de convidados em grupos geralmente é usado como parte de um cenário mais amplo que inclui o SharePoint ou o Teams. Esses serviços têm suas próprias configurações de compartilhamento de convidados. Para obter instruções completas para configurar o compartilhamento de convidados entre grupos, SharePoint e Teams, confira:

- [Colaborar com convidados em um site](../../solutions/collaborate-in-site.md)
- [Colaborar com convidados em uma equipe](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Gerenciar o acesso de convidados de grupos

Se quiser habilitar ou desabilitar o acesso de convidados em grupos, você pode fazê-lo no centro de administração do Microsoft 365.

1. No centro de administração, vá para Mostrar todas **as** configurações da Organização de Configurações e, na guia Serviços, selecione grupos \>  \>  do **Microsoft 365.** 
  
2. Na página **Grupos do Microsoft 365,** escolha se deseja permitir que pessoas de fora da sua organização acessem recursos de grupo ou permitir que os proprietários de grupos adicionem aos grupos pessoas de fora da sua organização.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Adicionar convidados a um grupo do Microsoft 365 no centro de administração

Se o convidado já existir em seu diretório, você poderá adicioná-lo aos seus grupos no centro de administração do Microsoft 365.
  
1. No centro de administração, vá para a página **Grupos**  >  **de** Grupos.
  
2. Clique no grupo ao que você deseja adicionar o convidado e selecione **Exibir todos e gerenciar** membros na **guia** Membros. 
  
4. Selecione **Adicionar membros** e escolha o nome do convidado que você deseja adicionar.
    
5. Selecione **Salvar**.

Se quiser adicionar um convidado diretamente ao diretório, você pode adicionar usuários de colaboração [B2B do Azure Active Directory no portal do Azure.](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)

Se quiser editar qualquer uma das informações de um convidado, você pode adicionar ou atualizar as informações de perfil de um usuário usando o [Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

## <a name="see-also"></a>Confira também

[Bloquear usuários convidados de um grupo específico](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[Gerenciar a associação de grupo no centro de administração do Microsoft 365](add-or-remove-members-from-groups.md)
  
[Revisões de acesso do Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
