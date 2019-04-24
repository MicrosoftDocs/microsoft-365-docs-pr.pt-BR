---
title: Criar e editar os perfis do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5cf7139e-cfa1-4765-8aad-001af1c74faa
description: 'Saiba como criar, editar, excluir ou remover perfis do autoPilot. '
ms.openlocfilehash: 85fc897b2f428afae8d55feeb577021adaa30f72
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277049"
---
# <a name="create-and-edit-autopilot-profiles"></a>Criar e editar os perfis do AutoPilot

## <a name="create-a-profile"></a>Criar um perfil

Um perfil aplica-se a um dispositivo ou a um grupo de dispositivos,
  
1. no centro de administração do Microsoft 365 Business, escolha **dispositivos** \> **autopilot**.
  
2. Na página **piloto automático** , escolha a guia **perfis** para \> **Criar perfil**.
    
3. Na página **Criar perfil**, insira um nome para o perfil que o ajude a identificá-lo, por exemplo, Marketing, ative a configuração desejada (confira [Sobre as configurações de perfil de AutoPilot](autopilot-profile-settings.md) para saber mais), e escolha **Salvar**.
    
    ![Enter name and turn on settings in the Create profile panel.](media/63b5a00d-6a5d-48d0-9557-e7531e80702a.png)
  
### <a name="apply-profile-to-a-device"></a>Aplicar perfil a um dispositivo

Depois de criar um perfil, pode aplicá-lo a um dispositivo ou a um grupo de dispositivos. Você pode escolher um perfil existente no [guia passo a passo](add-autopilot-devices-and-profile.md), aplicá-lo a outros dispositivos ou substituir um perfil existente para um dispositivo ou grupo de dispositivos. 
  
1. Na página **Preparar o Windows**, escolha a guia **Dispositivos**. 
    
2. Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Dispositivo**, escolha um perfil no menu suspenso **Perfil atribuído** \> **Salvar**.
    
    ![In the Device panel, select an Assigned profile to apply it.](media/ed0ce33f-9241-4403-a5de-2dddffdc6fb9.png)
  
## <a name="edit-delete-or-remove-a-profile"></a>Editar, excluir ou remover um perfil

Após atribuir um perfil a um dispositivo, você poderá atualizá-lo, mesmo que já tenha atribuído o dispositivo a um usuário. Quando o dispositivo se conecta à Internet, ele baixa a versão mais recente do seu perfil durante o processo de configuração. Se o usuário restaurar o dispositivo para as configurações padrão de fábrica, o dispositivo baixará novamente as atualizações mais recentes para seu perfil. 
  
### <a name="edit-a-profile"></a>Editar um perfil

1. Na página **Preparar o Windows**, escolha a guia **Perfis**. 
    
2. Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Perfil**, atualize qualquer uma das configurações disponíveis \> **Salvar**.
    
    Se você fizer isso antes de um usuário conectar o dispositivo à internet, o perfil será aplicado ao processo de configuração.
    
### <a name="delete-a-profile"></a>Excluir um perfil

1. Na página **Preparar o Windows**, escolha a guia **Perfis**. 
    
2. Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Perfil**, clique em **Excluir perfil** \> **Salvar**.
    
    Quando você exclui um perfil, ele é removido de um dispositivo ou grupo de dispositivos ao qual foi atribuído.
    
### <a name="remove-a-profile"></a>Remover um perfil

1. Na página **Preparar o Windows**, escolha a guia **Dispositivos**. 
    
2. Clique na caixa de seleção ao lado de um nome de dispositivo e, no painel **Dispositivo**, escolha **Nenhum** no menu suspenso **Perfil atribuído** \> **Salvar**.
    
