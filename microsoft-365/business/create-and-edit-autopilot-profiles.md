---
title: Criar e editar os perfis do AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
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
description: 'Saiba como criar, editar, excluir ou remover perfis de piloto automático. '
ms.openlocfilehash: 4658a27e5f2c64a52f8a7d08b3fc13df5e239dc3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26864983"
---
# <a name="create-and-edit-autopilot-profiles"></a>Criar e editar os perfis do AutoPilot

## <a name="create-a-profile"></a>Criar um perfil

Um perfil aplica-se a um dispositivo ou a um grupo de dispositivos,
  
1. No Centro de administração do Microsoft 365 Business, escolha **Implantar o Windows com o AutoPilot** no cartão **Ações do dispositivo**. 
    
    ![On the Device actions card, choose Deploy Windows with Autopilot.](media/160d5c2a-11a8-48f9-a8aa-70f084b85448.png)
  
2. Na página **Preparar o Windows**, escolha a guia **Perfis** \> **Criar perfil**.
    
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
    
